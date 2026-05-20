<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Iksan Kas - Keuangan Jajan Cilok & Baso</title>
    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Fonts: Poppins -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: #f1f5f9;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* APP CONTAINER */
        .app-container {
            max-width: 1400px;
            width: 100%;
            background: #ffffff;
            border-radius: 32px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            overflow: hidden;
            transition: all 0.2s ease;
        }

        /* HEADER with cilok/baso vibe */
        .header {
            background: linear-gradient(135deg, #F97316, #EA580C);
            padding: 1.2rem 2rem;
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 12px;
        }

        .logo-area h1 {
            font-size: 1.7rem;
            font-weight: 700;
            letter-spacing: -0.3px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-area h1 i {
            font-size: 2rem;
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.2));
        }

        .logo-area p {
            font-size: 0.8rem;
            opacity: 0.9;
            margin-top: 4px;
        }

        .user-badge {
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(4px);
            padding: 8px 18px;
            border-radius: 40px;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* LAYOUT: sidebar + main */
        .dashboard-layout {
            display: flex;
            flex-wrap: wrap;
        }

        /* SIDEBAR */
        .sidebar {
            width: 280px;
            background: #fff9f5;
            border-right: 1px solid #ffeadb;
            padding: 2rem 1rem;
            transition: all 0.2s;
        }

        .nav-section {
            margin-bottom: 2rem;
        }

        .nav-title {
            text-transform: uppercase;
            font-size: 0.7rem;
            font-weight: 700;
            letter-spacing: 1px;
            color: #b45309;
            margin-bottom: 1rem;
            padding-left: 0.8rem;
        }

        .nav-item {
            display: flex;
            align-items: center;
            gap: 14px;
            padding: 0.75rem 1rem;
            margin: 4px 0;
            border-radius: 60px;
            color: #431407;
            font-weight: 500;
            cursor: pointer;
            transition: 0.2s;
        }

        .nav-item i {
            width: 24px;
            font-size: 1.2rem;
            color: #ea580c;
        }

        .nav-item.active {
            background: #ffedd5;
            color: #c2410c;
            font-weight: 600;
        }

        .nav-item:not(.active):hover {
            background: #fff1e6;
        }

        /* MAIN CONTENT */
        .main-content {
            flex: 1;
            background: #fefcf9;
            padding: 1.8rem 2rem;
        }

        /* page title */
        .page-title {
            font-size: 1.8rem;
            font-weight: 700;
            color: #2c1a0e;
            border-left: 6px solid #f97316;
            padding-left: 1rem;
            margin-bottom: 1.8rem;
        }

        /* card style */
        .card {
            background: white;
            border-radius: 24px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
            margin-bottom: 2rem;
            border: 1px solid #ffe2cc;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            margin-bottom: 1.2rem;
            border-bottom: 2px dashed #ffd7b5;
            padding-bottom: 0.75rem;
        }

        .card-header h3 {
            font-weight: 700;
            color: #7c2d12;
        }

        .btn {
            border: none;
            background: #f97316;
            color: white;
            padding: 8px 18px;
            border-radius: 40px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
        }

        .btn-outline {
            background: transparent;
            border: 1px solid #f97316;
            color: #f97316;
        }

        .btn-outline:hover {
            background: #f97316;
            color: white;
        }

        .btn-sm {
            padding: 5px 12px;
            font-size: 0.75rem;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            text-align: left;
            padding: 12px 8px;
            border-bottom: 1px solid #f0e2d6;
        }

        th {
            color: #9a3412;
            font-weight: 600;
            background: #fff5ec;
        }

        .badge {
            background: #eef2ff;
            padding: 4px 12px;
            border-radius: 30px;
            font-size: 0.7rem;
            font-weight: 600;
        }

        .badge-income {
            background: #d1fae5;
            color: #065f46;
        }

        .badge-expense {
            background: #fee2e2;
            color: #b91c1c;
        }

        .text-right {
            text-align: right;
        }

        .total-recap {
            background: #fffbeb;
            border-radius: 24px;
            padding: 1.2rem;
            margin-top: 1rem;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 16px;
        }

        .total-card {
            flex: 1;
            background: white;
            border-radius: 20px;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .form-group {
            margin-bottom: 1rem;
        }

        label {
            font-weight: 500;
            color: #431407;
            display: block;
            margin-bottom: 6px;
        }

        input, select {
            width: 100%;
            padding: 10px 14px;
            border: 1px solid #fed7aa;
            border-radius: 40px;
            background: #fffaf5;
            outline: none;
        }

        input:focus, select:focus {
            border-color: #f97316;
        }

        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .action-icons i {
            margin: 0 6px;
            cursor: pointer;
            color: #a85520;
        }

        @media (max-width: 800px) {
            .sidebar {
                width: 100%;
                border-right: none;
                border-bottom: 1px solid #ffe2cc;
                padding: 1rem;
            }
            .nav-item {
                display: inline-flex;
                width: auto;
            }
            .nav-section {
                display: flex;
                flex-wrap: wrap;
                gap: 8px;
            }
            .main-content {
                padding: 1.2rem;
            }
            .grid-2 {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
<div class="app-container" id="app">
    <div class="header">
        <div class="logo-area">
            <h1><i class="fas fa-bowl-food"></i> Iksan Kas <i class="fas fa-cart-shopping"></i></h1>
            <p>Manajemen Jajan • Cilok • Baso • Cemilan fav</p>
        </div>
        <div class="user-badge">
            <i class="fas fa-user-circle"></i> <span id="currentUserDisplay">Admin (Iksan)</span>
        </div>
    </div>
    <div class="dashboard-layout">
        <!-- SIDEBAR MENU -->
        <div class="sidebar">
            <div class="nav-section">
                <div class="nav-title"><i class="fas fa-chart-line"></i> DASHBOARD</div>
                <div class="nav-item" data-page="dashboard">
                    <i class="fas fa-tachometer-alt"></i> <span>Dashboard</span>
                </div>
            </div>
            <div class="nav-section">
                <div class="nav-title"><i class="fas fa-exchange-alt"></i> TRANSAKSI</div>
                <div class="nav-item" data-page="pemasukan">
                    <i class="fas fa-arrow-down"></i> <span>Pemasukan (Duit Jajan)</span>
                </div>
                <div class="nav-item" data-page="pengeluaran">
                    <i class="fas fa-arrow-up"></i> <span>Pengeluaran (Beli Cilok/Baso)</span>
                </div>
            </div>
            <div class="nav-section">
                <div class="nav-title"><i class="fas fa-tags"></i> REFERENSI</div>
                <div class="nav-item" data-page="kategori">
                    <i class="fas fa-list-ul"></i> <span>Kategori Jajanan</span>
                </div>
            </div>
            <div class="nav-section">
                <div class="nav-title"><i class="fas fa-chart-pie"></i> LAPORAN</div>
                <div class="nav-item" data-page="laporan-pemasukan">
                    <i class="fas fa-coins"></i> <span>Lap. Pemasukan</span>
                </div>
                <div class="nav-item" data-page="laporan-pengeluaran">
                    <i class="fas fa-receipt"></i> <span>Lap. Pengeluaran</span>
                </div>
                <div class="nav-item" data-page="laporan-rekap">
                    <i class="fas fa-chart-simple"></i> <span>Rekapitulasi</span>
                </div>
            </div>
            <div class="nav-section">
                <div class="nav-title"><i class="fas fa-users-cog"></i> PENGATURAN</div>
                <div class="nav-item" data-page="manajemen-user">
                    <i class="fas fa-user-shield"></i> <span>Manajemen User</span>
                </div>
            </div>
        </div>

        <!-- MAIN CONTENT DYNAMIC -->
        <div class="main-content" id="mainContent">
            <!-- dinamis oleh JS -->
            <div style="text-align: center; padding: 40px;">Memuat data keuangan cilok & baso...</div>
        </div>
    </div>
</div>

<script>
    // ---------- DATA STORE (LocalStorage) ----------
    // Data transaksi & kategori & user
    let transactions = [];     // {id, type: 'income'/'expense', amount, category, description, date}
    let categories = [];      // {id, name, type: 'income'/'expense'}
    let users = [];           // {id, name, username, role: 'Admin'/'User'}

    // Inisialisasi data awal (demo jajan cilok/baso)
    function initData() {
        const storedTrans = localStorage.getItem('iksan_transactions');
        const storedCats = localStorage.getItem('iksan_categories');
        const storedUsers = localStorage.getItem('iksan_users');

        if(storedTrans) transactions = JSON.parse(storedTrans);
        else {
            transactions = [
                {id: 1, type: 'income', amount: 50000, category: 'Uang Jajan', description: 'Dari Ibu', date: '2025-05-18'},
                {id: 2, type: 'expense', amount: 12000, category: 'Cilok', description: 'Cilok get + saos', date: '2025-05-19'},
                {id: 3, type: 'expense', amount: 15000, category: 'Baso', description: 'Baso tahu + mie', date: '2025-05-20'},
                {id: 4, type: 'income', amount: 30000, category: 'THR jajan', description: 'Dari kakek', date: '2025-05-20'},
                {id: 5, type: 'expense', amount: 8000, category: 'Cilok', description: 'cilok aci', date: '2025-05-21'},
            ];
        }

        if(storedCats) categories = JSON.parse(storedCats);
        else {
            categories = [
                {id: 1, name: 'Uang Jajan', type: 'income'},
                {id: 2, name: 'THR', type: 'income'},
                {id: 3, name: 'Cilok', type: 'expense'},
                {id: 4, name: 'Baso', type: 'expense'},
                {id: 5, name: 'Es Teh', type: 'expense'},
                {id: 6, name: 'Lainnya', type: 'expense'},
            ];
        }

        if(storedUsers) users = JSON.parse(storedUsers);
        else {
            users = [
                {id: 1, name: 'Iksan', username: 'iksan', role: 'Admin'},
                {id: 2, name: 'Test User', username: 'test', role: 'User'},
                {id: 3, name: 'User Biasa', username: 'user', role: 'User'},
            ];
        }
        saveToLocal();
    }

    function saveToLocal() {
        localStorage.setItem('iksan_transactions', JSON.stringify(transactions));
        localStorage.setItem('iksan_categories', JSON.stringify(categories));
        localStorage.setItem('iksan_users', JSON.stringify(users));
    }

    // helper ambil kategori berdasarkan type
    function getCategoriesByType(type) {
        return categories.filter(c => c.type === type);
    }

    // format rupiah
    function formatRupiah(amount) {
        return 'Rp ' + amount.toLocaleString('id-ID');
    }

    // ========== RENDER DINAMIS ==========
    let currentPage = 'dashboard';

    function render() {
        const contentDiv = document.getElementById('mainContent');
        if(currentPage === 'dashboard') renderDashboard(contentDiv);
        else if(currentPage === 'pemasukan') renderTransaksi(contentDiv, 'income');
        else if(currentPage === 'pengeluaran') renderTransaksi(contentDiv, 'expense');
        else if(currentPage === 'kategori') renderKategori(contentDiv);
        else if(currentPage === 'laporan-pemasukan') renderLaporan(contentDiv, 'income');
        else if(currentPage === 'laporan-pengeluaran') renderLaporan(contentDiv, 'expense');
        else if(currentPage === 'laporan-rekap') renderRekap(contentDiv);
        else if(currentPage === 'manajemen-user') renderManajemenUser(contentDiv);
    }

    // DASHBOARD (ringkasan + stat jajan cilok/baso)
    function renderDashboard(container) {
        const totalIncome = transactions.filter(t => t.type === 'income').reduce((s, t) => s + t.amount, 0);
        const totalExpense = transactions.filter(t => t.type === 'expense').reduce((s, t) => s + t.amount, 0);
        const balance = totalIncome - totalExpense;
        const expenseCilok = transactions.filter(t => t.type === 'expense' && (t.category === 'Cilok')).reduce((s,t) => s+t.amount,0);
        const expenseBaso = transactions.filter(t => t.type === 'expense' && (t.category === 'Baso')).reduce((s,t) => s+t.amount,0);
        
        container.innerHTML = `
            <div class="page-title"><i class="fas fa-chart-line"></i> Dashboard Jajan Cilok & Baso</div>
            <div class="card">
                <div class="card-header"><h3>💰 Ringkasan Kas Iksan</h3></div>
                <div class="total-recap">
                    <div class="total-card"><i class="fas fa-hand-holding-usd"></i> <h4>Total Pemasukan</h4><p style="font-size:1.8rem; font-weight:800; color:#15803d;">${formatRupiah(totalIncome)}</p></div>
                    <div class="total-card"><i class="fas fa-shopping-cart"></i> <h4>Total Pengeluaran</h4><p style="font-size:1.8rem; font-weight:800; color:#b91c1c;">${formatRupiah(totalExpense)}</p></div>
                    <div class="total-card"><i class="fas fa-wallet"></i> <h4>Sisa Uang Jajan</h4><p style="font-size:1.8rem; font-weight:800; color:#f97316;">${formatRupiah(balance)}</p></div>
                </div>
            </div>
            <div class="card">
                <div class="card-header"><h3><i class="fas fa-utensils"></i> Statistik Jajan Favorit</h3></div>
                <div style="display:flex; gap:20px; flex-wrap:wrap;">
                    <div style="background:#fff1e6; border-radius:1.5rem; padding:1rem; flex:1; text-align:center;"><i class="fas fa-circle-notch fa-2x" style="color:#ea580c"></i><h4>🍢 Cilok</h4><p style="font-size:1.5rem; font-weight:bold;">${formatRupiah(expenseCilok)}</p></div>
                    <div style="background:#fff1e6; border-radius:1.5rem; padding:1rem; flex:1; text-align:center;"><i class="fas fa-egg fa-2x" style="color:#b45309"></i><h4>🍜 Baso</h4><p style="font-size:1.5rem; font-weight:bold;">${formatRupiah(expenseBaso)}</p></div>
                    <div style="background:#fff1e6; border-radius:1.5rem; padding:1rem; flex:1; text-align:center;"><i class="fas fa-chart-simple"></i><h4>Total Belanja Jajan</h4><p>${formatRupiah(totalExpense)}</p></div>
                </div>
                <p style="margin-top:16px; font-size:13px;"><i class="fas fa-info-circle"></i> Selalu catat setiap jajan cilok & baso agar keuangan tetap sehat!</p>
            </div>
            <div class="card"><div class="card-header"><h3>📋 Transaksi Terbaru</h3></div>
            <table><thead><tr><th>Tanggal</th><th>Kategori</th><th>Deskripsi</th><th>Jumlah</th><th>Tipe</th></tr></thead><tbody>
            ${transactions.slice().reverse().slice(0,5).map(t => `<tr><td>${t.date}</td><td>${t.category}</td><td>${t.description}</td><td class="${t.type === 'income' ? 'text-right' : 'text-right'}">${formatRupiah(t.amount)}</td><td><span class="badge ${t.type === 'income' ? 'badge-income' : 'badge-expense'}">${t.type === 'income' ? 'Pemasukan' : 'Pengeluaran'}</span></td></tr>`).join('')}
            ${transactions.length === 0 ? '<tr><td colspan="5">Belum ada transaksi jajan</td></tr>' : ''}
            </tbody></table></div>
        `;
    }

    // Form transaksi (pemasukan/pengeluaran)
    function renderTransaksi(container, type) {
        const title = type === 'income' ? '📥 Pemasukan (Uang Jajan)' : '📤 Pengeluaran (Beli Cilok/Baso)';
        const transList = transactions.filter(t => t.type === type);
        const catOptions = getCategoriesByType(type).map(c => `<option value="${c.name}">${c.name}</option>`).join('');
        container.innerHTML = `
            <div class="page-title">${title}</div>
            <div class="card">
                <div class="card-header"><h3><i class="fas fa-plus-circle"></i> Tambah Transaksi</h3></div>
                <form id="transForm">
                    <div class="grid-2">
                        <div class="form-group"><label>Nominal (Rp)</label><input type="number" id="amount" required placeholder="cth: 15000"></div>
                        <div class="form-group"><label>Kategori</label><select id="category">${catOptions}</select></div>
                        <div class="form-group"><label>Deskripsi</label><input type="text" id="desc" placeholder="Jajan cilok/sate/dll"></div>
                        <div class="form-group"><label>Tanggal</label><input type="date" id="date" value="${new Date().toISOString().slice(0,10)}"></div>
                    </div>
                    <button type="submit" class="btn"><i class="fas fa-save"></i> Simpan Transaksi</button>
                </form>
            </div>
            <div class="card"><div class="card-header"><h3>📋 Daftar ${type === 'income' ? 'Pemasukan' : 'Pengeluaran'}</h3></div>
            <table><thead><tr><th>Tgl</th><th>Kategori</th><th>Deskripsi</th><th>Jumlah</th><th>Aksi</th></tr></thead><tbody>
            ${transList.map(t => `<tr><td>${t.date}</td><td>${t.category}</td><td>${t.description}</td><td class="text-right">${formatRupiah(t.amount)}</td><td class="action-icons"><i class="fas fa-trash-alt" data-id="${t.id}" data-type="trans" style="color:#e07c3e;"></i></td></tr>`).join('')}
            ${transList.length === 0 ? '<tr><td colspan="5">Belum ada data</td></tr>' : ''}
            </tbody></table></div>
        `;
        document.getElementById('transForm')?.addEventListener('submit', (e) => {
            e.preventDefault();
            const amount = parseInt(document.getElementById('amount').value);
            const category = document.getElementById('category').value;
            const description = document.getElementById('desc').value || '-';
            const date = document.getElementById('date').value;
            if(isNaN(amount) || amount<=0) return alert("Masukkan nominal valid!");
            const newId = Date.now();
            transactions.push({id: newId, type, amount, category, description, date});
            saveToLocal();
            render();
        });
        attachDeleteEvents();
    }

    function renderKategori(container) {
        container.innerHTML = `
            <div class="page-title"><i class="fas fa-tags"></i> Kategori Jajanan & Pemasukan</div>
            <div class="card"><div class="card-header"><h3>Tambah Kategori Baru</h3></div>
            <form id="catForm"><div class="grid-2"><div class="form-group"><label>Nama Kategori</label><input id="catName" required placeholder="Contoh: Cilok Spesial"></div>
            <div class="form-group"><label>Tipe</label><select id="catType"><option value="expense">Pengeluaran (Jajan)</option><option value="income">Pemasukan</option></select></div></div>
            <button class="btn" type="submit"><i class="fas fa-plus"></i> Tambah</button></form></div>
            <div class="card"><h3>📌 Daftar Kategori</h3><table><thead><tr><th>Nama</th><th>Tipe</th><th>Aksi</th></tr></thead><tbody>
            ${categories.map(c => `<tr><td>${c.name}</td><td>${c.type === 'income' ? 'Pemasukan' : 'Pengeluaran (Jajan)'}</td><td class="action-icons"><i class="fas fa-trash-alt" data-id="${c.id}" data-type="cat"></i></td></tr>`).join('')}
            </tbody></table></div>
        `;
        document.getElementById('catForm')?.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('catName').value.trim();
            const type = document.getElementById('catType').value;
            if(!name) return;
            const newId = Date.now();
            categories.push({id: newId, name, type});
            saveToLocal();
            render();
        });
        attachDeleteEvents();
    }

    function renderLaporan(container, type) {
        const filtered = transactions.filter(t => t.type === type);
        const total = filtered.reduce((s,t)=>s+t.amount,0);
        container.innerHTML = `
            <div class="page-title">📄 Laporan ${type === 'income' ? 'Pemasukan' : 'Pengeluaran Jajan'}</div>
            <div class="card"><div class="card-header"><h3>Total ${type === 'income' ? 'Pemasukan' : 'Pengeluaran'}: ${formatRupiah(total)}</h3></div>
            <table><thead><tr><th>Tgl</th><th>Kategori</th><th>Deskripsi</th><th>Jumlah</th></tr></thead><tbody>
            ${filtered.map(t => `<tr><td>${t.date}</td><td>${t.category}</td><td>${t.description}</td><td class="text-right">${formatRupiah(t.amount)}</td></tr>`).join('')}
            </tbody></table></div>
        `;
    }

    function renderRekap(container) {
        const totalIncome = transactions.filter(t=>t.type==='income').reduce((s,t)=>s+t.amount,0);
        const totalExpense = transactions.filter(t=>t.type==='expense').reduce((s,t)=>s+t.amount,0);
        const groupedExpense = {};
        transactions.filter(t=>t.type==='expense').forEach(t=>{ groupedExpense[t.category] = (groupedExpense[t.category]||0) + t.amount; });
        container.innerHTML = `
            <div class="page-title">📊 Rekapitulasi Keuangan Jajan</div>
            <div class="card"><div class="card-header"><h3>Ringkasan Keseluruhan</h3></div>
            <p><strong>Total Pemasukan (Uang Jajan):</strong> ${formatRupiah(totalIncome)}</p>
            <p><strong>Total Pengeluaran (Jajan Cilok/Baso dll):</strong> ${formatRupiah(totalExpense)}</p>
            <p><strong>Sisa Tabungan Jajan:</strong> ${formatRupiah(totalIncome - totalExpense)}</p>
            <hr><h4>Rincian Pengeluaran per Kategori (Cilok/Baso favorit)</h4><ul>${Object.entries(groupedExpense).map(([k,v])=>`<li>🍽️ ${k} : ${formatRupiah(v)}</li>`).join('')}</ul>
            </div>
        `;
    }

    function renderManajemenUser(container) {
        container.innerHTML = `
            <div class="page-title"><i class="fas fa-users"></i> Manajemen User</div>
            <div class="card"><div class="card-header"><h3>Tambah User Baru</h3></div>
            <form id="userForm"><div class="grid-2"><div class="form-group"><label>Nama Lengkap</label><input id="userName" required></div>
            <div class="form-group"><label>Username</label><input id="userUsername" required></div></div>
            <div class="form-group"><label>Hak Akses</label><select id="userRole"><option>User</option><option>Admin</option></select></div>
            <button class="btn" type="submit">Tambah User</button></form></div>
            <div class="card"><h3>📋 Data User</h3><table><thead><tr><th>No</th><th>Nama User</th><th>Username</th><th>Hak Akses</th><th>Aksi</th></tr></thead><tbody>
            ${users.map((u,idx) => `<tr><td>${idx+1}</td><td>${u.name}</td><td>${u.username}</td><td>${u.role}</td><td class="action-icons"><i class="fas fa-trash-alt" data-id="${u.id}" data-type="user"></i></td></tr>`).join('')}
            </tbody></table><div>Menampilkan 1 sampai ${users.length} dari ${users.length} data</div></div>
        `;
        document.getElementById('userForm')?.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('userName').value.trim();
            const username = document.getElementById('userUsername').value.trim();
            const role = document.getElementById('userRole').value;
            if(!name || !username) return alert("Lengkapi data");
            const newId = Date.now();
            users.push({id: newId, name, username, role});
            saveToLocal();
            render();
        });
        attachDeleteEvents();
    }

    function attachDeleteEvents() {
        document.querySelectorAll('.action-icons i.fa-trash-alt').forEach(icon => {
            icon.removeEventListener('click', handleDelete);
            icon.addEventListener('click', handleDelete);
        });
    }
    function handleDelete(e) {
        const target = e.currentTarget;
        const id = parseInt(target.getAttribute('data-id'));
        const type = target.getAttribute('data-type');
        if(type === 'trans') {
            transactions = transactions.filter(t => t.id !== id);
            saveToLocal();
            render();
        } else if(type === 'cat') {
            categories = categories.filter(c => c.id !== id);
            saveToLocal();
            render();
        } else if(type === 'user') {
            users = users.filter(u => u.id !== id);
            saveToLocal();
            render();
        }
    }

    // Event menu sidebar
    function setupNavigation() {
        document.querySelectorAll('.nav-item').forEach(item => {
            item.addEventListener('click', (e) => {
                const page = item.getAttribute('data-page');
                if(page) {
                    currentPage = page;
                    document.querySelectorAll('.nav-item').forEach(nav => nav.classList.remove('active'));
                    item.classList.add('active');
                    render();
                }
            });
        });
    }

    initData();
    setupNavigation();
    render();
</script>
</body>
</html>
