<!DOCTYPE html>
<html>
<head>
    <title>Fuel Range Estimator - Vride Solutions</title>
    <style>
        body {
            background: #111;
            color: #0f0;
            font-family: Consolas, monospace;
            padding: 20px;
        }
        .console {
            background: #000;
            padding: 20px;
            border-radius: 8px;
            border: 2px solid #0f0;
            width: 100%;
            max-width: 500px;
            margin: auto;
            font-size: 18px;
        }
        input {
            background: #222;
            color: #0f0;
            border: 1px solid #0f0;
            padding: 8px;
            width: 90%;
            margin-top: 5px;
        }
        button {
            margin-top: 10px;
            padding: 8px 15px;
        }
    </style>
</head>

<body>
    <div class="console">
        <p>> Enter the number of fuel bars:</p>
        <input type="number" id="bars">

        <p>> Enter mileage of your vehicle (KMPL):</p>
        <input type="number" id="mileage">

        <button onclick="calculate()">Run</button>

        <pre id="output"></pre>
    </div>

    <script>
        function calculate() {
            let bar = parseFloat(document.getElementById("bars").value);
            let mileage = parseFloat(document.getElementById("mileage").value);

            let tank_cap = 50;
            let fuel_bars = 6;
            let per_bar_ltr = tank_cap / fuel_bars;

            let litre = per_bar_ltr * 1;
            let range = mileage * litre * bar;

            let text = "";
            text += `As per available info, 1 bar equals to ${per_bar_ltr.toFixed(2)} L\n`;
            text += `So in available fuel, your vehicle can go up to ${range.toFixed(2)} KM\n\n`;
            text += `Thank You for choosing Vride Solutions`;

            document.getElementById("output").textContent = text;
        }
    </script>

</body>
</html>

