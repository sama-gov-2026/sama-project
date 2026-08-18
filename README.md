<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منظومة سيادة الأعمال الذكية</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700&display=swap');
        body { font-family: 'Tajawal', sans-serif; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col">

    <!-- الهيدر -->
    <header class="bg-emerald-800 text-white p-6 shadow-md flex justify-between items-center">
        <div>
            <h1 class="text-2xl font-bold">منظومة سيادة الأعمال الذكية</h1>
            <p class="text-emerald-200 text-sm mt-1">الحوكمة والتميز التشغيلي المدعوم بالذكاء الاصطناعي</p>
        </div>
        <span class="bg-emerald-700 text-emerald-100 text-xs px-3 py-1 rounded-full border border-emerald-600">الإصدار 1.0 - احترافي</span>
    </header>

    <!-- المحتوى الرئيسي -->
    <main class="flex-1 max-w-6xl w-full mx-auto p-4 md:p-8 grid grid-cols-1 md:grid-cols-3 gap-6">

        <!-- القسم الأول: مساعد السياسات -->
        <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 flex flex-col justify-between">
            <div>
                <div class="w-12 h-12 bg-emerald-100 text-emerald-800 rounded-xl flex items-center justify-center font-bold text-xl mb-4">⚖️</div>
                <h2 class="text-lg font-bold text-slate-900 mb-2">مساعد السياسات والحوكمة</h2>
                <p class="text-slate-600 text-sm leading-relaxed mb-4">البحث الفوري في اللوائح الداخلية والسياسات مع الاستشهاد بالمواد النظامية بدقة.</p>
            </div>
            <button onclick="openPolicyAssistant()" class="w-full bg-emerald-700 hover:bg-emerald-800 text-white py-2.5 rounded-xl text-sm font-medium transition duration-200">فتح المساعد الذكي</button>
        </div>

        <!-- القسم الثاني: إدارة المشاريع والتشغيل -->
        <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 flex flex-col justify-between">
            <div>
                <div class="w-12 h-12 bg-emerald-100 text-emerald-800 rounded-xl flex items-center justify-center font-bold text-xl mb-4">📊</div>
                <h2 class="text-lg font-bold text-slate-900 mb-2">مؤشرات الأداء والمشاريع</h2>
                <p class="text-slate-600 text-sm leading-relaxed mb-4">متابعة سير العمل، رصد المخاطر التشغيلية، واستخراج مؤشرات الأداء لحظياً.</p>
            </div>
            <button onclick="openDashboard()" class="w-full bg-emerald-700 hover:bg-emerald-800 text-white py-2.5 rounded-xl text-sm font-medium transition duration-200">استعراض اللوحة</button>
        </div>

        <!-- القسم الثالث: مركز المعرفة -->
        <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200 flex flex-col justify-between">
            <div>
                <div class="w-12 h-12 bg-emerald-100 text-emerald-800 rounded-xl flex items-center justify-center font-bold text-xl mb-4">🗄️</div>
                <h2 class="text-lg font-bold text-slate-900 mb-2">مركز التوثيق والمعرفة</h2>
                <p class="text-slate-600 text-sm leading-relaxed mb-4">أرشفة ذكية للمخرجات الإدارية والوثائق بآليات تصنيف تمنع الهدر وتضمن الامتثال.</p>
            </div>
            <button onclick="openVault()" class="w-full bg-emerald-700 hover:bg-emerald-800 text-white py-2.5 rounded-xl text-sm font-medium transition duration-200">دخول الأرشيف</button>
        </div>

    </main>

    <!-- نافذة تفاعلية تظهر عند الضغط -->
    <div id="modal" class="fixed inset-0 bg-black/50 hidden flex items-center justify-center p-4 z-50">
        <div class="bg-white w-full max-w-lg rounded-2xl p-6 shadow-xl flex flex-col max-h-[80vh]">
            <div class="flex justify-between items-center border-b pb-3 mb-4">
                <h3 id="modal-title" class="font-bold text-lg text-slate-900"></h3>
                <button onclick="closeModal()" class="text-slate-400 hover:text-slate-600 font-bold text-xl">✕</button>
            </div>
            <div id="modal-body" class="flex-1 overflow-y-auto space-y-3 text-sm text-slate-600">
                <!-- محتوى تفاعلي ديناميكي -->
            </div>
            <div class="mt-4 pt-3 border-t flex gap-2">
                <input type="text" id="user-input" placeholder="اكتب استفسارك هنا..." class="flex-1 border rounded-xl px-4 py-2 text-sm focus:outline-none focus:border-emerald-700">
                <button onclick="sendMessage()" class="bg-emerald-700 text-white px-4 py-2 rounded-xl text-sm font-medium">إرسال</button>
            </div>
        </div>
    </div>

    <!-- الفوتر -->
    <footer class="bg-white border-t border-slate-200 text-center py-4 text-slate-500 text-sm">
        جميع الحقوق محفوظة - منظومة سيادة الأعمال الذكية © 2026 | تصميم وتنفيذ: سما العنزي
    </footer>

    <script>
        const modal = document.getElementById('modal');
        const modalTitle = document.getElementById('modal-title');
        const modalBody = document.getElementById('modal-body');

        function openPolicyAssistant() {
            modalTitle.innerText = "مساعد السياسات والحوكمة الذكي";
            modalBody.innerHTML = `
                <div class="bg-emerald-50 p-3 rounded-xl text-emerald-900">مرحباً بكِ يا سما. أنا مساعد السياسات جاهز للرد على استفسارات اللوائح الداخلية والامتثال.</div>
                <div class="bg-slate-100 p-3 rounded-xl">مثال سؤالي: ما هي سياسة تضارب المصالح المعتمدة؟</div>
            `;
            modal.classList.remove('hidden');
        }

        function openDashboard() {
            modalTitle.innerText = "لوحة مؤشرات الأداء والتشغيل";
            modalBody.innerHTML = `
                <div class="space-y-3">
                    <div class="flex justify-between items-center bg-slate-50 p-3 rounded-xl"><span>نسبة إنجاز المشاريع الاستراتيجية</span><strong class="text-emerald-700">94%</strong></div>
                    <div class="flex justify-between items-center bg-slate-50 p-3 rounded-xl"><span>مؤشر الامتثال للسياسات الداخلية</span><strong class="text-emerald-700">98.5%</strong></div>
                    <div class="flex justify-between items-center bg-slate-50 p-3 rounded-xl"><span>المخاطر التشغيلية المرصودة</span><strong class="text-amber-600">منخفضة جداً (0.2%)</strong></div>
                </div>
            `;
            modal.classList.remove('hidden');
        }

        function openVault() {
            modalTitle.innerText = "مركز التوثيق والمعرفة الرقمي";
            modalBody.innerHTML = `
                <div class="space-y-2">
                    <div class="p-3 border rounded-xl flex justify-between items-center"><span>📁 دليل سياسات الحوكمة المؤسسية.pdf</span><span class="text-xs bg-emerald-100 text-emerald-800 px-2 py-1 rounded">معتمد</span></div>
                    <div class="p-3 border rounded-xl flex justify-between items-center"><span>📁 لائحة تنظيم العمل الداخلية.pdf</span><span class="text-xs bg-emerald-100 text-emerald-800 px-2 py-1 rounded">معتمد</span></div>
                </div>
            `;
            modal.classList.remove('hidden');
        }

        function closeModal() {
            modal.classList.add('hidden');
        }

        function sendMessage() {
            const input = document.getElementById('user-input');
            if(!input.value.trim()) return;
            modalBody.innerHTML += `<div class="bg-slate-100 p-3 rounded-xl text-left">${input.value}</div>`;
            const userMsg = input.value;
            input.value = '';
            setTimeout(() => {
                modalBody.innerHTML += `<div class="bg-emerald-50 p-3 rounded-xl text-emerald-900">بناءً على لوائح الحوكمة المعتمدة في المنظومة، الإجابة على "${userMsg}" تخضع للمادة 14 من سياسات الامتثال التشغيلي.</div>`;
                modalBody.scrollTop = modalBody.scrollHeight;
            }, 1000);
        }
    </script>
</body>
</html>
