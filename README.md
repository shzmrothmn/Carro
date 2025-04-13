// Simple Trade-In Service Website using HTML, CSS, and JavaScript

const app = `
  <div style="font-family: Arial, sans-serif; padding: 2rem; max-width: 600px; margin: auto; background-color: orange; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1);">
    <div style="text-align: center; margin-bottom: 1.5rem;">
      <img src="/mnt/data/F8D975A3-FF13-4114-A687-15CBC2280FD2.png" alt="Carro Logo" style="max-width: 200px;">
    </div>
    <h1 style="text-align: center;">Servis Trade-In Kereta</h1>
    <p>Kami menyediakan servis trade-in kereta dengan tawaran berikut:</p>
    <ul>
      <li>Quote harga kereta mengikut brand, model, variasi dan tahun pembuatan</li>
      <li>Pemeriksaan kereta secara percuma</li>
      <li>Pembayaran dalam 24 jam</li>
    </ul>

    <h2>Hubungi Kami</h2>
    <p>Untuk maklumat lanjut atau untuk dapatkan quote, sila hubungi kami melalui WhatsApp:</p>
    <a href="https://wa.me/601133060668" style="display: inline-block; padding: 10px 20px; background-color: #25D366; color: white; text-decoration: none; border-radius: 5px;">Whatsapp Sekarang</a>

    <h2 style="margin-top: 2rem;">Dapatkan Quote Sekarang</h2>
    <form id="quoteForm">
      <label>Brand: <input type="text" name="brand" required></label><br><br>
      <label>Model: <input type="text" name="model" required></label><br><br>
      <label>Variasi: <input type="text" name="variant" required></label><br><br>
      <label>Tahun: <input type="number" name="year" required></label><br><br>
      <button type="submit">Dapatkan Quote</button>
    </form>
    <p id="result" style="margin-top: 1rem; font-weight: bold;"></p>
  </div>
`;

document.body.style.margin = 0;
document.body.style.backgroundColor = "orange";
document.body.innerHTML = app;

document.getElementById('quoteForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const brand = e.target.brand.value;
  const model = e.target.model.value;
  const variant = e.target.variant.value;
  const year = e.target.year.value;

  // Simulasi anggaran harga
  const hargaAnggaran = 50000 - (new Date().getFullYear() - year) * 3000;

  document.getElementById('result').textContent = `Anggaran harga untuk ${brand} ${model} (${variant}, ${year}): RM${hargaAnggaran.toLocaleString()}`;
});
