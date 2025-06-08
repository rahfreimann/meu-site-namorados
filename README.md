<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Dia dos Namorados 💘</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Arial', cursive;
    }

    body {
      background: linear-gradient(to bottom right, #ff060a, #360202);
      color: white;
      text-align: center;
      overflow-x: hidden;
      position: relative;
      height: 100vh;
      z-index: 1;
    }

    section {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    h1 {
      margin-bottom: 30px;
      font-size: 2em;
      text-shadow: 2px 2px #c0392b;
    }

    .btn {
      padding: 15px 30px;
      font-size: 1.2em;
      border: none;
      border-radius: 30px;
      margin: 10px;
      cursor: pointer;
      transition: 0.3s;
      background-color: white;
      color: red;
      width: 140px;
    }

    .btn:hover {
      background-color: #ffcccc;
    }

    #noBtn {
      position: absolute;
    }

    .envelope-box {
      margin: 40px auto;
      width: 200px;
      height: 120px;
      position: relative;
      cursor: pointer;
      background: white;
      border: 2px solid red;
      border-radius: 20px;
      box-shadow: 0 0 10px white;
      overflow: hidden;
    }

    .flap {
      position: absolute;
      top: -60px;
      left: 0;
      width: 0;
      height: 0;
      border-left: 100px solid transparent;
      border-right: 100px solid transparent;
      border-bottom: 60px solid red;
    }

    .heart {
      font-size: 30px;
      color: red;
      margin-top: 30px;
    }

    .letter {
      display: none;
      margin-top: 30px;
      background: white;
      color: red;
      padding: 20px;
      border-radius: 15px;
      width: 80%;
      margin-left: auto;
      margin-right: auto;
      box-shadow: 0 0 15px white;
    }

    .heart-float {
  position: fixed;
  color: red;
  font-size: 30px;
  animation: float 6s linear infinite;
  opacity: 0.8;
  pointer-events: none;
  z-index: 0;
}


    @keyframes float {
      0% {
        transform: translateY(100vh) scale(0.8);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- Música de fundo -->
  <iframe style="display:none;" src="https://www.youtube.com/embed/VWRkQARH-9o?autoplay=1&loop=1&playlist=VWRkQARH-9o" allow="autoplay"></iframe>

  <!-- Página Inicial -->
  <section id="inicio">
    <h1>Aceita passar todos os dias de sua vida comigo? 💘</h1>
    <div style="position: relative;">
      <button class="btn" onclick="mostrarSegundaParte()">Sim 💘</button>
      <button class="btn" id="noBtn">Não 😢</button>
    </div>
  </section>

  <!-- Segunda Parte -->
  <section id="segunda" style="display:none;">
    <div class="envelope-box" onclick="abrirCarta()">
      <div class="flap"></div>
      <div class="heart">💌</div>
    </div>
    <div class="letter" id="carta">
      <p>Você é o amor da minha vida! 💖</p>
      <p>Amor, hoje é Dia dos Namorados e eu não consigo parar de pensar em você. Cada momento ao seu lado é um presente que eu agradeço todos os dias. Você é minha paz, meu sorriso fácil, minha loucura boa. Com você, tudo faz sentido até as coisas mais simples ficam incríveis porque a gente vive junto.</p>
      <p>Quero continuar amando você do jeitinho que a gente é: intenso, verdadeiro, bagunçado, perfeito.</p>
      <p>Te amo mais do que as palavras conseguem dizer, e vou amar sempre. 💖</p>
    </div>
  </section>

  <!-- CORAÇÕES -->
  <script>
    // Botão "Não" foge
    const noBtn = document.getElementById("noBtn");
    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - 150);
      const y = Math.random() * (window.innerHeight - 50);
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });

    // Mostrar segunda parte
    function mostrarSegundaParte() {
      alert("Esse site diz: VOCÊ É O AMOR DA MINHA VIDA! ❤️");
      document.getElementById("segunda").style.display = "flex";
      document.getElementById("segunda").scrollIntoView({ behavior: 'smooth' });
    }

    // Mostrar carta
    function abrirCarta() {
      document.getElementById("carta").style.display = "block";
    }

    // CORAÇÕES CAINDO
    function criarCoracoes() {
      const heart = document.createElement('div');
      heart.classList.add('heart-float');
      heart.innerText = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (3 + Math.random() * 3) + 's';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }

    setInterval(criarCoracoes, 500);
  </script>
</body>
</html>
