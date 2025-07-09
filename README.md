<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>الفلاح الذكي - متجر الأدوات الزراعية في الجزائر</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#5D5CDE',
                        green: {
                            500: '#22c55e',
                            600: '#16a34a',
                            700: '#15803d'
                        }
                    },
                    fontFamily: {
                        arabic: ['Tahoma', 'Arial', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        body { font-family: 'Tahoma', Arial, sans-serif; }
        .product-card:hover { transform: translateY(-4px); }
        .cart-badge { 
            animation: pulse 0.5s;
            transform-origin: center;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body class="bg-gray-50 dark:bg-gray-900 text-gray-900 dark:text-gray-100 transition-colors duration-300">
    <!-- Header -->
    <header class="bg-white dark:bg-gray-800 shadow-lg sticky top-0 z-50">
        <div class="container mx-auto px-4 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-4 space-x-reverse">
                    <div class="bg-green-500 p-2 rounded-lg">
                        <i class="fas fa-seedling text-white text-xl"></i>
                    </div>
                    <h1 class="text-2xl font-bold text-green-600">الفلاح الذكي</h1>
                </div>
                
                <nav class="hidden md:flex space-x-6 space-x-reverse">
                    <a href="#home" class="hover:text-green-600 transition-colors">الرئيسية</a>
                    <a href="#products" class="hover:text-green-600 transition-colors">المنتجات</a>
                    <a href="#categories" class="hover:text-green-600 transition-colors">الأقسام</a>
                    <a href="#contact" class="hover:text-green-600 transition-colors">اتصل بنا</a>
                </nav>
                
                <div class="flex items-center space-x-4 space-x-reverse">
                    <button id="cartBtn" class="relative bg-primary text-white px-4 py-2 rounded-lg hover:bg-purple-700 transition-colors">
                        <i class="fas fa-shopping-cart"></i>
                        <span id="cartCount" class="absolute -top-2 -right-2 bg-red-500 text-white rounded-full text-xs w-5 h-5 flex items-center justify-center cart-badge hidden">0</span>
                    </button>
                    <button id="menuBtn" class="md:hidden">
                        <i class="fas fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="bg-gradient-to-r from-green-500 to-green-700 text-white py-20">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-4xl md:text-6xl font-bold mb-6">مرحباً بكم في الفلاح الذكي</h2>
            <p class="text-xl mb-8">جميع احتياجاتكم الزراعية في مكان واحد - أدوات، بذور، أسمدة ومعدات حديثة</p>
            <button onclick="scrollToSection('products')" class="bg-white text-green-600 px-8 py-3 rounded-lg font-bold hover:bg-gray-100 transition-colors">
                تسوق الآن
            </button>
        </div>
    </section>

    <!-- Categories -->
    <section id="categories" class="py-16">
        <div class="container mx-auto px-4">
            <h3 class="text-3xl font-bold text-center mb-12">أقسام المنتجات</h3>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="category-card bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition-shadow cursor-pointer" data-category="tools">
                    <i class="fas fa-tools text-4xl text-green-600 mb-4"></i>
                    <h4 class="font-bold text-lg">أدوات فلاحية</h4>
                    <p class="text-sm text-gray-600 dark:text-gray-400">مجارف، فؤوس، مناجل</p>
                </div>
                <div class="category-card bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition-shadow cursor-pointer" data-category="seeds">
                    <i class="fas fa-seedling text-4xl text-green-600 mb-4"></i>
                    <h4 class="font-bold text-lg">بذور ونباتات</h4>
                    <p class="text-sm text-gray-600 dark:text-gray-400">خضروات، فواكه، حبوب</p>
                </div>
                <div class="category-card bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition-shadow cursor-pointer" data-category="fertilizers">
                    <i class="fas fa-flask text-4xl text-green-600 mb-4"></i>
                    <h4 class="font-bold text-lg">أسمدة ومبيدات</h4>
                    <p class="text-sm text-gray-600 dark:text-gray-400">أسمدة عضوية وكيميائية</p>
                </div>
                <div class="category-card bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition-shadow cursor-pointer" data-category="machines">
                    <i class="fas fa-cog text-4xl text-green-600 mb-4"></i>
                    <h4 class="font-bold text-lg">معدات حديثة</h4>
                    <p class="text-sm text-gray-600 dark:text-gray-400">محاريث، مضخات، جرارات</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Products -->
    <section id="products" class="py-16 bg-gray-100 dark:bg-gray-800">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center mb-8">
                <h3 class="text-3xl font-bold">منتجاتنا المميزة</h3>
                <select id="categoryFilter" class="px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-700 text-base">
                    <option value="all">جميع المنتجات</option>
                    <option value="tools">أدوات فلاحية</option>
                    <option value="seeds">بذور ونباتات</option>
                    <option value="fertilizers">أسمدة ومبيدات</option>
                    <option value="machines">معدات حديثة</option>
                </select>
            </div>
            
            <div id="productsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                <!-- Products will be loaded here -->
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="py-16">
        <div class="container mx-auto px-4">
            <h3 class="text-3xl font-bold text-center mb-12">اتصل بنا</h3>
            <div class="grid md:grid-cols-2 gap-12">
                <div>
                    <h4 class="text-xl font-bold mb-6">معلومات الاتصال</h4>
                    <div class="space-y-4">
                        <div class="flex items-center space-x-3 space-x-reverse">
                            <i class="fas fa-phone text-green-600"></i>
                            <span>+213 555 123 456</span>
                        </div>
                        <div class="flex items-center space-x-3 space-x-reverse">
                            <i class="fas fa-envelope text-green-600"></i>
                            <span>info@smart-farmer.dz</span>
                        </div>
                        <div class="flex items-center space-x-3 space-x-reverse">
                            <i class="fas fa-map-marker-alt text-green-600"></i>
                            <span>الجزائر العاصمة، الجزائر</span>
                        </div>
                    </div>
                </div>
                <div>
                    <form id="contactForm" class="space-y-4">
                        <input type="text" placeholder="الاسم الكامل" class="w-full px-4 py-3 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-700 text-base">
                        <input type="tel" placeholder="رقم الهاتف" class="w-full px-4 py-3 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-700 text-base">
                        <textarea placeholder="رسالتك" rows="4" class="w-full px-4 py-3 rounded-lg border border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-700 text-base resize-none"></textarea>
                        <button type="submit" class="w-full bg-green-600 text-white py-3 rounded-lg hover:bg-green-700 transition-colors">
                            إرسال الرسالة
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-3 gap-8">
                <div>
                    <div class="flex items-center space-x-3 space-x-reverse mb-4">
                        <div class="bg-green-500 p-2 rounded-lg">
                            <i class="fas fa-seedling text-white"></i>
                        </div>
                        <h4 class="text-xl font-bold">الفلاح الذكي</h4>
                    </div>
                    <p class="text-gray-400">نحن نوفر أفضل الأدوات والمعدات الزراعية لمساعدة المزارعين الجزائريين في تحقيق أفضل النتائج.</p>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4">روابط سريعة</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#home" class="hover:text-white transition-colors">الرئيسية</a></li>
                        <li><a href="#products" class="hover:text-white transition-colors">المنتجات</a></li>
                        <li><a href="#categories" class="hover:text-white transition-colors">الأقسام</a></li>
                        <li><a href="#contact" class="hover:text-white transition-colors">اتصل بنا</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4">تابعنا</h4>
                    <div class="flex space-x-4 space-x-reverse">
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-facebook-f text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-instagram text-xl"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fab fa-whatsapp text-xl"></i>
                        </a>
                    </div>
                </div>
            </div>
            <div class="border-t border-gray-700 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 الفلاح الذكي. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <!-- Cart Modal -->
    <div id="cartModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden">
        <div class="flex items-center justify-center min-h-screen p-4">
            <div class="bg-white dark:bg-gray-800 rounded-lg max-w-lg w-full max-h-96 overflow-y-auto">
                <div class="p-6">
                    <div class="flex justify-between items-center mb-4">
                        <h3 class="text-xl font-bold">سلة التسوق</h3>
                        <button id="closeCart" class="text-gray-500 hover:text-gray-700">
                            <i class="fas fa-times text-xl"></i>
                        </button>
                    </div>
                    <div id="cartItems" class="space-y-4">
                        <!-- Cart items will be loaded here -->
                    </div>
                    <div id="cartTotal" class="mt-6 pt-4 border-t border-gray-200 dark:border-gray-600">
                        <div class="flex justify-between items-center font-bold text-lg">
                            <span>المجموع:</span>
                            <span id="totalAmount">0 دج</span>
                        </div>
                    </div>
                    <button id="checkoutBtn" class="w-full mt-4 bg-green-600 text-white py-3 rounded-lg hover:bg-green-700 transition-colors">
                        إتمام الطلب
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Dark mode support
        if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
            document.documentElement.classList.add('dark');
        }
        window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', event => {
            if (event.matches) {
                document.documentElement.classList.add('dark');
            } else {
                document.documentElement.classList.remove('dark');
            }
        });

        // Products data
        const products = [
            { id: 1, name: 'مجرفة كبيرة', category: 'tools', price: 2500, image: '🛠️', description: 'مجرفة قوية ومتينة للحفر والزراعة' },
            { id: 2, name: 'بذور طماطم', category: 'seeds', price: 800, image: '🍅', description: 'بذور طماطم عالية الجودة ومقاومة للأمراض' },
            { id: 3, name: 'سماد عضوي', category: 'fertilizers', price: 1200, image: '🌱', description: 'سماد طبيعي يحسن من جودة التربة' },
            { id: 4, name: 'مضخة مياه', category: 'machines', price: 25000, image: '💧', description: 'مضخة مياه قوية للري والزراعة' },
            { id: 5, name: 'منجل حصاد', category: 'tools', price: 1800, image: '⚔️', description: 'منجل حاد لحصاد المحاصيل' },
            { id: 6, name: 'بذور خيار', category: 'seeds', price: 600, image: '🥒', description: 'بذور خيار منتقاة للزراعة المحلية' },
            { id: 7, name: 'مبيد حشري', category: 'fertilizers', price: 1500, image: '🦟', description: 'مبيد آمن وفعال ضد الحشرات' },
            { id: 8, name: 'جرار صغير', category: 'machines', price: 180000, image: '🚜', description: 'جرار صغير مناسب للمزارع الصغيرة' },
            { id: 9, name: 'فأس زراعية', category: 'tools', price: 2200, image: '🪓', description: 'فأس قوية لتقليب التربة' },
            { id: 10, name: 'بذور قمح', category: 'seeds', price: 1000, image: '🌾', description: 'بذور قمح عالية الإنتاجية' },
            { id: 11, name: 'سماد NPK', category: 'fertilizers', price: 2000, image: '⚗️', description: 'سماد متوازن غني بالنيتروجين والفوسفور والبوتاسيوم' },
            { id: 12, name: 'آلة رش', category: 'machines', price: 8500, image: '💨', description: 'آلة رش محمولة للمبيدات والأسمدة السائلة' }
        ];

        let cart = [];
        let currentFilter = 'all';

        // DOM elements
        const productsGrid = document.getElementById('productsGrid');
        const categoryFilter = document.getElementById('categoryFilter');
        const cartBtn = document.getElementById('cartBtn');
        const cartModal = document.getElementById('cartModal');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartCount = document.getElementById('cartCount');
        const totalAmount = document.getElementById('totalAmount');
        const checkoutBtn = document.getElementById('checkoutBtn');

        // Functions
        function formatPrice(price) {
            return new Intl.NumberFormat('ar-DZ').format(price) + ' دج';
        }

        function renderProducts(productsToShow = products) {
            productsGrid.innerHTML = productsToShow.map(product => `
                <div class="product-card bg-white dark:bg-gray-700 rounded-lg shadow-lg overflow-hidden transition-transform duration-300 hover:shadow-xl">
                    <div class="p-6 text-center">
                        <div class="text-6xl mb-4">${product.image}</div>
                        <h4 class="font-bold text-lg mb-2">${product.name}</h4>
                        <p class="text-gray-600 dark:text-gray-400 text-sm mb-4">${product.description}</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xl font-bold text-green-600">${formatPrice(product.price)}</span>
                            <button onclick="addToCart(${product.id})" class="bg-primary text-white px-4 py-2 rounded-lg hover:bg-purple-700 transition-colors">
                                <i class="fas fa-cart-plus"></i>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function filterProducts(category) {
            currentFilter = category;
            const filtered = category === 'all' ? products : products.filter(p => p.category === category);
            renderProducts(filtered);
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }
            
            updateCartUI();
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartUI();
            renderCartItems();
        }

        function updateQuantity(productId, change) {
            const item = cart.find(item => item.id === productId);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(productId);
                    return;
                }
                updateCartUI();
                renderCartItems();
            }
        }

        function updateCartUI() {
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            if (totalItems > 0) {
                cartCount.textContent = totalItems;
                cartCount.classList.remove('hidden');
                cartCount.classList.add('cart-badge');
            } else {
                cartCount.classList.add('hidden');
            }
            
            totalAmount.textContent = formatPrice(total);
        }

        function renderCartItems() {
            if (cart.length === 0) {
                cartItems.innerHTML = '<p class="text-center text-gray-500 py-8">السلة فارغة</p>';
                return;
            }
            
            cartItems.innerHTML = cart.map(item => `
                <div class="flex items-center justify-between p-4 bg-gray-50 dark:bg-gray-700 rounded-lg">
                    <div class="flex items-center space-x-3 space-x-reverse">
                        <span class="text-2xl">${item.image}</span>
                        <div>
                            <h5 class="font-medium">${item.name}</h5>
                            <p class="text-sm text-gray-600 dark:text-gray-400">${formatPrice(item.price)}</p>
                        </div>
                    </div>
                    <div class="flex items-center space-x-2 space-x-reverse">
                        <button onclick="updateQuantity(${item.id}, -1)" class="bg-gray-300 dark:bg-gray-600 text-gray-700 dark:text-gray-300 w-8 h-8 rounded-full">-</button>
                        <span class="w-8 text-center">${item.quantity}</span>
                        <button onclick="updateQuantity(${item.id}, 1)" class="bg-gray-300 dark:bg-gray-600 text-gray-700 dark:text-gray-300 w-8 h-8 rounded-full">+</button>
                        <button onclick="removeFromCart(${item.id})" class="text-red-500 ml-2">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }

        function showCustomAlert(message) {
            const modal = document.createElement('div');
            modal.className = 'fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50';
            modal.innerHTML = `
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-lg max-w-sm w-full mx-4">
                    <div class="text-center">
                        <i class="fas fa-check-circle text-green-500 text-4xl mb-4"></i>
                        <p class="text-gray-700 dark:text-gray-300 mb-4">${message}</p>
                        <button class="px-6 py-2 bg-green-500 text-white hover:bg-green-600 rounded-lg" onclick="this.closest('.fixed').remove()">موافق</button>
                    </div>
                </div>
            `;
            document.body.appendChild(modal);
            setTimeout(() => modal.remove(), 3000);
        }

        // Event listeners
        categoryFilter.addEventListener('change', (e) => {
            filterProducts(e.target.value);
        });

        cartBtn.addEventListener('click', () => {
            cartModal.classList.remove('hidden');
            renderCartItems();
        });

        closeCart.addEventListener('click', () => {
            cartModal.classList.add('hidden');
        });

        cartModal.addEventListener('click', (e) => {
            if (e.target === cartModal) {
                cartModal.classList.add('hidden');
            }
        });

        checkoutBtn.addEventListener('click', () => {
            if (cart.length === 0) {
                showCustomAlert('السلة فارغة! يرجى إضافة منتجات قبل إتمام الطلب.');
                return;
            }
            
            const orderSummary = cart.map(item => `${item.name} x${item.quantity}`).join('\n');
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            showCustomAlert(`تم إرسال طلبكم بنجاح!\n\nالمنتجات:\n${orderSummary}\n\nالمجموع: ${formatPrice(total)}\n\nسنتصل بكم قريباً لتأكيد الطلب.`);
            
            cart = [];
            updateCartUI();
            cartModal.classList.add('hidden');
        });

        // Category cards click events
        document.querySelectorAll('.category-card').forEach(card => {
            card.addEventListener('click', () => {
                const category = card.dataset.category;
                categoryFilter.value = category;
                filterProducts(category);
                scrollToSection('products');
            });
        });

        // Contact form
        document.getElementById('contactForm').addEventListener('submit', (e) => {
            e.preventDefault();
            showCustomAlert('تم إرسال رسالتكم بنجاح! سنتواصل معكم قريباً.');
            e.target.reset();
        });

        // Initialize
        renderProducts();
        updateCartUI();
    </script>
</body>
</html># Agrico
