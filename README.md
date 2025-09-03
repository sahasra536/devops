<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Registration Form</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 40px; }
    form { width: 300px; margin: auto; }
    input[type="text"], input[type="email"], input[type="password"] {
      width: 100%; padding: 8px; margin: 8px 0; box-sizing: border-box;
    }
    input[type="submit"] {
      background: #007bff; color: white; border: none; padding: 10px;
      width: 100%; cursor: pointer; font-size: 16px;
    }
    .error { color: red; }
  </style>
</head>
<body>
  <h2>Registration Form</h2>
  <form id="registrationForm" autocomplete="off">
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required />

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required />

    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required minlength="6" />

    <label for="confirm_password">Confirm Password:</label>
    <input type="password" id="confirm_password" name="confirm_password" required minlength="6" />

    <div class="error" id="error"></div>
    <input type="submit" value="Register" />
  </form>
  <script>
    document.getElementById('registrationForm').addEventListener('submit', function(e) {
      e.preventDefault();
      var error = '';
      var password = document.getElementById('password').value;
      var confirm = document.getElementById('confirm_password').value;
      if (password.length < 6) {
        error = "Password must be at least 6 characters.";
      } else if (password !== confirm) {
        error = "Passwords do not match.";
      }
      document.getElementById('error').textContent = error;
      if (!error) {
        alert('Registration successful!');
        // Here you can send the data to your server using fetch/AJAX
        // e.g., fetch('/register', {method:'POST', body:...})
      }
    });
  </script>
</body>
</html>
