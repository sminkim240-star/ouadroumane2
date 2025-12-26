<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>تعلّم الإسلام | منصة واد الرمان التفاعلية</title>
    
    <!-- Scripts & Fonts -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        darkBg: '#0f172a',
                        darkCard: '#1e293b'
                    },
                    borderRadius: {
                        '4xl': '2rem',
                        '5xl': '2.5rem'
                    }
                }
            }
        }
    </script>

    <style>
        /* Base Styles */
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #f8fafc;
            scroll-behavior: smooth;
            transition: background-color 0.4s cubic-bezier(0.4, 0, 0.2, 1), color 0.4s ease;
        }

        /* Dark Mode Overrides */
        .dark body { background-color: #0f172a; color: #f1f5f9; }
        .dark aside, .dark header, .dark .bg-white, .dark .category-card, .dark footer { 
            background-color: #1e293b; 
            border-color: #334155; 
        }
        .dark .text-slate-600, .dark .text-slate-500 { color: #94a3b8; }
        .dark .text-slate-800 { color: #f1f5f9; }

        /* Scrollbar Styling */
        .sidebar-scroll::-webkit-scrollbar { width: 4px; }
        .sidebar-scroll::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        .dark .sidebar-scroll::-webkit-scrollbar-thumb { background: #475569; }

        /* Custom Gradients & Transitions */
        .hero-gradient { background: linear-gradient(135deg, #14b8a6 0%, #0d9488 100%); }
        .nav-item { transition: all 0.3s ease; }
        .active-nav { background-color: #f0fdfa; color: #0d9488; border-right: 4px solid #0d9488; }
        .dark .active-nav { background-color: rgba(20, 184, 166, 0.1); color: #5eead4; border-right-color: #5eead4; }

        .category-card { transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1); cursor: pointer; }
        .category-card:hover { transform: translateY(-8px); box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.05); }

        /* Dropdown Logic */
        .lang-dropdown { display: none; opacity: 0; transform: translateY(-10px); transition: all 0.3s ease; }
        .lang-dropdown.active { display: block; opacity: 1; transform: translateY(0); }
        
        /* Logo Styles */
        .platform-logo { width: 40px; height: 40px; object-fit: contain; border-radius: 8px; }
    </style>
</head>
<body class="text-slate-800 antialiased overflow-x-hidden">

    <!-- Mobile Header -->
    <nav class="lg:hidden flex items-center justify-between p-4 bg-white dark:bg-darkCard border-b dark:border-slate-700 sticky top-0 z-50 transition-colors duration-300">
        <button id="mobile-menu-btn" class="p-2 text-slate-600 dark:text-slate-300 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-lg transition-colors">
            <i data-lucide="menu"></i>
        </button>
        <div class="flex items-center gap-2">
            <img src="https://limewire.com/decrypt?downloadUrl=https%3A%2F%2Fb61cdfd8cf17f52ddc020162e738eb5d.r2.cloudflarestorage.com%2Flimewire-filesharing-production%2Fbuckets%2F12d9c2fd-3cdd-4876-bc38-103a6a681009%2Ff5cd1d3b-40f9-4f15-8dba-f68ceaf59297%2Fmetadata%2F8bbeb561-ed41-42d1-b183-8be6b6e3ed46%3FX-Amz-Algorithm%3DAWS4-HMAC-SHA256%26X-Amz-Date%3D20251226T231549Z%26X-Amz-SignedHeaders%3Dhost%26X-Amz-Credential%3Da1868571dfad6d4fe293ee5b945a0ad5%252F20251226%252Fauto%252Fs3%252Faws4_request%26X-Amz-Expires%3D3600%26X-Amz-Signature%3D0f2186759ed4eaf621ddc2d0212d4cab711e04bd4d70cb48c5ec312c2633477f&mediaType=image%2Fjpeg&decryptionKeys=eyJhZXNHY21Kd2siOnsiYWVzS2V5VHlwZSI6IlNZTU1FVFJJQ19BRVMtR0NNX0tFWSIsImp3ayI6eyJhbGciOiJBMjU2R0NNIiwiZXh0Ijp0cnVlLCJrIjoiNHJLWlVmUzJvLUtfNlhuelpnb3hGR0ZtM3p6VnpnaC05QmVKLXNmUVluNCIsImtleV9vcHMiOlsiZW5jcnlwdCIsImRlY3J5cHQiXSwia3R5Ijoib2N0In19LCJhZXNDdHJKd2siOnsiYWVzS2V5VHlwZSI6IlNZTU1FVFJJQ19BRVMtQ1RSX0tFWSIsImp3ayI6eyJhbGciOiJBMjU2Q1RSIiwiZXh0Ijp0cnVlLCJrIjoiNHJLWlVmUzJvLUtfNlhuelpnb3hGR0ZtM3p6VnpnaC05QmVKLXNmUVluNCIsImtleV9vcHMiOlsiZW5jcnlwdCIsImRlY3J5cHQiXSwia3R5Ijoib2N0In19fQ&preview=8bbeb561-ed41-42d1-b183-8be6b6e3ed46" alt="شعار منصة واد الرمان" class="platform-logo">
            <span class="font-bold text-xl tracking-tight" data-t="platform_name">منصة واد الرمان</span>
        </div>
        <div class="flex gap-2">
            <button onclick="toggleDarkMode()" class="p-2.5 bg-slate-100 dark:bg-slate-700 rounded-full text-slate-600 dark:text-amber-400 hover:scale-110 transition-transform">
                <i data-lucide="moon" class="dark:hidden w-5 h-5"></i>
                <i data-lucide="sun" class="hidden dark:block w-5 h-5"></i>
            </button>
        </div>
    </nav>

    <!-- Sidebar Overlay -->
    <div id="sidebar-overlay" class="fixed inset-0 bg-slate-900/40 z-40 hidden backdrop-blur-sm transition-opacity duration-300"></div>

    <!-- Sidebar Navigation -->
    <aside id="main-sidebar" class="fixed right-0 top-0 h-full w-72 bg-white dark:bg-darkCard border-l dark:border-slate-700 shadow-xl z-50 flex flex-col lg:translate-x-0 translate-x-full transition-transform duration-500 ease-in-out">
        <div class="p-8 flex items-center gap-3 border-b dark:border-slate-700">
            <img src="https://limewire.com/decrypt?downloadUrl=https%3A%2F%2Fb61cdfd8cf17f52ddc020162e738eb5d.r2.cloudflarestorage.com%2Flimewire-filesharing-production%2Fbuckets%2F12d9c2fd-3cdd-4876-bc38-103a6a681009%2Ff5cd1d3b-40f9-4f15-8dba-f68ceaf59297%2Fmetadata%2F8bbeb561-ed41-42d1-b183-8be6b6e3ed46%3FX-Amz-Algorithm%3DAWS4-HMAC-SHA256%26X-Amz-Date%3D20251226T231549Z%26X-Amz-SignedHeaders%3Dhost%26X-Amz-Credential%3Da1868571dfad6d4fe293ee5b945a0ad5%252F20251226%252Fauto%252Fs3%252Faws4_request%26X-Amz-Expires%3D3600%26X-Amz-Signature%3D0f2186759ed4eaf621ddc2d0
            <div class="text-2xl font-extrabold tracking-tight dark:text-white" data-t="platform_name">منصة واد الرمان</div>
        </div>

        <div class="flex-grow overflow-y-auto sidebar-scroll p-4 space-y-1 mt-4">
            <p class="text-[10px] font-bold text-slate-400 dark:text-slate-500 px-4 mb-2 uppercase tracking-[0.2em]" data-t="main_menu">القائمة الرئيسية</p>
            <a href="#" class="nav-item active-nav flex items-center gap-3 p-3.5 rounded-2xl">
                <i data-lucide="layout-grid" class="w-5 h-5"></i>
                <span class="font-bold" data-t="home">الرئيسية</span>
            </a>
            <a href="#lessons-section" class="nav-item flex items-center gap-3 p-3.5 rounded-2xl text-slate-600 dark:text-slate-400 hover:bg-slate-50 dark:hover:bg-slate-800">
                <i data-lucide="graduation-cap" class="w-5 h-5"></i>
                <span class="font-medium" data-t="lessons">الدروس التعليمية</span>
            </a>
            <a href="#challenge-section" class="nav-item flex items-center gap-3 p-3.5 rounded-2xl text-slate-600 dark:text-slate-400 hover:bg-slate-50 dark:hover:bg-slate-800">
                <i data-lucide="timer" class="w-5 h-5"></i>
                <span class="font-medium" data-t="time_challenge">تحدي الوقت</span>
            </a>
            <a href="#" class="nav-item flex items-center gap-3 p-3.5 rounded-2xl text-slate-600 dark:text-slate-400 hover:bg-slate-50 dark:hover:bg-slate-800">
                <i data-lucide="book-open" class="w-5 h-5"></i>
                <span class="font-medium" data-t="courses">المسارات التعليمية</span>
            </a>
            <a href="#" class="nav-item flex items-center gap-3 p-3.5 rounded-2xl text-slate-600 dark:text-slate-400 hover:bg-slate-50 dark:hover:bg-slate-800">
                <i data-lucide="file-text" class="w-5 h-5"></i>
                <span class="font-medium" data-t="library">المكتبة الشاملة</span>
            </a>
        </div>

        <div class="p-6 border-t dark:border-slate-700 bg-slate-50/50 dark:bg-slate-800/30">
            <button class="w-full flex items-center justify-center gap-2 p-4 bg-teal-600 hover:bg-teal-700 text-white rounded-2xl font-bold shadow-lg shadow-teal-500/10 transition-all active:scale-95">
                <i data-lucide="plus-circle" class="w-5 h-5"></i>
                <span data-t="register">تسجيل جديد</span>
            </button>
        </div>
    </aside>

    <!-- Main Content Area -->
    <main class="lg:mr-72 min-h-screen transition-all duration-500 flex flex-col">
        
        <div class="flex-grow">
            <!-- Desktop Header -->
            <header class="hidden lg:flex items-center justify-between p-6 sticky top-0 bg-white/80 dark:bg-darkCard/80 backdrop-blur-xl z-30 border-b dark:border-slate-700 px-10 transition-colors duration-300">
                <div class="relative w-80 group">
                    <input type="text" id="main-search-input" data-t-placeholder="search_placeholder" placeholder="ابحث عن موضوع شرعي..." class="w-full bg-slate-100 dark:bg-slate-800 border-2 border-transparent focus:border-teal-500/20 focus:bg-white dark:focus:bg-slate-900 rounded-2xl py-2.5 px-5 pr-12 outline-none dark:text-white transition-all">
                    <i data-lucide="search" class="absolute right-4 top-1/2 -translate-y-1/2 text-slate-400 group-focus-within:text-teal-500 transition-colors w-5 h-5"></i>
                </div>

                <div class="flex items-center gap-4">
                    <div class="relative">
                        <button onclick="toggleLangDropdown()" class="flex items-center gap-2 px-4 py-2.5 bg-slate-100 dark:bg-slate-800 hover:bg-slate-200 dark:hover:bg-slate-700 rounded-2xl border border-slate-200/50 dark:border-slate-700 transition-all font-bold text-sm shadow-sm active:scale-95 group">
                            <i data-lucide="languages" class="w-4 h-4 text-teal-600"></i>
                            <span id="current-lang-label" class="dark:text-slate-200">العربية</span>
                            <i data-lucide="chevron-down" class="w-4 h-4 text-slate-400 group-hover:translate-y-0.5 transition-transform"></i>
                        </button>
                        <div id="lang-menu" class="lang-dropdown absolute left-0 mt-3 w-44 bg-white dark:bg-slate-800 border border-slate-200/50 dark:border-slate-700 rounded-2xl shadow-2xl overflow-hidden z-50">
                            <button onclick="changeLang('ar')" class="w-full px-4 py-3 text-right text-sm hover:bg-teal-50 dark:hover:bg-teal-900/30 flex items-center justify-between transition-colors group">
                                <span class="dark:text-slate-300 group-hover:text-teal-600 transition-colors">العربية</span>
                                <span class="text-[10px] bg-slate-100 dark:bg-slate-700 px-1.5 py-0.5 rounded-md text-slate-400">AR</span>
                            </button>
                            <button onclick="changeLang('en')" class="w-full px-4 py-3 text-right text-sm hover:bg-teal-50 dark:hover:bg-teal-900/30 flex items-center justify-between transition-colors group">
                                <span class="dark:text-slate-300 group-hover:text-teal-600 transition-colors">English</span>
                                <span class="text-[10px] bg-slate-100 dark:bg-slate-700 px-1.5 py-0.5 rounded-md text-slate-400">EN</span>
                            </button>
                        </div>
                    </div>

                    <button onclick="toggleDarkMode()" class="p-3 bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 rounded-2xl shadow-sm hover:bg-slate-50 dark:hover:bg-slate-700 transition-all active:scale-90 group">
                        <i data-lucide="moon" class="dark:hidden w-5 h-5 text-slate-600 group-hover:-rotate-12 transition-transform"></i>
                        <i data-lucide="sun" class="hidden dark:block w-5 h-5 text-amber-400 group-hover:rotate-45 transition-transform"></i>
                    </button>
                    <div class="h-8 w-[1px] bg-slate-200 dark:bg-slate-700 mx-1"></div>
                    <div class="w-11 h-11 bg-teal-50 dark:bg-slate-700 rounded-2xl overflow-hidden border-2 border-white dark:border-slate-800 shadow-sm ring-4 ring-slate-100 dark:ring-slate-900/50">
                        <img src="https://api.dicebear.com/7.x/avataaars/svg?seed=Lucky" alt="avatar" class="w-full h-full object-cover">
                    </div>
                </div>
            </header>

            <!-- Hero Section -->
            <section class="p-6 lg:p-10">
                <div class="hero-gradient rounded-[3rem] p-10 md:p-16 text-white relative overflow-hidden shadow-2xl shadow-teal-900/10 dark:shadow-none">
                    <div class="absolute top-0 right-0 w-64 h-64 bg-white/5 rounded-full -translate-y-1/2 translate-x-1/2 blur-3xl"></div>
                    <div class="relative z-10 max-w-2xl">
                        <span class="inline-flex items-center gap-2 px-4 py-1.5 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-xs font-bold mb-8 tracking-wide animate-pulse" data-t="hero_badge">✨ تعلّم بذكاء، عش بإيمان</span>
                        <h1 class="text-4xl md:text-6xl font-black mb-8 leading-[1.15]" data-t="hero_title">رحلتك في تعلم العلوم الشرعية تبدأ هنا</h1>
                        <p class="text-lg md:text-xl text-teal-50/90 mb-12 leading-relaxed" data-t="hero_desc">منصة تفاعلية تدمج بين أصالة المحتوى العلمي وأحدث تقنيات التعليم الرقمي لتبسيط العلوم الدينية للجميع.</p>
                        <button class="bg-white text-teal-800 px-12 py-5 rounded-2xl font-black shadow-2xl shadow-black/10 hover:translate-y-[-4px] active:translate-y-0 transition-all duration-300" data-t="start_btn">ابدأ التعلم الآن</button>
                    </div>
                </div>
            </section>

            <!-- Lessons Section -->
            <section id="lessons-section" class="px-6 lg:px-10 mt-10">
                <div class="flex items-center justify-between mb-8">
                    <h2 class="text-2xl md:text-3xl font-black dark:text-white" data-t="lessons_title">أحدث الدروس</h2>
                    <a href="#" class="text-teal-600 dark:text-teal-400 font-bold text-sm hover:underline">مشاهدة الكل</a>
                </div>
                <div id="lessons-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="category-card bg-white dark:bg-darkCard p-6 rounded-3xl border dark:border-slate-700 shadow-sm group">
                        <div class="flex items-start justify-between mb-4">
                            <div class="p-3 bg-teal-50 dark:bg-teal-900/30 rounded-2xl"><i data-lucide="play-circle" class="w-6 h-6 text-teal-600"></i></div>
                            <span class="text-xs font-bold text-slate-400 px-3 py-1 bg-slate-100 dark:bg-slate-800 rounded-full">15 دقيقة</span>
                        </div>
                        <h3 class="font-bold text-lg mb-2 dark:text-white category-title">مقدمة في الفقه</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 mb-4 category-desc">تعريف الفقه في اللغة والاصطلاح وأهميته في حياة المسلم.</p>
                        <div class="flex items-center gap-2">
                            <div class="w-8 h-8 rounded-full bg-slate-200 overflow-hidden"><img src="https://api.dicebear.com/7.x/initials/svg?seed=احمد" alt="instructor"></div>
                            <span class="text-xs font-bold text-slate-600 dark:text-slate-400">د. أحمد محمود</span>
                        </div>
                    </div>
                    <div class="category-card bg-white dark:bg-darkCard p-6 rounded-3xl border dark:border-slate-700 shadow-sm group">
                        <div class="flex items-start justify-between mb-4">
                            <div class="p-3 bg-amber-50 dark:bg-amber-900/30 rounded-2xl"><i data-lucide="book-marked" class="w-6 h-6 text-amber-600"></i></div>
                            <span class="text-xs font-bold text-slate-400 px-3 py-1 bg-slate-100 dark:bg-slate-800 rounded-full">22 دقيقة</span>
                        </div>
                        <h3 class="font-bold text-lg mb-2 dark:text-white category-title">أركان الصلاة</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 mb-4 category-desc">شرح مفصل لأركان الصلاة وكيفية أدائها بالشكل الصحيح.</p>
                        <div class="flex items-center gap-2">
                            <div class="w-8 h-8 rounded-full bg-slate-200 overflow-hidden"><img src="https://api.dicebear.com/7.x/initials/svg?seed=محمد" alt="instructor"></div>
                            <span class="text-xs font-bold text-slate-600 dark:text-slate-400">الشيخ محمد علي</span>
                        </div>
                    </div>
                    <div class="category-card bg-white dark:bg-darkCard p-6 rounded-3xl border dark:border-slate-700 shadow-sm group">
                        <div class="flex items-start justify-between mb-4">
                            <div class="p-3 bg-blue-50 dark:bg-blue-900/30 rounded-2xl"><i data-lucide="mic" class="w-6 h-6 text-blue-600"></i></div>
                            <span class="text-xs font-bold text-slate-400 px-3 py-1 bg-slate-100 dark:bg-slate-800 rounded-full">10 دقيقة</span>
                        </div>
                        <h3 class="font-bold text-lg mb-2 dark:text-white category-title">قصص الصحابة</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 mb-4 category-desc">لمحات تربوية من حياة الصحابي الجليل أبو بكر الصديق.</p>
                        <div class="flex items-center gap-2">
                            <div class="w-8 h-8 rounded-full bg-slate-200 overflow-hidden"><img src="https://api.dicebear.com/7.x/initials/svg?seed=ياسر" alt="instructor"></div>
                            <span class="text-xs font-bold text-slate-600 dark:text-slate-400">أ. ياسر سعيد</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Challenge Section -->
            <section id="challenge-section" class="px-6 lg:px-10 mt-16">
                <div class="bg-slate-900 dark:bg-slate-800/50 rounded-[3rem] p-8 md:p-12 relative overflow-hidden border border-slate-700">
                    <div class="absolute -left-20 -top-20 w-64 h-64 bg-teal-500/10 blur-[100px] rounded-full"></div>
                    <div class="relative z-10 flex flex-col md:flex-row items-center justify-between gap-10">
                        <div class="max-w-xl text-center md:text-right">
                            <div class="inline-flex items-center gap-2 px-4 py-1.5 bg-teal-500/20 rounded-full text-teal-400 text-xs font-black mb-6 uppercase tracking-widest" data-t="new_feature">ميزة جديدة</div>
                            <h2 class="text-3xl md:text-4xl font-black text-white mb-4" data-t="challenge_title">تحدي الوقت الشرعي</h2>
                            <p class="text-slate-400 text-lg mb-8 leading-relaxed" data-t="challenge_desc">اختبر معلوماتك الشرعية تحت الضغط! أجب على أكبر عدد من الأسئلة في 60 ثانية فقط واجمع النقاط.</p>
                            <div class="flex flex-wrap justify-center md:justify-start gap-4">
                                <button class="px-8 py-4 bg-teal-600 hover:bg-teal-500 text-white rounded-2xl font-bold transition-all shadow-lg shadow-teal-500/20 active:scale-95">ابدأ التحدي الآن</button>
                                <button class="px-8 py-4 bg-slate-800 hover:bg-slate-700 text-slate-300 rounded-2xl font-bold border border-slate-700 transition-all">قائمة المتصدرين</button>
                            </div>
                        </div>
                        <div class="relative w-48 h-48 md:w-64 md:h-64 flex items-center justify-center">
                            <div class="absolute inset-0 border-4 border-dashed border-teal-500/30 rounded-full animate-[spin_20s_linear_infinite]"></div>
                            <div class="w-32 h-32 md:w-40 md:h-40 bg-teal-500/10 rounded-full flex flex-col items-center justify-center text-teal-400 border border-teal-500/20">
                                <span class="text-4xl md:text-5xl font-black leading-none">60</span>
                                <span class="text-xs font-bold uppercase mt-1">ثانية</span>
                            </div>
                            <i data-lucide="timer" class="absolute -top-4 right-4 w-10 h-10 text-teal-500 drop-shadow-[0_0_15px_rgba(20,184,166,0.5)]"></i>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Categories Section -->
            <section class="px-6 lg:px-10 mt-16 mb-20">
                <div class="flex items-center justify-between mb-10">
                    <h2 class="text-2xl md:text-3xl font-black dark:text-white" data-t="explore">استكشف الأقسام</h2>
                    <a href="#" id="view-all-btn" class="text-teal-600 dark:text-teal-400 font-bold text-sm hover:underline transition-opacity duration-300">عرض الكل</a>
                </div>
                <div id="categories-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <div class="category-card bg-white dark:bg-darkCard p-5 rounded-[2.5rem] border dark:border-slate-700 shadow-sm group">
                        <div class="h-44 bg-teal-50 dark:bg-teal-900/20 rounded-[2rem] mb-6 flex items-center justify-center group-hover:scale-[0.98] transition-transform">
                            <div class="w-16 h-16 bg-white dark:bg-teal-800 rounded-2xl shadow-sm flex items-center justify-center"><i data-lucide="book" class="w-8 h-8 text-teal-600 dark:text-teal-300"></i></div>
                        </div>
                        <h3 class="font-bold text-xl mb-3 dark:text-white category-title">فقه العبادات</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 leading-relaxed category-desc">تعلّم أحكام الطهارة، الصلاة، والزكاة بأسلوب ميسّر.</p>
                    </div>
                    <div class="category-card bg-white dark:bg-darkCard p-5 rounded-[2.5rem] border dark:border-slate-700 shadow-sm group">
                        <div class="h-44 bg-amber-50 dark:bg-amber-900/20 rounded-[2rem] mb-6 flex items-center justify-center group-hover:scale-[0.98] transition-transform">
                            <div class="w-16 h-16 bg-white dark:bg-amber-800 rounded-2xl shadow-sm flex items-center justify-center"><i data-lucide="scroll" class="w-8 h-8 text-amber-600 dark:text-amber-300"></i></div>
                        </div>
                        <h3 class="font-bold text-xl mb-3 dark:text-white category-title">السيرة النبوية</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 leading-relaxed category-desc">محطات من حياة النبي ﷺ بأسلوب قصصي تفاعلي.</p>
                    </div>
                    <div class="category-card bg-white dark:bg-darkCard p-5 rounded-[2.5rem] border dark:border-slate-700 shadow-sm group">
                        <div class="h-44 bg-blue-50 dark:bg-blue-900/20 rounded-[2rem] mb-6 flex items-center justify-center group-hover:scale-[0.98] transition-transform">
                            <div class="w-16 h-16 bg-white dark:bg-blue-800 rounded-2xl shadow-sm flex items-center justify-center"><i data-lucide="heart" class="w-8 h-8 text-blue-600 dark:text-blue-300"></i></div>
                        </div>
                        <h3 class="font-bold text-xl mb-3 dark:text-white category-title">تزكية النفس</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 leading-relaxed category-desc">دروس في الأخلاق والآداب لتهذيب الروح والقلب.</p>
                    </div>
                    <div class="category-card bg-white dark:bg-darkCard p-5 rounded-[2.5rem] border dark:border-slate-700 shadow-sm group">
                        <div class="h-44 bg-purple-50 dark:bg-purple-900/20 rounded-[2rem] mb-6 flex items-center justify-center group-hover:scale-[0.98] transition-transform">
                            <div class="w-16 h-16 bg-white dark:bg-purple-800 rounded-2xl shadow-sm flex items-center justify-center"><i data-lucide="shield-check" class="w-8 h-8 text-purple-600 dark:text-purple-300"></i></div>
                        </div>
                        <h3 class="font-bold text-xl mb-3 dark:text-white category-title">أصول العقيدة</h3>
                        <p class="text-sm text-slate-500 dark:text-slate-400 leading-relaxed category-desc">فهم أركان الإيمان والتوحيد بوضوح وبراهين ساطعة.</p>
                    </div>
                </div>
            </section>
        </div>

        <!-- Footer / Copyright Section -->
        <footer class="mt-auto px-6 lg:px-10 py-10 border-t dark:border-slate-700 bg-white dark:bg-darkCard transition-colors duration-300">
            <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
                <div class="flex items-center gap-3">
                    <img src="https://s3.filebin.net/filebin/38ea86c9ee42d700085864fc780a57d79957d69eca443616a10b37e4588db1b9/ef49fc095f7ad290adc5431ab7c527469cfd9f64b3e2da1e37dbffd880e98dae?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=7pMj6hGeoKewqmMQILjm%2F20251226%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251226T215556Z&X-Amz-Expires=60&X-Amz-SignedHeaders=host&response-cache-control=max-age%3D60&response-content-disposition=inline%3B%20filename%3D%22%D8%B4%D8%B9%D8%A7%D8%B1%20%D8%A3%D8%AE%D8%B6%D8%B1%20%D8%A3%D9%86%D9%8A%D9%82%20%D8%B9%D9%86%20%D9%85%D8%AA%D8%AC%D8%B1%20%D8%B9%D8%A8%D8%A7%D9%8A%D8%A7%D8%AA.png%22&response-content-type=image%2Fpng&X-Amz-Signature=2b540821df301ee9da03d05784b0ce788f2c4f6d79126663634135c2e1eb7847" alt="شعار منصة واد الرمان" class="platform-logo w-8 h-8 opacity-80 grayscale hover:grayscale-0 transition-all">
                    <span class="text-sm font-bold text-slate-500 dark:text-slate-400">© 2025 منصة واد الرمان</span>
                </div>
                
                <div class="flex items-center gap-2 text-sm text-slate-500 dark:text-slate-400">
                    <i data-lucide="code-2" class="w-4 h-4 text-teal-600"></i>
                    <span>تم التطوير بواسطة</span>
                    <span class="font-bold text-slate-800 dark:text-white bg-teal-50 dark:bg-teal-900/30 px-3 py-1 rounded-full border border-teal-100 dark:border-teal-800">شاوشي ابراهيم</span>
                </div>

                <div class="flex items-center gap-4">
                    <a href="#" class="p-2 bg-slate-100 dark:bg-slate-800 rounded-full hover:text-teal-600 transition-colors"><i data-lucide="facebook" class="w-4 h-4"></i></a>
                    <a href="#" class="p-2 bg-slate-100 dark:bg-slate-800 rounded-full hover:text-teal-400 transition-colors"><i data-lucide="twitter" class="w-4 h-4"></i></a>
                    <a href="#" class="p-2 bg-slate-100 dark:bg-slate-800 rounded-full hover:text-red-500 transition-colors"><i data-lucide="youtube" class="w-4 h-4"></i></a>
                </div>
            </div>
        </footer>

    </main>

    <!-- App Logic -->
    <script>
        const translations = {
            ar: {
                platform_name: "منصة واد الرمان",
                main_menu: "القائمة الرئيسية",
                home: "الرئيسية",
                lessons: "الدروس التعليمية",
                time_challenge: "تحدي الوقت",
                courses: "المسارات التعليمية",
                library: "المكتبة الشاملة",
                register: "تسجيل جديد",
                search_placeholder: "ابحث عن موضوع شرعي...",
                hero_badge: "✨ تعلّم بذكاء، عش بإيمان",
                hero_title: "رحلتك في تعلم العلوم الشرعية تبدأ هنا",
                hero_desc: "منصة تفاعلية تدمج بين أصالة المحتوى العلمي وأحدث تقنيات التعليم الرقمي لتبسيط العلوم الدينية للجميع.",
                start_btn: "ابدأ التعلم الآن",
                explore: "استكشف الأقسام",
                lang_label: "العربية",
                view_all: "عرض الكل",
                lessons_title: "أحدث الدروس",
                challenge_title: "تحدي الوقت الشرعي",
                challenge_desc: "اختبر معلوماتك الشرعية تحت الضغط! أجب على أكبر عدد من الأسئلة في 60 ثانية فقط واجمع النقاط.",
                new_feature: "ميزة جديدة"
            },
            en: {
                platform_name: "Wad El Roman Platform",
                main_menu: "Main Menu",
                home: "Home",
                lessons: "Educational Lessons",
                time_challenge: "Time Challenge",
                courses: "Courses",
                library: "Library",
                register: "Register",
                search_placeholder: "Search Islamic topics...",
                hero_badge: "✨ Learn Smart, Live Faith",
                hero_title: "Your Journey in Islamic Sciences Starts Here",
                hero_desc: "An interactive platform merging authentic content with modern tech to simplify religious education.",
                start_btn: "Start Now",
                explore: "Explore Categories",
                lang_label: "English",
                view_all: "View All",
                lessons_title: "Latest Lessons",
                challenge_title: "Islamic Time Challenge",
                challenge_desc: "Test your knowledge under pressure! Answer as many questions as you can in 60 seconds.",
                new_feature: "New Feature"
            }
        };

        function toggleLangDropdown() {
            document.getElementById('lang-menu').classList.toggle('active');
        }

        window.addEventListener('click', (e) => {
            if (!e.target.closest('.relative')) {
                const langMenu = document.getElementById('lang-menu');
                if (langMenu) langMenu.classList.remove('active');
            }
        });

        function changeLang(lang) {
            document.documentElement.lang = lang;
            document.documentElement.dir = lang === 'ar' ? 'rtl' : 'ltr';
            
            const sidebar = document.getElementById('main-sidebar');
            const main = document.querySelector('main');
            const isDesktop = window.innerWidth >= 1024;

            if (lang === 'ar') {
                sidebar.className = sidebar.className.replace('left-0 border-r', 'right-0 border-l');
                main.style.marginLeft = '0';
                main.style.marginRight = isDesktop ? '18rem' : '0';
            } else {
                sidebar.className = sidebar.className.replace('right-0 border-l', 'left-0 border-r');
                main.style.marginRight = '0';
                main.style.marginLeft = isDesktop ? '18rem' : '0';
            }

            const langLabel = document.getElementById('current-lang-label');
            if (langLabel) langLabel.innerText = translations[lang].lang_label;

            document.querySelectorAll('[data-t]').forEach(el => {
                const key = el.getAttribute('data-t');
                if (translations[lang][key]) el.innerText = translations[lang][key];
            });
            
            const viewAllBtn = document.getElementById('view-all-btn');
            if(viewAllBtn) viewAllBtn.innerText = translations[lang].view_all;

            document.querySelectorAll('[data-t-placeholder]').forEach(el => {
                const key = el.getAttribute('data-t-placeholder');
                if (translations[lang][key]) el.placeholder = translations[lang][key];
            });

            const langMenu = document.getElementById('lang-menu');
            if (langMenu) langMenu.classList.remove('active');
            localStorage.setItem('preferred_lang', lang);
        }

        function toggleDarkMode() {
            document.documentElement.classList.toggle('dark');
            const isDark = document.documentElement.classList.contains('dark');
            localStorage.setItem('theme', isDark ? 'dark' : 'light');
        }

        function initSearch() {
            const searchInput = document.getElementById('main-search-input');
            const cards = document.querySelectorAll('.category-card');
            const noResults = document.getElementById('no-results');
            const viewAllBtn = document.getElementById('view-all-btn');
            const heroSection = document.querySelector('section.p-6');
            const challengeSection = document.getElementById('challenge-section');
            const footer = document.querySelector('footer');

            if (!searchInput) return;

            searchInput.addEventListener('input', (e) => {
                const query = e.target.value.toLowerCase().trim();
                let hasMatches = false;

                if (query.length > 0) {
                    viewAllBtn.style.opacity = '0';
                    viewAllBtn.style.pointerEvents = 'none';
                    heroSection.style.display = 'none';
                    challengeSection.style.display = 'none';
                } else {
                    viewAllBtn.style.opacity = '1';
                    viewAllBtn.style.pointerEvents = 'auto';
                    heroSection.style.display = 'block';
                    challengeSection.style.display = 'block';
                }

                cards.forEach(card => {
                    const title = card.querySelector('.category-title').innerText.toLowerCase();
                    const desc = card.querySelector('.category-desc').innerText.toLowerCase();

                    if (title.includes(query) || desc.includes(query)) {
                        card.style.display = 'block';
                        hasMatches = true;
                    } else {
                        card.style.display = 'none';
                    }
                });

                if (hasMatches) {
                    noResults.classList.add('hidden');
                } else {
                    noResults.classList.remove('hidden');
                }
            });
        }

        window.onload = () => {
            lucide.createIcons();
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme === 'dark') document.documentElement.classList.add('dark');
            const savedLang = localStorage.getItem('preferred_lang') || 'ar';
            changeLang(savedLang);
            initSearch();
        };

        const mobileBtn = document.getElementById('mobile-menu-btn');
        const sidebar = document.getElementById('main-sidebar');
        const overlay = document.getElementById('sidebar-overlay');

        const toggleSidebar = () => {
            const isRTL = document.documentElement.dir === 'rtl';
            const hideClass = isRTL ? 'translate-x-full' : '-translate-x-full';
            sidebar.classList.toggle(hideClass);
            sidebar.classList.toggle('translate-x-0');
            overlay.classList.toggle('hidden');
        };

        if (mobileBtn) mobileBtn.onclick = toggleSidebar;
        if (overlay) overlay.onclick = toggleSidebar;
    </script>
</body>
</html>
