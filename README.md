<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine?</title>
<style>
    body {
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        font-family: 'Comic Sans MS', cursive, sans-serif;
    }

    .box {
        background: white;
        width: 360px;
        padding: 25px;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        position: relative;
    }

    img {
        width: 120px;
        margin-bottom: 10px;
    }

    h2 {
        color: #ff4d6d;
    }

    p {
        font-size: 16px;
        margin-bottom: 20px;
    }

    .buttons {
        position: relative;
        height: 120px;
    }

    button {
        padding: 12px 22px;
        font-size: 16px;
        border-radius: 30px;
        border: none;
        cursor: pointer;
        transition: all 0.3s ease;
        position: absolute;
    }

    #yes {
        background: #ff4d6d;
        color: white;
        left: 50%;
        transform: translateX(-50%);
    }

    #no {
        background: #ddd;
        color: #333;
        left: 60%;
        top: 60px;
    }

    .hidden {
        display: none;
    }
</style>
</head>
<body>

<div class="box">
    <img src="https://i.imgur.com/9M0KQxj.png" alt="Cute Fox">

    <h2>Will you be my Valentine? 💖</h2>

    <p id="question">
        I’ve been wanting to ask you something really special…
    </p>

    <div class="buttons">
        <button id="yes">YES 💕</button>
        <button id="no">NO 😅</button>
    </div>

    <p id="message" class="hidden">
        <!-- WRITE YOUR PERSONAL MESSAGE HERE -->
        You just made me the happiest person ever. I love you ❤️
    </p>
</div>

<script>
    const yesBtn = document.getElementById("yes");
    const noBtn = document.getElementById("no");
    const message = document.getElementById("message");
    const question = document.getElementById("question");

    let yesSize = 1;

    noBtn.addEventListener("mouseenter", () => {
        const box = document.querySelector(".buttons");
        const maxX = box.clientWidth - noBtn.offsetWidth;
        const maxY = box.clientHeight - noBtn.offsetHeight;

        const randX = Math.random() * maxX;
        const randY = Math.random() * maxY;

        noBtn.style.left = randX + "px";
        noBtn.style.top = randY + "px";

        yesSize += 0.2;
        yesBtn.style.transform = `translateX(-50%) scale(${yesSize})`;
    });

    yesBtn.addEventListener("click", () => {
        question.classList.add("hidden");
        yesBtn.classList.add("hidden");
        noBtn.classList.add("hidden");
        message.classList.remove("hidden");
    });
</script>

</body>
</html>
