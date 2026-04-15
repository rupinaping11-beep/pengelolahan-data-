<!doctype html>
<html lang="id" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tarian Tradisional Kalimantan Timur</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Bubblegum+Sans&amp;family=Nunito:wght@400;600;700;800&amp;display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; }
    .font-bubble { font-family: 'Bubblegum Sans', cursive; }
    .font-nunito { font-family: 'Nunito', sans-serif; }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    @keyframes wiggle {
      0%, 100% { transform: rotate(-3deg); }
      50% { transform: rotate(3deg); }
    }
    @keyframes popIn {
      0% { transform: scale(0); opacity: 0; }
      70% { transform: scale(1.1); }
      100% { transform: scale(1); opacity: 1; }
    }
    @keyframes sparkle {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(1.3); }
    }
    @keyframes slideUp {
      from { transform: translateY(40px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }
    @keyframes danceBounce {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      25% { transform: translateY(-8px) rotate(5deg); }
      75% { transform: translateY(-8px) rotate(-5deg); }
    }
    .anim-float { animation: float 3s ease-in-out infinite; }
    .anim-wiggle { animation: wiggle 2s ease-in-out infinite; }
    .anim-pop { animation: popIn 0.5s ease-out forwards; }
    .anim-sparkle { animation: sparkle 2s ease-in-out infinite; }
    .anim-slide-up { animation: slideUp 0.6s ease-out forwards; }
    .anim-dance { animation: danceBounce 1.5s ease-in-out infinite; }

    .dance-card {
      transition: all 0.3s ease;
      cursor: pointer;
    }
    .dance-card:hover {
      transform: translateY(-6px) scale(1.02);
    }
    .tab-btn {
      transition: all 0.25s ease;
    }
    .tab-btn.active {
      transform: scale(1.05);
    }
    .quiz-option {
      transition: all 0.2s ease;
      cursor: pointer;
    }
    .quiz-option:hover {
      transform: scale(1.03);
    }

    .bg-pattern {
      background-image:
        radial-gradient(circle at 20% 80%, rgba(255,200,50,0.15) 0%, transparent 50%),
        radial-gradient(circle at 80% 20%, rgba(255,100,50,0.1) 0%, transparent 50%),
        radial-gradient(circle at 50% 50%, rgba(100,200,255,0.08) 0%, transparent 50%);
    }

    .confetti-piece {
      position: fixed;
      width: 10px;
      height: 10px;
      border-radius: 2px;
      pointer-events: none;
      z-index: 9999;
    }

    .scroll-wrapper {
      overflow-y: auto;
      overflow-x: hidden;
      -webkit-overflow-scrolling: touch;
    }
    .scroll-wrapper::-webkit-scrollbar { width: 6px; }
    .scroll-wrapper::-webkit-scrollbar-thumb { background: rgba(0,0,0,0.15); border-radius: 3px; }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full font-nunito">
  <div id="app" class="h-full w-full scroll-wrapper bg-pattern" style="background-color: #FFF8F0;"><!-- HEADER -->
   <header class="relative overflow-hidden" style="background: linear-gradient(135deg, #E8530E, #FF8C42);">
    <div class="absolute inset-0 opacity-10">
     <div class="absolute top-2 left-6 text-4xl anim-float">
      🌺
     </div>
     <div class="absolute top-4 right-10 text-3xl anim-float" style="animation-delay:0.5s;">
      🎭
     </div>
     <div class="absolute bottom-2 left-1/3 text-3xl anim-float" style="animation-delay:1s;">
      💃
     </div>
     <div class="absolute bottom-1 right-1/4 text-4xl anim-float" style="animation-delay:1.5s;">
      🪘
     </div>
    </div>
    <div class="relative px-4 py-5 text-center">
     <div class="text-4xl mb-1 anim-dance">
      💃🏽
     </div>
     <h1 id="app-title" class="font-bubble text-white text-2xl md:text-3xl drop-shadow-lg">Tarian Tradisional Kalimantan Timur</h1>
     <p id="welcome-text" class="text-orange-100 mt-1 text-sm md:text-base font-semibold">Ayo belajar tarian daerah kita! 🎉</p>
    </div>
    <svg viewbox="0 0 1200 40" class="w-full -mb-1" preserveaspectratio="none"><path d="M0,20 Q300,45 600,20 T1200,20 L1200,40 L0,40 Z" fill="#FFF8F0" />
    </svg>
   </header><!-- TABS -->
   <nav class="flex justify-center gap-2 px-3 py-3 flex-wrap"><button onclick="switchTab('belajar')" id="tab-belajar" class="tab-btn active px-4 py-2 rounded-full font-bold text-sm shadow-md" style="background:#E8530E; color:white;"> 📖 Belajar </button> <button onclick="switchTab('galeri')" id="tab-galeri" class="tab-btn px-4 py-2 rounded-full font-bold text-sm shadow-md" style="background:#FFF3E6; color:#E8530E;"> 🎨 Galeri </button> <button onclick="switchTab('kuis')" id="tab-kuis" class="tab-btn px-4 py-2 rounded-full font-bold text-sm shadow-md" style="background:#FFF3E6; color:#E8530E;"> 🧠 Kuis </button> <button onclick="switchTab('mewarnai')" id="tab-mewarnai" class="tab-btn px-4 py-2 rounded-full font-bold text-sm shadow-md" style="background:#FFF3E6; color:#E8530E;"> 🖍️ Mewarnai </button>
   </nav><!-- BELAJAR TAB -->
   <div id="page-belajar" class="px-3 pb-6">
    <div id="dance-list" class="grid grid-cols-1 sm:grid-cols-2 gap-4 max-w-3xl mx-auto"></div>
    <div id="dance-detail" class="hidden max-w-2xl mx-auto"></div>
   </div><!-- GALERI TAB -->
   <div id="page-galeri" class="hidden px-3 pb-6">
    <div class="max-w-3xl mx-auto">
     <h2 class="font-bubble text-xl text-center mb-4" style="color:#E8530E;">🎨 Galeri Tarian Kaltim</h2>
     <div id="galeri-grid" class="grid grid-cols-2 sm:grid-cols-3 gap-3"></div>
    </div>
   </div><!-- KUIS TAB -->
   <div id="page-kuis" class="hidden px-3 pb-6">
    <div class="max-w-xl mx-auto">
     <div id="quiz-container"></div>
    </div>
   </div><!-- MEWARNAI TAB -->
   <div id="page-mewarnai" class="hidden px-3 pb-6">
    <div class="max-w-xl mx-auto text-center">
     <h2 class="font-bubble text-xl mb-3" style="color:#E8530E;">🖍️ Mewarnai Penari</h2>
     <p class="text-sm mb-3" style="color:#7A4B2A;">Klik bagian penari untuk mewarnai! Pilih warna dulu ya~ 🎨</p>
     <div class="flex justify-center gap-2 mb-4 flex-wrap" id="color-palette"></div>
     <div class="bg-white rounded-2xl shadow-lg p-4 inline-block">
      <svg id="coloring-svg" viewbox="0 0 300 400" width="260" height="350" class="mx-auto"></svg>
     </div><button onclick="resetColoring()" class="mt-3 px-5 py-2 rounded-full font-bold text-sm text-white shadow-md" style="background:#E8530E;">🔄 Mulai Ulang</button>
    </div>
   </div><!-- FOOTER -->
   <footer class="text-center py-4 text-xs font-semibold" style="color:#C4916E;">
    <div class="text-lg mb-1">
     🌺💃🏽🪘🎭🌺
    </div> Seni Budaya Kelas 3 SD — Kalimantan Timur 🇮🇩
   </footer>
  </div>
  <script>
// ===== DATA =====
const dances = [
  {
    id: 'kancet-ledo',
    name: 'Tari Kancet Ledo',
    emoji: '💃🏽',
    icon: '🪶',
    origin: 'Suku Dayak Kenyah',
    meaning: 'Tarian kegembiraan dan keanggunan wanita Dayak',
    desc: 'Tari Kancet Ledo adalah tarian tradisional dari suku Dayak Kenyah. Tarian ini menggambarkan keanggunan dan kegembiraan seorang wanita. Penari memegang bulu burung Enggang sambil bergerak lembut dan anggun. Tarian ini biasa ditampilkan saat pesta adat dan penyambutan tamu.',
    moves: ['Gerakan tangan seperti burung terbang 🦅', 'Langkah kaki yang lembut dan pelan 🦶', 'Kepala menoleh ke kanan dan kiri 👤', 'Badan bergoyang perlahan 🌊'],
    costume: 'Pakaian adat Dayak dengan manik-manik warna-warni, topi bulu burung Enggang, dan gelang-gelang indah ✨',
    music: 'Diiringi alat musik Sape (sejenis gitar tradisional) 🎸',
    funFact: 'Bulu burung Enggang sangat sakral bagi suku Dayak! 🦜',
    colors: ['#D4543A', '#FFB74D', '#4CAF50', '#795548'],
    bgGradient: 'linear-gradient(135deg, #FFF5E6, #FFE8CC)'
  },
  {
    id: 'hudoq',
    name: 'Tari Hudoq',
    emoji: '🎭',
    icon: '🌾',
    origin: 'Suku Dayak Bahau & Modang',
    meaning: 'Tarian memohon kesuburan dan panen yang baik',
    desc: 'Tari Hudoq adalah tarian topeng yang sangat unik! Penari memakai topeng kayu besar yang menyerupai wajah dewa atau binatang. Tarian ini dilakukan untuk memohon kesuburan tanah dan hasil panen yang melimpah. Gerakan penari sangat energik dan semangat!',
    moves: ['Hentak kaki yang kuat 🦶💥', 'Gerakan tangan mengibas 🤚', 'Melompat-lompat penuh semangat 🏃', 'Berputar-putar di tempat 🌀'],
    costume: 'Topeng kayu besar berwarna-warni, baju dari kulit kayu, dan daun-daun pisang 🍃',
    music: 'Diiringi gendang dan teriakan semangat! 🪘',
    funFact: 'Topeng Hudoq bisa sebesar kepala orang dewasa! 😮',
    colors: ['#E65100', '#33691E', '#4E342E', '#F9A825'],
    bgGradient: 'linear-gradient(135deg, #F0F9E8, #E8F5E9)'
  },
  {
    id: 'belian',
    name: 'Tari Belian',
    emoji: '🌟',
    icon: '✨',
    origin: 'Suku Dayak Benuaq',
    meaning: 'Tarian penyembuhan dan pengobatan tradisional',
    desc: 'Tari Belian adalah tarian sakral untuk upacara penyembuhan. Seorang Belian (dukun/tabib) menari sambil membaca doa dan mantra. Tarian ini dipercaya dapat menyembuhkan orang yang sakit dan mengusir roh jahat. Gerakannya penuh mistis dan kekuatan!',
    moves: ['Gerakan memutar perlahan 🌀', 'Tangan mengayun seperti menghipnotis 🤲', 'Mata terpejam penuh konsentrasi 😌', 'Gerakan badan seperti gelombang 🌊'],
    costume: 'Pakaian putih dengan selendang warna-warni dan mahkota daun 🍃👑',
    music: 'Diiringi bunyi gong dan nyanyian mantra 🎶',
    funFact: 'Upacara Belian bisa berlangsung sampai 7 hari 7 malam! 🌙',
    colors: ['#6A1B9A', '#00695C', '#F57F17', '#FFFFFF'],
    bgGradient: 'linear-gradient(135deg, #F3E5F5, #E8EAF6)'
  },
  {
    id: 'gantar',
    name: 'Tari Gantar',
    emoji: '🌾',
    icon: '🎋',
    origin: 'Suku Dayak Tunjung & Benuaq',
    meaning: 'Tarian menanam padi dan bercocok tanam',
    desc: 'Tari Gantar menggambarkan kegiatan menanam padi di ladang. Penari memegang tongkat kayu panjang dan menghentakkannya ke tanah, seperti sedang menugal (membuat lubang untuk benih padi). Tarian ini penuh semangat dan kebersamaan!',
    moves: ['Menghentakkan tongkat ke lantai 🏑', 'Kaki melangkah maju mundur 🦶', 'Badan membungkuk seperti menanam 🌱', 'Bergerak bersama secara kompak 👥'],
    costume: 'Pakaian adat Dayak dengan kain tenun dan aksesoris manik-manik 📿',
    music: 'Bunyi tongkat yang berirama dan gendang 🥁',
    funFact: 'Tari Gantar biasa ditarikan bersama-sama oleh banyak orang! 👨‍👩‍👧‍👦',
    colors: ['#33691E', '#F57F17', '#795548', '#FF8F00'],
    bgGradient: 'linear-gradient(135deg, #FFFDE7, #F9FBE7)'
  }
];

const quizData = [
  { q: 'Tarian apa yang menggunakan bulu burung Enggang?', opts: ['Tari Hudoq', 'Tari Kancet Ledo', 'Tari Gantar', 'Tari Belian'], ans: 1, emoji: '🪶' },
  { q: 'Tari Hudoq menggunakan apa di wajah?', opts: ['Topi', 'Topeng kayu', 'Kacamata', 'Cat wajah'], ans: 1, emoji: '🎭' },
  { q: 'Tari Gantar menggambarkan kegiatan apa?', opts: ['Memancing', 'Berburu', 'Menanam padi', 'Memasak'], ans: 2, emoji: '🌾' },
  { q: 'Alat musik Sape mirip dengan alat musik apa?', opts: ['Drum', 'Piano', 'Gitar', 'Seruling'], ans: 2, emoji: '🎸' },
  { q: 'Tari Belian biasanya dilakukan untuk apa?', opts: ['Pesta ulang tahun', 'Penyembuhan', 'Olahraga', 'Memasak'], ans: 1, emoji: '🌟' },
  { q: 'Tari Kancet Ledo berasal dari suku apa?', opts: ['Dayak Kenyah', 'Dayak Bahau', 'Banjar', 'Kutai'], ans: 0, emoji: '💃🏽' },
  { q: 'Berapa lama upacara Belian bisa berlangsung?', opts: ['1 jam', '1 hari', '7 hari 7 malam', '1 bulan'], ans: 2, emoji: '🌙' },
  { q: 'Tari Gantar menggunakan alat apa saat menari?', opts: ['Payung', 'Tongkat kayu', 'Kipas', 'Pedang'], ans: 1, emoji: '🎋' },
];

const colorPalette = ['#E8530E','#FF8C42','#FFD54F','#4CAF50','#2196F3','#9C27B0','#E91E63','#795548','#FFFFFF','#333333'];

// ===== STATE =====
let currentTab = 'belajar';
let currentQuiz = 0;
let quizScore = 0;
let quizAnswered = false;
let selectedColor = '#E8530E';

// ===== DEFAULT CONFIG =====
const defaultConfig = {
  app_title: 'Tarian Tradisional Kalimantan Timur',
  welcome_text: 'Ayo belajar tarian daerah kita! 🎉',
  background_color: '#FFF8F0',
  surface_color: '#FFFFFF',
  text_color: '#5D3A1A',
  primary_action_color: '#E8530E',
  secondary_action_color: '#FF8C42',
  font_family: 'Nunito',
  font_size: 14
};

// ===== ELEMENT SDK =====
window.elementSdk.init({
  defaultConfig,
  onConfigChange: async (config) => {
    const c = key => config[key] || defaultConfig[key];
    const app = document.getElementById('app');
    app.style.backgroundColor = c('background_color');

    document.getElementById('app-title').textContent = c('app_title');
    document.getElementById('welcome-text').textContent = c('welcome_text');

    const font = c('font_family');
    const baseSize = c('font_size');
    app.style.fontFamily = `${font}, Nunito, sans-serif`;
    app.style.fontSize = `${baseSize}px`;
    app.style.color = c('text_color');

    document.querySelectorAll('.dance-card, .galeri-item, .quiz-box, #coloring-svg').forEach(el => {
      el.style.backgroundColor = c('surface_color');
    });

    document.querySelectorAll('.tab-btn.active').forEach(el => {
      el.style.backgroundColor = c('primary_action_color');
    });
    document.querySelectorAll('.tab-btn:not(.active)').forEach(el => {
      el.style.color = c('primary_action_color');
    });

    document.querySelectorAll('.primary-btn').forEach(el => {
      el.style.backgroundColor = c('primary_action_color');
    });
    document.querySelectorAll('.secondary-btn').forEach(el => {
      el.style.backgroundColor = c('secondary_action_color');
    });

    document.querySelectorAll('h2, .card-title').forEach(el => {
      el.style.color = c('primary_action_color');
    });

    document.querySelectorAll('.font-bubble').forEach(el => {
      el.style.fontSize = `${baseSize * 1.5}px`;
    });
  },
  mapToCapabilities: (config) => {
    const c = key => config[key] || defaultConfig[key];
    const mk = (key) => ({
      get: () => c(key),
      set: (v) => { config[key] = v; window.elementSdk.setConfig({ [key]: v }); }
    });
    return {
      recolorables: [
        mk('background_color'),
        mk('surface_color'),
        mk('text_color'),
        mk('primary_action_color'),
        mk('secondary_action_color')
      ],
      borderables: [],
      fontEditable: mk('font_family'),
      fontSizeable: mk('font_size')
    };
  },
  mapToEditPanelValues: (config) => new Map([
    ['app_title', config.app_title || defaultConfig.app_title],
    ['welcome_text', config.welcome_text || defaultConfig.welcome_text]
  ])
});

// ===== TAB SWITCHING =====
function switchTab(tab) {
  currentTab = tab;
  ['belajar','galeri','kuis','mewarnai'].forEach(t => {
    document.getElementById('page-' + t).classList.toggle('hidden', t !== tab);
    const btn = document.getElementById('tab-' + t);
    const isActive = t === tab;
    btn.classList.toggle('active', isActive);
    btn.style.backgroundColor = isActive ? '#E8530E' : '#FFF3E6';
    btn.style.color = isActive ? 'white' : '#E8530E';
  });
  if (tab === 'belajar') { showDanceList(); }
  if (tab === 'kuis') { renderQuiz(); }
  if (tab === 'galeri') { renderGaleri(); }
  if (tab === 'mewarnai') { renderColoring(); }
}

// ===== BELAJAR =====
function showDanceList() {
  document.getElementById('dance-detail').classList.add('hidden');
  const list = document.getElementById('dance-list');
  list.classList.remove('hidden');
  list.innerHTML = dances.map((d, i) => `
    <div class="dance-card rounded-2xl p-4 shadow-lg anim-slide-up" style="background:${d.bgGradient}; animation-delay:${i*0.1}s;" onclick="showDance('${d.id}')">
      <div class="text-center">
        <div class="text-5xl mb-2 anim-dance" style="animation-delay:${i*0.2}s;">${d.emoji}</div>
        <h3 class="font-bubble card-title text-lg" style="color:${d.colors[0]};">${d.name}</h3>
        <p class="text-xs mt-1 font-semibold" style="color:#7A4B2A;">${d.icon} ${d.origin}</p>
        <p class="text-xs mt-2" style="color:#9C7A5A;">${d.meaning}</p>
        <div class="mt-3 inline-block px-3 py-1 rounded-full text-xs font-bold text-white" style="background:${d.colors[0]};">
          Pelajari →
        </div>
      </div>
    </div>
  `).join('');
}

function showDance(id) {
  const d = dances.find(x => x.id === id);
  if (!d) return;
  document.getElementById('dance-list').classList.add('hidden');
  const detail = document.getElementById('dance-detail');
  detail.classList.remove('hidden');
  detail.innerHTML = `
    <div class="anim-slide-up">
      <button onclick="showDanceList()" class="mb-3 px-4 py-2 rounded-full font-bold text-sm text-white shadow-md primary-btn" style="background:#E8530E;">
        ← Kembali
      </button>
      <div class="rounded-2xl overflow-hidden shadow-xl" style="background:${d.bgGradient};">
        <div class="text-center py-6">
          <div class="text-6xl anim-dance mb-2">${d.emoji}</div>
          <h2 class="font-bubble text-2xl" style="color:${d.colors[0]};">${d.name}</h2>
          <p class="text-sm font-semibold mt-1" style="color:#7A4B2A;">${d.icon} ${d.origin}</p>
        </div>
        <div class="bg-white bg-opacity-80 p-4 space-y-4">
          <section>
            <h3 class="font-bold flex items-center gap-2" style="color:${d.colors[0]};"><span class="text-xl">📖</span> Tentang Tarian</h3>
            <p class="text-sm mt-1 leading-relaxed" style="color:#5D3A1A;">${d.desc}</p>
          </section>
          <section>
            <h3 class="font-bold flex items-center gap-2" style="color:${d.colors[0]};"><span class="text-xl">🕺</span> Gerakan Utama</h3>
            <ul class="mt-1 space-y-1">${d.moves.map(m => `<li class="text-sm pl-2" style="color:#5D3A1A;">• ${m}</li>`).join('')}</ul>
          </section>
          <section>
            <h3 class="font-bold flex items-center gap-2" style="color:${d.colors[0]};"><span class="text-xl">👗</span> Kostum</h3>
            <p class="text-sm mt-1" style="color:#5D3A1A;">${d.costume}</p>
          </section>
          <section>
            <h3 class="font-bold flex items-center gap-2" style="color:${d.colors[0]};"><span class="text-xl">🎵</span> Musik Pengiring</h3>
            <p class="text-sm mt-1" style="color:#5D3A1A;">${d.music}</p>
          </section>
          <div class="rounded-xl p-3 mt-2" style="background:linear-gradient(135deg, #FFF9C4, #FFECB3);">
            <p class="text-sm font-bold" style="color:#E65100;">💡 Tahukah Kamu?</p>
            <p class="text-sm mt-1" style="color:#5D3A1A;">${d.funFact}</p>
          </div>
        </div>
      </div>
    </div>
  `;
}

// ===== GALERI =====
function renderGaleri() {
  const items = [
    { emoji: '💃🏽', label: 'Penari Kancet Ledo', bg: '#FFCCBC' },
    { emoji: '🎭', label: 'Topeng Hudoq', bg: '#C8E6C9' },
    { emoji: '🪶', label: 'Bulu Enggang', bg: '#FFE0B2' },
    { emoji: '🎸', label: 'Alat Musik Sape', bg: '#BBDEFB' },
    { emoji: '🪘', label: 'Gendang Dayak', bg: '#E1BEE7' },
    { emoji: '📿', label: 'Manik-manik Dayak', bg: '#FFF9C4' },
    { emoji: '🌾', label: 'Menanam Padi', bg: '#DCEDC8' },
    { emoji: '👑', label: 'Mahkota Daun', bg: '#FFE0B2' },
    { emoji: '🏠', label: 'Lamin (Rumah Adat)', bg: '#D7CCC8' },
  ];
  document.getElementById('galeri-grid').innerHTML = items.map((it, i) => `
    <div class="galeri-item rounded-2xl p-4 text-center shadow-md anim-slide-up" style="background:${it.bg}; animation-delay:${i*0.08}s;">
      <div class="text-5xl mb-2 anim-float" style="animation-delay:${i*0.3}s;">${it.emoji}</div>
      <p class="text-xs font-bold" style="color:#5D3A1A;">${it.label}</p>
    </div>
  `).join('');
}

// ===== KUIS =====
function renderQuiz() {
  const container = document.getElementById('quiz-container');
  if (currentQuiz >= quizData.length) {
    const pct = Math.round(quizScore / quizData.length * 100);
    const star = pct >= 80 ? '🌟🏆🌟' : pct >= 50 ? '⭐👍' : '💪😊';
    container.innerHTML = `
      <div class="quiz-box bg-white rounded-2xl shadow-xl p-6 text-center anim-pop">
        <div class="text-5xl mb-3">${star}</div>
        <h2 class="font-bubble text-xl" style="color:#E8530E;">Kuis Selesai!</h2>
        <p class="text-3xl font-extrabold my-3" style="color:#E8530E;">${quizScore}/${quizData.length}</p>
        <p class="text-sm font-semibold" style="color:#7A4B2A;">${pct >= 80 ? 'Hebat sekali! Kamu pintar! 🎉' : pct >= 50 ? 'Bagus! Terus belajar ya! 📚' : 'Jangan menyerah! Coba lagi! 💪'}</p>
        <button onclick="resetQuiz()" class="mt-4 px-6 py-2 rounded-full font-bold text-white shadow-md primary-btn" style="background:#E8530E;">🔄 Coba Lagi</button>
      </div>
    `;
    if (pct >= 80) launchConfetti();
    return;
  }
  const qd = quizData[currentQuiz];
  quizAnswered = false;
  container.innerHTML = `
    <div class="quiz-box bg-white rounded-2xl shadow-xl p-5 anim-slide-up">
      <div class="flex justify-between items-center mb-3">
        <span class="text-xs font-bold px-3 py-1 rounded-full" style="background:#FFF3E6; color:#E8530E;">Soal ${currentQuiz+1}/${quizData.length}</span>
        <span class="text-xs font-bold" style="color:#E8530E;">⭐ ${quizScore}</span>
      </div>
      <div class="text-center mb-4">
        <div class="text-4xl mb-2">${qd.emoji}</div>
        <p class="font-bold text-base" style="color:#5D3A1A;">${qd.q}</p>
      </div>
      <div class="space-y-2" id="quiz-opts">
        ${qd.opts.map((o, i) => `
          <div class="quiz-option rounded-xl p-3 text-sm font-semibold border-2" style="border-color:#FFE0B2; background:#FFFAF0; color:#5D3A1A;" onclick="answerQuiz(${i})" id="opt-${i}">
            <span class="mr-2">${['🅰️','🅱️','©️','🅳'][i]}</span> ${o}
          </div>
        `).join('')}
      </div>
    </div>
  `;
}

function answerQuiz(idx) {
  if (quizAnswered) return;
  quizAnswered = true;
  const qd = quizData[currentQuiz];
  const correct = idx === qd.ans;
  if (correct) quizScore++;

  for (let i = 0; i < qd.opts.length; i++) {
    const el = document.getElementById('opt-' + i);
    if (i === qd.ans) {
      el.style.borderColor = '#4CAF50';
      el.style.background = '#E8F5E9';
      el.innerHTML = '✅ ' + qd.opts[i];
    } else if (i === idx && !correct) {
      el.style.borderColor = '#F44336';
      el.style.background = '#FFEBEE';
      el.innerHTML = '❌ ' + qd.opts[i];
    }
  }

  setTimeout(() => { currentQuiz++; renderQuiz(); }, 1200);
}

function resetQuiz() {
  currentQuiz = 0;
  quizScore = 0;
  renderQuiz();
}

// ===== MEWARNAI =====
function renderColoring() {
  const palette = document.getElementById('color-palette');
  palette.innerHTML = colorPalette.map(c => `
    <div class="w-8 h-8 rounded-full cursor-pointer border-2 shadow-sm" style="background:${c}; border-color:${selectedColor===c?'#333':'#ddd'};" onclick="pickColor('${c}')"></div>
  `).join('');

  const svg = document.getElementById('coloring-svg');
  svg.innerHTML = `
    <!-- Head -->
    <ellipse cx="150" cy="70" rx="40" ry="45" fill="#FFE0BD" stroke="#795548" stroke-width="2" class="colorable" data-part="head"/>
    <!-- Hair -->
    <path d="M110,55 Q120,15 150,20 Q180,15 190,55 Q185,35 150,30 Q115,35 110,55Z" fill="#333" stroke="#222" stroke-width="1.5" class="colorable" data-part="hair"/>
    <!-- Crown -->
    <path d="M115,48 L130,20 L145,40 L160,15 L175,40 L185,48" fill="#FFD54F" stroke="#F9A825" stroke-width="2" class="colorable" data-part="crown"/>
    <!-- Crown jewels -->
    <circle cx="150" cy="30" r="4" fill="#E91E63" class="colorable" data-part="jewel"/>
    <!-- Eyes -->
    <ellipse cx="137" cy="68" rx="5" ry="6" fill="white"/><circle cx="137" cy="69" r="3" fill="#333"/>
    <ellipse cx="163" cy="68" rx="5" ry="6" fill="white"/><circle cx="163" cy="69" r="3" fill="#333"/>
    <!-- Smile -->
    <path d="M140,82 Q150,92 160,82" fill="none" stroke="#795548" stroke-width="2" stroke-linecap="round"/>
    <!-- Neck -->
    <rect x="142" y="110" width="16" height="20" fill="#FFE0BD" rx="3"/>
    <!-- Body / Dress -->
    <path d="M105,130 Q110,125 150,125 Q190,125 195,130 L210,280 Q150,295 90,280 Z" fill="#E8530E" stroke="#C62828" stroke-width="2" class="colorable" data-part="dress"/>
    <!-- Dress pattern -->
    <path d="M120,180 L150,170 L180,180" fill="none" stroke="#FFD54F" stroke-width="2.5"/>
    <path d="M115,210 L150,200 L185,210" fill="none" stroke="#FFD54F" stroke-width="2.5"/>
    <path d="M110,240 L150,230 L190,240" fill="none" stroke="#FFD54F" stroke-width="2.5"/>
    <!-- Necklace -->
    <path d="M125,125 Q150,140 175,125" fill="none" stroke="#FFD54F" stroke-width="3" class="colorable" data-part="necklace"/>
    <!-- Beads on necklace -->
    <circle cx="133" cy="130" r="3" fill="#E91E63"/>
    <circle cx="150" cy="135" r="3" fill="#4CAF50"/>
    <circle cx="167" cy="130" r="3" fill="#2196F3"/>
    <!-- Left arm with feather -->
    <path d="M105,135 L60,200 L55,195" fill="none" stroke="#FFE0BD" stroke-width="10" stroke-linecap="round"/>
    <path d="M50,185 Q30,150 55,130 Q40,160 50,185Z" fill="#4CAF50" stroke="#2E7D32" stroke-width="1.5" class="colorable" data-part="feather-left"/>
    <!-- Right arm with feather -->
    <path d="M195,135 L240,200 L245,195" fill="none" stroke="#FFE0BD" stroke-width="10" stroke-linecap="round"/>
    <path d="M250,185 Q270,150 245,130 Q260,160 250,185Z" fill="#4CAF50" stroke="#2E7D32" stroke-width="1.5" class="colorable" data-part="feather-right"/>
    <!-- Hands -->
    <circle cx="55" cy="198" r="7" fill="#FFE0BD"/>
    <circle cx="245" cy="198" r="7" fill="#FFE0BD"/>
    <!-- Feet -->
    <ellipse cx="130" cy="290" rx="18" ry="8" fill="#795548" class="colorable" data-part="feet"/>
    <ellipse cx="170" cy="290" rx="18" ry="8" fill="#795548" class="colorable" data-part="feet2"/>
    <!-- Belt -->
    <rect x="100" y="170" width="100" height="8" rx="4" fill="#FFD54F" stroke="#F9A825" stroke-width="1" class="colorable" data-part="belt"/>
    <!-- Arm bracelets -->
    <rect x="68" y="165" width="14" height="6" rx="3" fill="#FFD54F" class="colorable" data-part="bracelet"/>
    <rect x="218" y="165" width="14" height="6" rx="3" fill="#FFD54F" class="colorable" data-part="bracelet2"/>
  `;

  svg.querySelectorAll('.colorable').forEach(el => {
    el.style.cursor = 'pointer';
    el.addEventListener('click', () => { el.setAttribute('fill', selectedColor); });
  });
}

function pickColor(c) {
  selectedColor = c;
  document.querySelectorAll('#color-palette > div').forEach(el => {
    el.style.borderColor = el.style.backgroundColor === c || rgbToHex(el.style.backgroundColor) === c ? '#333' : '#ddd';
  });
}

function rgbToHex(rgb) {
  if (rgb.startsWith('#')) return rgb;
  const m = rgb.match(/\d+/g);
  if (!m) return rgb;
  return '#' + m.slice(0,3).map(x => parseInt(x).toString(16).padStart(2,'0')).join('');
}

function resetColoring() {
  renderColoring();
}

// ===== CONFETTI =====
function launchConfetti() {
  const colors = ['#E8530E','#FFD54F','#4CAF50','#2196F3','#E91E63','#9C27B0'];
  for (let i = 0; i < 40; i++) {
    const el = document.createElement('div');
    el.className = 'confetti-piece';
    el.style.background = colors[Math.floor(Math.random()*colors.length)];
    el.style.left = Math.random()*100 + '%';
    el.style.top = '-10px';
    el.style.transform = `rotate(${Math.random()*360}deg)`;
    document.body.appendChild(el);
    const dur = 1500 + Math.random()*1500;
    el.animate([
      { top: '-10px', opacity: 1 },
      { top: '110%', opacity: 0 }
    ], { duration: dur, easing: 'ease-in' });
    setTimeout(() => el.remove(), dur);
  }
}

// ===== INIT =====
showDanceList();
lucide.createIcons();
</script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9ec7456c9362ea85',t:'MTc3NjIxNzUzMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
