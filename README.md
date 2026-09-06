<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>عيد ميلاد سعيد يا يوسف!</title>
  <!-- مكتبة الألعاب النارية -->
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <style>
    body {
      background: linear-gradient(135deg, #1a1a2e, #16213e);
      color: #fff;
      font-family: Arial, sans-serif;
      text-align: center;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
      cursor: pointer;
    }
    .card {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      padding: 40px;
      border-radius: 20px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
    }
    h1 { color: #ff758c; font-size: 2.5rem; margin-bottom: 10px; }
    .name { color: #ffd700; font-size: 2.2rem; font-weight: bold; margin-bottom: 20px; }
    p { font-size: 1.2rem; line-height: 1.6; }
    .hint { font-size: 0.9rem; color: #aaa; margin-top: 20px; }
  </style>
</head>
<body>

  <!-- عنصر الصوت -->
  <audio id="birthdaySong" loop>
    <source src="https://www.bensound.com/bensound-music/bensound-acousticbreeze.mp3" type="audio/mp3">
    متصفحك لا يدعم تشغيل الصوت.
  </audio>

  <div class="card">
    <h1>🎉 عيد ميلاد سعيد 🎂</h1>
    <div class="name">يا يوسف! ✨</div>
    <p>كل عام وأنت بألف خير، أتمنى لك سنة مليئة بالنجاح والسعادة والتحقيق للأحلام!</p>
    <div class="hint">(اضغط في أي مكان على الشاشة لتشغيل الموسيقى وإطلاق الألعاب النارية 🎆)</div>
  </div>

  <script>
    const song = document.getElementById('birthdaySong');
    let isPlaying = false;

    function launchFireworks() {
      confetti({
        particleCount: 100,
        spread: 70,
        origin: { y: 0.6 }
      });
    }

    document.addEventListener('click', function(e) {
      if (!isPlaying) {
        song.play().then(() => {
          isPlaying = true;
        }).catch(error => {
          console.log("المتصفح منع التشغيل التلقائي:", error);
        });
      }

      confetti({
        particleCount: 50,
        spread: 60,
        origin: {
          x: e.clientX / window.innerWidth,
          y: e.clientY / window.innerHeight
        }
      });
    });

    window.onload = function() {
      launchFireworks();
    };
  </script>
</body>
</html>
