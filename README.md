<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CONTROLE DE PESO</title>
    <style>
        body {
            background-image: url('https://images.pexels.com/photos/2803158/pexels-photo-2803158.jpeg?auto=compress&cs=tinysrgb&w=600');
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
        }
        h1 {
            margin-top: 20px;
            color: #333;
        }
        .planner {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 10px;
            max-width: 600px;
            margin: 20px auto;
        }
        .day-container {
            background-color: #d0e4f7;
            padding: 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
            transition: background-color 0.3s ease;
            position: relative;
        }
        .day-container.completed {
            background-color: #5cb85c;
            color: white;
        }
        .day-container:hover {
            background-color: #a4d4f2;
        }
        .comment {
            margin-top: 10px;
            display: block;
        }
        .comment input {
            width: 100%;
            padding: 5px;
            margin-top: 5px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <h1>Controle de peso</h1>
    <div class="planner" id="planner">
        <!-- Os dias serão gerados automaticamente via JavaScript -->
    </div>

    <script>
        const planner = document.getElementById("planner");

        // Função para gerar os dias do planner
        function criarPlanner() {
            for (let dia = 1; dia <= 30; dia++) {
                // Criando o container do dia
                let diaContainer = document.createElement("div");
                diaContainer.classList.add("day-container");

                // Número do dia
                let diaDiv = document.createElement("div");
                diaDiv.textContent = `Dia ${dia}`;

                // Criando a caixa de comentário
                let commentDiv = document.createElement("div");
                commentDiv.classList.add("comment");

                // Campo de texto para o comentário
                let inputComment = document.createElement("input");
                inputComment.type = "text";
                inputComment.placeholder = "Adicione um comentário...";

                // Adicionando o evento de clique para completar o dia
                diaContainer.addEventListener("click", function() {
                    this.classList.toggle("completed");
                });

                // Adiciona o campo de comentário ao div de comentários
                commentDiv.appendChild(inputComment);

                // Adiciona o número do dia e o campo de comentário ao container do dia
                diaContainer.appendChild(diaDiv);
                diaContainer.appendChild(commentDiv);

                // Adiciona o container completo ao planner
                planner.appendChild(diaContainer);
            }
        }

        // Chamar a função para gerar o planner
        criarPlanner();
    </script>
</body>
</html>
