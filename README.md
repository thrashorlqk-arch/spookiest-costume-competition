<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Spookiest Costume Competition</title>
<style>
  :root{
    --bg:#100b16; --panel:#1b1222; --panel2:#24162d; --orange:#ff7a18;
    --purple:#a855f7; --text:#f7f1fb; --muted:#b9aabd; --gold:#ffd166;
    --danger:#ff5c5c; --line:#3b2745;
  }
  *{box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    margin:0; font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;
    color:var(--text); background:
      radial-gradient(circle at 15% 10%, #32183d 0, transparent 28%),
      radial-gradient(circle at 85% 15%, #3b1b19 0, transparent 25%),
      linear-gradient(145deg,#0b0710,#17101e 55%,#0d0912);
    min-height:100vh;
  }
  body:before{
    content:""; position:fixed; inset:0; pointer-events:none; opacity:.08;
    background-image:radial-gradient(#fff 1px,transparent 1px); background-size:24px 24px;
  }
  .container{width:min(1150px,92%);margin:auto}
  header{
    min-height:470px; display:flex; align-items:center; text-align:center; position:relative;
    overflow:hidden; border-bottom:1px solid var(--line);
  }
  .moon{position:absolute;width:230px;height:230px;border-radius:50%;background:#ffdca0;right:10%;top:55px;box-shadow:0 0 60px #ffb84d55}
  .moon:after{content:"";position:absolute;inset:0;border-radius:50%;background:radial-gradient(circle at 30% 35%,#d8a96e22 0 8%,transparent 9%),radial-gradient(circle at 70% 65%,#a96d4c22 0 10%,transparent 11%)}
  .bat{position:absolute;font-size:42px;animation:fly 7s ease-in-out infinite}
  .b1{left:10%;top:90px}.b2{right:27%;top:170px;font-size:27px;animation-delay:1s}.b3{left:27%;top:250px;font-size:24px;animation-delay:2s}
  @keyframes fly{50%{transform:translate(30px,-18px) rotate(-5deg)}}
  .hero{position:relative;z-index:2;width:100%}
  .eyebrow{color:var(--orange);font-weight:800;letter-spacing:.18em;text-transform:uppercase}
  h1{font-family:Georgia,serif;font-size:clamp(3rem,8vw,6.4rem);line-height:.95;margin:14px 0;color:#fff;text-shadow:0 6px 30px #000}
  h1 span{color:var(--orange)}
  .hero p{font-size:1.15rem;color:var(--muted);max-width:680px;margin:20px auto 30px}
  .btn{
    border:0;border-radius:999px;padding:13px 22px;font-weight:800;cursor:pointer;
    background:var(--orange);color:#180b05;box-shadow:0 8px 25px #ff7a1833; transition:.2s;
  }
  .btn:hover{transform:translateY(-2px);filter:brightness(1.08)}
  .btn.secondary{background:var(--panel2);color:var(--text);border:1px solid var(--line);box-shadow:none}
  nav{position:sticky;top:0;z-index:10;background:#100b16e8;backdrop-filter:blur(14px);border-bottom:1px solid var(--line)}
  nav .container{display:flex;justify-content:center;gap:10px;padding:12px;flex-wrap:wrap}
  nav a{color:var(--muted);text-decoration:none;padding:8px 14px;border-radius:999px}
  nav a:hover{background:var(--panel2);color:#fff}
  section{padding:70px 0}
  .section-title{text-align:center;font-family:Georgia,serif;font-size:2.5rem;margin:0 0 10px}
  .section-sub{text-align:center;color:var(--muted);margin:0 auto 35px;max-width:700px}
  .criteria{display:grid;grid-template-columns:repeat(5,1fr);gap:14px}
  .criterion,.card,.judge-panel,.winner{
    background:linear-gradient(160deg,#21152a,#160f1c);border:1px solid var(--line);
    border-radius:20px;padding:20px;box-shadow:0 18px 45px #0004;
  }
  .criterion{text-align:center}.criterion .icon{font-size:2rem}.criterion h3{margin:9px 0 5px}.criterion p{color:var(--muted);font-size:.9rem;margin:0}
  .entries{display:grid;grid-template-columns:repeat(2,1fr);gap:18px}
  .card{position:relative;overflow:hidden}
  .card-top{display:flex;align-items:center;justify-content:space-between;gap:12px}
  .avatar{width:58px;height:58px;border-radius:50%;display:grid;place-items:center;font-size:1.7rem;background:#2d1a38;border:1px solid #533561}
  .name{font-size:1.2rem;font-weight:850;flex:1}.class{color:var(--muted);font-size:.86rem}
  .badge{padding:6px 10px;border-radius:999px;background:#2a1a08;color:#ffbd71;font-size:.75rem;font-weight:800}
  .desc{color:var(--muted);line-height:1.55;margin:15px 0}
  .score-row{display:grid;grid-template-columns:1fr 70px;gap:10px;align-items:center;margin:9px 0}
  .score-row label{font-size:.88rem}.score-row input{
    width:70px;padding:9px;border-radius:10px;border:1px solid var(--line);background:#0f0a14;color:#fff;text-align:center;font-weight:800
  }
  .score-row input:focus{outline:2px solid var(--purple)}
  .total{display:flex;justify-content:space-between;align-items:center;margin-top:15px;padding-top:14px;border-top:1px solid var(--line);font-weight:800}
  .total strong{font-size:1.4rem;color:var(--gold)}
  .judge-controls{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-bottom:25px}
  .judge-panel{max-width:850px;margin:auto}
  .notice{padding:13px 16px;border-radius:12px;background:#241b0e;border:1px solid #60451f;color:#e9c98c;margin-bottom:20px}
  .winner{text-align:center;max-width:700px;margin:0 auto;border-color:#6e4d1e;background:linear-gradient(145deg,#291b0d,#181019)}
  .trophy{font-size:4rem}.winner h3{font-family:Georgia,serif;font-size:2.2rem;margin:8px}.winner .score{color:var(--gold);font-size:1.4rem;font-weight:900}
  .hidden{display:none!important}
  footer{border-top:1px solid var(--line);padding:35px 0;text-align:center;color:var(--muted)}
  .small{font-size:.85rem;color:var(--muted)}
  @media(max-width:850px){.criteria{grid-template-columns:repeat(2,1fr)}.entries{grid-template-columns:1fr}.moon{width:150px;height:150px;right:-25px;top:30px;opacity:.65}}
  @media(max-width:520px){.criteria{grid-template-columns:1fr}.hero p{font-size:1rem}section{padding:50px 0}.card{padding:16px}}
</style>
</head>
<body>

<header>
  <div class="moon"></div><div class="bat b1">🦇</div><div class="bat b2">🦇</div><div class="bat b3">🦇</div>
  <div class="container hero">
    <div class="eyebrow">🎃 Halloween 2026</div>
    <h1>Spookiest <span>Costume</span> Competition</h1>
    <p>Welcome, brave creatures! Explore the contestants, cast your judges' scores, and discover who will claim the Halloween crown.</p>
    <a class="btn" href="#entries">Meet the Contestants</a>
  </div>
</header>

<nav>
  <div class="container">
    <a href="#criteria">Criteria</a><a href="#entries">Contestants</a><a href="#judging">Judging</a><a href="#winner">Winner</a>
  </div>
</nav>

<main>
<section id="criteria">
  <div class="container">
    <h2 class="section-title">Judging Criteria</h2>
    <p class="section-sub">Each category can receive up to 10 points. The maximum total score is 50 points.</p>
    <div class="criteria">
      <div class="criterion"><div class="icon">💡</div><h3>Creativity</h3><p>Originality and imagination.</p></div>
      <div class="criterion"><div class="icon">👻</div><h3>Spookiness</h3><p>How wonderfully spooky is it?</p></div>
      <div class="criterion"><div class="icon">🎨</div><h3>Costume Design</h3><p>Details, effort and presentation.</p></div>
      <div class="criterion"><div class="icon">🎭</div><h3>Presentation</h3><p>Confidence and character.</p></div>
      <div class="criterion"><div class="icon">🕸️</div><h3>Overall Effect</h3><p>The complete Halloween impression.</p></div>
    </div>
  </div>
</section>

<section id="entries">
  <div class="container">
    <h2 class="section-title">Meet the Contestants</h2>
    <p class="section-sub">Replace the sample names, classes and descriptions with your students' details.</p>
    <div class="entries" id="contestants"></div>
  </div>
</section>

<section id="judging">
  <div class="container">
    <h2 class="section-title">Judges' Panel</h2>
    <p class="section-sub">Enter a score from 0–10 for each criterion. Totals update automatically.</p>
    <div class="judge-panel">
      <div class="notice">🔒 <strong>Judge Mode:</strong> Scores are stored only in this browser. They are not uploaded anywhere.</div>
      <div class="judge-controls">
        <button class="btn" onclick="calculateWinner()">🏆 Calculate Winner</button>
        <button class="btn secondary" onclick="resetScores()">↺ Reset Scores</button>
      </div>
      <p class="small" style="text-align:center">Tip: You can print this page from your browser if you want a paper judging sheet.</p>
    </div>
  </div>
</section>

<section id="winner">
  <div class="container">
    <h2 class="section-title">Halloween Crown</h2>
    <div class="winner" id="winnerBox">
      <div class="trophy">🎃</div>
      <h3>Awaiting the judges...</h3>
      <p class="section-sub" style="margin-bottom:0">Enter scores above and click “Calculate Winner”.</p>
    </div>
  </div>
</section>
</main>

<footer>
  <div class="container">
    <strong>🕯️ Spookiest Costume Competition • Halloween 2026</strong>
    <div class="small" style="margin-top:8px">A school Halloween celebration of creativity, imagination and fun.</div>
  </div>
</footer>

<script>
const contestants = [
  {name:"Student 1", cls:"Class 5", emoji:"🧛", desc:"A mysterious creature has entered the competition..."},
  {name:"Student 2", cls:"Class 6", emoji:"🧙", desc:"A magical Halloween look with plenty of character."},
  {name:"Student 3", cls:"Class 7", emoji:"🧟", desc:"Something has escaped from the Halloween laboratory."},
  {name:"Student 4", cls:"Class 8", emoji:"👹", desc:"A bold and wonderfully creepy costume."},
  {name:"Student 5", cls:"Class 9", emoji:"🕷️", desc:"A dark Halloween-inspired creation."},
  {name:"Student 6", cls:"Class 10", emoji:"🎃", desc:"Classic Halloween spirit with a creative twist."},
  {name:"Student 7", cls:"Class 11", emoji:"👻", desc:"A spooky appearance designed to surprise."},
  {name:"Student 8", cls:"Class 12", emoji:"🧟‍♀️", desc:"A carefully designed costume full of details."},
  {name:"Student 9", cls:"Class 6", emoji:"🧛‍♀️", desc:"A mysterious Halloween character comes to life."},
  {name:"Student 10", cls:"Class 7", emoji:"☠️", desc:"A striking costume ready for the Halloween stage."}
];
const criteria = ["Creativity","Spookiness","Costume Design","Presentation","Overall Effect"];

function renderContestants(){
  const root=document.getElementById("contestants");
  root.innerHTML=contestants.map((c,i)=>`
    <article class="card">
      <div class="card-top">
        <div class="avatar">${c.emoji}</div>
        <div class="name">${c.name}<div class="class">${c.cls}</div></div>
        <div class="badge">ENTRY ${i+1}</div>
      </div>
      <p class="desc">${c.desc}</p>
      ${criteria.map((x,j)=>`
        <div class="score-row">
          <label>${x}</label>
          <input type="number" min="0" max="10" value="" placeholder="0" data-i="${i}" data-j="${j}" oninput="updateTotal(${i})">
        </div>`).join("")}
      <div class="total"><span>Total Score</span><strong id="total-${i}">0 / 50</strong></div>
    </article>`).join("");
}
function updateTotal(i){
  const inputs=[...document.querySelectorAll(`input[data-i="${i}"]`)];
  let total=inputs.reduce((sum,x)=>sum+Math.max(0,Math.min(10,Number(x.value)||0)),0);
  document.getElementById(`total-${i}`).textContent=`${total} / 50`;
  saveScores();
}
function saveScores(){
  const scores=[...document.querySelectorAll("input[data-i]")].map(x=>x.value);
  localStorage.setItem("halloweenScores",JSON.stringify(scores));
}
function loadScores(){
  const saved=JSON.parse(localStorage.getItem("halloweenScores")||"[]");
  document.querySelectorAll("input[data-i]").forEach((x,k)=>{if(saved[k]!==undefined)x.value=saved[k];});
  contestants.forEach((_,i)=>updateTotal(i));
}
function resetScores(){
  if(!confirm("Reset all judging scores?")) return;
  localStorage.removeItem("halloweenScores");
  document.querySelectorAll("input[data-i]").forEach(x=>x.value="");
  contestants.forEach((_,i)=>updateTotal(i));
  document.getElementById("winnerBox").innerHTML=`<div class="trophy">🎃</div><h3>Awaiting the judges...</h3><p class="section-sub" style="margin-bottom:0">Enter scores above and click “Calculate Winner”.</p>`;
}
function calculateWinner(){
  const totals=contestants.map((_,i)=>{
    return [...document.querySelectorAll(`input[data-i="${i}"]`)]
      .reduce((s,x)=>s+Math.max(0,Math.min(10,Number(x.value)||0)),0);
  });
  const max=Math.max(...totals);
  if(max===0){alert("Please enter some scores first.");return;}
  const winners=contestants.map((c,i)=>({c,i,total:totals[i]})).filter(x=>x.total===max);
  const box=document.getElementById("winnerBox");
  if(winners.length>1){
    box.innerHTML=`<div class="trophy">🏆</div><h3>It's a Tie!</h3><p>${winners.map(w=>w.c.name).join(" & ")} are tied with <span class="score">${max} / 50</span>.</p><p class="small">The judges can use your school's tie-break procedure.</p>`;
  }else{
    const w=winners[0];
    box.innerHTML=`<div class="trophy">🏆</div><h3>${w.c.emoji} ${w.c.name}</h3><p>${w.c.cls}</p><div class="score">${w.total} / 50 points</div><p class="small" style="margin-top:15px">Congratulations on winning the Spookiest Costume Competition!</p>`;
  }
  document.getElementById("winner").scrollIntoView({behavior:"smooth"});
}
renderContestants();
loadScores();
</script>
</body>
</html>
