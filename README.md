<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Escape Room: Doodverlaard</title>
    <style>
        body {
            background-color: #000000;
            color: #ff0000;
            font-family: 'Creepster', sans-serif;
            text-align: center;
        }
        h1 {
            font-size: 3em;
            margin-top: 20px;
        }
        .start-screen, .end-screen, .puzzle {
            display: none;
        }
        #startScreen {
            display: block;
        }
        .btn {
            background-color: #ff0000;
            color: #000;
            padding: 10px 20px;
            font-size: 1.5em;
            border: none;
            cursor: pointer;
            margin-top: 20px;
        }
        .btn:hover {
            background-color: #b30000;
        }
        .puzzle {
            margin-top: 20px;
            font-size: 1.2em;
        }
        .puzzle input {
            padding: 10px;
            font-size: 1.2em;
            border: 1px solid #fff;
            margin-top: 10px;
        }
        .correct {
            color: #00ff00;
        }
        .incorrect {
            color: #ff3333;
        }
        .end-screen h2 {
            font-size: 2.5em;
            margin-top: 20px;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Creepster&display=swap" rel="stylesheet">
</head>
<body>
    <div id="startScreen">
        <h1>Escape Room: Doodverlaard</h1>
        <p>Welkom bij de escape room geïnspireerd op het boek "Doodverlaard". Los de raadsels op om te ontsnappen!</p>
        <button class="btn" onclick="startGame()">Start de game</button>
    </div>

    <div id="puzzleScreen" class="puzzle">
        <h2>Raadsel 1</h2>
        <p>Wie is het hoofdpersonage in het boek "Doodverlaard"?</p>
        <input type="text" id="answer1" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer1', 'Lars')">Check antwoord</button>
        <p id="response1"></p>
    </div>

    <div id="puzzleScreen2" class="puzzle">
        <h2>Raadsel 2</h2>
        <p>Wat is het mysterieuze object dat centraal staat in het verhaal?</p>
        <input type="text" id="answer2" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer2', 'De spiegel')">Check antwoord</button>
        <p id="response2"></p>
    </div>

    <div id="puzzleScreen3" class="puzzle">
        <h2>Raadsel 3</h2>
        <p>Welke stad speelt een grote rol in het boek?</p>
        <input type="text" id="answer3" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer3', 'Antwerpen')">Check antwoord</button>
        <p id="response3"></p>
    </div>

    <div id="puzzleScreen4" class="puzzle">
        <h2>Raadsel 4</h2>
        <p>Wat gebeurt er met Lars' vriendin in het verhaal?</p>
        <input type="text" id="answer4" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer4', 'Ze verdwijnt')">Check antwoord</button>
        <p id="response4"></p>
    </div>

    <div id="puzzleScreen5" class="puzzle">
        <h2>Raadsel 5</h2>
        <p>Hoe wordt het geheim van de spiegel onthuld?</p>
        <input type="text" id="answer5" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer5', 'Door een oude brief')">Check antwoord</button>
        <p id="response5"></p>
    </div>

    <div id="puzzleScreen6" class="puzzle">
        <h2>Raadsel 6</h2>
        <p>Wat is de betekenis van de titel "Doodverlaard"?</p>
        <input type="text" id="answer6" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer6', 'Het idee van het onvermijdelijke einde')">Check antwoord</button>
        <p id="response6"></p>
    </div>

    <div id="puzzleScreen7" class="puzzle">
        <h2>Raadsel 7</h2>
        <p>Welke mysterieuze figuur helpt Lars tijdens zijn zoektocht?</p>
        <input type="text" id="answer7" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer7', 'De oude man')">Check antwoord</button>
        <p id="response7"></p>
    </div>

    <div id="puzzleScreen8" class="puzzle">
        <h2>Raadsel 8</h2>
        <p>Wat is de ultieme oplossing voor het mysterie van de spiegel?</p>
        <input type="text" id="answer8" placeholder="Antwoord hier..." />
        <button class="btn" onclick="checkAnswer('answer8', 'De spiegel is een poort naar een andere wereld')">Check antwoord</button>
        <p id="response8"></p>
    </div>

    <div id="endScreen" class="end-screen">
        <h2>Gefeliciteerd, je hebt het mysterie van Doodverlaard opgelost!</h2>
        <p>Je hebt ontsnapt!</p>
        <button class="btn" onclick="resetGame()">Speel opnieuw</button>
    </div>

    <script>
        function startGame() {
            document.getElementById('startScreen').style.display = 'none';
            document.getElementById('puzzleScreen').style.display = 'block';
        }

        function checkAnswer(answerId, correctAnswer) {
            var userAnswer = document.getElementById(answerId).value.trim().toLowerCase();
            var responseId = 'response' + answerId.charAt(answerId.length - 1);
            var responseMessage = document.getElementById(responseId);

            if (userAnswer === correctAnswer.toLowerCase()) {
                responseMessage.textContent = "Correct!";
                responseMessage.className = 'correct';
                nextPuzzle(answerId);
            } else {
                responseMessage.textContent = "Helaas, probeer het opnieuw.";
                responseMessage.className = 'incorrect';
            }
        }

        function nextPuzzle(answerId) {
            if (answerId === 'answer1') {
                document.getElementById('puzzleScreen2').style.display = 'block';
            } else if (answerId === 'answer2') {
                document.getElementById('puzzleScreen3').style.display = 'block';
            } else if (answerId === 'answer3') {
                document.getElementById('puzzleScreen4').style.display = 'block';
            } else if (answerId === 'answer4') {
                document.getElementById('puzzleScreen5').style.display = 'block';
            } else if (answerId === 'answer5') {
                document.getElementById('puzzleScreen6').style.display = 'block';
            } else if (answerId === 'answer6') {
                document.getElementById('puzzleScreen7').style.display = 'block';
            } else if (answerId === 'answer7') {
                document.getElementById('puzzleScreen8').style.display = 'block';
            } else if (answerId === 'answer8') {
                document.getElementById('endScreen').style.display = 'block';
            }
        }

        function resetGame() {
            location.reload();
        }
    </script>
</body>
</html>
