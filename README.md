# Atividade-1<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Sistema de Cálculo de Notas</title>

<style>
    body {
        background: #f3f3f3;
        font-family: Arial;
        display: flex;
        justify-content: center;
        padding: 30px;
    }
    .container {
        background: white;
        padding: 25px;
        border-radius: 10px;
        box-shadow: 0 0 10px #999;
        width: 450px;
    }
    .grupo {
        background: #eef;
        padding: 10px;
        margin-bottom: 12px;
        border-radius: 5px;
    }
    input {
        width: 120px;
        padding: 5px;
        margin: 4px;
        text-align: center;
    }
    button {
        margin-top: 20px;
        padding: 10px;
        width: 100%;
        font-size: 16px;
        background: rgb(0, 140, 255);
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    button:hover {
        background: rgb(0, 100, 200);
    }
    #resultado {
        margin-top: 20px;
        padding: 10px;
        background: #eef;
        border-radius: 5px;
    }
</style>
</head>

<body>
<div class="container">
    <h2>Sistema de Cálculo Escolar</h2>
    <p>Insira as notas bimestrais:</p>

    <div class="grupo">
        <strong>1º BIMESTRE</strong><br>
        <input type="number" id="n1" placeholder="1ª Nota B1" step="0.1">
        <input type="number" id="n2" placeholder="2ª Nota B1" step="0.1">
    </div>

    <div class="grupo">
        <strong>2º BIMESTRE</strong><br>
        <input type="number" id="n3" placeholder="1ª Nota B2" step="0.1">
        <input type="number" id="n4" placeholder="2ª Nota B2" step="0.1">
    </div>

    <div class="grupo">
        <strong>3º BIMESTRE</strong><br>
        <input type="number" id="n5" placeholder="1ª Nota B3" step="0.1">
        <input type="number" id="n6" placeholder="2ª Nota B3" step="0.1">
    </div>

    <div class="grupo">
        <strong>4º BIMESTRE</strong><br>
        <input type="number" id="n7" placeholder="1ª Nota B4" step="0.1">
        <input type="number" id="n8" placeholder="2ª Nota B4" step="0.1">
    </div>

    <button onclick="calcular()">Calcular Médias</button>

    <div id="resultado"></div>
</div>

<script>
function calcular() {
    let notas = [];
    for (let i = 1; i <= 8; i++) {
        let valor = document.getElementById("n" + i).value;
        if (valor === "") {
            alert("Preencha todas as notas!");
            return;
        }
        notas.push(parseFloat(valor));
    }

    let b1 = (notas[0] + notas[1]) / 2;
    let b2 = (notas[2] + notas[3]) / 2;
    let b3 = (notas[4] + notas[5]) / 2;
    let b4 = (notas[6] + notas[7]) / 2;

    let s1 = (b1 + b2) / 2;
    let s2 = (b3 + b4) / 2;

    let final = (s1 + s2) / 2;

    document.getElementById("resultado").innerHTML = `
        <strong>RESULTADOS:</strong><br><br>
        1º Bimestre: ${b1.toFixed(1)}<br>
        2º Bimestre: ${b2.toFixed(1)}<br>
        <strong>1º Semestre: ${s1.toFixed(1)}</strong><br><br>

        3º Bimestre: ${b3.toFixed(1)}<br>
        4º Bimestre: ${b4.toFixed(1)}<br>
        <strong>2º Semestre: ${s2.toFixed(1)}</strong><br><br>

        <strong style="font-size:18px;">Média Final: ${final.toFixed(1)}</strong>
    `;
}
</script>

</body>
</html>
