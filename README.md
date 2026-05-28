# ePortfolio.v2
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>John Smith | Cybersecurity ePortfolio</title>
  <style>
    :root{
      --bg:#05070d;
      --panel:#0b1220;
      --panel-2:#0f1728;
      --text:#d8ffe9;
      --muted:#8fbfa5;
      --neon:#00ff9c;
      --neon-2:#00d9ff;
    }

    *{
      box-sizing:border-box;
      margin:0;
      padding:0;
    }

    html{
      scroll-behavior:smooth;
    }

    body{
      font-family:"Courier New", monospace;
      background:
        radial-gradient(circle at top, rgba(0,255,156,0.08), transparent 30%),
        radial-gradient(circle at bottom right, rgba(0,217,255,0.08), transparent 25%),
        linear-gradient(180deg, #03050a 0%, #07111b 100%);
      color:var(--text);
      line-height:1.6;
      overflow-x:hidden;
    }

    body::before{
      content:"";
      position:fixed;
      inset:0;
      pointer-events:none;
      background:
        repeating-linear-gradient(
          to bottom,
          rgba(255,255,255,0.03) 0px,
          rgba(255,255,255,0.03) 1px,
          transparent 2px,
          transparent 4px
        );
      opacity:0.08;
      z-index:999;
    }

    header{
      position:sticky;
      top:0;
      z-index:100;
      backdrop-filter:blur(10px);
      background:rgba(5, 10, 18, 0.82);
      border-bottom:1px solid rgba(0,255,156,0.25);
      box-shadow:0 0 18px rgba(0,255,156,0.08);
    }

    nav{
      max-width:1150px;
      margin:auto;
      padding:18px 20px;
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:16px;
      flex-wrap:wrap;
    }

    .logo{
      color:var(--neon);
      font-weight:700;
      font-size:1.15rem;
      text-shadow:0 0 8px rgba(0,255,156,0.65);
      letter-spacing:1px;
    }

    nav ul{
      list-style:none;
      display:flex;
      gap:18px;
      flex-wrap:wrap;
    }

    nav a{
      color:var(--text);
      text-decoration:none;
      font-size:0.95rem;
      transition:0.25s ease;
    }

    nav a:hover{
      color:var(--neon);
      text-shadow:0 0 8px rgba(0,255,156,0.7);
    }

    .hero{
      min-height:100vh;
      display:grid;
      place-items:center;
      padding:70px 20px 40px;
      position:relative;
    }

    .hero-box{
      width:min(980px, 100%);
      background:rgba(10,17,28,0.75);
      border:1px solid rgba(0,255,156,0.25);
      border-radius:18px;
      padding:40px 28px;
      box-shadow:
        0 0 25px rgba(0,255,156,0.12),
        inset 0 0 25px rgba(0,255,156,0.03);
      position:relative;
      overflow:hidden;
    }

    .hero-box::before{
      content:"ACCESS GRANTED";
      position:absolute;
      top:14px;
      right:18px;
      font-size:0.75rem;
      color:var(--neon);
      opacity:0.75;
      letter-spacing:2px;
    }

    .terminal-line{
      color:var(--muted);
      margin-bottom:12px;
      font-size:0.95rem;
    }

    .hero h1{
      font-size:clamp(2.1rem, 5vw, 4.2rem);
      color:var(--neon);
      text-shadow:
        0 0 8px rgba(0,255,156,0.9),
        0 0 24px rgba(0,255,156,0.25);
      margin-bottom:14px;
    }

    .hero h2{
      font-size:clamp(1rem, 2vw, 1.4rem);
      color:#cffff0;
      margin-bottom:16px;
      font-weight:400;
    }

    .hero p{
      max-width:720px;
      color:#b8e7d0;
      margin-bottom:24px;
    }

    .btn-group{
      display:flex;
      gap:14px;
      flex-wrap:wrap;
    }

    .btn{
      display:inline-block;
      padding:12px 20px;
      border-radius:10px;
      text-decoration:none;
      font-weight:700;
      letter-spacing:0.5px;
      transition:0.25s ease;
      border:1px solid var(--neon);
    }

    .btn-primary{
      background:var(--neon);
      color:#03120b;
      box-shadow:0 0 18px rgba(0,255,156,0.35);
    }

    .btn-primary:hover{
      transform:translateY(-2px);
      box-shadow:0 0 30px rgba(0,255,156,0.55);
    }

    .btn-secondary{
      color:var(--neon);
      background:transparent;
    }

    .btn-secondary:hover{
      background:rgba(0,255,156,0.08);
      box-shadow:0 0 20px rgba(0,255,156,0.18);
    }

    main{
      max-width:1150px;
      margin:auto;
      padding:0 20px 50px;
    }

    section{
      margin:30px 0;
      padding:30px 24px;
      background:rgba(11,18,32,0.82);
      border:1px solid rgba(0,255,156,0.18);
      border-radius:16px;
      box-shadow:0 0 18px rgba(0,255,156,0.06);
    }

    section h3{
      color:var(--neon);
      margin-bottom:18px;
      font-size:1.5rem;
      text-shadow:0 0 10px rgba(0,255,156,0.25);
    }

    .cards{
      display:grid;
      grid-template-columns:repeat(auto-fit, minmax(240px, 1fr));
      gap:18px;
    }

    .card{
      background:linear-gradient(180deg, rgba(13,24,38,0.95), rgba(8,15,25,0.92));
      border:1px solid rgba(0,255,156,0.16);
      border-radius:14px;
      padding:18px;
      transition:0.25s ease;
      box-shadow:inset 0 0 18px rgba(0,255,156,0.02);
    }

    .card:hover{
      transform:translateY(-5px);
      border-color:rgba(0,255,156,0.45);
      box-shadow:0 0 22px rgba(0,255,156,0.12);
    }

    .card h4{
      color:#e8fff4;
      margin-bottom:10px;
    }

    .card p, .card li{
      color:#a8d8c1;
      font-size:0.96rem;
    }

    .card ul{
      padding-left:18px;
    }

    .contact-list{
      display:grid;
      gap:10px;
    }

    .contact-list a{
      color:var(--neon);
      text-decoration:none;
    }

    footer{
      text-align:center;
      padding:24px;
      color:#7fb59e;
      border-top:1px solid rgba(0,255,156,0.15);
      margin-top:24px;
    }

    .blink{
      animation:blink 1s step-end infinite;
    }

    @keyframes blink{
      50%{opacity:0;}
    }
  </style>
</head>
<body>
  <header>
    <nav>
      <div class="logo">root@johnsmith:~$</div>
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#certifications">Certifications</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section class="hero">
    <div class="hero-box">
      <div class="terminal-line">Initializing secure portfolio session...</div>
      <h1>John Smith<span class="blink">_</span></h1>
      <h2>Cybersecurity Analyst Candidate | CIS Lab Technician | Security+ Certified</h2>
      <p>
        Entry-level cybersecurity candidate with a bachelor’s degree in Computer and Information Science and hands-on experience supporting cybersecurity and networking labs, troubleshooting Windows and Linux systems, and configuring foundational network services.
      </p>
      <div class="btn-group">
        <a class="btn btn-primary" href="#projects">View Projects</a>
        <a class="btn btn-secondary" href="#contact">Contact Me</a>
      </div>
    </div>
  </section>

  <main>
    <section id="about">
      <h3>About Me</h3>
      <p>
        I am an entry-level cybersecurity professional with hands-on academic and lab experience in network security, packet analysis, firewall administration, virtualization, and basic scripting. I hold CompTIA A+ and Security+ certifications and am seeking opportunities in cybersecurity analysis, SOC operations, junior security administration, or information security.
      </p>
    </section>

    <section id="skills">
      <h3>Technical Skills</h3>
      <div class="cards">
        <div class="card">
          <h4>Security Tools</h4>
          <p>Wireshark, Kali Linux, pfSense, Cisco Packet Tracer, PuTTY, VMware Workstation</p>
        </div>
        <div class="card">
          <h4>Systems & Platforms</h4>
          <p>Windows 10/11, Windows Server, Linux, macOS, Microsoft 365</p>
        </div>
        <div class="card">
          <h4>Networking & Security</h4>
          <p>TCP/IP, routing and switching, VLANs, subnetting, DHCP, NAT, packet analysis, firewall configuration, workstation hardening</p>
        </div>
        <div class="card">
          <h4>Scripting & CLI</h4>
          <p>Python, PowerShell, CMD, Bash, Git/GitHub</p>
        </div>
        <div class="card">
          <h4>Compliance</h4>
          <p>HIPAA data handling</p>
        </div>
      </div>
    </section>

    <section id="experience">
      <h3>Experience</h3>
      <div class="cards">
        <div class="card">
          <h4>CIS Lab Technician</h4>
          <p><strong>ECPI University | Manassas, VA | Jul 2022 - Present</strong></p>
          <ul>
            <li>Configure and maintain routers, switches, PCs, and lab workstations used for cybersecurity and networking instruction.</li>
            <li>Provide front-line technical support for students and faculty by troubleshooting hardware, software, Windows, and basic network connectivity issues.</li>
            <li>Assist with lab exercises involving subnetting, VLAN configuration, packet analysis, and secure workstation setup using tools such as Packet Tracer and Wireshark.</li>
            <li>Support classroom readiness, virtual lab setup, and ongoing maintenance of instructional technology resources.</li>
          </ul>
        </div>
        <div class="card">
          <h4>Administrative Specialist</h4>
          <p><strong>ITMS-Inc. | McLean, VA | Apr 2017 - May 2022</strong></p>
          <p>Supported departmental operations, basic technical troubleshooting, digital file management, and confidential record handling in a fast-paced office environment.</p>
        </div>
        <div class="card">
          <h4>Front Desk Receptionist</h4>
          <p><strong>Incredicare | Woodbridge, VA | May 2014 - Feb 2017</strong></p>
          <p>Maintained sensitive records, delivered customer support, and worked in a HIPAA-compliant healthcare environment.</p>
        </div>
      </div>
    </section>

    <section id="certifications">
      <h3>Certifications</h3>
      <div class="cards">
        <div class="card">
          <h4>CompTIA A+</h4>
        </div>
        <div class="card">
          <h4>CompTIA Security+</h4>
        </div>
      </div>
    </section>

    <section id="projects">
      <h3>Projects & Hands-On Experience</h3>
      <div class="cards">
        <div class="card">
          <h4>Network Design Project (CYB495)</h4>
          <p>
            Designed a new ISP solution for several large regional medical groups responding to a Request for Proposal (RFP). The design focused on secure healthcare internet services, protection of patient information, and support for access by medical professionals, hospitals, pharmacies, and patients.
          </p>
        </div>
        <div class="card">
          <h4>SOC Analyst Simulation Experience</h4>
          <p>
            Completed advanced simulations in SOC Analyst I and SOC Analyst II, gaining hands-on experience with ticketing workflows, incident investigation, threat research, reporting, log analysis, and security operations processes.
          </p>
        </div>
        <div class="card">
          <h4>Segmented Network Design</h4>
          <p>
            Designed and configured a segmented network using VLANs, subnetting, and DHCP to strengthen traffic control and reinforce network security fundamentals.
          </p>
        </div>
        <div class="card">
          <h4>Windows Server Domain Configuration</h4>
          <p>
            Completed a Windows Server domain configuration project focused on system administration, account management, and secure service setup.
          </p>
        </div>
      </div>
    </section>

    <section id="education">
      <h3>Education</h3>
      <div class="cards">
        <div class="card">
          <h4>Bachelor of Science in Computer and Information Science</h4>
          <p><strong>ECPI University | Manassas, VA | Graduated July 2023</strong></p>
          <p>Relevant Coursework: Networking, Operating Systems, Cybersecurity Fundamentals, Python Programming</p>
        </div>
      </div>
    </section>

    <section id="contact">
      <h3>Contact</h3>
      <div class="contact-list">
        <p>Email: <a href="mailto:jsmith123@yahoo.com">jsmith123@yahoo.com</a></p>
        <p>Phone: <a href="tel:15712975889">(571) 297-5889</a></p>
        <p>Location: Washington, DC</p>
        <p>GitHub: <a href="#">Add your GitHub profile link here</a></p>
        <p>LinkedIn: <a href="#">Add your LinkedIn profile link here</a></p>
        <p>Resume: <a href="#">Add resume file link here</a></p>
      </div>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 John Smith | Cybersecurity ePortfolio</p>
  </footer>
</body>
</html>
