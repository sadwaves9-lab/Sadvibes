# Sadvibes
My practice html class notes
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<title>StudyCare</title><style>

body{
margin:0;
font-family:Arial,Helvetica,sans-serif;
background:linear-gradient(135deg,#4facfe,#00f2fe);
height:100vh;
overflow:hidden;
}

.dark{
background:#111;
color:white;
}

#loginPage{
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

.login-box{
background:white;
padding:40px;
border-radius:12px;
width:320px;
box-shadow:0 10px 30px rgba(0,0,0,0.3);
text-align:center;
}

.login-box h1{
margin-bottom:20px;
}

input{
width:100%;
padding:12px;
margin:10px 0;
border-radius:8px;
border:1px solid #ccc;
}

button{
padding:12px;
border:none;
border-radius:8px;
background:#4facfe;
color:white;
width:100%;
cursor:pointer;
font-size:16px;
}

button:hover{
background:#2196f3;
}

#dashboard{
display:none;
height:100vh;
}

header{
background:#222;
color:white;
padding:20px;
display:flex;
justify-content:space-between;
align-items:center;
}

.sidebar{
width:220px;
background:#333;
height:100%;
position:fixed;
top:0;
left:0;
padding-top:70px;
}

.sidebar button{
width:100%;
border:none;
background:none;
color:white;
padding:15px;
text-align:left;
font-size:16px;
cursor:pointer;
}

.sidebar button:hover{
background:#444;
}

.content{
margin-left:220px;
padding:30px;
height:100%;
overflow:auto;
}

.card-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:20px;
}

.card{
background:white;
padding:30px;
border-radius:10px;
box-shadow:0 5px 15px rgba(0,0,0,0.2);
cursor:pointer;
transition:0.3s;
}

.card:hover{
transform:scale(1.05);
}

.section{
display:none;
}

.section.active{
display:block;
}

.quiz-box{
background:#fff;
padding:20px;
border-radius:10px;
max-width:500px;
}

.dark .card{
background:#222;
color:white;
}

.dark .sidebar{
background:#111;
}

.dark header{
background:#000;
}

</style><script>

function login(){

let u=document.getElementById("user").value;
let p=document.getElementById("pass").value;

if(u==="admin" && p==="1234"){

document.getElementById("loginPage").style.display="none";
document.getElementById("dashboard").style.display="block";

}else{

alert("Wrong username or password");

}

}

function openSection(id){

let sections=document.querySelectorAll(".section");

sections.forEach(s=>s.classList.remove("active"));

document.getElementById(id).classList.add("active");

}

function toggleDark(){

document.body.classList.toggle("dark");

}

function checkQuiz(){

let ans=document.querySelector('input[name="q1"]:checked');

if(!ans){

alert("Select answer");

return;

}

if(ans.value==="correct"){

alert("Correct!");

}else{

alert("Wrong!");

}

}

</script></head><body><div id="loginPage"><div class="login-box"><h1>StudyCare</h1><input id="user" placeholder="Username"><input id="pass" type="password" placeholder="Password"><button onclick="login()">Login</button>

</div></div><div id="dashboard"><header><div>StudyCare Dashboard</div><button onclick="toggleDark()">Dark Mode</button>

</header><div class="sidebar"><button onclick="openSection('home')">Home</button>
<button onclick="openSection('html')">HTML Learning</button>
<button onclick="openSection('css')">CSS Learning</button>
<button onclick="openSection('js')">JavaScript</button>
<button onclick="openSection('notes')">Notes</button>
<button onclick="openSection('quiz')">Quiz</button>
<button onclick="openSection('videos')">Videos</button>
<button onclick="openSection('projects')">Projects</button>
<button onclick="openSection('about')">About</button>

</div><div class="content"><div id="home" class="section active"><h2>Welcome to StudyCare</h2><div class="card-grid"><div class="card">Learn HTML</div>
<div class="card">Learn CSS</div>
<div class="card">Learn JavaScript</div>
<div class="card">Programming</div>
<div class="card">Practice Questions</div>
<div class="card">Mock Tests</div>
<div class="card">Study Notes</div>
<div class="card">Projects</div></div></div><div id="html" class="section"><h2>HTML Learning</h2><p>HTML is used to create websites structure.</p><pre>
&lt;html&gt;
&lt;head&gt;
&lt;title&gt;Page&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
Hello World
&lt;/body&gt;
&lt;/html&gt;
</pre></div><div id="css" class="section"><h2>CSS Learning</h2><p>CSS is used to style websites.</p><pre>
body{
background:red;
color:white;
}
</pre></div><div id="js" class="section"><h2>JavaScript</h2><button onclick="alert('Hello from JavaScript!')">Run JS</button>

</div><div id="notes" class="section"><h2>Study Notes</h2><ul>
<li>HTML Basics</li>
<li>CSS Layout</li>
<li>JavaScript Functions</li>
<li>DOM Manipulation</li>
</ul></div><div id="quiz" class="section"><h2>Quick Quiz</h2><div class="quiz-box"><p>HTML stands for?</p><label>
<input type="radio" name="q1"> Hyper Trainer Marking Language
</label><br><br>

<label>
<input type="radio" name="q1" value="correct"> Hyper Text Markup Language
</label><br><br>

<label>
<input type="radio" name="q1"> Hyper Text Marketing Language
</label><br><br>

<button onclick="checkQuiz()">Submit</button>

</div></div><div id="videos" class="section"><h2>Video Tutorials</h2><p>You can embed YouTube videos here.</p></div><div id="projects" class="section"><h2>Projects</h2><ul>
<li>Portfolio Website</li>
<li>Calculator App</li>
<li>Todo List</li>
<li>Weather App</li>
</ul></div><div id="about" class="section"><h2>About StudyCare</h2><p>StudyCare is a learning platform for coding and web development.</p></div></div></div></body>
</html>
