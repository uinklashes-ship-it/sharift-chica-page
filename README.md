import { useEffect, useMemo, useState } from "react";

export default function ShariftChicaPage() {
  const [selectedMedia, setSelectedMedia] = useState(null);
  const [heroIndex, setHeroIndex] = useState(0);

  const whatsappUrl =
    "https://wa.me/573214557541?text=Hola%20UINK,%20quiero%20informacion%20sobre%20los%20cursos%20de%20Sharift%20Chica";

  const photos = [
    "https://i.imgur.com/dqjUTUg.jpeg",
    "https://i.imgur.com/CpNU7rB.jpeg",
    "https://i.imgur.com/FnL0z5s.png",
    "https://i.imgur.com/ugKGPBr.jpeg",
    "https://i.imgur.com/Cx8RcOe.jpeg",
    "https://i.imgur.com/J2q81Hw.png",
    "https://i.imgur.com/f5nRI7a.jpeg",
    "https://i.imgur.com/D1ywSw9.png",
    "https://i.imgur.com/IufLGK7.png",
    "https://i.imgur.com/blZFuj5.png",
    "https://i.imgur.com/nNfjUw3.jpeg",
    "https://i.imgur.com/g9aswqN.jpeg",
    "https://i.imgur.com/UYHpbzv.jpeg",
    "https://i.imgur.com/7fWbkoI.jpeg",
    "https://i.imgur.com/MHzrXnP.jpeg",
    "https://i.imgur.com/ODcTSZn.jpeg",
    "https://i.imgur.com/zYNidna.jpeg",
    "https://i.imgur.com/ENKKILC.jpeg",
    "https://i.imgur.com/C7MTPpu.jpeg",
    "https://i.imgur.com/ZBgO854.jpeg",
    "https://i.imgur.com/6nFUiGZ.jpeg",
    "https://i.imgur.com/cgZ8ijY.jpeg",
  ];

  const videos = [
    "https://i.imgur.com/Q2yoAy0.mp4",
    "https://i.imgur.com/9HTlU6o.mp4",
    "https://i.imgur.com/PSpW6Rf.mp4",
    "https://i.imgur.com/3ro3WSM.mp4",
    "https://i.imgur.com/yDFZzaz.mp4",
    "https://i.imgur.com/TksBKIF.mp4",
    "https://i.imgur.com/OAYZr2x.mp4",
    "https://i.imgur.com/42KjN3T.mp4",
    "https://i.imgur.com/SACv2b4.mp4",
    "https://i.imgur.com/CKPxuMb.mp4",
    "https://i.imgur.com/MGOiCWH.mp4",
    "https://i.imgur.com/3DJNTo5.mp4",
    "https://i.imgur.com/FsU7nJc.mp4",
    "https://i.imgur.com/Jwx0MnX.mp4",
    "https://i.imgur.com/o4p3fmZ.mp4",
    "https://i.imgur.com/KQdR7ap.mp4",
    "https://i.imgur.com/RkWs8QD.mp4",
    "https://i.imgur.com/FEwc6Yu.mp4",
    "https://i.imgur.com/oNTfdPU.mp4",
    "https://i.imgur.com/h2u2evk.mp4",
    "https://i.imgur.com/QD3mscs.mp4",
    "https://i.imgur.com/MCUb8fR.mp4",
    "https://i.imgur.com/e4f397S.mp4",
    "https://i.imgur.com/CfJijDO.mp4",
    "https://i.imgur.com/S72BwCh.mp4",
    "https://i.imgur.com/e0aqGrV.mp4",
  ];

  const heroVisuals = useMemo(
    () => [
      { type: "image", src: photos[0], label: "Sharift Chica" },
      { type: "video", src: videos[0], label: "Formación real" },
      { type: "image", src: photos[2], label: "UINK Academy" },
      { type: "video", src: videos[4], label: "Experiencia beauty" },
    ],
    []
  );

  useEffect(() => {
    const timer = setInterval(() => {
      setHeroIndex((prev) => (prev + 1) % heroVisuals.length);
    }, 4500);
    return () => clearInterval(timer);
  }, [heroVisuals.length]);

  const rotateHero = () => setHeroIndex((prev) => (prev + 1) % heroVisuals.length);

  const courses = [
    ["Extensiones de pestañas", "Principiantes y avanzadas", "Técnica clásica, retención, efectos, fibras tecnológicas y modelos reales."],
    ["Actualización en efectos", "Tendencias y precisión", "Foxy, delineado, wispy, mapping, espigas, capas y análisis de mirada."],
    ["Laminación + Lifting", "Mirada natural", "Diseño, arquitectura, salud de la fibra y protocolos de alto nivel."],
    ["Hidralips", "Labios y estética", "Técnica, bioseguridad, protocolo, cuidados y experiencia de servicio."],
    ["Limpieza facial", "Estética profesional", "Análisis de piel, aparatología, protocolo y experiencia facial UINK."],
  ];

  const classicTraining = [
    ["Día 1", "Teoría + práctica real", "Tricología aplicada, contraindicaciones, análisis de mirada, curvas, grosores, longitudes y práctica guiada."],
    ["Día 2", "Técnicas avanzadas", "Efecto rímel, higiene, postura de parches, mapping, pelo a pelo, retiros profesionales y corrección."],
    ["Día 3", "Adhesivos y volumen", "Teoría de adhesivos, fibras tecnológicas, fichas técnicas y práctica final en paciente real."],
  ];

  const method = [
    ["Técnica", "Retención, diseño, seguridad, aislamiento y aplicación limpia."],
    ["Mentalidad", "Seguridad, disciplina y confianza para empezar desde cero."],
    ["Negocio", "Cómo vender, cobrar, comunicar y convertir tu talento en ingresos."],
    ["Acompañamiento", "Corrección cercana, seguimiento y respaldo después del curso."],
  ];

  const Media = ({ src, type = "image", label = "Ver", className = "" }) => (
    <button className={`media ${className}`} onClick={() => setSelectedMedia({ src, type })}>
      {type === "video" ? <video src={src} muted autoPlay loop playsInline /> : <img src={src} alt={label} />}
      <span>{label}</span>
    </button>
  );

  return (
    <>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Bodoni+Moda:wght@500;600;700;800;900&family=Inter:wght@400;500;600;700;800;900&display=swap');
        *{box-sizing:border-box}html{scroll-behavior:smooth}body{margin:0;background:#f4f2ef;color:#111;font-family:'Inter',sans-serif}a{text-decoration:none;color:inherit}button{font-family:inherit}.page{min-height:100vh;background:radial-gradient(circle at 78% 8%,rgba(130,0,32,.13),transparent 28%),radial-gradient(circle at 5% 20%,rgba(0,0,0,.08),transparent 34%),linear-gradient(180deg,#f6f4f1 0%,#e7e5e2 45%,#101010 100%);overflow:hidden}.container{width:min(1320px,calc(100% - 48px));margin:0 auto}.nav{position:fixed;inset:0 0 auto 0;height:78px;z-index:70;background:rgba(246,244,241,.78);backdrop-filter:blur(18px);border-bottom:1px solid rgba(0,0,0,.08)}.navin{height:78px;display:flex;align-items:center;justify-content:space-between;gap:22px}.brand{display:flex;align-items:center;gap:12px}.brand-mark{width:48px;height:48px;border-radius:50%;background:#111;color:#fff;display:grid;place-items:center;font-family:'Bodoni Moda',serif;font-weight:900;font-size:20px}.brand b{font-family:'Bodoni Moda',serif;font-size:24px;letter-spacing:.02em}.brand small{display:block;color:#8d0b2a;text-transform:uppercase;letter-spacing:.22em;font-size:10px;margin-top:2px}.links{display:flex;gap:24px;color:rgba(17,17,17,.68);font-size:12px;font-weight:900;text-transform:uppercase;letter-spacing:.12em}.navbtn,.btn{display:inline-flex;align-items:center;justify-content:center;border-radius:999px;padding:14px 22px;text-transform:uppercase;letter-spacing:.12em;font-weight:900;font-size:12px}.navbtn,.redbtn{background:linear-gradient(135deg,#111,#4b4b4b 42%,#9c1236);color:#fff;box-shadow:0 22px 55px rgba(156,18,54,.16)}.lightbtn{background:rgba(255,255,255,.62);border:1px solid rgba(0,0,0,.14);color:#111}.whatsapp{position:fixed;right:22px;bottom:22px;z-index:80;width:58px;height:58px;border-radius:999px;background:#25d366;color:#06130b;display:grid;place-items:center;font-weight:900;box-shadow:0 20px 60px rgba(0,0,0,.28)}
        .hero{position:relative;min-height:100vh;padding-top:78px;overflow:hidden}.hero:before{content:"";position:absolute;inset:0;background:linear-gradient(90deg,rgba(246,244,241,.94) 0%,rgba(246,244,241,.72) 42%,rgba(246,244,241,.35) 62%,rgba(17,17,17,.5) 100%);z-index:1}.hero-word{position:absolute;left:3%;top:17%;font-family:'Bodoni Moda',serif;font-size:clamp(90px,15vw,220px);line-height:.78;font-weight:900;letter-spacing:-.08em;color:rgba(17,17,17,.045);z-index:1}.red-glow{position:absolute;right:13%;top:13%;width:520px;height:720px;background:radial-gradient(circle,rgba(165,8,49,.24),rgba(165,8,49,.08) 38%,transparent 70%);filter:blur(20px);z-index:0;animation:glowPulse 6s ease-in-out infinite}.hero-portrait{position:absolute;right:11%;bottom:0;height:88vh;width:min(490px,35vw);z-index:4;display:flex;align-items:flex-end;justify-content:center;pointer-events:none}.portrait-halo{position:absolute;left:50%;top:48%;transform:translate(-50%,-50%);width:142%;height:92%;background:radial-gradient(circle,rgba(156,18,54,.26),rgba(0,0,0,.08) 50%,transparent 75%);filter:blur(18px);z-index:0}.hero-portrait img{position:relative;z-index:2;width:100%;height:100%;object-fit:cover;object-position:center 15%;border-radius:48% 48% 0 0;filter:drop-shadow(0 28px 64px rgba(0,0,0,.28));animation:portraitFloat 7s ease-in-out infinite}.hero-content{position:relative;z-index:5;min-height:calc(100vh - 78px);display:grid;grid-template-columns:minmax(450px,620px) 330px;justify-content:space-between;gap:42px;align-items:center;padding:94px 0 170px}.hero-copy{max-width:620px;background:linear-gradient(90deg,rgba(246,244,241,.84),rgba(246,244,241,.5),transparent);padding:22px 22px 22px 0;border-radius:28px}.pill{display:inline-flex;border:1px solid rgba(156,18,54,.28);background:rgba(156,18,54,.06);border-radius:999px;padding:9px 14px;color:#8d0b2a;text-transform:uppercase;letter-spacing:.18em;font-size:11px;font-weight:900}.hero-title{font-family:'Bodoni Moda',serif;font-size:clamp(50px,6.2vw,94px);line-height:.94;margin:20px 0 0;letter-spacing:-.06em}.hero-title span{display:block;color:#8d0b2a}.hero-sub{max-width:570px;margin:22px 0 0;color:rgba(17,17,17,.7);line-height:1.8;font-size:17px}.hero-actions{display:flex;gap:14px;flex-wrap:wrap;margin-top:30px}.hero-card{align-self:end;position:relative;z-index:8;border:1px solid rgba(0,0,0,.1);background:rgba(255,255,255,.62);backdrop-filter:blur(14px);border-radius:28px;padding:22px;box-shadow:0 28px 80px rgba(0,0,0,.12)}.hero-card b{font-family:'Bodoni Moda',serif;font-size:38px;color:#8d0b2a}.hero-card span{display:block;margin-top:6px;text-transform:uppercase;letter-spacing:.12em;font-size:11px;font-weight:900;color:rgba(17,17,17,.58)}.hero-live{position:absolute;right:4%;bottom:178px;z-index:7;width:320px;height:190px;border-radius:26px;overflow:hidden;border:1px solid rgba(156,18,54,.18);background:#111;box-shadow:0 28px 80px rgba(0,0,0,.16)}.hero-live img,.hero-live video{width:100%;height:100%;object-fit:cover;object-position:center 26%;display:block}.hero-live:after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent 44%,rgba(0,0,0,.72))}.hero-live span{position:absolute;left:16px;right:16px;bottom:15px;z-index:2;color:#fff;text-transform:uppercase;letter-spacing:.14em;font-size:10px;font-weight:900}.hero-live button{position:absolute;right:13px;top:13px;z-index:3;border:1px solid rgba(255,255,255,.25);background:rgba(0,0,0,.42);color:#fff;border-radius:999px;padding:8px 11px;cursor:pointer}.hero-strip{position:absolute;left:0;right:0;bottom:0;z-index:6;display:grid;grid-template-columns:repeat(5,1fr);height:150px;background:#111}.strip{position:relative;overflow:hidden;border-right:1px solid rgba(255,255,255,.1)}.strip img,.strip video{width:100%;height:100%;object-fit:cover;object-position:center 28%;display:block;filter:saturate(.85)}.strip:after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent,rgba(0,0,0,.58))}.strip span{position:absolute;left:14px;bottom:12px;z-index:2;color:#fff;text-transform:uppercase;letter-spacing:.14em;font-size:10px;font-weight:900}
        section{padding:94px 0}.section-head{display:flex;justify-content:space-between;align-items:end;gap:28px;margin-bottom:34px}.kicker{color:#8d0b2a;text-transform:uppercase;letter-spacing:.18em;font-size:10px;font-weight:900}.title{font-family:'Bodoni Moda',serif;font-size:clamp(38px,4.9vw,78px);line-height:.96;margin:12px 0 0;letter-spacing:-.05em}.desc{max-width:640px;color:rgba(17,17,17,.64);line-height:1.85;margin:0}.glass{border:1px solid rgba(0,0,0,.09);background:rgba(255,255,255,.58);box-shadow:0 30px 80px rgba(0,0,0,.1);backdrop-filter:blur(12px);border-radius:34px}.dark-section{background:#101010;color:#f5f3ef}.dark-section .desc{color:rgba(245,243,239,.66)}.dark-section .glass{background:rgba(255,255,255,.055);border-color:rgba(255,255,255,.12);box-shadow:0 30px 80px rgba(0,0,0,.3)}.story{display:grid;grid-template-columns:.95fr 1.05fr;gap:24px}.story-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}.media{position:relative;overflow:hidden;border:1px solid rgba(0,0,0,.09);background:#151515;border-radius:28px;padding:0;cursor:pointer;transition:transform .45s cubic-bezier(.2,.8,.2,1),box-shadow .45s ease,border-color .45s ease}.media:hover{transform:translateY(-8px) scale(1.012);border-color:rgba(156,18,54,.38);box-shadow:0 28px 70px rgba(156,18,54,.12)}.media img,.media video{width:100%;height:100%;object-fit:cover;object-position:center 26%;display:block}.media:after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,transparent 42%,rgba(0,0,0,.72))}.media span{position:absolute;left:16px;right:16px;bottom:16px;z-index:2;color:#fff;text-transform:uppercase;letter-spacing:.14em;font-size:10px;font-weight:900}.big{grid-column:span 2;height:380px}.small{height:270px}.story-text{padding:42px}.story-text p{color:rgba(17,17,17,.68);line-height:1.9}.dark-section .story-text p{color:rgba(245,243,239,.7)}.quote{padding:80px 0;text-align:center;background:linear-gradient(90deg,#111,#1f1f1f,#111);color:#fff}.quote h2{font-family:'Bodoni Moda',serif;font-size:clamp(40px,5.2vw,78px);line-height:1;margin:0;letter-spacing:-.04em}.quote p{max-width:780px;margin:22px auto 0;color:rgba(255,255,255,.68);line-height:1.9}.impact{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;border:1px solid rgba(0,0,0,.08);border-radius:30px;overflow:hidden;background:rgba(0,0,0,.08);margin-top:24px}.impact-card{background:rgba(255,255,255,.62);padding:30px;text-align:center}.impact-card b{font-family:'Bodoni Moda',serif;font-size:42px;color:#8d0b2a}.impact-card span{display:block;margin-top:8px;text-transform:uppercase;letter-spacing:.12em;font-size:11px;font-weight:900;color:rgba(17,17,17,.6)}.specialties,.method,.learning{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}.s-card,.m-card,.learn{padding:26px}.s-card h3,.m-card h3,.learn h4{font-family:'Bodoni Moda',serif;font-size:27px;line-height:1.05;margin:0 0 10px;letter-spacing:-.03em}.s-card p,.m-card p,.learn p{color:rgba(17,17,17,.64);line-height:1.75;font-size:14px;margin:0}.course-block{display:grid;grid-template-columns:1fr 1fr;overflow:hidden}.course-media{display:grid;grid-template-columns:1fr 1fr;gap:12px;padding:12px;background:#111}.course-media .media{height:292px}.course-info{padding:42px}.course-info p,.course-info li{line-height:1.85;color:rgba(17,17,17,.68)}.price{margin:24px 0;display:grid;grid-template-columns:1fr 1fr;gap:12px}.price-card{border:1px solid rgba(156,18,54,.16);background:rgba(156,18,54,.06);border-radius:24px;padding:22px}.price-card b{font-family:'Bodoni Moda',serif;font-size:34px;color:#8d0b2a}.timeline{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:22px}.day{padding:26px}.day b{font-family:'Bodoni Moda',serif;font-size:36px;color:#8d0b2a}.day h3{font-family:'Bodoni Moda',serif;font-size:28px;margin:10px 0}.day p{line-height:1.75;color:rgba(17,17,17,.64)}.gallery{display:flex;gap:16px;overflow-x:auto;padding-bottom:14px}.gallery .media{flex:0 0 260px;height:380px}.footer{padding:100px 0;text-align:center;background:#0d0d0d;color:#fff}.footer h2{font-family:'Bodoni Moda',serif;font-size:clamp(42px,5.5vw,86px);line-height:.95;margin:0 auto;max-width:980px;letter-spacing:-.05em}.footer p{max-width:720px;margin:24px auto;color:rgba(255,255,255,.66);line-height:1.9}.modal{position:fixed;inset:0;z-index:100;background:rgba(0,0,0,.88);display:grid;place-items:center;padding:24px}.modal-box{position:relative;width:min(1050px,94vw);max-height:90vh;background:#111;border:1px solid rgba(255,255,255,.16);border-radius:26px;padding:18px}.modal-box img,.modal-box video{width:100%;max-height:80vh;object-fit:contain;border-radius:18px}.close{position:absolute;right:16px;top:16px;z-index:2;background:rgba(0,0,0,.62);color:#fff;border:1px solid rgba(255,255,255,.18);border-radius:12px;padding:10px 14px;cursor:pointer}
        @keyframes portraitFloat{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-10px) scale(1.012)}}@keyframes glowPulse{0%,100%{opacity:.76;transform:scale(1)}50%{opacity:1;transform:scale(1.08)}}
        @media(max-width:1100px){.links{display:none}.hero-content{grid-template-columns:1fr}.hero-card{display:none}.hero-portrait{right:-4%;width:48vw;opacity:.72}.hero-live{display:none}.story,.course-block{grid-template-columns:1fr}.specialties,.method,.learning,.timeline,.impact{grid-template-columns:repeat(2,1fr)}.section-head{display:block}.desc{margin-top:16px}}
        @media(max-width:720px){.container{width:min(100% - 28px,1320px)}.navbtn{display:none}.brand b{font-size:18px}.hero{min-height:auto}.hero-content{min-height:740px;padding:62px 0 170px}.hero-portrait{right:-42%;width:110vw;height:78vh;opacity:.32}.hero-title{font-size:48px}.hero-strip{grid-template-columns:repeat(2,1fr);height:auto}.strip{height:125px}.story-grid,.course-media,.specialties,.method,.learning,.timeline,.impact,.price{grid-template-columns:1fr}.big{grid-column:auto;height:310px}.small{height:260px}section{padding:66px 0}.whatsapp{left:14px;right:14px;width:auto}}
      `}</style>

      <main className="page">
        <a className="whatsapp" href={whatsappUrl} target="_blank" rel="noreferrer">WA</a>
        <nav className="nav"><div className="container navin"><a className="brand" href="#inicio"><div className="brand-mark">SC</div><div><b>Sharift Chica</b><small>UINK Academy</small></div></a><div className="links"><a href="#historia">Historia</a><a href="#uink">UINK</a><a href="#cursos">Cursos</a><a href="#metodo">Método</a><a href="#impacto">Impacto</a></div><a className="navbtn" href={whatsappUrl} target="_blank" rel="noreferrer">Quiero aprender</a></div></nav>

        <header className="hero" id="inicio"><div className="red-glow" /><div className="hero-word">Beauty<br/>Power</div><div className="hero-portrait"><div className="portrait-halo" /><img src={photos[0]} alt="Sharift Chica" /></div><div className="hero-live">{heroVisuals[heroIndex].type === "video" ? <video src={heroVisuals[heroIndex].src} muted autoPlay loop playsInline /> : <img src={heroVisuals[heroIndex].src} alt={heroVisuals[heroIndex].label} />}<button onClick={rotateHero}>↻</button><span>{heroVisuals[heroIndex].label}</span></div><div className="container hero-content"><div className="hero-copy"><div className="pill">Cosmetóloga · Lash Artist · Mentora</div><h1 className="hero-title">No nací en el éxito.<span>Lo construí.</span></h1><p className="hero-sub">Sharift Chica transforma pestañas, negocios y vidas. De empezar desde cero a convertirse en cofundadora de UINK, creadora de UINK Academy y mentora de mujeres que quieren vivir de su talento.</p><div className="hero-actions"><a className="btn redbtn" href={whatsappUrl} target="_blank" rel="noreferrer">Quiero aprender con Sharift</a><a className="btn lightbtn" href="#historia">Conoce su historia</a></div></div><div className="hero-card"><b>+500</b><span>personas acompañadas a convertir la belleza en ingresos reales</span></div></div><div className="hero-strip"><div className="strip"><img src={photos[1]} alt="" /><span>Mentora</span></div><div className="strip"><video src={videos[0]} muted autoPlay loop playsInline /><span>Curso</span></div><div className="strip"><img src={photos[5]} alt="" /><span>UINK</span></div><div className="strip"><video src={videos[2]} muted autoPlay loop playsInline /><span>Resultados</span></div><div className="strip"><img src={photos[10]} alt="" /><span>Beauty</span></div></div></header>

        <section id="historia"><div className="container story"><div className="story-grid"><Media src={photos[1]} label="Sharift Chica" className="big" /><Media src={videos[1]} type="video" label="Proceso real" className="small" /><Media src={photos[4]} label="Marca personal" className="small" /></div><div className="glass story-text"><div className="kicker">Historia personal</div><h2 className="title">De la necesidad al legado.</h2><p>Sharift no empezó desde la comodidad. Empezó con días sin clientas, inseguridad, falta de guía y errores que nadie le enseñó a evitar.</p><p>Pero decidió no rendirse. Su motor más grande tiene nombre: Noah, su hijo. Él es parte de la razón por la que todos los días construye algo más grande.</p><p>Su historia no se trata solo de belleza. Se trata de independencia, disciplina y visión.</p></div></div></section>

        <section className="quote"><div className="container"><h2>“No formo lashistas que solo aplican pestañas. Formo mujeres que aprenden a vivir de su talento.”</h2><p>La técnica te da resultados, pero la mentalidad te da libertad.</p></div></section>

        <section id="uink"><div className="container"><div className="section-head"><div><div className="kicker">Qué representa UINK</div><h2 className="title">Un hogar para lashistas.</h2></div><p className="desc">UINK nace como respuesta a todo lo que Sharift no tuvo: educación clara, productos confiables, acompañamiento real y una comunidad sin ego.</p></div><div className="impact"><div className="impact-card"><b>+6</b><span>años de experiencia</span></div><div className="impact-card"><b>+500</b><span>personas acompañadas</span></div><div className="impact-card"><b>UINK</b><span>Academy + Lash</span></div><div className="impact-card"><b>Noah</b><span>su motor y legado</span></div></div></div></section>

        <section className="dark-section"><div className="container"><div className="section-head"><div><div className="kicker">Especialidades</div><h2 className="title">Ciencia, práctica y negocio.</h2></div><p className="desc">Sharift integra salud ocular, técnica, productos profesionales y mentalidad empresarial.</p></div><div className="specialties"><div className="glass s-card"><h3>Pestañas</h3><p>Técnica clásica, volumen, efectos avanzados, fibras tecnológicas, retención y salud ocular.</p></div><div className="glass s-card"><h3>Facial</h3><p>Limpieza facial profunda, acné, despigmentación, antiaging e hidralips.</p></div><div className="glass s-card"><h3>Cejas</h3><p>Laminación, diseño, arquitectura, depilación con hilo y análisis de mirada.</p></div><div className="glass s-card"><h3>Productos</h3><p>Adhesivos profesionales, bonder, protocolos de retención y productos libres de etil.</p></div></div></div></section>

        <section id="cursos"><div className="container"><div className="section-head"><div><div className="kicker">UINK Academy</div><h2 className="title">Cursos que cambian la forma de trabajar.</h2></div><p className="desc">Formaciones presenciales con kit, certificación, modelos reales, metodología actualizada y acompañamiento.</p></div><div className="glass course-block"><div className="course-media"><Media src={videos[3]} type="video" label="Clase en acción" /><Media src={photos[6]} label="Kit UINK" /><Media src={videos[4]} type="video" label="Práctica real" /><Media src={photos[8]} label="Experiencia UINK" /></div><div className="course-info"><div className="kicker">Entrenamiento para lashistas principiantes</div><h2 className="title">Técnica clásica.</h2><p>Entrenamiento intensivo de 3 días, 8 AM a 1 PM, con prácticas guiadas, kit premium, certificación, break, protocolos de bioseguridad, acompañamiento personalizado y modelos reales.</p><div className="price"><div className="price-card"><span>Grupal</span><br/><b>$1.000.000</b></div><div className="price-card"><span>Personalizado</span><br/><b>$1.500.000</b></div></div><a className="btn redbtn" href={whatsappUrl} target="_blank" rel="noreferrer">Inscribirme</a></div></div><div className="timeline">{classicTraining.map((d)=><div className="glass day" key={d[0]}><b>{d[0]}</b><h3>{d[1]}</h3><p>{d[2]}</p></div>)}</div></div></section>

        <section className="dark-section" id="metodo"><div className="container"><div className="section-head"><div><div className="kicker">Método Sharift</div><h2 className="title">Técnica, mentalidad y negocio.</h2></div><p className="desc">No busca alumnas perfectas. Busca alumnas que evolucionen, entiendan lo que hacen y puedan vivir de su talento.</p></div><div className="method">{method.map((m)=><div className="glass m-card" key={m[0]}><h3>{m[0]}</h3><p>{m[1]}</p></div>)}</div><div className="gallery" style={{marginTop:18}}>{videos.slice(5,13).map((v)=><Media key={v} src={v} type="video" label="Método Sharift" />)}</div></div></section>

        <section id="impacto"><div className="container"><div className="section-head"><div><div className="kicker">Cursos disponibles</div><h2 className="title">Un ecosistema completo.</h2></div><p className="desc">Venta de cursos, servicios profesionales, productos UINK Luxe, marca personal y eventos como Lash Revolution.</p></div><div className="learning">{courses.map((c)=><div className="glass learn" key={c[0]}><h4>{c[0]}</h4><p><b>{c[1]}</b><br/>{c[2]}</p></div>)}</div></div></section>

        <section><div className="container"><div className="section-head"><div><div className="kicker">Galería editorial</div><h2 className="title">Beauty, academia y propósito.</h2></div><p className="desc">Una mirada visual al universo de Sharift: formación, marca, productos, estilo y comunidad.</p></div><div className="gallery">{photos.slice(0,18).map((p)=><Media key={p} src={p} label="Sharift Chica" />)}{videos.slice(13).map((v)=><Media key={v} src={v} type="video" label="UINK Academy" />)}</div></div></section>

        <footer className="footer"><div className="container"><h2>¿Estás lista para cambiar tu vida?</h2><p>Si Sharift pudo empezar desde cero y construir algo grande, tú también puedes empezar a construir independencia, técnica y visión.</p><a className="btn redbtn" href={whatsappUrl} target="_blank" rel="noreferrer">Escribir por WhatsApp</a></div></footer>

        {selectedMedia && <div className="modal" onClick={() => setSelectedMedia(null)}><div className="modal-box" onClick={(e)=>e.stopPropagation()}><button className="close" onClick={()=>setSelectedMedia(null)}>Cerrar</button>{selectedMedia.type === "video" ? <video src={selectedMedia.src} controls autoPlay playsInline /> : <img src={selectedMedia.src} alt="Vista" />}</div></div>}
      </main>
    </>
  );
}
