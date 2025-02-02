<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع تبادل الأغراض</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #e9ecef;
            margin: 0;
            padding: 0;
        }
        header {
            background: linear-gradient(to right, #007BFF, #0056b3);
            color: #fff;
            padding: 20px 0;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        .container {
            width: 90%;
            max-width: 800px;
            margin: 20px auto;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
        }
        h2, h3 {
            color: #343a40;
            margin-bottom: 15px;
        }
        .item {
            border: 1px solid #ddd;
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
            background: #f8f9fa;
            transition: transform 0.2s;
        }
        .item:hover {
            transform: scale(1.02);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }
        button {
            background: #28a745;
            color: #fff;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 5px;
            transition: background 0.3s;
        }
        button:hover {
            background: #218838;
        }
        input {
            margin: 5px 0;
            padding: 10px;
            width: 100%;
            box-sizing: border-box;
            border: 1px solid #ced4da;
            border-radius: 5px;
        }
        input:focus {
            border-color: #007BFF;
            outline: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>موقع تبادل الأغراض</h1>
        <p>تبادل، شارك، واستفد!</p>
    </header>
    <div class="container">
        <h2>تسجيل الدخول</h2>
        <input type="text" id="username" placeholder="اسم المستخدم">
        <input type="password" id="password" placeholder="كلمة المرور">
        <button onclick="login()">تسجيل الدخول</button>

        <h2>الأغراض المتاحة للتبادل</h2>
        <div id="itemsList"></div>

        <h3>أضف غرضًا جديدًا</h3>
        <input type="text" id="itemInput" placeholder="اسم الغرض">
        <button onclick="addItem()">أضف</button>
    </div>

    <script>
        const itemsList = [];

        function addItem() {
            const itemInput = document.getElementById('itemInput');
            const itemName = itemInput.value.trim();
            if (itemName) {
                itemsList.push(itemName);
                itemInput.value = '';
                displayItems();
            }
        }

        function displayItems() {
            const itemsDiv = document.getElementById('itemsList');
            itemsDiv.innerHTML = '';
            itemsList.forEach(item => {
                itemsDiv.innerHTML += `<div class="item">${item}</div>`;
            });
        }

        function login() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            if (username && password) {
                alert('تسجيل الدخول بنجاح!');
            } else {
                alert('يرجى إدخال اسم المستخدم وكلمة المرور!');
            }
        }
    </script>
</body>
</html>
