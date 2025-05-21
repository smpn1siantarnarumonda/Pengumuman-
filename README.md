<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Pengumuman Kelulusan</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
    }
    .container {
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
      text-align: center;
      max-width: 400px;
      width: 100%;
    }
    input {
      padding: 10px;
      width: 100%;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 20px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
    .lulus {
      color: green;
    }
    .tidak-lulus {
      color: red;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Pengumuman Kelulusan</h2>
    <p>Masukkan NISN Anda untuk melihat hasil kelulusan.</p>
    <input type="text" id="nisnInput" placeholder="Masukkan NISN">
    <button onclick="cekKelulusan()">Cek</button>
    <div id="result" class="result"></div>
  </div>

  <script>
    // Contoh data siswa: NISN => Status Kelulusan
    const dataKelulusan = {
      "1234567890": "LULUS",
      "0987654321": "TIDAK LULUS",
      "1122334455": "LULUS"
    };

    function cekKelulusan() {
      const nisn = document.getElementById("nisnInput").value.trim();
      const resultDiv = document.getElementById("result");

      if (nisn in dataKelulusan) {
        const status = dataKelulusan[nisn];
        resultDiv.innerHTML = `Status Kelulusan: <span class="${status === 'LULUS' ? 'lulus' : 'tidak-lulus'}">${status}</span>`;
      } else {
        resultDiv.innerHTML = `<span class="tidak-lulus">NISN tidak ditemukan.</span>`;
      }
    }
  </script>
</body>
</html>
