<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shafin Al Shadab - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #00D9FF;
            --secondary: #6B5FFF;
            --accent: #FF006E;
            --dark: #0a0e27;
            --light: #f8f9ff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--dark) 0%, #1a1a3e 100%);
            color: var(--light);
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(ellipse at 20% 50%, rgba(107, 95, 255, 0.15) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 80%, rgba(0, 217, 255, 0.1) 0%, transparent 50%);
            z-index: 0;
            animation: gradientShift 8s ease infinite;
        }

        @keyframes gradientShift {
            0%, 100% {
                background: 
                    radial-gradient(ellipse at 20% 50%, rgba(107, 95, 255, 0.15) 0%, transparent 50%),
                    radial-gradient(ellipse at 80% 80%, rgba(0, 217, 255, 0.1) 0%, transparent 50%);
            }
            50% {
                background: 
                    radial-gradient(ellipse at 80% 30%, rgba(107, 95, 255, 0.15) 0%, transparent 50%),
                    radial-gradient(ellipse at 20% 70%, rgba(0, 217, 255, 0.1) 0%, transparent 50%);
            }
        }

        /* Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: var(--primary);
            border-radius: 50%;
            opacity: 0.5;
            animation: float linear infinite;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 0.5;
            }
            90% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(-10vh) translateX(100px);
                opacity: 0;
            }
        }

        /* Main Content */
        .container {
            position: relative;
            z-index: 2;
            max-width: 900px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            margin-bottom: 80px;
            animation: slideInDown 0.8s ease-out;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientText 3s ease infinite;
        }

        @keyframes gradientText {
            0%, 100% {
                background: linear-gradient(135deg, var(--primary), var(--secondary));
                -webkit-background-clip: text;
            }
            50% {
                background: linear-gradient(135deg, var(--secondary), var(--accent));
                -webkit-background-clip: text;
            }
        }

        .hero .tagline {
            font-size: 1.3rem;
            color: var(--primary);
            margin-bottom: 20px;
            animation: slideInUp 1s ease-out 0.3s both;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero .subtitle {
            font-size: 1.1rem;
            color: #aaa;
            max-width: 600px;
            margin: 0 auto 40px;
            line-height: 1.6;
            animation: slideInUp 1s ease-out 0.5s both;
        }

        /* CTA Button */
        .cta-button {
            display: inline-block;
            padding: 12px 40px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--dark);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            animation: slideInUp 1s ease-out 0.7s both;
            border: 2px solid transparent;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.3);
            background: linear-gradient(135deg, var(--secondary), var(--primary));
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin: 60px 0;
            animation: slideInUp 1s ease-out 0.9s both;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 217, 255, 0.2);
            padding: 30px 20px;
            border-radius: 15px;
            text-align: center;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: var(--primary);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.2);
        }

        .stat-card .number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .stat-card .label {
            font-size: 0.9rem;
            color: #aaa;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Tech Stack */
        .tech-section {
            margin: 60px 0;
            animation: slideInUp 1s ease-out 1.1s both;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 30px;
            color: var(--primary);
            text-align: center;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 15px;
        }

        .tech-badge {
            background: rgba(107, 95, 255, 0.15);
            border: 1px solid rgba(107, 95, 255, 0.3);
            padding: 15px 10px;
            border-radius: 10px;
            text-align: center;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-badge:hover {
            background: rgba(0, 217, 255, 0.2);
            border-color: var(--primary);
            transform: translateY(-3px);
        }

        /* Divider */
        .divider {
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
            margin: 40px auto;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: #666;
            animation: slideInUp 1s ease-out 1.3s both;
        }

        .social-links {
            margin: 20px 0;
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .social-links a {
            color: var(--primary);
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .social-links a:hover {
            color: var(--secondary);
            transform: scale(1.1);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .tagline {
                font-size: 1.1rem;
            }

            .stats {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Loading Animation */
        .loading-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent));
            animation: loading 2s ease-out;
            z-index: 1000;
        }

        @keyframes loading {
            0% {
                width: 0;
            }
            80% {
                width: 100%;
            }
            100% {
                width: 100%;
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="loading-bar"></div>
    <div class="animated-bg"></div>
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero">
            <h1>Shafin Al Shadab</h1>
            <p class="tagline">⚡ Vibe Coder • Builder • Entrepreneur</p>
            <p class="subtitle">Turning ideas into digital products, businesses & experiences. From SaaS to AI tools, I build things that matter.</p>
            <a href="#connect" class="cta-button">Let's Build Together</a>
        </section>

        <div class="divider"></div>

        <!-- Stats Section -->
        <section class="stats">
            <div class="stat-card">
                <div class="number">20+</div>
                <div class="label">Projects Built</div>
            </div>
            <div class="stat-card">
                <div class="number">3+</div>
                <div class="label">Businesses</div>
            </div>
            <div class="stat-card">
                <div class="number">5+</div>
                <div class="label">Years Coding</div>
            </div>
            <div class="stat-card">
                <div class="number">∞</div>
                <div class="label">Coffee ☕</div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Tech Stack -->
        <section class="tech-section">
            <h2 class="section-title">Tech Stack</h2>
            <div class="tech-grid">
                <div class="tech-badge">HTML5</div>
                <div class="tech-badge">CSS3</div>
                <div class="tech-badge">JavaScript</div>
                <div class="tech-badge">React</div>
                <div class="tech-badge">Node.js</div>
                <div class="tech-badge">Python</div>
                <div class="tech-badge">PHP</div>
                <div class="tech-badge">Java</div>
                <div class="tech-badge">MongoDB</div>
                <div class="tech-badge">MySQL</div>
                <div class="tech-badge">Git</div>
                <div class="tech-badge">Docker</div>
            </div>
        </section>

        <div class="divider"></div>

        <!-- Footer -->
        <footer id="connect">
            <h2 class="section-title">Let's Connect</h2>
            <p>Have a project or idea? Let's build something amazing together!</p>
            <div class="social-links">
                <a href="https://linkedin.com/in/shafinalshadab" target="_blank">LinkedIn</a>
                <a href="https://facebook.com/shafin2506" target="_blank">Facebook</a>
                <a href="mailto:your-email@gmail.com">Email</a>
            </div>
            <p style="margin-top: 30px; font-size: 0.9rem;">Think it. Build it. Ship it. Scale it. 🚀</p>
        </footer>
    </div>

    <script>
        // Generate floating particles
        const particlesContainer = document.getElementById('particles');
        const particleCount = 50;

        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = (Math.random() * 15 + 10) + 's';
            particle.style.animationDelay = Math.random() * 5 + 's';
            particle.style.opacity = Math.random() * 0.5 + 0.2;
            particlesContainer.appendChild(particle);

            // Remove particle after animation
            setTimeout(() => particle.remove(), 20000);
        }

        // Create initial particles
        for (let i = 0; i < particleCount; i++) {
            setTimeout(createParticle, i * 100);
        }

        // Create new particles continuously
        setInterval(createParticle, 500);

        // Smooth scroll for links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
