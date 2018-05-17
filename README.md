
TX Hash: e1549bf8cef205d077603babba715532feb726e2e8af464d34d82df6ad1c31c5

Contract address: n1raGSiaKzjXdwvwx2URF58LbdAjQdSpHt9

https://wallet.nasscan.io/contract.html
![image](https://ws3.sinaimg.cn/large/006tKfTcly1fre5n13on6j31kw0ssagc.jpg)
# index.html 主页呈现
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>iMemory</title>
    <!--<link rel="stylesheet" href="css/style.css">-->

</head>
<body>
<style>
    .input {
        width: 550px;
        height: 70px;
        color: deeppink;
        font-size: 40px;
        border-radius: 50px;
        background-color: #2d2d2d;
        padding-left: 50px; }
    .button {
        height: 50px;
        width: 50px;
        font-size: 20px;
        font-weight: bolder;
        border-radius: 100px;
        color: deeppink;
        background-color: #2d2d2d; }
    :root {
        font-size: calc(3.5vW); }
    * {
        margin: 0;
        padding: 0;
        outline: none; }
    *:active {
        outline: none; }
    body {
        font-family: 'Ubuntu', sans-serif;
        font-weight: 300;
        background-color: #2d2d2d; }
    button {
        cursor: pointer;
        color: #333333;
        border-radius: 100px; }
    button:disabled {
        cursor: auto;
        color: rgba(51, 51, 51, 0.8);
        border-radius: 100px; }
    .container {
        width: 100vW;
        height: 100vH;
        overflow-y: hidden;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center; }
    .ball-container {
        width: 75vW;
        height: 25vH;
        margin-bottom: 5rem;
        display: flex;
        justify-content: space-between;
        align-items: center; }
    .ball, .ball::after, .ball::before {
        min-width: 4.5rem;
        min-height: 4.5rem;
        border-radius: 50%;
        border-style: none;
        transition: all 0.25s linear;
        position: relative; }
    .ball {
        box-shadow: none;
        opacity: 0.075; }
    .ball:nth-child(1), .ball:nth-last-child(1) {
        margin-top: 9rem; }
    .ball::after, .ball::before {
        position: absolute;
        content: '';
        display: block;
        pointer-events: none; }
    .yellow {
        background: #fffb80;
        /* fallback for old browsers */
        background: -webkit-radial-gradient(#fffb80 15%, #fff71a 50%);
        /* Chrome 10-25, Safari 5.1-6 */
        background: radial-gradient(#fffb80 15%, #fff71a 50%);
        /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */ }
    .yellow.show {
        box-shadow: 0 0 1.75rem rgba(255, 251, 128, 0.5); }
    .yellow::after {
        background: rgba(255, 251, 128, 0.07);
        /* fallback for old browsers */
        background: -webkit-linear-gradient(to bottom, rgba(255, 251, 128, 0.1), rgba(255, 251, 128, 0.02));
        background: linear-gradient(to bottom, rgba(255, 251, 128, 0.1), rgba(255, 251, 128, 0.05)); }
    .yellow::before {
        box-shadow: 0 0 3rem rgba(255, 251, 128, 0.04); }
    .green {
        background: #20cf3b;
        /* fallback for old browsers */
        background: -webkit-radial-gradient(#57e56d 15%, #20cf3b 50%);
        /* Chrome 10-25, Safari 5.1-6 */
        background: radial-gradient(#57e56d 15%, #20cf3b 50%);
        /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */ }
    .green.show {
        box-shadow: 0 0 1.75rem rgba(87, 229, 109, 0.6); }
    .green::after {
        background: rgba(87, 229, 109, 0.07);
        /* fallback for old browsers */
        background: -webkit-linear-gradient(to bottom, rgba(87, 229, 109, 0.1), rgba(87, 229, 109, 0.02));
        background: linear-gradient(to bottom, rgba(87, 229, 109, 0.1), rgba(87, 229, 109, 0.05)); }
    .green::before {
        box-shadow: 0 0 3rem rgba(87, 229, 109, 0.04); }
    .blue {
        background: #196aeb;
        /* fallback for old browsers */
        background: -webkit-radial-gradient(#4385ef 15%, #196aeb 50%);
        /* Chrome 10-25, Safari 5.1-6 */
        background: radial-gradient(#4385ef 15%, #196aeb 50%);
        /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */ }
    .blue.show {
        box-shadow: 0 0 1.75rem rgba(67, 133, 239, 0.8); }
    .blue::after {
        background: rgba(67, 133, 239, 0.07);
        /* fallback for old browsers */
        background: -webkit-linear-gradient(to bottom, rgba(67, 133, 239, 0.1), rgba(67, 133, 239, 0.02));
        background: linear-gradient(to bottom, rgba(67, 133, 239, 0.1), rgba(67, 133, 239, 0.05)); }
    .blue::before {
        box-shadow: 0 0 3rem rgba(67, 133, 239, 0.04); }
    .red {
        background: #e11414;
        /* fallback for old browsers */
        background: -webkit-radial-gradient(#f15b5b 15%, #e11414 50%);
        /* Chrome 10-25, Safari 5.1-6 */
        background: radial-gradient(#f15b5b 15%, #e11414 50%);
        /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */ }
    .red.show {
        box-shadow: 0 0 1.75rem rgba(241, 91, 91, 0.8); }
    .red::after {
        background: rgba(241, 91, 91, 0.07);
        /* fallback for old browsers */
        background: -webkit-linear-gradient(to bottom, rgba(241, 91, 91, 0.1), rgba(241, 91, 91, 0.02));
        background: linear-gradient(to bottom, rgba(241, 91, 91, 0.1), rgba(241, 91, 91, 0.05)); }
    .red::before {
        box-shadow: 0 0 3rem rgba(241, 91, 91, 0.04); }
    .show {
        animation-name: show;
        animation-duration: 0.75s;
        animation-timing-function: linear; }
    @keyframes show {
        0% {
            opacity: 0.075; }
        50% {
            opacity: 1; }
        100% {
            opacity: 0.075; } }
    .menu {
        width: auto;
        /* height: 30%; */
        margin: 2rem;
        padding: 11px;
        border-radius: 100px;
        background: rgba(255, 255, 255, 0.1);
        justify-content: space-around;
        align-items: center;
        z-index: 1; }
    .setting {
        margin: .25rem;
        padding: 0.2rem 0.5rem;
        min-width: 1rem;
        background: #eee;
        border: none;
        border-radius: 5px;
        font-family: inherit;
        font-size: 12px;
        text-transform: uppercase;
        text-align: center; }
    .strict::after {
        content: '';
        display: block;
        float: right;
        margin: 0.2rem 0 0 0.2rem;
        height: 0.4rem;
        width: 0.4rem;
        border-radius: 50%;
        background: rgba(0, 0, 0, 0.5); }
    .strict-active::after {
        background: #ff4b4b;
        border: 0.01rem solid #ff9696;
        box-shadow: 0 0 0.25rem #ff9696;
        box-sizing: border-box; }
    .step-display {
        margin: 10px;
        padding: 1px;
        text-align: center;
        font-family: 'Ubuntu Mono', monospace;
        line-height: 1.175rem;
        background: #222;
        border-radius: 100px;
        color: #c8c8c8;
        letter-spacing: 0.075rem;
        transition: color 0.5s ease-in; }
    .no-display {
        color: rgba(100, 100, 100, 0.15); }
    .game-end {
        width: 95%;
        height: 90%;
        overflow: hidden;
        background: rgba(0, 0, 0, 0.75);
        color: white;
        font-size: 2rem;
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        box-sizing: border-box;
        z-index: -1;
        opacity: 0; }
    .visible {
        animation-name: visible;
        animation-duration: 2.5s;
        animation-timing-function: ease-in-out;
        z-index: 3; }
    @keyframes visible {
        0% {
            opacity: 0; }
        50% {
            opacity: 1; }
        100% {
            opacity: 0; } }
    @media (min-width: 1024px) {
        :root {
            font-size: calc(3vW); }
        .ball-container {
            width: 65vW; } }
    @media (min-width: 1281px) {
        :root {
            font-size: calc(2vW); }
        .ball-container {
            width: 50vW; } }
</style>
<div class="container">

    <div class="ball-container">
        <button data-id="0" class="ball yellow button">A</button>
        <button data-id="1" class="ball green button">B</button>
        <button data-id="2" class="ball blue button">C</button>
        <button data-id="3" class="ball red button">D</button>
    </div>

    <div class="menu">
        <button type="button" name="button" class="setting energy">ON</button>
        <button type="button" name="button" class="setting toggle" disabled>Go</button>
        <!--<button type="button" name="button" class="setting strict" disabled>STRICT</button>-->
        <div class="step-display no-display">
            <span class="counter-display">00</span>|<span class="total-display">00</span>
        </div>
    </div>

    <div class="game-end">
        You won! 🎉
    </div>


    <div>
        <div style="color: #20cf3b" id="theUsersName"></div>
        <input class="input" id="nameValue" placeholder="Winners: Search Your Name">
        <button class="button" onclick="findYourName()">find</button>
    </div>
</div>



<audio data-id="0" class="piano yellow" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/Piano.mf.G3.mp3"></audio>
<audio data-id="1" class="piano green" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/Piano.mf.B3.mp3"></audio>
<audio data-id="2" class="piano blue" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/Piano.mf.D4.mp3"></audio>
<audio data-id="3" class="piano red" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/Piano.mf.G4.mp3"></audio>
<audio class="buzzer" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/buzzer.mp3"></audio>
<audio class="gameover" src="https://raw.githubusercontent.com/Miffili/freeCodeCamp/0c7242f6d8f5b81707a9fff5facce6405c49e74c/FED-simongame/resources/gameover.mp3"></audio>

<script>
    const balls = document.querySelectorAll(".ball");
    const energyBtn = document.querySelector(".energy");
    const toggleBtn = document.querySelector(".toggle");
    const strictBtn = document.querySelector(".strict");
    const display = document.querySelector(".step-display");
    const displayCounter = document.querySelector(".counter-display");
    const displayTotal = document.querySelector(".total-display");
    const gameEnd = document.querySelector(".game-end");
    const audios = document.querySelectorAll(".piano");
    const buzzer = document.querySelector(".buzzer");
    const gameEndSound = document.querySelector(".gameover");
    const animation = "show";
    const ballTimeOuts = {};
    const userTimeOuts = {};
    const autoSequence = [0, 1, 2, 3];
    const gameSequence = [];
    let on = false;
    let gameRunning = false;
    let userturn = false;
    let strict = false;
    let gameCounter;
    let userCounter = 0;
    const coreTime = 750;
    const autoTimer = 50;
    const step = 100;
    const win = 19;
    const contractAddress = "n1vkEwW8LuNU3NmXJB3SUh8EBCxgBY6wbMF"
    document.addEventListener("DOMContentLoaded", function () {
        setTimeout(chromeWallet, 1000);
    });
    function chromeWallet() {
        console.log("check nebpay")
        try {
            var chromeCheck = require("nebpay");
        } catch (e) {
            console.log(e);
            if (window.confirm('Winners can save there progress if they use the Chrome web wallet extension. Click Confirm to download now ')) {
                window.location.href = 'https://github.com/ChengOrangeJu/WebExtensionWallet';
            }
        }
    }
    audios.forEach(function(audio) {
        audio.playbackRate = 3;
    });
    buzzer.volume = 0.05;
    gameEndSound.volume = 0.05;
    function randomize() {
        const num = Math.floor(Math.random() * 4);
        return num;
    }
    function initGame() {
        gameCounter = 0;
        gameSequence.splice(0);
        for (let i = 0; i < 20; i++) {
            const random = randomize();
            gameSequence.push(random);
        }
        playSeq();
    }
    window.addEventListener('message', function (e) {
        var theUsersName = e.data.data.neb_call.result;
        if (theUsersName === "null") {
            document.getElementById("theUsersName").innerHTML = `<h1> The Game did not find your name. Are you sure you Won? </h1>`;
        }
        if (theUsersName !== "null") {
            theUsersName = JSON.parse(e.data.data.neb_call.result)
            var encourageMent = ["Your Great", "You the Bomb", "Sick Bro", "Hella Cool", "Wow Amazing"]
            var randomEncourage = encourageMent[Math.floor(Math.random() * encourageMent.length)];
            document.getElementById("theUsersName").innerHTML = `<h1> ${theUsersName.key} </h1> <div> - ${theUsersName.value } ${randomEncourage} </div>`
        }
    })
    function resetGame() {
        clearBallTimeouts();
        clearBallAni();
        userturn = false;
        gameRunning = false;
        displayCounter.innerHTML = "00";
        toggleBtn.innerHTML = "start";
    }
    function gameOver() {
        gameEnd.classList.add("visible");
        gameEndSound.play();
        setTimeout(function() {
            gameEnd.classList.remove("visible");
            initGame();
        }, 2500);
    }
    function name2Contract() {
        var username = prompt("Your a Winner!!! enter your name", "Harry Potter");
        if (username == null) {
            username = prompt("Please enter your name", "Harry Potter");
        }else
            var highscore  = 20;
        username = username.toLowerCase()
        var func = "save";
        var args = "[\"" + username + "\",\"" + highscore  + "\"]";
        window.postMessage({
            "target": "contentscript",
            "data": {
                "to": contractAddress,
                "value": "0",
                "contract": {
                    "function": func,
                    "args": args
                }
            },
            "method": "neb_sendTransaction"
        }, "*");
    }
    function playSeq() {
        blockBalls();
        displayCounter.innerHTML =
            gameCounter < 9 ? `0${gameCounter + 1}` : `${gameCounter + 1}`;
        for (let i = 0; i <= gameCounter; i++) {
            ballTimeOuts[`ball${i}`] = setTimeout(function() {
                playBall(gameSequence[i]);
            }, i * (coreTime + 10));
        }
        // release Balls
        // includes userturn = true;
        const releaseTime = (gameCounter + 0.5) * (coreTime + 25);
        setTimeout(releaseBalls, releaseTime);
    }
    function replaySeq(input) {
        const id = parseInt(input);
        userGlowBall(id);
        if (gameCounter === win){
            alert("hey")
        }
        if (id !== gameSequence[userCounter]) {
            // wrong
            userturn = false;
            setTimeout(() => {
                buzzer.play();
            }, coreTime);
            if (!strict) {
                // non-strict
                setTimeout(playSeq, coreTime + 1000);
            } else {
                // strict
                setTimeout(initGame, coreTime + 1000);
            }
        } else {
            // right
            if (userCounter < gameCounter) {
                // In Replay
                userCounter++;
            } else {
                // End of Replay
                if (gameCounter === win) {
                    // End of Game
                    setTimeout(gameOver, coreTime * 1.5);
                } else {
                    // In Game
                    gameCounter++;
                    setTimeout(playSeq, coreTime + 500);
                }
            }
        }
    }
    function playBall(id) {
        soundBall(id);
        glowBall(id);
    }
    function soundBall(id) {
        const audio = document.querySelector(`audio[data-id="${id}"]`);
        audio.currentTime = 0;
        audio.play();
    }
    function glowBall(id) {
        const ball = document.querySelector(`button[data-id="${id}"]`);
        ball.classList.add(animation);
        setTimeout(function() {
            ball.classList.remove(animation);
        }, coreTime - 15);
    }
    function userGlowBall(id) {
        soundBall(id);
        if (balls[id].classList.value.includes("show")) {
            clearTimeout(userTimeOuts[`ball${id}`]);
            balls[id].classList.remove("show");
        }
        setTimeout(function() {
            balls[id].classList.add("show");
            userTimeOuts[`ball${id}`] = setTimeout(function() {
                balls[id].classList.remove("show");
            }, 1.2 * coreTime);
        }, 10);
    }
    function clearBallTimeouts() {
        for (let i = 0; i <= gameCounter; i++) {
            clearTimeout(ballTimeOuts[`ball${i}`]);
        }
    }
    function clearBallAni() {
        balls.forEach(function(ball) {
            ball.classList.remove(animation);
        });
    }
    function blockBalls() {
        userturn = false;
        balls.forEach(function(ball) {
            ball.setAttribute("disabled", "true");
        });
    }
    function releaseBalls() {
        userturn = true;
        userCounter = 0;
        balls.forEach(function(ball) {
            ball.removeAttribute("disabled");
        });
    }
    function autoBalls(type, autoTimer, step) {
        balls.forEach(function(ball) {
            ball.classList.remove(animation);
        });
        audios.forEach(function(audio) {
            audio.pause();
        });
        if (type === "on") {
            for (let i = 0; i < autoSequence.length; i++) {
                setTimeout(function() {
                    glowBall(i);
                }, autoTimer);
                autoTimer += step;
            }
        } else if (type === "off") {
            for (let i = autoSequence.length; i > 0; i--) {
                setTimeout(function() {
                    glowBall(i - 1);
                }, autoTimer);
                autoTimer += step;
            }
        }
    }
    balls.forEach(ball =>
        ball.addEventListener("click", function() {
            if (on && !gameRunning) {
                userGlowBall(ball.dataset.id);
            } else if (gameRunning && userturn) {
                replaySeq(ball.dataset.id);
            }
        })
    );
    energyBtn.addEventListener("click", function() {
        energyBtn.setAttribute("disabled", "true");
        if (energyBtn.innerHTML === "ON") {
            // ON
            autoBalls("on", autoTimer, step);
            on = true;
            energyBtn.innerHTML = "OFF";
            displayTotal.innerHTML = win < 9 ? `0${win + 1}` : `${win + 1}`;
            display.classList.toggle("no-display");
            setTimeout(function() {
                toggleBtn.removeAttribute("disabled");
                strictBtn.removeAttribute("disabled");
            }, autoTimer + step * autoSequence.length + coreTime / 2);
        } else {
            // OFF
            resetGame();
            setTimeout(function() {
                autoBalls("off", autoTimer, step);
            }, 50);
            on = false;
            strict = false;
            energyBtn.innerHTML = "ON";
            toggleBtn.setAttribute("disabled", "true");
            strictBtn.setAttribute("disabled", "true");
            strictBtn.classList.remove("strict-active");
            displayTotal.innerHTML = "00";
            display.classList.toggle("no-display");
        }
        setTimeout(function() {
            energyBtn.removeAttribute("disabled");
        }, autoTimer + step * autoSequence.length + coreTime / 2);
    });
    toggleBtn.addEventListener("click", function() {
        clearBallTimeouts();
        gameRunning = true;
        const status = toggleBtn.innerHTML.toLowerCase();
        toggleBtn.innerHTML = gameRunning ? "reset" : "start";
        toggleBtn.setAttribute("disabled", "true");
        setTimeout(function() {
            toggleBtn.removeAttribute("disabled");
            initGame();
        }, 500);
    });
    function findYourName() {
        var nameValue = document.getElementById("nameValue").value
        var func = "get"
        var args = "[\"" + nameValue + "\"]"
        window.postMessage({
            "target": "contentscript",
            "data": {
                "to": contractAddress,
                "value": "0",
                "contract": {
                    "function": func,
                    "args": args
                }
            },
            "method": "neb_call"
        }, "*");
    }
    if(userCounter === win){
        name2Contract()
    }
</script>
</body>
</html>
```
# 智能合约代码

```
"use strict";

var Name = function(text) {
	if (text) {
		var obj = JSON.parse(text);
		this.key = obj.key;
		this.value = obj.value;
	} else {
	    this.key = "";
	    this.value = "";
	}
};

Name.prototype = {
	toString: function () {
		return JSON.stringify(this);
	}
};

var MyMemory = function () {
    LocalContractStorage.defineMapProperty(this, "repo", {
        parse: function (text) {
            return new Name(text);
        },
        stringify: function (o) {
            return o.toString();
        }
    });
};

MyMemory.prototype = {
    init: function () {

    },

    save: function (key, value) {

        key = key.trim();
        value = value.trim();
        if (key === "" || value === ""){
            throw new Error("no name");
        }

        var usersName = this.repo.get(key);
        if (usersName){
            throw new Error("This Name is already being used");
        }

        usersName = new Name();
        usersName.key = key;
        usersName.value = value;

        this.repo.put(key, usersName);
    },

    get: function (key) {
        key = key.trim();
        if ( key === "" ) {
            throw new Error("empty key")
        }
        return this.repo.get(key);
    }
};
module.exports = MyMemory;
```
