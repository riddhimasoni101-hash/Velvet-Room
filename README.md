# Velvet-Room

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Velvet Room | Beauty • Style • Elegance</title>

<style>
:root {
  --plum: #4B2145;
  --plum2: #63345C;
  --pink: #C7A0C2;
  --pink2: #DCC4D9;
  --pale: #F0E2ED;
  --bg: #F5EBDD;
  --ink: #302030;
  --muted: #756775;
  --line: #E6D9E2;
  --white: #FFFCF7;
  --green: #347451;
  --red: #9A414D;
  --shadow: 0 8px 24px #3020300d;
  --surface: #FFFCF7;
  --hover: #F3E7F0;
  color-scheme: light;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Arial, sans-serif;
  background: var(--bg);
  color: var(--ink);
}

button, input, select, textarea { font: inherit; }
button { cursor: pointer; }
.app { min-height: 100vh; }

.sidebar {
  position: fixed;
  inset: 0 auto 0 0;
  width: 230px;
  background: linear-gradient(180deg, #4B2145, #381832);
  color: var(--white);
  padding: 22px 14px;
  display: flex;
  flex-direction: column;
  z-index: 5;
}

.brand {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 0 5px 28px;
}

.brand-mark { font-size: 32px; }
.brand strong { display: block; font-size: 20px; }
.brand small { color: #E8D7E5; font-size: 11px; }

.nav { display: grid; gap: 7px; }

.nav button {
  border: 0;
  color: #F9F0F7;
  background: transparent;
  text-align: left;
  padding: 13px 14px;
  border-radius: 10px;
  display: flex;
  gap: 12px;
  align-items: center;
  font-weight: 600;
  transition: .18s ease;
}

.nav button span {
  width: 20px;
  text-align: center;
  font-size: 18px;
}

.nav button:hover,
.nav button.active {
  background: var(--pink);
  color: var(--ink);
}

.nav button:hover { transform: translateX(2px); }
.sidebar-bottom { margin-top: auto; }

.main {
  margin-left: 230px;
  min-height: 100vh;
}

.topbar {
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 0 26px;
  background: var(--white);
  border-bottom: 1px solid var(--line);
  position: sticky;
  top: 0;
  z-index: 4;
}

.search { max-width: 430px; width: 100%; position: relative; }

.search input {
  width: 100%;
  border: 1px solid var(--line);
  border-radius: 12px;
  padding: 11px 14px 11px 40px;
  background: var(--white);
  color: var(--ink);
}

.search span {
  position: absolute;
  left: 14px;
  top: 9px;
  color: var(--muted);
}

.admin { font-weight: 650; font-size: 13px; }
.mobile-menu { display: none; }

.content {
  padding: 25px;
  max-width: 1600px;
  margin: auto;
}

.page { display: none; }
.page.active { display: block; }

.page-heading {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 15px;
  margin-bottom: 22px;
}

.page-heading h1 {
  font-size: 26px;
  margin: 0 0 5px;
  color: var(--ink);
}

.page-heading p {
  margin: 0;
  color: var(--muted);
  font-size: 14px;
}

.stats {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 15px;
  margin-bottom: 20px;
}

.stat, .panel, .form-card {
  background: var(--white);
  border: 1px solid var(--line);
  border-radius: 14px;
  box-shadow: var(--shadow);
}

.stat { padding: 19px; }

.stat-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: var(--muted);
  font-size: 13px;
}

.stat-icon {
  width: 38px;
  height: 38px;
  display: grid;
  place-items: center;
  background: var(--pale);
  border-radius: 11px;
  font-size: 19px;
}

.stat strong {
  display: block;
  font-size: 27px;
  margin: 13px 0 4px;
  color: var(--plum);
}

.stat small { color: var(--muted); }

.grid2 {
  display: grid;
  grid-template-columns: minmax(0, 1.3fr) minmax(280px, 1fr);
  gap: 18px;
}

.panel {
  padding: 20px;
  margin-bottom: 18px;
  min-width: 0;
}

.panel h2 {
  font-size: 17px;
  margin: 0 0 5px;
  color: var(--plum);
}

.sub {
  font-size: 12px;
  color: var(--muted);
  margin: 0 0 17px;
}

.btn {
  border: 1px solid var(--line);
  border-radius: 9px;
  padding: 10px 14px;
  background: var(--white);
  color: var(--ink);
  font-weight: 650;
  font-size: 13px;
  transition: .18s ease;
}

.btn:hover {
  background: var(--hover);
  border-color: var(--pink);
  box-shadow: 0 3px 10px #4B214510;
}

.btn.primary {
  background: var(--pink);
  color: var(--ink);
  border-color: var(--pink);
}

.btn.primary:hover {
  background: #D6B5D2;
  border-color: #D6B5D2;
}

.btn.danger { color: var(--red); }
.btn.small { padding: 6px 9px; font-size: 12px; }

.actions {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.field-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 15px;
}

.field { display: grid; gap: 7px; }
.field.full { grid-column: 1 / -1; }

.field label {
  font-size: 12px;
  font-weight: 700;
  color: var(--plum);
}

.field input, .field select, .field textarea {
  width: 100%;
  border: 1px solid #DCCED9;
  border-radius: 8px;
  padding: 11px 12px;
  background: var(--white);
  color: var(--ink);
  min-width: 0;
}

.field input:focus, .field select:focus, .field textarea:focus {
  border-color: var(--pink);
  box-shadow: 0 0 0 3px #C7A0C222;
  outline: none;
}

.field textarea { resize: vertical; min-height: 75px; }
.required { color: #A65C98; }

.form-actions {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  margin-top: 20px;
}

.toolbar {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 15px;
}

.toolbar input, .toolbar select {
  border: 1px solid var(--line);
  border-radius: 9px;
  padding: 10px 12px;
  background: var(--white);
  color: var(--ink);
}

.toolbar input { flex: 1; min-width: 190px; }

.table-wrap { overflow: auto; }

table {
  border-collapse: collapse;
  width: 100%;
  font-size: 13px;
  white-space: nowrap;
}

th, td {
  padding: 12px 10px;
  text-align: left;
  border-bottom: 1px solid var(--line);
}

th {
  font-size: 11px;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: .4px;
  background: #F6EDF4;
}

tbody tr:hover { background: #F8F0F6; }

.pill {
  display: inline-block;
  padding: 5px 8px;
  border-radius: 20px;
  font-size: 11px;
  font-weight: 700;
  background: var(--pale);
  color: var(--plum2);
}

.pill.good { background: #E4F0E7; color: var(--green); }
.pill.warn { background: #F7EBD2; color: #80601D; }
.pill.bad { background: #F6E3E7; color: var(--red); }

.empty { text-align: center; padding: 28px; color: var(--muted); }

.category-list { display: grid; gap: 10px; }

.category-row {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  border: 1px solid var(--line);
  border-radius: 10px;
}

.category-emoji {
  width: 43px;
  height: 43px;
  display: grid;
  place-items: center;
  background: var(--pale);
  border-radius: 10px;
  font-size: 22px;
}

.category-row strong { display: block; font-size: 13px; color: var(--plum); }
.category-row small { color: var(--muted); font-size: 11px; }
.category-row .count { margin-left: auto; font-weight: 750; }

.notice {
  padding: 12px 14px;
  border-radius: 10px;
  background: #F6EDF4;
  border: 1px solid #E5D1E2;
  color: #593451;
  font-size: 13px;
  margin-bottom: 16px;
}

.bar-row {
  display: grid;
  grid-template-columns: 130px 1fr 40px;
  gap: 10px;
  align-items: center;
  margin: 14px 0;
  font-size: 12px;
}

.bar {
  height: 9px;
  background: var(--pale);
  border-radius: 9px;
  overflow: hidden;
}

.bar i {
  height: 100%;
  display: block;
  background: linear-gradient(90deg, #9C7197, var(--pink));
  border-radius: 9px;
}

.footer {
  color: var(--muted);
  font-size: 11px;
  border-top: 1px solid var(--line);
  padding: 17px 0 4px;
  display: flex;
  justify-content: space-between;
  gap: 12px;
}

.settings-grid {
  display: grid;
  grid-template-columns: minmax(0, 600px);
  gap: 18px;
}

.hint { font-size: 12px; color: var(--muted); line-height: 1.6; }

.toast {
  position: fixed;
  right: 22px;
  bottom: 22px;
  background: var(--plum);
  color: var(--white);
  padding: 13px 17px;
  border-radius: 10px;
  box-shadow: var(--shadow);
  z-index: 20;
  display: none;
}

.toast.show { display: block; }
.receipt {
  background: #F9F0F7;
  border: 1px dashed var(--pink);
  border-radius: 10px;
  padding: 14px;
  margin-top: 15px;
}
.hidden { display: none !important; }

@media(max-width: 1050px) {
  .stats { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .grid2 { grid-template-columns: 1fr; }
}

@media(max-width: 700px) {
  .sidebar { width: 76px; padding: 16px 9px; }
  .brand { justify-content: center; padding-bottom: 24px; }
  .brand-copy, .nav-label { display: none; }
  .nav button { justify-content: center; padding: 13px 8px; }
  .main { margin-left: 76px; }
  .topbar { padding: 0 12px; height: 62px; }
  .content { padding: 14px; }
  .stats { gap: 9px; }
  .stat { padding: 13px; }
  .field-grid { grid-template-columns: 1fr; }
  .field.full { grid-column: auto; }
  .panel { padding: 14px; }
  .footer { flex-direction: column; }
  .page-heading { flex-direction: column; }
}

@media(max-width: 420px) {
  .stats { grid-template-columns: 1fr 1fr; }
  .admin { display: none; }
  .toolbar input, .toolbar select { min-width: 100%; width: 100%; }
}
</style>
</head>

<body>
<div class="app">

<aside class="sidebar">
  <div class="brand">
    <div class="brand-mark">🌸</div>
    <div class="brand-copy">
      <strong>Velvet <span style="color:#C7A0C2">Room</span></strong>
      <small>Beauty • Style • Elegance</small>
    </div>
  </div>

  <nav class="nav" id="mainNav">
    <button class="active" data-page="dashboard">⌂ Dashboard</button>
    <button data-page="inventory">▣ Inventory</button>
    <button data-page="sales">🛒 Sales</button>
    <button data-page="reports">▥ Reports</button>
    <button data-page="settings">⚙ Settings</button>
  </nav>

  <div class="sidebar-bottom nav">
    <button id="resetDemo">↻ Reset demo data</button>
  </div>
</aside>

<main class="main">
<header class="topbar">
  <div class="search">
    <span>⌕</span>
    <input id="globalSearch" placeholder="Search products...">
  </div>
  <div class="admin">◉ <span id="adminShopName">Admin</span></div>
</header>

<div class="content">

<section class="page active" id="page-dashboard">
  <div class="page-heading">
    <div>
      <h1>Welcome to Velvet Room ✨</h1>
      <p>Here’s what’s happening in your shop today.</p>
    </div>
    <button class="btn primary" data-go="inventory">＋ Add Product</button>
  </div>

  <div class="stats">
    <div class="stat"><div class="stat-top">Total Products</div><strong id="statProducts">0</strong><small>Unique items</small></div>
    <div class="stat"><div class="stat-top">Units in Stock</div><strong id="statUnits">0</strong><small>Across categories</small></div>
    <div class="stat"><div class="stat-top">Low Stock Items</div><strong id="statLow">0</strong><small>Restocking alerts</small></div>
    <div class="stat"><div class="stat-top">Sales Recorded</div><strong id="statSales">₹0</strong><small id="statSalesCount">0 transactions</small></div>
  </div>

  <div class="grid2">
    <div class="panel">
      <h2>Recent Inventory</h2><p class="sub">Your latest products</p>
      <div class="table-wrap">
        <table><thead><tr><th>Product</th><th>Category</th><th>Qty</th><th>Status</th></tr></thead><tbody id="recentTable"></tbody></table>
      </div>
    </div>
    <div class="panel">
      <h2>Product Categories</h2><p class="sub">Your shop range</p>
      <div class="category-list" id="dashCategories"></div>
    </div>
  </div>

  <div class="panel">
    <h2>Low Stock Alerts</h2><p class="sub">Products that may need restocking</p>
    <div id="lowAlerts"></div>
  </div>
</section>

<section class="page" id="page-inventory">
  <div class="page-heading">
    <div><h1>Inventory Management</h1><p>Add products and manage your stock.</p></div>
    <button class="btn primary" id="newProductBtn">＋ Add Product</button>
  </div>

  <div class="grid2">
    <div class="panel" id="productFormCard">
      <h2 id="formTitle">＋ Add Product</h2><p class="sub">Enter product details.</p>
      <form id="productForm">
        <input type="hidden" id="editId">
        <div class="field-grid">
          <div class="field"><label>Product Name *</label><input id="productName" required></div>
          <div class="field"><label>Category *</label><select id="category" required><option value="">Select</option><option>Cosmetics</option><option>Hair Accessories</option><option>Jewellery</option><option>Beauty & Personal Care</option><option>Other</option></select></div>
          <div class="field"><label>Brand</label><input id="brand"></div>
          <div class="field"><label>Unit</label><select id="unit"><option>Piece</option><option>Pack</option><option>Pair</option><option>Set</option><option>Bottle</option><option>Box</option></select></div>
          <div class="field"><label>Quantity *</label><input id="quantity" type="number" min="0" value="1" required></div>
          <div class="field"><label>Low Stock Threshold *</label><input id="threshold" type="number" min="0" value="5" required></div>
          <div class="field"><label>Purchase Price (₹)</label><input id="purchasePrice" type="number" min="0" value="0"></div>
          <div class="field"><label>Selling Price (₹) *</label><input id="sellingPrice" type="number" min="0" required></div>
          <div class="field"><label>Expiry Date</label><input id="expiryDate" type="date"></div>
          <div class="field"><label>Storage Location</label><input id="location"></div>
          <div class="field full"><label>Description</label><textarea id="description"></textarea></div>
        </div>
        <div class="form-actions">
          <button class="btn" type="reset" id="clearForm">Reset</button>
          <div class="actions">
            <button class="btn hidden" type="button" id="cancelEdit">Cancel</button>
            <button class="btn primary" type="submit" id="saveProduct">Save Product</button>
          </div>
        </div>
      </form>
    </div>

    <div class="panel">
      <h2>Inventory Tips</h2>
      <p class="hint">♡ Update quantities after each sale.<br><br>♡ Set a low-stock threshold.<br><br>♡ Add expiry dates where needed.</p>
    </div>
  </div>

  <div class="panel">
    <h2>All Products</h2><p class="sub">Search, filter, edit or remove products.</p>
    <div class="toolbar">
      <input id="inventorySearch" placeholder="Search products...">
      <select id="categoryFilter"><option value="">All categories</option><option>Cosmetics</option><option>Hair Accessories</option><option>Jewellery</option><option>Beauty & Personal Care</option><option>Other</option></select>
      <select id="stockFilter"><option value="">All stock levels</option><option value="low">Low stock</option><option value="in">In stock</option><option value="out">Out of stock</option></select>
    </div>
    <div class="table-wrap">
      <table><thead><tr><th>Product</th><th>Category</th><th>Brand</th><th>Qty</th><th>Cost</th><th>Price</th><th>Status</th><th>Actions</th></tr></thead><tbody id="inventoryTable"></tbody></table>
    </div>
  </div>
</section>

<section class="page" id="page-sales">
  <div class="page-heading"><div><h1>Sales</h1><p>Record sales and update stock automatically.</p></div></div>
  <div class="grid2">
    <div class="panel">
      <h2>＋ Record a Sale</h2><p class="sub">Choose a product and quantity.</p>
      <form id="saleForm">
        <div class="field-grid">
          <div class="field full"><label>Product *</label><select id="saleProduct" required><option value="">Select product</option></select></div>
          <div class="field"><label>Quantity *</label><input id="saleQty" type="number" min="1" value="1" required></div>
          <div class="field"><label>Unit Price (₹)</label><input id="salePrice" readonly></div>
          <div class="field full"><label>Customer</label><input id="customer"></div>
        </div>
        <div class="receipt"><div>Sale total: <strong id="saleTotal">₹0.00</strong></div><p class="hint" id="saleAvailability">Select a product.</p></div>
        <div class="form-actions"><button class="btn" type="reset">Reset</button><button class="btn primary" type="submit">Complete Sale</button></div>
      </form>
    </div>
    <div class="panel">
      <h2>Sales at a glance</h2>
      <div class="stats" style="grid-template-columns:1fr 1fr">
        <div class="stat"><div class="stat-top">Revenue</div><strong id="salesRevenue">₹0</strong></div>
        <div class="stat"><div class="stat-top">Transactions</div><strong id="salesTransactions">0</strong></div>
      </div>
    </div>
  </div>
  <div class="panel">
    <h2>Sales History</h2>
    <div class="table-wrap"><table><thead><tr><th>Date</th><th>Product</th><th>Qty</th><th>Unit Price</th><th>Total</th><th>Customer</th></tr></thead><tbody id="salesTable"></tbody></table></div>
  </div>
</section>

<section class="page" id="page-reports">
  <div class="page-heading"><div><h1>Reports & Insights</h1><p>Review inventory and sales performance.</p></div><div class="actions"><button class="btn" id="exportInventory">Export Inventory CSV</button><button class="btn primary" id="exportSales">Export Sales CSV</button></div></div>
  <div class="stats">
    <div class="stat"><div class="stat-top">Inventory Cost</div><strong id="reportCost">₹0</strong></div>
    <div class="stat"><div class="stat-top">Retail Value</div><strong id="reportRetail">₹0</strong></div>
    <div class="stat"><div class="stat-top">Estimated Margin</div><strong id="reportMargin">₹0</strong></div>
    <div class="stat"><div class="stat-top">Units Sold</div><strong id="reportUnitsSold">0</strong></div>
  </div>
  <div class="grid2">
    <div class="panel"><h2>Inventory by Category</h2><div id="categoryBars"></div></div>
    <div class="panel"><h2>Expiry Review</h2><div id="expiryReview"></div></div>
  </div>
  <div class="panel"><h2>Stock Report</h2><div class="table-wrap"><table><thead><tr><th>Product</th><th>Category</th><th>Quantity</th><th>Threshold</th><th>Stock Value</th><th>Status</th></tr></thead><tbody id="stockReport"></tbody></table></div></div>
</section>

<section class="page" id="page-settings">
  <div class="page-heading"><div><h1>Settings</h1><p>Personalize your shop dashboard.</p></div></div>
  <div class="settings-grid">
    <div class="panel">
      <h2>Shop Information</h2>
      <form id="settingsForm">
        <div class="field-grid">
          <div class="field full"><label>Shop Name</label><input id="shopName" value="Velvet Room"></div>
          <div class="field"><label>Currency</label><select id="currency"><option value="INR">Indian Rupee (₹)</option></select></div>
          <div class="field"><label>Manager Name</label><input id="managerName" value="Admin"></div>
        </div>
        <div class="form-actions"><span></span><button class="btn primary" type="submit">Save Settings</button></div>
      </form>
    </div>
    <div class="panel">
      <h2>Data & Privacy</h2>
      <p class="hint">Products and sales are saved in this browser's local storage.</p>
      <div class="actions"><button class="btn" id="backupAll">Export full backup (JSON)</button><button class="btn danger" id="clearAll">Clear all shop data</button></div>
    </div>
  </div>
</section>

<div class="footer"><span>Velvet Room © <span id="year"></span> | Beauty • Style • Elegance</span><span>A little luxury in every detail. ✦</span></div>
</div>
</main>
</div>

<div class="toast" id="toast" role="status"></div>

<script>
(() => {
"use strict";

const KEY = "velvetroom_inventory_v1";
const CATEGORIES = ["Cosmetics","Hair Accessories","Jewellery","Beauty & Personal Care","Other"];
const EMOJI = {
  "Cosmetics":"💄",
  "Hair Accessories":"🎀",
  "Jewellery":"💍",
  "Beauty & Personal Care":"🧴",
  "Other":"✨"
};

const $ = id => document.getElementById(id);

let state = {
  products: [],
  sales: [],
  settings: {
    shopName: "Velvet Room",
    managerName: "Admin",
    currency: "INR"
  }
};

const money = n => "₹" + Number(n || 0).toLocaleString("en-IN", {
  minimumFractionDigits: 2,
  maximumFractionDigits: 2
});

const esc = s => String(s ?? "").replace(/[&<>"']/g, c => ({
  "&":"&amp;",
  "<":"&lt;",
  ">":"&gt;",
  '"':"&quot;",
  "'":"&#39;"
}[c]));

function toast(message) {
  $("toast").textContent = message;
  $("toast").classList.add("show");
  clearTimeout(toast.timer);
  toast.timer = setTimeout(() => $("toast").classList.remove("show"), 2600);
}

function save() {
  try {
    localStorage.setItem(KEY, JSON.stringify(state));
  } catch (error) {
    toast("Could not save data. Browser storage may be disabled.");
  }
}

function load() {
  try {
    const raw = localStorage.getItem(KEY);
    if (raw) {
      const data = JSON.parse(raw);
      if (data && Array.isArray(data.products) && Array.isArray(data.sales)) {
        state = {
          products: data.products,
          sales: data.sales,
          settings: { ...state.settings, ...data.settings }
        };
      }
    }
  } catch (error) {
    console.warn("Could not load saved data", error);
  }
}

function status(product) {
  if (Number(product.quantity) <= 0) return ["Out of stock", "bad"];
  if (Number(product.quantity) <= Number(product.threshold)) return ["Low stock", "warn"];
  return ["In stock", "good"];
}

function emptyRow(columns, message) {
  return `<tr><td colspan="${columns}" class="empty">${message}</td></tr>`;
}

function nav(page) {
  const target = $("page-" + page);
  if (!target) return;

  document.querySelectorAll(".page").forEach(item => {
    item.classList.toggle("active", item === target);
  });

  document.querySelectorAll("#mainNav button[data-page]").forEach(button => {
    button.classList.toggle("active", button.dataset.page === page);
  });
}

$("mainNav").addEventListener("click", event => {
  const button = event.target.closest("button[data-page]");
  if (button) nav(button.dataset.page);
});

document.querySelectorAll("[data-go]").forEach(button => {
  button.addEventListener("click", () => nav(button.dataset.go));
});

function renderDashboard() {
  const products = state.products;
  const revenue = state.sales.reduce((sum, sale) => sum + Number(sale.total || 0), 0);
  const units = products.reduce((sum, product) => sum + Number(product.quantity || 0), 0);
  const low = products.filter(product => Number(product.quantity) <= Number(product.threshold));

  $("statProducts").textContent = products.length;
  $("statUnits").textContent = units;
  $("statLow").textContent = low.length;
  $("statSales").textContent = money(revenue);
  $("statSalesCount").textContent = `${state.sales.length} transactions`;

  $("recentTable").innerHTML = products.length
    ? [...products].reverse().slice(0, 5).map(product => {
        const stock = status(product);
        return `<tr>
          <td>${esc(product.name)}</td>
          <td>${esc(product.category)}</td>
          <td>${product.quantity}</td>
          <td><span class="pill ${stock[1]}">${stock[0]}</span></td>
        </tr>`;
      }).join("")
    : emptyRow(4, "No products added yet.");

  $("dashCategories").innerHTML = CATEGORIES.map(category => {
    const count = products.filter(product => product.category === category).length;
    return `<div class="category-row">
      <div class="category-emoji">${EMOJI[category]}</div>
      <div><strong>${esc(category)}</strong><small>Products in category</small></div>
      <div class="count">${count}</div>
    </div>`;
  }).join("");

  $("lowAlerts").innerHTML = low.length
    ? low.map(product => `<div class="notice">
        <strong>${esc(product.name)}</strong> — only ${product.quantity} unit(s) left.
      </div>`).join("")
    : '<div class="empty">Everything looks good. No low-stock alerts!</div>';
}

function resetProductForm() {
  $("productForm").reset();
  $("editId").value = "";
  $("formTitle").textContent = "＋ Add Product";
  $("saveProduct").textContent = "Save Product";
  $("cancelEdit").classList.add("hidden");
}

$("newProductBtn").addEventListener("click", () => {
  resetProductForm();
  $("productName").focus();
});

$("cancelEdit").addEventListener("click", resetProductForm);
$("clearForm").addEventListener("click", () => setTimeout(resetProductForm, 0));

function renderInventory() {
  const query = $("inventorySearch").value.toLowerCase().trim();
  const category = $("categoryFilter").value;
  const stockFilter = $("stockFilter").value;

  const products = state.products.filter(product => {
    const matchesQuery = [product.name, product.brand, product.category]
      .join(" ").toLowerCase().includes(query);

    const stock = status(product)[0].toLowerCase();
    const matchesCategory = !category || product.category === category;
    const matchesStock =
      !stockFilter ||
      (stockFilter === "low" && stock === "low stock") ||
      (stockFilter === "in" && stock === "in stock") ||
      (stockFilter === "out" && stock === "out of stock");

    return matchesQuery && matchesCategory && matchesStock;
  });

  $("inventoryTable").innerHTML = products.length
    ? products.map(product => {
        const stock = status(product);
        return `<tr>
          <td>${esc(product.name)}</td>
          <td>${esc(product.category)}</td>
          <td>${esc(product.brand || "—")}</td>
          <td>${product.quantity}</td>
          <td>${money(product.purchasePrice)}</td>
          <td>${money(product.sellingPrice)}</td>
          <td><span class="pill ${stock[1]}">${stock[0]}</span></td>
          <td>
            <button class="btn small" data-edit="${product.id}">Edit</button>
            <button class="btn small danger" data-delete="${product.id}">Delete</button>
          </td>
        </tr>`;
      }).join("")
    : emptyRow(8, "No matching products found.");

  $("inventoryCategories").innerHTML = CATEGORIES.map(category => {
    const count = state.products.filter(product => product.category === category).length;
    return `<div class="category-row">
      <div class="category-emoji">${EMOJI[category]}</div>
      <div><strong>${esc(category)}</strong><small>Click to filter</small></div>
      <div class="count">${count}</div>
    </div>`;
  }).join("");
}

$("inventoryTable").addEventListener("click", event => {
  const editButton = event.target.closest("[data-edit]");
  const deleteButton = event.target.closest("[data-delete]");

  if (editButton) editProduct(editButton.dataset.edit);
  if (deleteButton) deleteProduct(deleteButton.dataset.delete);
});

function editProduct(id) {
  const product = state.products.find(item => item.id === id);
  if (!product) return;

  const fields = {
    productName: "name",
    category: "category",
    brand: "brand",
    unit: "unit",
    quantity: "quantity",
    threshold: "threshold",
    purchasePrice: "purchasePrice",
    sellingPrice: "sellingPrice",
    expiryDate: "expiryDate",
    location: "location",
    description: "description"
  };

  Object.entries(fields).forEach(([field, key]) => {
    $(field).value = product[key] ?? "";
  });

  $("editId").value = product.id;
  $("formTitle").textContent = "✎ Edit Product";
  $("saveProduct").textContent = "Update Product";
  $("cancelEdit").classList.remove("hidden");
  $("productFormCard").scrollIntoView({ behavior: "smooth", block: "start" });
}

function deleteProduct(id) {
  const product = state.products.find(item => item.id === id);
  if (!product) return;

  if (!confirm(`Delete "${product.name}" from inventory?`)) return;

  state.products = state.products.filter(item => item.id !== id);
  save();
  renderAll();
  toast("Product deleted.");
}

$("productForm").addEventListener("submit", event => {
  event.preventDefault();

  const id = $("editId").value;
  const old = state.products.find(product => product.id === id);

  const product = {
    id: id || (crypto.randomUUID ? crypto.randomUUID() : String(Date.now())),
    name: $("productName").value.trim(),
    category: $("category").value,
    brand: $("brand").value.trim(),
    unit: $("unit").value,
    quantity: Number($("quantity").value),
    threshold: Number($("threshold").value),
    purchasePrice: Number($("purchasePrice").value || 0),
    sellingPrice: Number($("sellingPrice").value),
    expiryDate: $("expiryDate").value,
    location: $("location").value.trim(),
    description: $("description").value.trim(),
    createdAt: old?.createdAt || Date.now(),
    updatedAt: Date.now()
  };

  if (!product.name || !product.category || product.quantity < 0 ||
      product.threshold < 0 || product.purchasePrice < 0 ||
      product.sellingPrice < 0) {
    toast("Please check the product details.");
    return;
  }

  if (old) {
    state.products = state.products.map(item => item.id === id ? product : item);
  } else {
    state.products.push(product);
  }

  save();
  resetProductForm();
  renderAll();
  toast(old ? "Product updated successfully." : "Product added successfully.");
});

function renderSales() {
  const select = $("saleProduct");
  const previous = select.value;

  select.innerHTML = '<option value="">Select a product</option>' +
    state.products.filter(product => Number(product.quantity) > 0)
      .map(product => `<option value="${product.id}">${esc(product.name)} — ${product.quantity} available</option>`)
      .join("");

  if (state.products.some(product => product.id === previous && product.quantity > 0)) {
    select.value = previous;
  }

  updateSalePreview();

  $("salesRevenue").textContent = money(
    state.sales.reduce((sum, sale) => sum + Number(sale.total || 0), 0)
  );
  $("salesTransactions").textContent = state.sales.length;

  $("salesTable").innerHTML = state.sales.length
    ? [...state.sales].reverse().map(sale => `<tr>
        <td>${new Date(sale.date).toLocaleString()}</td>
        <td>${esc(sale.productName)}</td>
        <td>${sale.quantity}</td>
        <td>${money(sale.unitPrice)}</td>
        <td><strong>${money(sale.total)}</strong></td>
        <td>${esc(sale.customer || "—")}</td>
      </tr>`).join("")
    : emptyRow(6, "No sales recorded yet.");
}

function updateSalePreview() {
  const product = state.products.find(item => item.id === $("saleProduct").value);
  const quantity = Number($("saleQty").value || 0);

  $("salePrice").value = product ? product.sellingPrice : "";
  $("saleTotal").textContent = money(product ? product.sellingPrice * quantity : 0);
  $("saleAvailability").textContent = product
    ? `${product.quantity} unit(s) available.`
    : "Select a product to see available stock.";
  $("saleQty").max = product ? product.quantity : "";
}

$("saleProduct").addEventListener("change", updateSalePreview);
$("saleQty").addEventListener("input", updateSalePreview);
$("saleForm").addEventListener("reset", () => setTimeout(updateSalePreview, 0));

$("saleForm").addEventListener("submit", event => {
  event.preventDefault();

  const product = state.products.find(item => item.id === $("saleProduct").value);
  const quantity = Number($("saleQty").value);

  if (!product) return toast("Choose a product first.");
  if (!Number.isInteger(quantity) || quantity < 1 || quantity > product.quantity) {
    return toast("Sale quantity exceeds available stock.");
  }

  const unitPrice = Number(product.sellingPrice);

  state.sales.push({
    id: crypto.randomUUID ? crypto.randomUUID() : String(Date.now()),
    date: new Date().toISOString(),
    productId: product.id,
    productName: product.name,
    quantity,
    unitPrice,
    total: quantity * unitPrice,
    customer: $("customer").value.trim()
  });

  product.quantity -= quantity;
  product.updatedAt = Date.now();

  save();
  $("saleForm").reset();
  renderAll();
  toast("Sale recorded and stock updated!");
});

function renderReports() {
  const cost = state.products.reduce((sum, product) =>
    sum + Number(product.quantity) * Number(product.purchasePrice || 0), 0);

  const retail = state.products.reduce((sum, product) =>
    sum + Number(product.quantity) * Number(product.sellingPrice || 0), 0);

  const sold = state.sales.reduce((sum, sale) => sum + Number(sale.quantity), 0);

  $("reportCost").textContent = money(cost);
  $("reportRetail").textContent = money(retail);
  $("reportMargin").textContent = money(retail - cost);
  $("reportUnitsSold").textContent = sold;

  const maximum = Math.max(1, ...CATEGORIES.map(category =>
    state.products.filter(product => product.category === category).length
  ));

  $("categoryBars").innerHTML = CATEGORIES.map(category => {
    const count = state.products.filter(product => product.category === category).length;
    return `<div class="bar-row">
      <span>${EMOJI[category]} ${esc(category)}</span>
      <div class="bar"><i style="width:${count / maximum * 100}%"></i></div>
      <strong>${count}</strong>
    </div>`;
  }).join("");

  const today = new Date();
  today.setHours(0, 0, 0, 0);
  const endDate = today.getTime() + 30 * 86400000;

  const expiring = state.products.filter(product => {
    if (!product.expiryDate) return false;
    const date = new Date(product.expiryDate + "T00:00:00").getTime();
    return date >= today.getTime() && date <= endDate;
  });

  $("expiryReview").innerHTML = expiring.length
    ? expiring.map(product => `<div class="notice">${esc(product.name)} — expires ${esc(product.expiryDate)}</div>`).join("")
    : '<div class="empty">No products expiring in the next 30 days.</div>';

  $("stockReport").innerHTML = state.products.length
    ? state.products.map(product => {
        const stock = status(product);
        return `<tr>
          <td>${esc(product.name)}</td>
          <td>${esc(product.category)}</td>
          <td>${product.quantity}</td>
          <td>${product.threshold}</td>
          <td>${money(product.quantity * product.purchasePrice)}</td>
          <td><span class="pill ${stock[1]}">${stock[0]}</span></td>
        </tr>`;
      }).join("")
    : emptyRow(6, "No inventory to report yet.");
}

function renderSettings() {
  $("shopName").value = state.settings.shopName || "Velvet Room";
  $("managerName").value = state.settings.managerName || "Admin";
  $("adminShopName").textContent = state.settings.managerName || "Admin";
  document.title = (state.settings.shopName || "Velvet Room") + " | Beauty • Style • Elegance";
}

$("settingsForm").addEventListener("submit", event => {
  event.preventDefault();

  state.settings.shopName = $("shopName").value.trim() || "Velvet Room";
  state.settings.managerName = $("managerName").value.trim() || "Admin";

  save();
  renderSettings();
  toast("Settings saved.");
});

function csvDownload(filename, rows) {
  const csv = rows.map(row =>
    row.map(value => '"' + String(value ?? "").replace(/"/g, '""') + '"').join(",")
  ).join("\r\n");

  const blob = new Blob(["\ufeff" + csv], { type: "text/csv;charset=utf-8;" });
  const url = URL.createObjectURL(blob);
  const link = document.createElement("a");

  link.href = url;
  link.download = filename;
  document.body.appendChild(link);
  link.click();
  link.remove();
  URL.revokeObjectURL(url);
  toast("CSV export ready.");
}

$("exportInventory").addEventListener("click", () => {
  csvDownload("velvet-room-inventory.csv", [
    ["Product","Category","Brand","Unit","Quantity","Threshold","Purchase Price","Selling Price","Expiry","Location","Description"],
    ...state.products.map(product => [
      product.name, product.category, product.brand, product.unit,
      product.quantity, product.threshold, product.purchasePrice,
      product.sellingPrice, product.expiryDate, product.location, product.description
    ])
  ]);
});

$("exportSales").addEventListener("click", () => {
  csvDownload("velvet-room-sales.csv", [
    ["Date","Product","Quantity","Unit Price","Total","Customer"],
    ...state.sales.map(sale => [
      sale.date, sale.productName, sale.quantity,
      sale.unitPrice, sale.total, sale.customer
    ])
  ]);
});

$("backupAll").addEventListener("click", () => {
  const blob = new Blob([JSON.stringify(state, null, 2)], { type: "application/json" });
  const url = URL.createObjectURL(blob);
  const link = document.createElement("a");
  link.href = url;
  link.download = "velvet-room-backup.json";
  link.click();
  URL.revokeObjectURL(url);
  toast("Full backup exported.");
});

$("clearAll").addEventListener("click", () => {
  if (!confirm("Clear all products, sales and settings?")) return;

  state = {
    products: [],
    sales: [],
    settings: { shopName: "Velvet Room", managerName: "Admin", currency: "INR" }
  };

  save();
  renderAll();
  nav("dashboard");
  toast("Shop data cleared.");
});

$("resetDemo").addEventListener("click", () => {
  if (!confirm("Load sample products? This replaces current project data.")) return;

  state = {
    products: [
      {
        id: "demo1", name: "Velvet Matte Lipstick", category: "Cosmetics",
        brand: "Glow Studio", unit: "Piece", quantity: 18, threshold: 5,
        purchasePrice: 180, sellingPrice: 299, expiryDate: "", location: "Shelf A",
        description: "Soft matte finish"
      },
      {
        id: "demo2", name: "Pearl Claw Clip", category: "Hair Accessories",
        brand: "Pretty Days", unit: "Piece", quantity: 3, threshold: 5,
        purchasePrice: 60, sellingPrice: 129, expiryDate: "", location: "Rack B",
        description: "Pearl detail hair clip"
      },
      {
        id: "demo3", name: "Gold-Tone Hoop Earrings", category: "Jewellery",
        brand: "Luna", unit: "Pair", quantity: 12, threshold: 4,
        purchasePrice: 120, sellingPrice: 249, expiryDate: "", location: "Display C",
        description: "Lightweight hoop earrings"
      }
    ],
    sales: [],
    settings: { shopName: "Velvet Room", managerName: "Admin", currency: "INR" }
  };

  save();
  renderAll();
  nav("dashboard");
  toast("Sample data loaded.");
});

$("inventorySearch").addEventListener("input", renderInventory);
$("categoryFilter").addEventListener("change", renderInventory);
$("stockFilter").addEventListener("change", renderInventory);

$("globalSearch").addEventListener("input", () => {
  const query = $("globalSearch").value.trim();
  if (query) {
    nav("inventory");
    $("inventorySearch").value = query;
    renderInventory();
  }
});

function renderAll() {
  renderDashboard();
  renderInventory();
  renderSales();
  renderReports();
  renderSettings();
  $("year").textContent = new Date().getFullYear();
}

load();
renderAll();

})();
</script>
</body>
</html>
