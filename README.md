<!DOCTYPE html>
<html lang="hi" data-theme="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Video Enhancer Pro</title>
<style>
:root{--bg:#0f1115;--card:#181b22;--tx:#f2f4f8;--mu:#8b93a3;--ac:#7c5cff;--ac2:#00d4c8;--bd:#272b35;--gold:#ffb830}
[data-theme=light]{--bg:#f3f5f9;--card:#fff;--tx:#14171f;--mu:#667085;--bd:#e3e7ee}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font-family:system-ui,sans-serif;padding:14px}
.wrap{max-width:520px;margin:auto}
header{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px;gap:8px}
h1{font-size:19px;margin:0}
h1 span{background:linear-gradient(90deg,var(--ac),var(--ac2));-webkit-background-clip:text;color:transparent}
.badge{padding:6px 10px;border-radius:14px;font-size:12px;font-weight:700;border:1px solid var(--bd);background:var(--card)}
.badge.p{background:var(--gold);color:#000;border-color:var(--gold)}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:14px;margin-bottom:12px}
.card h2{font-size:13px;color:var(--mu);margin:0 0 10px;text-transform:uppercase;letter-spacing:.5px}
.drop{display:block;border:2px dashed var(--bd);border-radius:12px;padding:22px;text-align:center;cursor:pointer;color:var(--mu)}
.drop b{color:var(--tx);display:block;margin-bottom:4px}
input[type=file]{display:none}
#info{margin-top:10px;font-size:13px;color:var(--mu)}
.chips{display:flex;gap:8px;flex-wrap:wrap}
.chip{padding:8px 14px;border-radius:20px;border:1px solid var(--bd);background:transparent;color:var(--tx);font-size:14px}
.chip.on{background:var(--ac);border-color:var(--ac);color:#fff}
.row{display:flex;justify-content:space-between;font-size:14px;margin-top:12px}
.row span:last-child{color:var(--ac2)}
input[type=range]{width:100%;accent-color:var(--ac)}
select{width:100%;padding:10px;border-radius:10px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);font-size:15px;margin-top:8px}
label.ck{display:flex;gap:8px;align-items:center;margin-top:12px;font-size:14px}
.btn{width:100%;padding:14px;border:0;border-radius:12px;font-size:16px;font-weight:600;color:#fff;background:linear-gradient(90deg,var(--ac),var(--ac2))}
.btn:disabled{opacity:.5}
.btn.gold{background:var(--gold);color:#000}
.btn2{padding:10px 14px;border-radius:10px;border:1px solid var(--bd);background:transparent;color:var(--tx);font-size:14px}
.bar{height:8px;background:var(--bd);border-radius:6px;overflow:hidden;margin-top:12px;display:none}
.bar div{height:100%;width:0;background:linear-gradient(90deg,var(--ac),var(--ac2));transition:width .2s}
#status{font-size:13px;color:var(--mu);margin-top:8px;text-align:center}
.cmp{position:relative;width:100%;background:#000;border-radius:12px;overflow:hidden;user-select:none}
.cmp video{position:absolute;inset:0;width:100%;height:100%;object-fit:contain}
#after{position:absolute;inset:0}
.tag{position:absolute;top:8px;padding:3px 9px;border-radius:8px;background:rgba(0,0,0,.6);color:#fff;font-size:12px;z-index:3}
#handle{position:absolute;top:0;bottom:0;width:44px;margin-left:-22px;z-index:4;touch-action:none;cursor:ew-resize}
#handle::before{content:"";position:absolute;left:21px;top:0;bottom:0;width:2px;background:#fff}
#handle::after{content:"\2194";position:absolute;left:4px;top:50%;margin-top:-18px;width:36px;height:36px;border-radius:50%;background:#fff;color:#000;text-align:center;line-height:36px;font-size:18px;box-shadow:0 2px 8px rgba(0,0,0,.5)}
.ctrl{display:flex;gap:8px;align-items:center;margin-top:10px}
.ctrl input{flex:1}
.stats{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:10px;font-size:13px}
.stats div{background:var(--bg);border-radius:10px;padding:10px}
.stats b{display:block;color:var(--mu);font-weight:500;font-size:12px}
#dl{display:block;text-align:center;text-decoration:none;margin-top:10px}
.hide{display:none}
.ov{position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:50;display:none;align-items:center;justify-content:center;padding:16px}
.ov.show{display:flex}
.box{background:var(--card);border:1px solid var(--bd);border-radius:18px;padding:18px;max-width:420px;width:100%;max-height:90vh;overflow:auto}
.box h3{margin:0 0 8px}
.plan{border:1px solid var(--bd);border-radius:12px;padding:10px;margin:8px 0;font-size:14px}
.plan.g{border-color:var(--gold)}
.plan b{display:block;margin-bottom:4px}
.box input[type=text]{width:100%;padding:11px;border-radius:10px;border:1px solid var(--bd);background:var(--bg);color:var(--tx);font-size:15px;margin:6px 0}
.adph{height:160px;border-radius:12px;background:repeating-linear-gradient(45deg,#222,#222 10px,#2a2a2a 10px,#2a2a2a 20px);display:flex;align-items:center;justify-content:center;color:#aaa;text-align:center;font-size:14px;margin:10px 0}
</style>
</head>
<body>
<div class="wrap">
<header>
  <h1>🎬 Video <span>Enhancer Pro</span></h1>
  <div style="display:flex;gap:6px;align-items:center">
    <span class="badge" id="badge" onclick="openModal()">FREE</span>
    <button class="btn2" id="theme">🌓</button>
  </div>
</header>

<div class="card">
  <h2>1. Video chuno</h2>
  <label class="drop" for="file"><b>📁 Yahan tap karke video chuno</b>Gallery se koi bhi video</label>
  <input type="file" id="file" accept="video/*">
  <div id="info"></div>
</div>

<div class="card">
  <h2>2. Style (Preset)</h2>
  <div class="chips" id="chips"></div>
</div>

<div class="card">
  <h2>3. Picture settings</h2>
  <div class="row"><span>Sharpness</span><span id="sharpV"></span></div>
  <input type="range" class="rg" id="sharp" min="0" max="2" step="0.1" value="1">
  <div class="row"><span>Brightness</span><span id="brightV"></span></div>
  <input type="range" class="rg" id="bright" min="-0.3" max="0.3" step="0.01" value="0.03">
  <div class="row"><span>Contrast</span><span id="contrastV"></span></div>
  <input type="range" class="rg" id="contrast" min="0.7" max="1.6" step="0.01" value="1.1">
  <div class="row"><span>Color (Saturation)</span><span id="satV"></span></div>
  <input type="range" class="rg" id="sat" min="0" max="2.5" step="0.05" value="1.15">
  <div class="row"><span>Gamma (andhere ko ujaala)</span><span id="gammaV"></span></div>
  <input type="range" class="rg" id="gamma" min="0.6" max="2" step="0.05" value="1">
  <div class="row"><span>Warm ⟷ Cool ⭐</span><span id="warmV"></span></div>
  <input type="range" class="rg" id="warm" min="-0.3" max="0.3" step="0.05" value="0" data-prem="1" data-def="0">
  <select id="dn">
    <option value="0">Noise reduction: Off</option>
    <option value="1">Noise reduction: Light</option>
    <option value="2" data-p="1" data-t="Noise reduction: Medium">x</option>
  </select>
  <label class="ck"><input type="checkbox" id="stab" data-prem="1" data-def="0"> Stabilize / hilna kam karo ⭐ <span class="lk">🔒</span></label>
  <label class="ck"><input type="checkbox" id="vig" data-prem="1" data-def="0"> Cinematic vignette ⭐ <span class="lk">🔒</span></label>
</div>

<div class="card">
  <h2>4. Resolution, speed, quality</h2>
  <select id="res">
    <option value="0">Resolution: Original</option>
    <option value="480">480p</option>
    <option value="720">720p HD (tez)</option>
    <option value="1080" selected>1080p Full HD</option>
    <option value="1440" data-p="1" data-t="1440p (2K)">x</option>
    <option value="2160" data-p="1" data-t="2160p (4K)">x</option>
  </select>
  <select id="fps">
    <option value="0">Frame rate: Original</option>
    <option value="24">24 fps (cinema)</option>
    <option value="30">30 fps</option>
  </select>
  <select id="speed">
    <option value="fast" selected>Speed: Fast</option>
    <option value="bal">Speed: Balanced</option>
    <option value="best">Speed: Best quality (slow)</option>
  </select>
  <select id="qual">
    <option value="26">Output quality: Normal (chhoti file)</option>
    <option value="22" selected>Output quality: High</option>
    <option value="18" data-p="1" data-t="Output quality: Max">x</option>
    <option value="16" data-p="1" data-t="Output quality: Ultra (badi file)">x</option>
  </select>
  <label class="ck"><input type="checkbox" id="prev" checked> Sirf 5 second ka preview (jaldi test, bina ad)</label>
</div>

<div class="card">
  <h2>5. Audio</h2>
  <div class="row"><span>Volume</span><span id="volV"></span></div>
  <input type="range" class="rg" id="vol" min="0.5" max="2.5" step="0.1" value="1">
  <label class="ck"><input type="checkbox" id="norm"> Awaaz barabar karo (normalize)</label>
  <label class="ck"><input type="checkbox" id="mute"> Awaaz hata do (mute)</label>
</div>

<button class="btn" id="go">✨ Enhance karo</button>
<div class="bar" id="bar"><div id="fill"></div></div>
<div id="status">Pehle video chuno</div>

<div class="card hide" id="result" style="margin-top:12px">
  <h2>Pehle vs Baad</h2>
  <div class="cmp" id="cmp">
    <video id="vb" playsinline muted></video>
    <div id="after"><video id="va" playsinline></video></div>
    <span class="tag" style="left:8px">PEHLE</span>
    <span class="tag" style="right:8px">BAAD</span>
    <div id="handle"></div>
  </div>
  <div class="ctrl">
    <button class="btn2" id="pp">▶ Play</button>
    <input type="range" id="seek" min="0" max="1000" value="0">
  </div>
  <div class="stats">
    <div><b>Pehle</b><span id="s1"></span></div>
    <div><b>Baad</b><span id="s2"></span></div>
  </div>
  <a id="dl" class="btn" download="enhanced.mp4">⬇️ Download karo</a>
</div>
</div>

<div class="ov" id="modal">
  <div class="box">
    <h3>⭐ Premium unlock karo</h3>
    <div class="plan"><b>FREE</b>1080p tak • har poore video se pehle ad • 5 sec preview bina ad</div>
    <div class="plan g"><b>PREMIUM ⭐</b>1440p + 4K • No ads • Stabilize • Warm/Cool • Vignette • Max quality presets</div>
    <button class="btn gold" id="buy">💳 Premium kharido</button>
    <p style="font-size:13px;color:var(--mu)">Paise dene ke baad aapko ek key milegi. Yahan daalo:</p>
    <input type="text" id="key" placeholder="Premium key">
    <button class="btn" id="act">Activate karo</button>
    <div id="keyMsg" style="font-size:13px;margin-top:6px"></div>
    <button class="btn2" style="width:100%;margin-top:10px" id="mclose">Band karo</button>
  </div>
</div>

<div class="ov" id="adbox">
  <div class="box">
    <h3>📺 Ad (free ke liye)</h3>
    <div class="adph" id="adArea">YAHAN ASLI AD AAYEGA<br>(abhi placeholder hai)</div>
    <button class="btn" id="adClose" disabled>Ruko: <span id="adT"></span> sec</button>
    <button class="btn2" style="width:100%;margin-top:8px" id="adX">Cancel</button>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/@ffmpeg/ffmpeg@0.12.10/dist/umd/ffmpeg.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@ffmpeg/util@0.12.1/dist/umd/index.js"></script>
<script>
const PAY_LINK = "https://rzp.io/l/YOUR_PAYMENT_LINK";
const PREMIUM_KEYS = ["ROHIT-OWNER-7391", "DEMO-PREMIUM-2026"];
const AD_SECONDS = 10;
const FREE_MAX_MB = 150, PREM_MAX_MB = 600;

const $ = id => document.getElementById(id);
const { FFmpeg } = FFmpegWASM;
const { fetchFile } = FFmpegUtil;
const ff = new FFmpeg();
let loaded=false, file=null, srcURL=null, outURL=null, srcW=0, srcH=0, t0=0;

function isPrem(){
  try { return PREMIUM_KEYS.includes(localStorage.getItem("pkey")); } catch(e){ return false; }
}
function refreshPlan(){
  const p = isPrem();
  $("badge").textContent = p ? "PREMIUM ⭐" : "FREE";
  $("badge").className = "badge" + (p ? " p" : "");
  document.querySelectorAll(".lk").forEach(e => e.style.display = p ? "none" : "inline");
  document.querySelectorAll("option[data-p]").forEach(o => o.textContent = o.dataset.t + (p ? " ⭐" : " 🔒"));
  buildChips();
}
function openModal(){ $("modal").classList.add("show"); }
$("mclose").onclick = () => $("modal").classList.remove("show");
$("buy").onclick = () => window.open(PAY_LINK, "_blank");
$("act").onclick = () => {
  const k = $("key").value.trim();
  if (PREMIUM_KEYS.includes(k)) {
    try { localStorage.setItem("pkey", k); } catch(e){}
    $("keyMsg").textContent = "✅ Premium activate ho gaya!";
    refreshPlan();
    setTimeout(() => $("modal").classList.remove("show"), 900);
  } else $("keyMsg").textContent = "❌ Key galat hai";
};

document.querySelectorAll("[data-prem],select").forEach(el => el.addEventListener("input", () => {
  if (isPrem()) return;
  const locked = el.tagName === "SELECT" ? !!el.selectedOptions[0].dataset.p : el.dataset.prem === "1";
  if (!locked) return;
  if (el.tagName === "SELECT") {
    const safe = [...el.options].findIndex(o => o.defaultSelected && !o.dataset.p);
    el.selectedIndex = safe >= 0 ? safe : 0;
  }
  else if (el.type === "checkbox") el.checked = false;
  else el.value = el.dataset.def;
  syncLabels(); openModal();
}));

try { const t = localStorage.getItem("theme"); if (t) document.documentElement.dataset.theme = t; } catch(e){}
$("theme").onclick = () => {
  const d = document.documentElement;
  d.dataset.theme = d.dataset.theme === "dark" ? "light" : "dark";
  try { localStorage.setItem("theme", d.dataset.theme); } catch(e){}
};

const presets = {
  "Auto":        {sharp:0.8,bright:0.02,contrast:1.08,sat:1.10,gamma:1.0,warm:0,dn:0},
  "Natural":     {sharp:0.4,bright:0,contrast:1.04,sat:1.04,gamma:1.0,warm:0,dn:0},
  "Vivid":       {sharp:0.8,bright:0.03,contrast:1.12,sat:1.35,gamma:1.0,warm:0,dn:0},
  "Cinematic":   {sharp:0.5,bright:-0.02,contrast:1.18,sat:0.95,gamma:1.0,warm:0,dn:0},
  "Night Fix":   {sharp:0.6,bright:0.07,contrast:1.12,sat:1.08,gamma:1.35,warm:0,dn:1},
  "Saaf":        {sharp:0.6,bright:0.02,contrast:1.06,sat:1.08,gamma:1.0,warm:0,dn:1},
  "Max Quality ⭐": {sharp:0.7,bright:0.01,contrast:1.06,sat:1.08,gamma:1.0,warm:0,dn:1,qual:"16",speed:"best",prem:true},
  "Film Look ⭐": {sharp:0.4,bright:-0.01,contrast:1.20,sat:0.92,gamma:1.0,warm:0.1,dn:1,vig:true,qual:"18",speed:"bal",prem:true},
  "Ultra 4K ⭐":  {sharp:0.9,bright:0.02,contrast:1.08,sat:1.10,gamma:1.0,warm:0,dn:1,res:"2160",qual:"18",speed:"bal",prem:true}
};
function syncLabels(){
  document.querySelectorAll(".rg").forEach(r => { const s = $(r.id + "V"); if (s) s.textContent = (+r.value).toFixed(2); });
}
document.querySelectorAll(".rg").forEach(r => r.addEventListener("input", () => {
  document.querySelectorAll(".chip").forEach(c => c.classList.remove("on")); syncLabels();
}));
function applyPreset(name){
  const p = presets[name];
  if (p.prem && !isPrem()) { openModal(); return; }
  ["sharp","bright","contrast","sat","gamma","warm"].forEach(k => $(k).value = p[k]);
  $("dn").value = p.dn; $("vig").checked = !!p.vig;
  if (p.res) $("res").value = p.res;
  if (p.qual) $("qual").value = p.qual;
  if (p.speed) $("speed").value = p.speed;
  syncLabels();
  document.querySelectorAll(".chip").forEach(c => c.classList.toggle("on", c.dataset.n === name));
}
function buildChips(){
  const box = $("chips"), cur = box.querySelector(".on") ? box.querySelector(".on").dataset.n : null;
  box.innerHTML = "";
  Object.keys(presets).forEach(n => {
    const b = document.createElement("button");
    b.className = "chip" + (n === cur ? " on" : ""); b.dataset.n = n;
    b.textContent = (presets[n].prem && !isPrem() ? "🔒 " : "") + n;
    b.onclick = () => applyPreset(n);
    box.appendChild(b);
  });
}

const mb = b => (b/1048576).toFixed(1) + " MB";
function upscaleWarn(){
  const t = +$("res").value, s = Math.min(srcW, srcH);
  if (t && s && t > s * 2) $("status").textContent = "⚠️ Video " + s + "p se " + t + "p: bahut zyada upscale, result dhundhla lagega. 2x tak rakho.";
  else if (+$("res").value >= 1440 && isPrem()) $("status").textContent = "⚠️ 2K/4K phone par bhaari hai. Pehle 5 sec preview se test karo.";
}
$("file").onchange = () => {
  file = $("file").files[0]; if (!file) return;
  const lim = isPrem() ? PREM_MAX_MB : FREE_MAX_MB;
  if (file.size/1048576 > lim) {
    $("info").textContent = "❌ Video " + mb(file.size) + " hai. Limit " + lim + " MB" + (isPrem() ? "." : " (Premium mein " + PREM_MAX_MB + " MB).");
    file = null; return;
  }
  if (srcURL) URL.revokeObjectURL(srcURL);
  srcURL = URL.createObjectURL(file);
  const tv = document.createElement("video");
  tv.preload = "metadata"; tv.src = srcURL;
  tv.onloadedmetadata = () => {
    srcW = tv.videoWidth; srcH = tv.videoHeight;
    $("info").textContent = "✅ " + file.name + " | " + srcW + "x" + srcH + " | " + Math.round(tv.duration) + " sec | " + mb(file.size);
    $("status").textContent = "Ready! Enhance dabao";
    upscaleWarn();
  };
};
$("res").addEventListener("change", upscaleWarn);

ff.on("progress", ({progress}) => {
  const p = Math.min(100, Math.max(0, Math.round(progress*100)));
  $("fill").style.width = p + "%";
  $("status").textContent = "Processing: " + p + "% (" + Math.round((Date.now()-t0)/1000) + " sec)";
});

async function fetchBlob(url, mime, label){
  const ctrl = new AbortController();
  let timer = setTimeout(() => ctrl.abort(), 30000);
  const res = await fetch(url, {signal: ctrl.signal});
  if (!res.ok) throw new Error("HTTP " + res.status);
  const reader = res.body.getReader();
  const chunks = []; let got = 0;
  while (true) {
    const r = await reader.read();
    if (r.done) break;
    chunks.push(r.value); got += r.value.length;
    clearTimeout(timer); timer = setTimeout(() => ctrl.abort(), 30000);
    $("status").textContent = label + ": " + (got/1048576).toFixed(1) + " MB (lagbhag 31 MB)";
  }
  clearTimeout(timer);
  return URL.createObjectURL(new Blob(chunks, {type: mime}));
}

async function load(){
  if (loaded) return;
  const cdns = ["https://cdn.jsdelivr.net/npm", "https://unpkg.com", "https://fastly.jsdelivr.net/npm"];
  let lastErr;
  for (const c of cdns) {
    const name = c.split("//")[1].split("/")[0];
    try {
      const base = c + "/@ffmpeg/core@0.12.6/dist/esm";
      const coreURL = await fetchBlob(base + "/ffmpeg-core.js", "text/javascript", "Engine (" + name + ") JS");
      const wasmURL = await fetchBlob(base + "/ffmpeg-core.wasm", "application/wasm", "Engine (" + name + ")");
      const classWorkerURL = await fetchBlob(c + "/@ffmpeg/ffmpeg@0.12.10/dist/umd/814.ffmpeg.js", "text/javascript", "Engine (" + name + ") worker");
      $("status").textContent = "Engine start ho raha hai...";
      await ff.load({coreURL: coreURL, wasmURL: wasmURL, classWorkerURL: classWorkerURL});
      loaded = true;
      return;
    } catch (e) {
      lastErr = e;
      try { ff.terminate(); } catch (_) {}
    }
  }
  throw new Error("Engine load nahi hua. Wi-Fi try karo. (" + (lastErr && lastErr.message) + ")");
}

function showAd(){
  return new Promise(resolve => {
    let s = AD_SECONDS;
    const btn = $("adClose");
    btn.disabled = true; btn.innerHTML = "Ruko: <span id='adT'>" + s + "</span> sec";
    $("adbox").classList.add("show");
    const iv = setInterval(() => {
      s--;
      if (s > 0) $("adT").textContent = s;
      else { clearInterval(iv); btn.disabled = false; btn.textContent = "✅ Reward lo, enhance shuru karo"; }
    }, 1000);
    btn.onclick = () => { $("adbox").classList.remove("show"); resolve(true); };
    $("adX").onclick = () => { clearInterval(iv); $("adbox").classList.remove("show"); resolve(false); };
  });
}

$("go").onclick = async () => {
  if (!file) { $("status").textContent = "Pehle video chuno!"; return; }
  const prem = isPrem();
  if (!prem && !$("prev").checked) {
    const ok = await showAd();
    if (!ok) { $("status").textContent = "Poora video enhance karne ke liye ad dekhna padega (ya 5 sec preview use karo)."; return; }
  }
  $("go").disabled = true; $("bar").style.display = "block"; $("fill").style.width = "0";
  $("result").classList.add("hide");
  try {
    await load();
    await ff.writeFile("in.mp4", await fetchFile(file));

    const preset = {fast:"veryfast", bal:"fast", best:"medium"}[$("speed").value];

    const f = [];
    if ($("stab").checked) f.push("deshake");
    if (+$("fps").value) f.push("fps=" + $("fps").value);
    if ($("dn").value === "1") f.push("hqdn3d=1.5:1.5:3:3");
    if ($("dn").value === "2") f.push("hqdn3d=3:3:5:5");

    const target = +$("res").value, shortSide = Math.min(srcW, srcH), portrait = srcH > srcW;
    if (target && target !== shortSide)
      f.push(portrait ? "scale=" + target + ":-2:flags=lanczos" : "scale=-2:" + target + ":flags=lanczos");

    if (+$("sharp").value > 0) f.push("unsharp=5:5:" + $("sharp").value + ":5:5:0");
    f.push("eq=contrast=" + $("contrast").value + ":brightness=" + $("bright").value +
           ":saturation=" + $("sat").value + ":gamma=" + $("gamma").value);
    const w = +$("warm").value;
    if (w !== 0) f.push("colorbalance=rs=" + w + ":bs=" + (-w) + ":rm=" + w + ":bm=" + (-w));
    if ($("vig").checked) f.push("vignette=angle=0.5");

    const args = ["-i", "in.mp4"];
    if ($("prev").checked) args.push("-t", "5");
    args.push("-vf", f.join(","),
      "-c:v","libx264","-preset",preset,"-crf",$("qual").value,
      "-profile:v","high","-pix_fmt","yuv420p");

    if ($("mute").checked) args.push("-an");
    else {
      const af = [];
      if (+$("vol").value !== 1) af.push("volume=" + $("vol").value);
      if ($("norm").checked) af.push("dynaudnorm");
      if (af.length) args.push("-af", af.join(","));
      args.push("-c:a","aac","-b:a","160k");
    }
    args.push("-movflags","+faststart","out.mp4");

    t0 = Date.now();
    $("status").textContent = "Shuru ho gaya...";
    await ff.exec(args);

    const data = await ff.readFile("out.mp4");
    if (outURL) URL.revokeObjectURL(outURL);
    const blob = new Blob([data.buffer], {type:"video/mp4"});
    outURL = URL.createObjectURL(blob);
    try { await ff.deleteFile("in.mp4"); await ff.deleteFile("out.mp4"); } catch(e){}

    setupCompare(blob.size);
    $("status").textContent = "✅ Ho gaya! " + Math.round((Date.now()-t0)/1000) + " second mein";
  } catch(e) {
    const m = String(e.message || e);
    $("status").textContent = "Error: " + m + (/memory|abort|OOM/i.test(m) ? " — Resolution kam karo ya chhota video lo." : "");
    loaded = false;
  }
  $("go").disabled = false;
};

const va = $("va"), vb = $("vb");
function setPos(p){
  p = Math.max(0, Math.min(100, p));
  $("after").style.clipPath = "inset(0 0 0 " + p + "%)";
  $("handle").style.left = p + "%";
}
function setupCompare(outSize){
  $("result").classList.remove("hide");
  $("cmp").style.aspectRatio = srcW + "/" + srcH;
  vb.src = srcURL; va.src = outURL;
  va.onloadedmetadata = () => { $("s2").textContent = va.videoWidth + "x" + va.videoHeight + " | " + mb(outSize); };
  $("s1").textContent = srcW + "x" + srcH + " | " + mb(file.size);
  $("dl").href = outURL;
  $("pp").textContent = "▶ Play";
  setPos(50);
  $("result").scrollIntoView({behavior:"smooth"});
}
let drag = false;
const h = $("handle");
h.onpointerdown = e => { drag = true; h.setPointerCapture(e.pointerId); };
h.onpointermove = e => {
  if (!drag) return;
  const r = $("cmp").getBoundingClientRect();
  setPos((e.clientX - r.left) / r.width * 100);
};
h.onpointerup = () => drag = false;
$("pp").onclick = () => {
  if (va.paused) { va.play(); vb.play(); $("pp").textContent = "⏸ Pause"; }
  else { va.pause(); vb.pause(); $("pp").textContent = "▶ Play"; }
};
va.ontimeupdate = () => {
  if (Math.abs(vb.currentTime - va.currentTime) > 0.2) vb.currentTime = va.currentTime;
  if (va.duration) $("seek").value = va.currentTime / va.duration * 1000;
};
va.onended = () => { vb.pause(); $("pp").textContent = "▶ Play"; };
$("seek").oninput = () => {
  const t = $("seek").value / 1000 * va.duration;
  va.currentTime = t; vb.currentTime = t;
};

syncLabels(); refreshPlan(); applyPreset("Auto");
</script>
</body>
</html>
