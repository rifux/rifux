<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vladimir Blinkov - rifux</title>
    <style>
        /* General Styles & Resets */
        :root {
            --tw-gray-900: #111827;
            --tw-black: #000;
            --tw-gray-100: #f3f4f6;
            --tw-gray-300: #d1d5db;
            --tw-gray-400: #9ca3af;
            --tw-gray-500: #6b7280;
            --tw-gray-700: #374151;
            --tw-gray-800: #1f2937;
            --tw-blue-300: #93c5fd;
            --tw-blue-400: #60a5fa;
            --tw-blue-500: #3b82f6;
            --tw-purple-300: #d8b4fe;
            --tw-purple-400: #c084fc;
            --tw-purple-500: #a855f7;
            --tw-purple-600: #9333ea;
            --tw-pink-400: #f472b6;
            --tw-cyan-500: #06b6d4;
        }

        body {
            margin: 0;
            min-height: 100vh;
            background-image: linear-gradient(to bottom right, var(--tw-gray-900), var(--tw-black));
            color: var(--tw-gray-100);
            font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
            overflow-x: hidden;
            position: relative;
        }

        /* Keyframe Animations */
        @keyframes blob {
            0% { transform: translate(0px, 0px) scale(1); }
            33% { transform: translate(30px, -50px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
            100% { transform: translate(0px, 0px) scale(1); }
        }

        @keyframes fadeInAndUp {
            from {
                opacity: 0;
                transform: translateY(-2.5rem);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Background Animated Blobs */
        .background-blobs {
            position: fixed;
            top: 0; right: 0; bottom: 0; left: 0;
            z-index: 0;
            opacity: 0.2;
        }

        .blob {
            position: absolute;
            width: 16rem; /* 256px */
            height: 16rem; /* 256px */
            border-radius: 9999px;
            mix-blend-mode: multiply;
            filter: blur(72px);
            animation: blob 7s infinite;
        }

        .blob-1 { top: 0; left: 0; background-color: var(--tw-blue-500); }
        .blob-2 { top: 0; right: 0; background-color: var(--tw-purple-500); animation-delay: 2s; }
        .blob-3 { bottom: 0; left: 33.33%; background-color: var(--tw-pink-400); animation-delay: 4s; }
        
        /* Main Container & Layout */
        .container {
            max-width: 1280px;
            margin-left: auto;
            margin-right: auto;
            padding: 3rem 1rem;
            position: relative;
            z-index: 1;
            animation: fadeInAndUp 1s ease-out forwards;
        }

        /* Utility Classes from Tailwind */
        .text-center { text-align: center; }
        .mb-16 { margin-bottom: 4rem; }
        .mb-12 { margin-bottom: 3rem; }
        .mb-8 { margin-bottom: 2rem; }
        .mb-4 { margin-bottom: 1rem; }
        .mb-3 { margin-bottom: 0.75rem; }
        .mb-20 { margin-bottom: 5rem; }
        .mr-2 { margin-right: 0.5rem; }
        .mr-3 { margin-right: 0.75rem; }
        .mt-2 { margin-top: 0.5rem; }
        .font-bold { font-weight: 700; }
        .font-extrabold { font-weight: 800; }
        .font-medium { font-weight: 500; }
        .text-xl { font-size: 1.25rem; line-height: 1.75rem; }
        .text-2xl { font-size: 1.5rem; line-height: 2rem; }
        .text-3xl { font-size: 1.875rem; line-height: 2.25rem; }
        .text-4xl { font-size: 2.25rem; line-height: 2.5rem; }
        .text-sm { font-size: 0.875rem; line-height: 1.25rem; }
        .text-xs { font-size: 0.75rem; line-height: 1rem; }
        .capitalize { text-transform: capitalize; }
        .inline-block { display: inline-block; }
        .flex { display: flex; }
        .flex-col { flex-direction: column; }
        .items-center { align-items: center; }
        .justify-center { justify-content: center; }
        .gap-6 { gap: 1.5rem; }
        .grid { display: grid; }
        .grid-cols-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
        .rounded-xl { border-radius: 0.75rem; }
        .rounded-lg { border-radius: 0.5rem; }
        .rounded-full { border-radius: 9999px; }
        .shadow-lg { box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05); }
        .border { border-width: 1px; }
        .transition-all { transition-property: all; transition-duration: 300ms; }
        .hover-scale:hover { transform: scale(1.05); }
        .hover-translate:hover { transform: translateY(-0.25rem); }

        /* Text Gradient Effect */
        .bg-clip-text {
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .gradient-blue-purple { background-image: linear-gradient(to right, var(--tw-blue-300), var(--tw-purple-300)); }
        .gradient-blue-purple-pink { background-image: linear-gradient(to right, var(--tw-blue-400), var(--tw-purple-400), var(--tw-pink-400)); }
        .gradient-blue-to-purple-400 { background-image: linear-gradient(to right, var(--tw-blue-400), var(--tw-purple-400)); }

        /* Header Styles */
        header .name-badge {
            padding: 0.75rem 1.5rem;
            background-image: linear-gradient(to right, var(--tw-blue-500), var(--tw-purple-600));
            color: white;
            transform: rotate(1deg);
        }
        
        header h1 { color: var(--tw-gray-100); }
        
        header .title-tags span {
            padding: 0.25rem 0.75rem;
            backdrop-filter: blur(4px);
        }
        .tag-go { background-color: rgba(30, 64, 175, 0.3); } /* blue-900/30 */
        .tag-linux { background-color: rgba(88, 28, 135, 0.3); } /* purple-900/30 */

        /* Skills Section */
        .skills-grid {
            grid-template-columns: repeat(2, minmax(0, 1fr));
        }
        
        .skill-card {
            display: flex; /* FIX: Added display: flex */
            flex-direction: column;
            align-items: center;
            padding: 1rem;
            background-color: rgba(31, 41, 55, 0.5); /* gray-800/50 */
            backdrop-filter: blur(4px);
            transition: all 300ms;
        }
        .skill-card:hover {
            background-color: rgba(55, 65, 81, 0.5); /* gray-700/50 */
            transform: scale(1.05);
        }
        .skill-card img { width: 4rem; height: 4rem; margin-bottom: 0.75rem; }

        .secondary-skill-card {
            background-color: rgba(31, 41, 55, 0.3); /* gray-800/30 */
        }
        .secondary-skill-card:hover {
             background-color: rgba(55, 65, 81, 0.3); /* gray-700/30 */
        }
        .secondary-skill-card img { width: 3rem; height: 3rem; opacity: 0.8; }
        .secondary-skill-card span { color: var(--tw-gray-400); }

        /* Codewars Badge */
        .codewars-link {
            display: inline-block;
            transition: transform 300ms;
        }
        .codewars-link:hover {
            transform: scale(1.05);
        }
        .codewars-img {
            border-radius: 0.75rem;
            border: 1px solid var(--tw-gray-700);
            box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05);
            transition: all 300ms;
        }
        .codewars-img:hover {
            border-color: rgba(168, 85, 247, 0.5); /* purple-500/50 */
        }
        
        /* Contact Section */
        .contact-link {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            border: 1px solid;
            backdrop-filter: blur(4px);
            transition: all 300ms;
            color: var(--tw-gray-100); /* FIX: Added text color */
            text-decoration: none; /* FIX: Removed underline */
        }
        .contact-link:hover {
            transform: translateY(-0.25rem);
        }

        .contact-email {
            background-image: linear-gradient(to right, rgba(59, 130, 246, 0.2), rgba(6, 182, 212, 0.2));
            border-color: rgba(59, 130, 246, 0.3);
        }
        .contact-email:hover {
            background-image: linear-gradient(to right, rgba(59, 130, 246, 0.3), rgba(6, 182, 212, 0.3));
            border-color: rgba(96, 165, 250, 0.6);
        }
        .contact-email svg { color: var(--tw-blue-400); }
        .contact-email:hover svg { color: var(--tw-blue-300); }
        
        .contact-telegram {
            background-image: linear-gradient(to right, rgba(59, 130, 246, 0.2), rgba(168, 85, 247, 0.2));
            border-color: rgba(168, 85, 247, 0.3);
        }
        .contact-telegram:hover {
            background-image: linear-gradient(to right, rgba(168, 85, 247, 0.3), rgba(147, 51, 234, 0.3));
            border-color: rgba(192, 132, 252, 0.6);
        }
        .contact-telegram svg { color: var(--tw-purple-400); }
        .contact-telegram:hover svg { color: var(--tw-purple-300); }

        .contact-link svg {
            width: 1.5rem;
            height: 1.5rem;
            margin-right: 0.75rem;
            transition: color 300ms;
        }

        /* Footer */
        footer {
            color: var(--tw-gray-500);
            padding-bottom: 2rem;
        }

        /* Responsive Design */
        @media (min-width: 768px) {
            .md-text-6xl { font-size: 3.75rem; line-height: 1; }
            .md-text-2xl { font-size: 1.5rem; line-height: 2rem; }
            .md-grid-cols-6 { grid-template-columns: repeat(6, minmax(0, 1fr)); }
            .md-flex-row { flex-direction: row; }
            .container { padding-left: 2rem; padding-right: 2rem;}
        }
    </style>
</head>
<body>

    <div class="background-blobs">
        <div class="blob blob-1"></div>
        <div class="blob blob-2"></div>
        <div class="blob blob-3"></div>
    </div>

    <div class="container">
        <header class="text-center mb-16">
            <div class="inline-block name-badge rounded-full mb-4">
                <span class="bg-clip-text gradient-blue-purple">
                    Vladimir Blinkov
                </span>
            </div>
            
            <h1 class="text-4xl md-text-6xl font-extrabold mb-4">
                <span class="bg-clip-text gradient-blue-purple-pink">
                    rifux
                </span>
            </h1>
            
            <p class="text-xl md-text-2xl text-gray-300 title-tags">
                <span class="inline-block rounded-lg tag-go mr-2">Go Enthusiast</span>
                <span class="inline-block rounded-lg tag-linux">Linux Wizard</span>
            </p>
        </header>

        <section class="mb-20">
            <h2 class="text-3xl font-bold text-center mb-12 bg-clip-text gradient-blue-to-purple-400">
                Crafting With
            </h2>
            
            <div class="grid skills-grid md-grid-cols-6 gap-6 mb-8">
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=go&theme=dark" alt="Go">
                    <span class="text-sm font-medium capitalize">Go</span>
                </div>
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=postgresql&theme=dark" alt="PostgreSQL">
                    <span class="text-sm font-medium capitalize">PostgreSQL</span>
                </div>
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=redis&theme=dark" alt="Redis">
                    <span class="text-sm font-medium capitalize">Redis</span>
                </div>
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=linux&theme=dark" alt="Linux">
                    <span class="text-sm font-medium capitalize">Linux</span>
                </div>
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=git&theme=dark" alt="Git">
                    <span class="text-sm font-medium capitalize">Git</span>
                </div>
                <div class="skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=docker&theme=dark" alt="Docker">
                    <span class="text-sm font-medium capitalize">Docker</span>
                </div>
            </div>
            
            <h2 class="text-2xl font-bold text-center mb-8" style="color: var(--tw-gray-400);">Also Working With</h2>
            
            <div class="grid skills-grid md-grid-cols-6 gap-6">
                 <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=bash&theme=dark" alt="Bash">
                    <span class="text-xs font-medium capitalize">Bash</span>
                </div>
                <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=godot&theme=dark" alt="Godot">
                    <span class="text-xs font-medium capitalize">Godot</span>
                </div>
                <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=github&theme=dark" alt="GitHub">
                    <span class="text-xs font-medium capitalize">GitHub</span>
                </div>
                <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=mongo&theme=dark" alt="MongoDB">
                    <span class="text-xs font-medium capitalize">Mongo</span>
                </div>
                <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=cpp&theme=dark" alt="C++">
                    <span class="text-xs font-medium capitalize">C++</span>
                </div>
                <div class="skill-card secondary-skill-card rounded-xl">
                    <img src="https://skillicons.dev/icons?i=python&theme=dark" alt="Python">
                    <span class="text-xs font-medium capitalize">Python</span>
                </div>
            </div>
        </section>

        <section class="mb-20">
            <div class="flex justify-center">
                <a href="https://www.codewars.com/users/rifux" target="_blank" rel="noopener noreferrer" class="codewars-link">
                    <img src="https://github.r2v.ch/codewars?user=rifux&name=false&theme=purple_dark&hide_clan=true&top_languages=true" alt="CodeWars Stats" class="codewars-img">
                </a>
            </div>
        </section>

        <section class="mb-20">
            <h2 class="text-3xl font-bold text-center mb-12 bg-clip-text gradient-blue-to-purple-400">
                Connect With Me
            </h2>
            
            <div class="flex flex-col md-flex-row justify-center gap-6">
                <a href="mailto:contact@rifux.dev" class="contact-link contact-email rounded-xl">
                    <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M20 4H4C2.89543 4 2 4.89543 2 6V18C2 19.1046 2.89543 20 4 20H20C21.1046 20 22 19.1046 22 18V6C22 4.89543 21.1046 4 20 4Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        <path d="M22 6L12 13L2 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                    contact@rifux.dev
                </a>
                
                <a href="https://t.me/rifux_dev" target="_blank" rel="noopener noreferrer" class="contact-link contact-telegram rounded-xl">
                    <svg viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                        <path d="M22.26465,2.42773a2.04837,2.04837,0,0,0-2.07813-.32421L2.26562,9.33887a2.043,2.043,0,0,0,.1045,3.81836l3.625,1.26074,2.0205,6.68164A.998.998,0,0,0,8.134,21.352c.00775.012.01868.02093.02692.03259a.98844.98844,0,0,0,.21143.21576c.02307.01758.04516.03406.06982.04968a.98592.98592,0,0,0,.31073.13611l.01184.001.00671.00287a1.02183,1.02183,0,0,0,.20215.02051c.00653,0,.01233-.00312.0188-.00324a.99255.99255,0,0,0,.30109-.05231c.02258-.00769.04193-.02056.06384-.02984a.9931.9931,0,0,0,.20429-.11456,250.75993,250.75993,0,0,1,.15222-.12818L12.416,18.499l4.03027,3.12207a2.02322,2.02322,0,0,0,1.24121.42676A2.05413,2.05413,0,0,0,19.69531,20.415L22.958,4.39844A2.02966,2.02966,0,0,0,22.26465,2.42773ZM9.37012,14.73633a.99357.99357,0,0,0-.27246.50586l-.30951,1.504-.78406-2.59307,4.06525-2.11695ZM17.67188,20.04l-4.7627-3.68945a1.00134,1.00134,0,0,0-1.35352.11914l-.86541.9552.30584-1.48645,7.083-7.083a.99975.99975,0,0,0-1.16894-1.59375L6.74487,12.55432,3.02051,11.19141,20.999,3.999Z"/>
                    </svg>
                    @rifux_dev
                </a>
            </div>
        </section>

        <footer class="text-center">
            <p>© 2025 Vladimir Blinkov</p>
        </footer>

    </div>

</body>
</html>