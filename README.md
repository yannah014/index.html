<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ICT HTML Creator</title>
    
    <link rel="icon" type="image/png" href="Jeon.PNG">
    
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.12/codemirror.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.12/codemirror.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.12/mode/xml/xml.min.js"></script>

    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }

        body {
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.8), rgba(25, 25, 112, 0.8)), url('Grace.JPG') no-repeat center center fixed;
            background-size: cover;
            color: white;
            text-align: center;
            padding: 20px;
            transition: 0.5s;
        }

        .dark-mode {
            background: linear-gradient(135deg, #1e1e1e, #252525);
            color: #ffcc00;
        }

        .dark-mode-toggle {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 25px;
            cursor: pointer;
            transition: transform 0.5s ease-in-out;
        }

        .dark-mode-toggle:hover {
            transform: rotate(360deg);
        }

        h1 {
            font-size: 3rem;
            color: #ffcc00;
            text-shadow: 0 0 10px #ffcc00, 0 0 20px #ffcc00;
            display: inline-block;
        }

        .container {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(12px);
            padding: 25px;
            border-radius: 15px;
            width: 90%;
            max-width: 500px;
            margin: 20px auto;
            transition: transform 0.3s ease-in-out;
        }

        .container:hover {
            transform: scale(1.05);
        }

        .output-container {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(12px);
            padding: 20px;
            border-radius: 15px;
            width: 100%;
            max-width: 550px;
            margin: 20px auto;
        }

        button {
            background: #ffcc00;
            color: #333;
            font-weight: bold;
            cursor: pointer;
            padding: 8px;
            width: 48%;
            border: none;
            border-radius: 5px;
            margin-top: 10px;
            font-size: 14px;
            transition: all 0.3s ease-in-out;
        }

        button:hover {
            background: #ff9900;
        }

        iframe {
            width: 100%;
            height: 300px;
            border: none;
            margin-top: 20px;
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <i class="fa-solid fa-moon dark-mode-toggle" onclick="toggleDarkMode()"></i>
    <h1 class="typing">HTML Creator Web</h1>

    <div class="container">
        <label><strong>Records:</strong></label>
        <select onchange="navigateToPage(this.value)">
            <option value="">Select an option</option>
            <option value="ATV.html">Activities</option>
            <option value="test_scores.html">Test Scores</option>
        </select>

        <label><strong>Attendance:</strong></label>
        <select onchange="navigateToPage(this.value)">
            <option value="">Select a month</option>
            <option value="attendance_february.html">February</option>
            <option value="attendance_march.html">March</option>
            <option value="attendance_april.html">April</option>
        </select>
        <button onclick="location.href='view_saved.html'">View Saved Files</button>
    </div>

    <div class="container">
        <h2>Coding Time!</h2>
        <textarea id="htmlInput"></textarea><br>
        <button onclick="generateHTML()">Generate Webpage</button>
    </div>

    <div class="output-container">
        <iframe id="outputFrame"></iframe>
        <button onclick="saveHTML()">Save</button>
        <button onclick="deleteInput()">Delete</button>
    </div>

    <footer>
       <h4>
    <button onclick="location.href='chatbot.html'" 
        style="color: white; background: none; border: none; font-size: 1rem; cursor: pointer; font-weight: bold;">
        WEBPAGE created by </button>
</h4>

        <h3>
            <a href="https://www.facebook.com/share/16486S6DxY/?mibextid=wwXIfr"" target="_blank" style="color: #4caf50; text-decoration: none; font-weight: bold;">
                Villano, Irish Grace D.
            </a>
            <a href="https://www.facebook.com/share/1BVSj4zZSL/?mibextid=wwXIfr" targ
