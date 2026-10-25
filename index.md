<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 7.2 — Pricing Cards & Centered Login Form</title>
    <!-- Tailwind CSS for styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#f0f5ff',
                            100: '#e0ebff',
                            500: '#3b82f6',
                            600: '#2563eb',
                            700: '#1d4ed8',
                        }
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .font-mono-code {
            font-family: 'Fira Code', monospace;
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col antialiased">

    <!-- Header & Navigation -->
    <header class="sticky top-0 z-50 bg-white/90 backdrop-blur-md border-b border-slate-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Assignment Info -->
                <div class="flex items-center space-x-3">
                    <span class="bg-blue-600 text-white font-bold text-xs px-2.5 py-1 rounded-full uppercase tracking-wider">Assignment 7.2</span>
                    <h1 class="text-lg font-bold text-slate-900 hidden sm:block">Flexbox: Pricing & Centered Login</h1>
                </div>

                <!-- Navigation Tabs -->
                <nav class="flex space-x-1 sm:space-x-2 bg-slate-100 p-1 rounded-xl text-sm font-medium">
                    <button onclick="switchTab('pricing')" id="tab-pricing" class="px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 bg-white text-blue-600 shadow-sm font-semibold flex items-center gap-2">
                        <i class="fa-solid fa-[#3b82f6] fa-tags"></i>
                        <span>Pricing Cards</span>
                    </button>
                    <button onclick="switchTab('login')" id="tab-login" class="px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 text-slate-600 hover:text-slate-900 flex items-center gap-2">
                        <i class="fa-solid fa-user-lock"></i>
                        <span>Centered Form</span>
                    </button>
                    <button onclick="switchTab('combined')" id="tab-combined" class="px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 text-slate-600 hover:text-slate-900 flex items-center gap-2">
                        <i class="fa-solid fa-layer-group"></i>
                        <span class="hidden md:inline">Full Demo Page</span>
                    </button>
                </nav>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-grow">
        
        <!-- SECTION 1: PRICING CARDS -->
        <section id="section-pricing" class="py-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
            
            <!-- Section Header & Explanation -->
            <div class="text-center max-w-3xl mx-auto mb-10">
                <h2 class="text-3xl font-extrabold text-slate-900 tracking-tight sm:text-4xl">
                    Flexible Pricing Plans
                </h2>
                <p class="mt-3 text-lg text-slate-600">
                    Demonstrating horizontal alignment and card layout using CSS Flexbox.
                </p>
                
                <!-- Flexbox Concept Code Badge -->
                <div class="mt-4 inline-flex items-center gap-2 bg-slate-900 text-slate-200 px-4 py-2 rounded-lg text-xs font-mono-code shadow-md text-left overflow-x-auto">
                    <span class="text-blue-400">.pricing-container</span> { <span class="text-emerald-400">display</span>: flex; <span class="text-emerald-400">justify-content</span>: center; <span class="text-emerald-400">align-items</span>: stretch; <span class="text-emerald-400">flex-wrap</span>: wrap; }
                </div>
            </div>

            <!-- Live Interactive Controls for Demonstration -->
            <div class="bg-white border border-slate-200 rounded-xl p-4 mb-8 shadow-sm max-w-4xl mx-auto">
                <div class="flex flex-wrap items-center justify-between gap-4 text-xs sm:text-sm">
                    <div class="flex items-center gap-2 font-semibold text-slate-700">
                        <i class="fa-solid fa-sliders text-blue-500"></i>
                        <span>Interactive Flexbox Inspector:</span>
                    </div>
                    <div class="flex flex-wrap items-center gap-3">
                        <div>
                            <label class="text-slate-500 mr-1 font-medium">justify-content:</label>
                            <select id="pricing-justify" onchange="updatePricingFlex()" class="bg-slate-50 border border-slate-300 rounded px-2 py-1 text-slate-800 font-mono text-xs focus:ring-2 focus:ring-blue-500 outline-none">
                                <option value="justify-center" selected>center</option>
                                <option value="justify-start">flex-start</option>
                                <option value="justify-end">flex-end</option>
                                <option value="justify-between">space-between</option>
                                <option value="justify-around">space-around</option>
                                <option value="justify-evenly">space-evenly</option>
                            </select>
                        </div>
                        <div>
                            <label class="text-slate-500 mr-1 font-medium">align-items:</label>
                            <select id="pricing-align" onchange="updatePricingFlex()" class="bg-slate-50 border border-slate-300 rounded px-2 py-1 text-slate-800 font-mono text-xs focus:ring-2 focus:ring-blue-500 outline-none">
                                <option value="items-stretch" selected>stretch</option>
                                <option value="items-center">center</option>
                                <option value="items-start">flex-start</option>
                                <option value="items-end">flex-end</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>

            <!-- FLEXBOX PARENT CONTAINER FOR CARDS -->
            <!-- Step 3 & 4: Uses Flexbox, justify-content, align-items, flex-wrap -->
            <div id="pricing-container" class="flex flex-wrap justify-center items-stretch gap-8 transition-all duration-300">
                
                <!-- Card 1: Basic Plan -->
                <div class="w-full md:w-80 max-w-sm bg-white rounded-2xl border border-slate-200 shadow-sm hover:shadow-xl transition-all duration-300 flex flex-col justify-between p-8 relative hover:-translate-y-1">
                    <div>
                        <div class="flex justify-between items-center mb-4">
                            <h3 class="text-xl font-bold text-slate-900">Basic</h3>
                            <span class="text-xs font-semibold uppercase px-2.5 py-1 bg-slate-100 text-slate-600 rounded-full">Starter</span>
                        </div>
                        <p class="text-slate-500 text-sm mb-6">Essential tools for individuals and small personal projects.</p>
                        
                        <div class="mb-6">
                            <span class="text-4xl font-extrabold text-slate-900">$9</span>
                            <span class="text-slate-500 text-sm font-medium">/ month</span>
                        </div>

                        <!-- Features list -->
                        <ul class="space-y-3 text-sm text-slate-600 mb-8">
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Up to 3 Personal Projects</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>5 GB Cloud Storage</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Basic Analytics</span>
                            </li>
                            <li class="flex items-center gap-3 text-slate-400 line-through">
                                <i class="fa-solid fa-circle-xmark text-slate-300 text-base"></i>
                                <span>24/7 Priority Support</span>
                            </li>
                            <li class="flex items-center gap-3 text-slate-400 line-through">
                                <i class="fa-solid fa-circle-xmark text-slate-300 text-base"></i>
                                <span>Custom Domain Integration</span>
                            </li>
                        </ul>
                    </div>

                    <button onclick="handlePlanSelect('Basic')" class="w-full py-3 px-4 bg-slate-100 hover:bg-slate-200 text-slate-800 font-semibold rounded-xl transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-slate-400">
                        Get Started
                    </button>
                </div>

                <!-- Card 2: Pro Plan (Highlighted/Popular) -->
                <div class="w-full md:w-80 max-w-sm bg-white rounded-2xl border-2 border-blue-600 shadow-xl hover:shadow-2xl transition-all duration-300 flex flex-col justify-between p-8 relative hover:-translate-y-1 transform md:-translate-y-2">
                    <!-- Popular Badge -->
                    <div class="absolute -top-3.5 left-1/2 -translate-x-1/2 bg-blue-600 text-white font-bold text-xs px-3 py-1 rounded-full uppercase tracking-wider shadow-md">
                        Most Popular
                    </div>

                    <div>
                        <div class="flex justify-between items-center mb-4 mt-1">
                            <h3 class="text-xl font-bold text-slate-900">Pro</h3>
                            <span class="text-xs font-semibold uppercase px-2.5 py-1 bg-blue-50 text-blue-600 rounded-full">Pro Choice</span>
                        </div>
                        <p class="text-slate-500 text-sm mb-6">Perfect for growing professionals and active team workflows.</p>
                        
                        <div class="mb-6">
                            <span class="text-4xl font-extrabold text-slate-900">$29</span>
                            <span class="text-slate-500 text-sm font-medium">/ month</span>
                        </div>

                        <!-- Features list -->
                        <ul class="space-y-3 text-sm text-slate-600 mb-8">
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Unlimited Active Projects</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>50 GB Cloud Storage</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Advanced Real-time Analytics</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Priority Email Support</span>
                            </li>
                            <li class="flex items-center gap-3 text-slate-400 line-through">
                                <i class="fa-solid fa-circle-xmark text-slate-300 text-base"></i>
                                <span>Dedicated Account Manager</span>
                            </li>
                        </ul>
                    </div>

                    <button onclick="handlePlanSelect('Pro')" class="w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-xl shadow-md shadow-blue-500/20 transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
                        Start 14-Day Free Trial
                    </button>
                </div>

                <!-- Card 3: Premium Plan -->
                <div class="w-full md:w-80 max-w-sm bg-white rounded-2xl border border-slate-200 shadow-sm hover:shadow-xl transition-all duration-300 flex flex-col justify-between p-8 relative hover:-translate-y-1">
                    <div>
                        <div class="flex justify-between items-center mb-4">
                            <h3 class="text-xl font-bold text-slate-900">Premium</h3>
                            <span class="text-xs font-semibold uppercase px-2.5 py-1 bg-purple-50 text-purple-600 rounded-full">Enterprise</span>
                        </div>
                        <p class="text-slate-500 text-sm mb-6">Designed for organizations with advanced scaling and security needs.</p>
                        
                        <div class="mb-6">
                            <span class="text-4xl font-extrabold text-slate-900">$79</span>
                            <span class="text-slate-500 text-sm font-medium">/ month</span>
                        </div>

                        <!-- Features list -->
                        <ul class="space-y-3 text-sm text-slate-600 mb-8">
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Everything in Pro Plan</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span> Unlimited Cloud Storage</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>Custom Domain Integration</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>24/7 Dedicated Support</span>
                            </li>
                            <li class="flex items-center gap-3">
                                <i class="fa-solid fa-circle-check text-emerald-500 text-base"></i>
                                <span>SLA & Enterprise Security</span>
                            </li>
                        </ul>
                    </div>

                    <button onclick="handlePlanSelect('Premium')" class="w-full py-3 px-4 bg-slate-900 hover:bg-slate-800 text-white font-semibold rounded-xl transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-slate-900">
                        Contact Sales
                    </button>
                </div>

            </div>
        </section>

        <!-- SECTION DIVIDER -->
        <div id="divider" class="max-w-7xl mx-auto px-4 my-8">
            <hr class="border-slate-200">
        </div>

        <!-- SECTION 2: CENTERED LOGIN FORM -->
        <!-- Step 5: Center the login form horizontally and vertically -->
        <section id="section-login" class="px-4 sm:px-6 lg:px-8 py-12 flex flex-col justify-center items-center min-h-[80vh] bg-slate-100/60 relative">
            
            <!-- Technical Badge Overlay -->
            <div class="text-center mb-6 max-w-md">
                <span class="text-xs font-semibold text-blue-600 uppercase tracking-widest bg-blue-50 px-3 py-1 rounded-full border border-blue-200">
                    Dual-Axis Flexbox Centering
                </span>
                <h2 class="text-2xl font-bold text-slate-900 mt-2">Centered Login Form</h2>
                <p class="text-xs text-slate-500 mt-1 font-mono-code bg-slate-200/80 px-2 py-1 rounded inline-block">
                    display: flex; justify-content: center; align-items: center; min-height: 80vh;
                </p>
            </div>

            <!-- THE CENTERED FORM CARD -->
            <div class="w-full max-w-md bg-white rounded-2xl shadow-xl border border-slate-200/80 p-8 sm:p-10 transition-all">
                
                <!-- Logo & Heading -->
                <div class="text-center mb-8">
                    <div class="inline-flex items-center justify-center w-14 h-14 bg-blue-600 text-white rounded-2xl shadow-lg shadow-blue-500/30 mb-4">
                        <i class="fa-solid fa-lock text-2xl"></i>
                    </div>
                    <h3 class="text-2xl font-bold text-slate-900">Welcome Back</h3>
                    <p class="text-slate-500 text-sm mt-1">Please enter your credentials to sign in</p>
                </div>

                <!-- Simulation Alert Box -->
                <div id="login-alert" class="hidden mb-6 p-4 rounded-xl text-sm font-medium transition-all"></div>

                <!-- Form -->
                <form id="login-form" onsubmit="handleLogin(event)" class="space-y-5">
                    
                    <!-- Email Field -->
                    <div>
                        <label for="email" class="block text-xs font-semibold text-slate-700 uppercase tracking-wider mb-2">Email Address</label>
                        <div class="relative">
                            <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-400">
                                <i class="fa-regular fa-envelope"></i>
                            </div>
                            <input 
                                type="email" 
                                id="email" 
                                required
                                placeholder="name@company.com"
                                class="w-full pl-10 pr-4 py-3 bg-slate-50 border border-slate-300 text-slate-900 text-sm rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-blue-500 block transition-all outline-none"
                            >
                        </div>
                    </div>

                    <!-- Password Field -->
                    <div>
                        <div class="flex justify-between items-center mb-2">
                            <label for="password" class="block text-xs font-semibold text-slate-700 uppercase tracking-wider">Password</label>
                            <a href="#" onclick="alertNotice('Password reset link sent to your email demo.')" class="text-xs text-blue-600 hover:text-blue-700 font-medium">Forgot password?</a>
                        </div>
                        <div class="relative">
                            <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-400">
                                <i class="fa-solid fa-lock"></i>
                            </div>
                            <input 
                                type="password" 
                                id="password" 
                                required
                                placeholder="••••••••"
                                class="w-full pl-10 pr-10 py-3 bg-slate-50 border border-slate-300 text-slate-900 text-sm rounded-xl focus:ring-2 focus:ring-blue-500 focus:border-blue-500 block transition-all outline-none"
                            >
                            <button 
                                type="button" 
                                onclick="togglePasswordVisibility()" 
                                class="absolute inset-y-0 right-0 pr-3.5 flex items-center text-slate-400 hover:text-slate-600"
                            >
                                <i id="eye-icon" class="fa-regular fa-eye"></i>
                            </button>
                        </div>
                    </div>

                    <!-- Remember Me & Checkbox -->
                    <div class="flex items-center justify-between">
                        <label class="flex items-center space-x-2 cursor-pointer">
                            <input type="checkbox" id="remember" class="w-4 h-4 text-blue-600 bg-slate-100 border-slate-300 rounded focus:ring-blue-500">
                            <span class="text-sm text-slate-600 select-none">Remember me for 30 days</span>
                        </label>
                    </div>

                    <!-- Submit Button -->
                    <button 
                        type="submit" 
                        id="login-btn"
                        class="w-full py-3.5 px-4 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-xl shadow-md shadow-blue-500/20 transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 flex justify-center items-center gap-2"
                    >
                        <span>Sign In</span>
                        <i class="fa-solid fa-arrow-right text-xs"></i>
                    </button>

                </form>

                <!-- Footer Text -->
                <p class="text-center text-xs text-slate-500 mt-6">
                    Don't have an account? <a href="#" onclick="alertNotice('Sign up demo page clicked.')" class="text-blue-600 font-semibold hover:underline">Create account</a>
                </p>
            </div>
        </section>

        <!-- SECTION 3: ASSIGNMENT DOCUMENTATION / EDUCATIONAL SUMMARY -->
        <!-- Step 6: Demonstrate the practical use of flex-direction and alignment properties -->
        <section class="bg-white border-t border-slate-200 py-12 px-4 sm:px-6 lg:px-8">
            <div class="max-w-5xl mx-auto">
                <div class="text-center mb-8">
                    <h3 class="text-xl font-bold text-slate-900">Flexbox Concepts Used in Assignment 7.2</h3>
                    <p class="text-sm text-slate-600 mt-1">Summary of CSS Flexbox implementation and layout choices</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <!-- Concept 1 -->
                    <div class="bg-slate-50 p-5 rounded-xl border border-slate-200">
                        <div class="w-8 h-8 bg-blue-100 text-blue-600 rounded-lg flex items-center justify-center font-bold text-sm mb-3">1</div>
                        <h4 class="font-bold text-slate-900 text-sm font-mono-code mb-2">justify-content</h4>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Controls main-axis alignment. Used with <code class="bg-slate-200 px-1 rounded text-slate-800">center</code> on the Pricing Cards container to evenly center 3 cards, and on the Login section to horizontally center the login box.
                        </p>
                    </div>

                    <!-- Concept 2 -->
                    <div class="bg-slate-50 p-5 rounded-xl border border-slate-200">
                        <div class="w-8 h-8 bg-blue-100 text-blue-600 rounded-lg flex items-center justify-center font-bold text-sm mb-3">2</div>
                        <h4 class="font-bold text-slate-900 text-sm font-mono-code mb-2">align-items</h4>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            Controls cross-axis alignment. Used with <code class="bg-slate-200 px-1 rounded text-slate-800">stretch</code> for pricing cards so all cards reach equal height, and <code class="bg-slate-200 px-1 rounded text-slate-800">center</code> for perfect vertical form centering.
                        </p>
                    </div>

                    <!-- Concept 3 -->
                    <div class="bg-slate-50 p-5 rounded-xl border border-slate-200">
                        <div class="w-8 h-8 bg-blue-100 text-blue-600 rounded-lg flex items-center justify-center font-bold text-sm mb-3">3</div>
                        <h4 class="font-bold text-slate-900 text-sm font-mono-code mb-2">flex-direction & wrap</h4>
                        <p class="text-xs text-slate-600 leading-relaxed">
                            <code class="bg-slate-200 px-1 rounded text-slate-800">flex-direction: column</code> arranges inner card contents vertically (Title → Price → Features → Button), while <code class="bg-slate-200 px-1 rounded text-slate-800">flex-wrap: wrap</code> enables responsive mobile stacking.
                        </p>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-slate-900 text-slate-400 py-6 text-center text-xs">
        <p>Assignment 7.2 Submission • Created with HTML & Tailwind CSS Flexbox</p>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // Tab Switcher Logic
        function switchTab(tabName) {
            const pricingSec = document.getElementById('section-pricing');
            const loginSec = document.getElementById('section-login');
            const divider = document.getElementById('divider');

            const tabPricingBtn = document.getElementById('tab-pricing');
            const tabLoginBtn = document.getElementById('tab-login');
            const tabCombinedBtn = document.getElementById('tab-combined');

            // Reset tab button styles
            [tabPricingBtn, tabLoginBtn, tabCombinedBtn].forEach(btn => {
                btn.className = "px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 text-slate-600 hover:text-slate-900 flex items-center gap-2";
            });

            if (tabName === 'pricing') {
                pricingSec.style.display = 'block';
                loginSec.style.display = 'none';
                divider.style.display = 'none';
                tabPricingBtn.className = "px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 bg-white text-blue-600 shadow-sm font-semibold flex items-center gap-2";
            } else if (tabName === 'login') {
                pricingSec.style.display = 'none';
                loginSec.style.display = 'flex';
                divider.style.display = 'none';
                tabLoginBtn.className = "px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 bg-white text-blue-600 shadow-sm font-semibold flex items-center gap-2";
            } else {
                pricingSec.style.display = 'block';
                loginSec.style.display = 'flex';
                divider.style.display = 'block';
                tabCombinedBtn.className = "px-3 sm:px-4 py-1.5 rounded-lg transition-all duration-200 bg-white text-blue-600 shadow-sm font-semibold flex items-center gap-2";
            }
        }

        // Live Flexbox Inspector Controls
        function updatePricingFlex() {
            const container = document.getElementById('pricing-container');
            const justifyVal = document.getElementById('pricing-justify').value;
            const alignVal = document.getElementById('pricing-align').value;

            // Remove previous alignment classes
            container.className = "flex flex-wrap gap-8 transition-all duration-300 " + justifyVal + " " + alignVal;
        }

        // Password Visibility Toggle
        function togglePasswordVisibility() {
            const pwdInput = document.getElementById('password');
            const eyeIcon = document.getElementById('eye-icon');

            if (pwdInput.type === 'password') {
                pwdInput.type = 'text';
                eyeIcon.className = 'fa-regular fa-eye-slash';
            } else {
                pwdInput.type = 'password';
                eyeIcon.className = 'fa-regular fa-eye';
            }
        }

        // Plan Selection Callback
        function handlePlanSelect(planName) {
            const alertBox = document.getElementById('login-alert');
            switchTab('login');
            alertBox.className = "mb-6 p-4 rounded-xl text-sm font-medium bg-blue-50 text-blue-800 border border-blue-200 block";
            alertBox.innerHTML = `<i class="fa-solid fa-circle-info mr-2"></i> Selected plan: <strong>${planName}</strong>. Please sign in to finalize setup.`;
            
            // Scroll smooth to login section
            document.getElementById('section-login').scrollIntoView({ behavior: 'smooth' });
        }

        // Form Login Handler
        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('email').value;
            const alertBox = document.getElementById('login-alert');
            const submitBtn = document.getElementById('login-btn');

            submitBtn.disabled = true;
            submitBtn.innerHTML = `<i class="fa-solid fa-spinner animate-spin"></i> Processing...`;

            setTimeout(() => {
                submitBtn.disabled = false;
                submitBtn.innerHTML = `<span>Sign In</span><i class="fa-solid fa-arrow-right text-xs"></i>`;

                alertBox.className = "mb-6 p-4 rounded-xl text-sm font-medium bg-emerald-50 text-emerald-800 border border-emerald-200 block";
                alertBox.innerHTML = `<i class="fa-solid fa-circle-check mr-2"></i> Welcome back! Successfully signed in as <strong>${email}</strong>.`;
            }, 1000);
        }

        // Generic Notice Banner
        function alertNotice(msg) {
            const alertBox = document.getElementById('login-alert');
            alertBox.className = "mb-6 p-4 rounded-xl text-sm font-medium bg-amber-50 text-amber-800 border border-amber-200 block";
            alertBox.innerHTML = `<i class="fa-solid fa-bell mr-2"></i> ${msg}`;
        }
    </script>
</body>
</html>