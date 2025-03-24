 <!DOCTYPE html>
<html lang="zh-CN">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript 演示</title>
  <style>
    button {
      display: block;
      margin: 20px auto;
    }

    #time-display {
      text-align: center;
      margin-top: 50px;
    }

    #returnButton {
      display: none;
    }

    #randomColorButton {
      display: none;
    }
  </style>
</head>

<body>
  <button id="originalButton">弹出对话框并执行操作</button>
  <div id="time-display"></div>
  <button id="returnButton">回到原来位置</button>
  <button id="randomColorButton">随机改变背景颜色</button>

  <script>
    const originalButton = document.getElementById('originalButton');
    const returnButton = document.getElementById('returnButton');
    const timeDisplay = document.getElementById('time-display');
    const randomColorButton = document.getElementById('randomColorButton');

    function showAlertAndChange() {
      originalButton.style.display = 'none';
      returnButton.style.display = 'block';
      randomColorButton.style.display = 'block';
      alert("这是一个弹出对话框演示");
      document.body.style.backgroundColor = "lightblue";
      const now = new Date();
      const currentTime = now.toLocaleString();
      timeDisplay.innerHTML = "当前时间是：" + currentTime;
    }

    function goBackToOriginal() {
      document.location.reload();
    }

    function getRandomHexChar() {
      const hexChars = '0123456789ABCDEF';
      return hexChars[Math.floor(Math.random() * 16)];
    }

    function getRandomColor() {
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += getRandomHexChar();
      }
      return color;
    }

    function changeBackgroundColor() {
      const randomColor = getRandomColor();
      document.body.style.backgroundColor = randomColor;
    }

    originalButton.addEventListener('click', showAlertAndChange);
    returnButton.addEventListener('click', goBackToOriginal);
    randomColorButton.addEventListener('click', changeBackgroundColor);
  </script>
</body>

</html>


