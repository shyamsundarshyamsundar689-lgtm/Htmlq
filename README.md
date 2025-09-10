# Htmlq
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(120deg, #89f7fe, #66a6ff);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .container {
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.2);
      width: 300px;
      text-align: center;
    }

    h2 {
      margin-bottom: 15px;
      color: #333;
    }

    input {
      padding: 10px;
      width: 70%;
      border: 1px solid #ccc;
      border-radius: 8px;
      outline: none;
    }

    button {
      padding: 10px;
      border: none;
      background: #66a6ff;
      color: white;
      border-radius: 8px;
      cursor: pointer;
      margin-left: 5px;
    }

    button:hover {
      background: #557ee0;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      background: #f1f1f1;
      margin: 5px 0;
      padding: 10px;
      border-radius: 8px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .delete {
      background: crimson;
      border: none;
      padding: 5px 8px;
      color: white;
      border-radius: 6px;
      cursor: pointer;
    }

    .delete:hover {
      background: darkred;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>To-Do List</h2>
    <input type="text" id="taskInput" placeholder="Enter a task...">
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const taskText = input.value.trim();

      if (taskText === "") {
        alert("Please enter a task!");
        return;
      }

      const li = document.createElement("li");
      li.textContent = taskText;

      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "X";
      deleteBtn.className = "delete";
      deleteBtn.onclick = function () {
        li.remove();
      };

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);

      input.value = "";
    }
  </script>
</body>
</html>
