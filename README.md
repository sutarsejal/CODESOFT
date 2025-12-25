# CODESOFT
Internship level task in codesoft, 'A Calculator'.

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Calculator</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family: Arial, Helvetica, sans-serif;
}

body{
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:linear-gradient(135deg,#1e293b,#0f172a);
}

.calculator{
  width:300px;
  background:#0f172a;
  padding:20px;
  border-radius:10px;
  box-shadow:0 10px 25px rgba(0,0,0,0.4);
}

.display{
  width:100%;
  height:60px;
  background:#020617;
  color:#38bdf8;
  text-align:right;
  font-size:28px;
  padding:10px;
  border-radius:6px;
  margin-bottom:15px;
  overflow:hidden;
}

.buttons{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:10px;
}

button{
  padding:15px;
  font-size:18px;
  border:none;
  border-radius:6px;
  cursor:pointer;
}

.number{
  background:#1e293b;
  color:#fff;
}

.operator{
  background:#38bdf8;
  color:#000;
}

.clear{
  background:#ef4444;
  color:#fff;
}

.equal{
  background:#22c55e;
  color:#fff;
  grid-column:span 2;
}

button:hover{
  opacity:0.85;
}
</style>
</head>

<body>

<div class="calculator">
  <div class="display" id="display">0</div>

  <div class="buttons">
    <button class="clear" onclick="clearDisplay()">C</button>
    <button class="operator" onclick="append('/')">÷</button>
    <button class="operator" onclick="append('*')">×</button>
    <button class="operator" onclick="append('-')">−</button>

    <button class="number" onclick="append('7')">7</button>
    <button class="number" onclick="append('8')">8</button>
    <button class="number" onclick="append('9')">9</button>
    <button class="operator" onclick="append('+')">+</button>

    <button class="number" onclick="append('4')">4</button>
    <button class="number" onclick="append('5')">5</button>
    <button class="number" onclick="append('6')">6</button>

    <button class="number" onclick="append('1')">1</button>
    <button class="number" onclick="append('2')">2</button>
    <button class="number" onclick="append('3')">3</button>

    <button class="number" onclick="append('0')">0</button>
    <button class="number" onclick="append('.')">.</button>
    <button class="equal" onclick="calculate()">=</button>
  </div>
</div>

<script>
let display = document.getElementById("display");

function append(value){
  if(display.innerText === "0"){
    display.innerText = value;
  }else{
    display.innerText += value;
  }
}

function clearDisplay(){
  display.innerText = "0";
}

function calculate(){
  try{
    display.innerText = eval(display.innerText);
  }catch{
    display.innerText = "Error";
  }
}
</script>

</body>
</html>
