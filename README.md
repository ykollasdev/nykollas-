pedido_coracoes.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedido Especial</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        /* Estilo inspirado em um tema romântico */
        body {
            font-family: 'Cinzel', serif;
            background-color: #ffd6e7;
            color: #6c4d17;
            text-align: center;
            padding: 50px;
            overflow: hidden;
        }

        h1 {
            font-size: 3rem;
            color: #6c4d17;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
        }

        p {
            font-size: 1.5rem;
            margin: 20px 0;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
        }

        button {
            background: linear-gradient(135deg, #e7c87e, #9b572c);
            color: #fff7d6;
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }

        button:hover {
            transform: scale(1.1);
            box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.5);
        }

        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .heart {
            position: absolute;
            width: 40px;
            height: 40px;
            background: red;
            clip-path: polygon(50% 0%, 100% 35%, 80% 100%, 50% 75%, 20% 100%, 0% 35%);
            animation: float 8s infinite ease-in-out;
            opacity: 0;
        }

        @keyframes float {
            0% {
                transform: translateY(100%);
                opacity: 0.5;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-20%);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <h1>Manuela, você aceita ser minha princesa?</h1>
    <p>Assim como no conto de fadas, quero que nossa história seja cheia de amor e magia! ❤️</p>
    <button id="acceptButton">Sim, eu aceito!</button>

    <!-- Corações -->
    <div class="hearts"></div>

    <script>
        // Adiciona corações flutuando
        function createHearts() {
            for (let i = 0; i < 20; i++) {
                let heart = $('<div class="heart"></div>');
                heart.css({
                    left: Math.random() * 100 + "%",
                    animationDelay: Math.random() * 6 + "s",
                    animationDuration: Math.random() * 10 + 6 + "s"
                });
                $(".hearts").append(heart);
            }
        }

        // Inicializa os corações
        $(document).ready(function () {
            createHearts();

            // Clique no botão
            $("#acceptButton").on("click", function () {
                $("body").css("background", "linear-gradient(135deg, #ffcce7, #ffe6f2)");
                $("h1").text("Ela disse SIM! 🎉💖");
                $("p").text("Agora, nosso amor está oficializado!");
                $(this).fadeOut();
            });
        });
    </script>
</body>
</html>
