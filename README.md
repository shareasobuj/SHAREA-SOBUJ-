# SHAREA-SOBUJ

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>SHAREA SOBUJ | Portfolio</title>
  <style>
    *{margin:0;padding:0;box-sizing:border-box;font-family:sans-serif}
    body{background:orchid}
    .hidden{display:none}
    .container{max-width:900px;margin:auto;padding:20px}
    .login-box,.portfolio{background:#fff;padding:20px;border-radius:10px;box-shadow:0 0 10px #ccc;margin-top:40px}
    h2{text-align:center;margin-bottom:20px;color:#333}
    input,button,textarea{width:100%;padding:10px;margin:10px 0;border:1px solid #ccc;border-radius:5px}
    button{background:#007bff;color:white;border:none;cursor:pointer}
    button:hover{background:#0056b3}
    .project{border:1px solid #ddd;padding:10px;border-radius:8px;margin-bottom:15px}
    .project img{width:100%;border-radius:6px;margin-top:10px}
    .profile-pic{width:120px;height:120px;border-radius:50%;object-fit:cover;margin:20px auto;display:block;border:3px solid #007bff}
    nav{text-align:center;margin:10px}
    nav a{margin:0 10px;color:#007bff;text-decoration:none}
    .skills div{margin:10px 0}
    .skills span{font-weight:bold}
    .progress{background:#ddd;height:10px;border-radius:5px;overflow:hidden}
    .progress div{background:#007bff;height:10px}
    .export-btns{display:flex;gap:10px;flex-wrap:wrap;margin-top:20px}
  </style>
</head>
<body>

<div class="container">
  <!-- Login -->
  <div class="login-box" id="loginBox">
    <h2>Login to view Portfolio</h2>
    <input type="email" placeholder="Enter email" id="email" required />
    <input type="password" placeholder="Enter password" id="password" required />
    <button onclick="login()">Login</button>
    <p style="text-align:center">Default: sobuj@example.com | 123456</p>
  </div>

  <!-- Portfolio -->
  <div class="portfolio hidden" id="portfolio">
    <img src="1747646682277 (1) (1) (3).jpg" alt="Profile Picture" class="profile-pic" />
    <h2>SHAREA SOBUJ</h2>
    <p style="text-align:center;color:#555">Web Developer | Ethical Hacker | Freelancer</p>

    <nav>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </nav>

    <hr><h3 id="projects">Projects</h3>
    <div class="project">
      <h4>🧮 Calculator App</h4>
      <p>Basic calculator using JavaScript</p>
      <a href="https://shareasobuj.github.io/CalculatorApp/" target="_blank">Live Demo</a>
      <img src="https://via.placeholder.com/400x150?text=Calculator+App" />
    </div>

    <div class="project">
      <h4>📝 To-Do List</h4>
      <p>Task management web app</p>
      <a href="https://shareasobuj.github.io/TodoApp/" target="_blank">Live Demo</a>
      <img src="https://via.placeholder.com/400x150?text=To-Do+App" />
    </div>

    <div class="project">
      <h4>🧠 MindBridge AI</h4>
      <p>AI-powered mental health support</p>
      <a href="https://shareasobuj.github.io/MindBridge/" target="_blank">Live Demo</a>
      <img src="https://via.placeholder.com/400x150?text=MindBridge+AI" />
    </div>

    <hr><h3 id="skills">Skills</h3>
    <div class="skills">
      <div><span>HTML:</span><div class="progress"><div style="width:95%"></div></div></div>
      <div><span>CSS:</span><div class="progress"><div style="width:90%"></div></div></div>
      <div><span>JavaScript:</span><div class="progress"><div style="width:85%"></div></div></div>
      <div><span>Firebase:</span><div class="progress"><div style="width:80%"></div></div></div>
      <div><span>React:</span><div class="progress"><div style="width:75%"></div></div></div>
    </div>

    <hr><h3 id="contact">Contact Me</h3>
    <p>Email: <a href="mailto:shareasobuj9829@gmail.com">shareasobuj9829@gmail.com</a></p>
    <p>GitHub: <a href="https://github.com/shareasobuj" target="_blank">github.com/shareasobuj</a></p>

    <hr>
    <div class="export-btns">
      <button onclick="downloadCSV()">Download CSV</button>
      <button onclick="window.print()">Print as PDF</button>
      <button onclick="logout()">Logout</button>
    </div>
  </div>
</div>

<script>
  function login(){
    const email = document.getElementById("email").value;
    const password = document.getElementById("password").value;
    if(email === "sobuj@example.com" && password === "123456"){
      document.getElementById("loginBox").classList.add("hidden");
      document.getElementById("portfolio").classList.remove("hidden");
    }else{
      alert("Incorrect email or password!");
    }
  }

  function logout(){
    document.getElementById("portfolio").classList.add("hidden");
    document.getElementById("loginBox").classList.remove("hidden");
  }

  function downloadCSV(){
    const csv = `Project,Description,Link
Calculator App,Basic calculator using JS,https://shareasobuj.github.io/CalculatorApp/
To-Do List,Task app with JS,https://shareasobuj.github.io/TodoApp/
MindBridge AI,AI mental health,https://shareasobuj.github.io/MindBridge/`;
    const blob = new Blob([csv], {type: 'text/csv'});
    const link = document.createElement('a');
    link.href = URL.createObjectURL(blob);
    link.download = "projects.csv";
    link.click();
  }
</script>

</body>
</html>
