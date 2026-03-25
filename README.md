<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Кнопка с попапом</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #f2f2f2;
    }

    .btn {
      padding: 15px 25px;
      font-size: 18px;
      border: none;
      border-radius: 12px;
      background: #4CAF50;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    .btn:active {
      transform: scale(0.95);
    }

    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
      text-align: center;
      width: 80%;
      max-width: 300px;
      transition: 0.3s;
    }

    .popup.active {
      transform: translate(-50%, -50%) scale(1);
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.4);
      opacity: 0;
      pointer-events: none;
      transition: 0.3s;
    }

    .overlay.active {
      opacity: 1;
      pointer-events: all;
    }

    @media (max-width: 480px) {
      .btn {
        font-size: 16px;
        padding: 12px 20px;
      }

      .popup {
        width: 90%;
        font-size: 14px;
      }
    }
  </style>
</head>
<body>

  <button class="btn" onclick="openPopup()">Нажмите, чтоб узнать кто самый красивый в мире</button>

  <div class="overlay" id="overlay" onclick="closePopup()"></div>

  <div class="popup" id="popup">
    <p>Ты :)</p>
    <br>
    <button class="btn" onclick="closePopup()">Закрыть</button>
  </div>

  <script>
    function openPopup() {
      document.getElementById('popup').classList.add('active');
      document.getElementById('overlay').classList.add('active');
    }

    function closePopup() {
      document.getElementById('popup').classList.remove('active');
      document.getElementById('overlay').classList.remove('active');
    }
  </script>

</body>
</html>
