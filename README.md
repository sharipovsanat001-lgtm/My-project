<!DOCTYPE html>
<html lang="uz"> 
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sharipov Sanat | Full Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css"> 
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800&display=swap" rel="stylesheet">  
    <style>
        /* --- ASOSIY STILLAR --- */  
        * {  
            margin: 0; 
            padding: 0; 
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }
 
        body {
            background-color: #020617; 
            color: #ffffff;
            overflow-x: hidden;
        }

        #bg-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .floating-shape {
            position: absolute;
            background: rgba(0, 188, 212, 0.1);
            border: 1px solid rgba(0, 188, 212, 0.2);
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            transition: transform 0.2s ease-out;
        }

        header {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 1100px;
            padding: 15px 30px;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
        }

        #progress-bar {
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            height: 2px;
            width: 0%;
            background: #00bcd4;
            transition: width 0.1s;
        }

        .logo { font-size: 1.4rem; font-weight: 800; color: #00bcd4; }
        nav { display: flex; gap: 20px; }
        nav a { color: white; text-decoration: none; font-size: 0.9rem; font-weight: 500; transition: 0.3s; }
        nav a:hover { color: #00bcd4; }

        section {
            padding: 150px 10% 80px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 40px;
            border-left: 5px solid #00bcd4;
            padding-left: 15px;
        }

        #home { text-align: center; }
        #home h1 { font-size: 4rem; margin-bottom: 10px; }
        #home p { font-size: 1.5rem; color: #00bcd4; }

        /* --- ABOUT --- */
        .profile-circle {
            width: 200px;
            height: 200px;
            border: 3px dashed #00bcd4;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            overflow: hidden;
            background: rgba(0, 188, 212, 0.05);
            margin-bottom: 20px;
        }

        #user-photo { width: 100%; height: 100%; object-fit: cover; display: none; }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .stat-card {
            background: rgba(255,255,255,0.05);
            padding: 15px;
            border-radius: 12px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        /* --- PORTFOLIO --- */
        .upload-area {
            border: 2px dashed #00bcd4;
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            background: rgba(0, 188, 212, 0.05);
            cursor: pointer;
            transition: 0.3s;
            margin-bottom: 40px;
        }

        .upload-area:hover { background: rgba(0, 188, 212, 0.1); }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 20px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            position: relative;
            transition: 0.3s;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: #00bcd4;
            background: rgba(0, 188, 212, 0.05);
        }

        .project-card i { font-size: 3rem; color: #00bcd4; margin-bottom: 15px; }
        
        .project-card h4 { 
            font-size: 0.9rem; 
            margin-bottom: 10px; 
            white-space: nowrap; 
            overflow: hidden; 
            text-overflow: ellipsis; 
        }

        .remove-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #ff4d4d;
            color: white;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 12px;
            z-index: 5;
        }

        /* --- SKILLS --- */
        .skills-wrap { display: flex; gap: 15px; flex-wrap: wrap; }
        .skill-box {
            padding: 10px 25px;
            background: rgba(0, 188, 212, 0.1);
            border: 1px solid #00bcd4;
            border-radius: 10px;
            font-weight: 600;
        }

        footer { text-align: center; padding: 40px; border-top: 1px solid rgba(255,255,255,0.05); }

    </style>
</head>
<body>

    <div id="bg-shapes"></div>

    <header>
        <div class="logo">SANAT</div>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#portfolio">Portfolio</a>
            <a href="#skills">Skills</a>
        </nav>
        <div id="progress-bar"></div>
    </header>

    <section id="home">
        <h1>Salom, Men <span style="color: #00bcd4;">Sharipov Sanat</span></h1>
        <p>Frontend Developer</p>
    </section>

    <section id="about">
        <h2 class="section-title">Men Haqimda</h2>
        <div style="display: flex; flex-wrap: wrap; gap: 40px; align-items: center;">
            <div class="profile-circle" onclick="document.getElementById('p-input').click()">
                <div id="p-text"><i class="fas fa-camera"></i><br>Rasm</div>
                <img id="user-photo">
            </div>
            <div style="flex: 1;">
                <p>Men kreativ veb-interfeyslar yaratuvchi dasturchiman.</p>
                <div class="stats-grid">
                    <div class="stat-card"><h4>Tajriba</h4><p>1+ yil</p></div>
                    <div class="stat-card"><h4>Loyihalar</h4><p>10+ ta</p></div>
                </div>
            </div>
        </div>
        <input type="file" id="p-input" hidden onchange="uploadProfile(this)">
    </section>

    <section id="portfolio">
        <h2 class="section-title">Mening Loyihalarim</h2>
        
        <div class="upload-area" onclick="document.getElementById('f-input').click()">
            <i class="fas fa-folder-plus" style="font-size: 3rem; color: #00bcd4; margin-bottom: 10px;"></i>
            <h3>Loyiha fayllarini yuklang</h3>
            <p>(Fayllar xotirada saqlanib qoladi)</p>
            <input type="file" id="f-input" multiple hidden onchange="handleFiles(this.files)">
        </div>

        <div class="project-grid" id="project-list"></div>
    </section>

    <section id="skills">
        <h2 class="section-title">Ko'nikmalar</h2>
        <div class="skills-wrap">
            <div class="skill-box">HTML5</div>
            <div class="skill-box">CSS3</div>
            <div class="skill-box">JavaScript</div>
            <div class="skill-box">Responsive Design</div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 SHARIPOV SANAT</p>
    </footer>

    <script>
        // --- 1. LOCALSTORAGE DAN MA'LUMOTLARNI YUKLASH ---
        window.onload = () => {
            // Saqlangan profil rasmini yuklash
            const savedPhoto = localStorage.getItem('userPhoto');
            if (savedPhoto) {
                const img = document.getElementById('user-photo');
                img.src = savedPhoto;
                img.style.display = 'block';
                document.getElementById('p-text').style.display = 'none';
            }

            // Saqlangan loyihalarni yuklash
            const savedProjects = JSON.parse(localStorage.getItem('myProjects') || '[]');
            savedProjects.forEach(proj => createProjectCard(proj.name, proj.type, proj.id));
        };

        // --- 2. PROFIL RASMINI SAQLASH ---
        function uploadProfile(input) {
            const file = input.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = (e) => {
                    const base64 = e.target.result;
                    document.getElementById('user-photo').src = base64;
                    document.getElementById('user-photo').style.display = 'block';
                    document.getElementById('p-text').style.display = 'none';
                    
                    // LocalStoragega saqlash
                    localStorage.setItem('userPhoto', base64);
                };
                reader.readAsDataURL(file);
            }
        }

        // --- 3. LOYIHALARNI BOSHQARISH ---
        function handleFiles(files) {
            const currentProjects = JSON.parse(localStorage.getItem('myProjects') || '[]');
            
            Array.from(files).forEach(file => {
                const projectId = Date.now() + Math.random(); // Noyob ID
                const projectData = {
                    id: projectId,
                    name: file.name,
                    type: file.type
                };

                currentProjects.push(projectData);
                createProjectCard(projectData.name, projectData.type, projectData.id);
            });

            localStorage.setItem('myProjects', JSON.stringify(currentProjects));
        }

        function createProjectCard(name, type, id) {
            const list = document.getElementById('project-list');
            const card = document.createElement('div');
            card.className = 'project-card';
            card.setAttribute('data-id', id);
            
            let iconClass = "fa-file-alt";
            if(type.startsWith('image/')) iconClass = "fa-file-image";
            if(name.endsWith('.html')) iconClass = "fa-code";

            card.innerHTML = `
                <button class="remove-btn" onclick="removeProject(${id})">X</button>
                <i class="fas ${iconClass}"></i>
                <h4 title="${name}">${name}</h4>
                <p style="color: #00bcd4; font-size: 0.8rem;">Loyiha fayli</p>
            `;
            list.appendChild(card);
        }

        function removeProject(id) {
            // Ekrandan o'chirish
            const card = document.querySelector(`[data-id="${id}"]`);
            if(card) card.remove();

            // LocalStoragedan o'chirish
            let currentProjects = JSON.parse(localStorage.getItem('myProjects') || '[]');
            currentProjects = currentProjects.filter(p => p.id != id);
            localStorage.setItem('myProjects', JSON.stringify(currentProjects));
        }

        // --- 4. DEKORATIV VA FON FUNKSIYALARI ---
        const container = document.getElementById('bg-shapes');
        for (let i = 0; i < 15; i++) {
            const shape = document.createElement('div');
            shape.className = 'floating-shape';
            shape.style.width = Math.random() * 100 + 50 + 'px';
            shape.style.height = shape.style.width;
            shape.style.left = Math.random() * 100 + '%';
            shape.style.top = Math.random() * 100 + '%';
            container.appendChild(shape);
        }

        window.onscroll = () => {
            let winScroll = document.documentElement.scrollTop;
            let height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            document.getElementById("progress-bar").style.width = (winScroll / height) * 100 + "%";
        };
    </script>
</body>
</html>
