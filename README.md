<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>AuraMind AI</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
margin:0;
font-family:Arial;
background:#0f0f12;
color:white;
display:flex;
height:100vh;
}

.sidebar{
width:260px;
background:#1a1a1f;
padding:15px;
box-sizing:border-box;
}

.main{
flex:1;
display:flex;
flex-direction:column;
}

.chat{
flex:1;
padding:20px;
overflow-y:auto;
}

.msg{
margin:10px 0;
padding:12px;
border-radius:10px;
max-width:70%;
word-wrap:break-word;
}

.user{
background:#2d2f3a;
margin-left:auto;
}

.ai{
background:#d46a47;
}

.inputBox{
display:flex;
padding:10px;
background:#1a1a1f;
gap:10px;
}

input{
flex:1;
padding:12px;
border:none;
outline:none;
border-radius:8px;
}

button{
padding:12px 16px;
background:#d46a47;
border:none;
color:white;
border-radius:8px;
cursor:pointer;
}

button:hover{
opacity:0.85;
}

.payment{
background:#111;
padding:15px;
margin-top:20px;
border-radius:10px;
font-size:14px;
}

small{color:#aaa;}
</style>

</head>

<body>

<div class="sidebar">
<h2>AuraMind AI</h2>
<p>Offline AI Chat Website</p>

<div class="payment">
<h3>Premium Info</h3>
<p><b>Name:</b> Hussain Ahmad</p>
<p><b>Number:</b> 03464318737</p>
<p><small>EasyPaisa Payment</small></p>
</div>

</div>

<div class="main">

<div class="chat" id="chat"></div>

<div class="inputBox">
<input id="input" placeholder="Ask something..." onkeydown="enter(event)">
<button onclick="send()">Send</button>
</div>

</div>

<script>

function addMsg(text,type){
const div = document.createElement("div");
div.className = "msg " + type;
div.innerText = text;

let chat = document.getElementById("chat");
chat.appendChild(div);
chat.scrollTop = chat.scrollHeight;
}

/* 🧠 SIMPLE AI BRAIN */
function brain(q){

q = q.toLowerCase();

if(q.includes("boss") || q.includes("creator")){
return "Mera boss Suraqa Ubaid hai 🇵🇰";
}

if(q.includes("python")){
return "Python AI aur web development ke liye use hoti hai.";
}

if(q.includes("html")){
return "HTML website ka structure banata hai.";
}

if(q.includes("css")){
return "CSS design control karta hai.";
}

if(q.includes("javascript")){
return "JavaScript website ko interactive banata hai.";
}

if(q.includes("hello") || q.includes("hi")){
return "Hello 👋 main AuraMind AI hoon!";
}

if(q.includes("what is ai")){
return "AI machines ko smart banata hai jo human jaisa kaam karti hain.";
}

return "Mujhe samajh nahi aaya, simple question pucho.";
}

function send(){

let input = document.getElementById("input");
let text = input.value.trim();

if(!text) return;

addMsg(text,"user");

setTimeout(()=>{
addMsg(brain(text),"ai");
},400);

input.value="";

}

function enter(e){
if(e.key === "Enter"){
send();
}
}

</script>

</body>
</html>
