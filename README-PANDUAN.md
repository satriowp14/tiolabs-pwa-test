# TIOLABS PWA Compatibility Test v1

Tujuan: menguji dukungan PWA di PC yang dikelola administrator, TANPA mencoba melewati kebijakan IT. Tidak menggunakan API eksternal, login, tracking, atau data BRI.

## Pasang ke GitHub Pages (disarankan)
1. Di GitHub, buat repository PUBLIC baru misalnya `tiolabs-pwa-test` (kontennya hanya berisi alat tes).
2. Upload SEMUA file dari folder ini ke root repository: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`. Jangan upload ZIP saja.
3. Buka Settings > Pages > Build and deployment: Deploy from a branch > `main` > `/ (root)` > Save.
4. Akses `https://USERNAME.github.io/tiolabs-pwa-test/` (ganti USERNAME). Untuk tes offline/Service Worker wajib HTTPS.
5. Pastikan URL tersebut diizinkan oleh kebijakan jaringan dan administrator TI. Jika situs diblokir, JANGAN mencari cara bypass; minta izin TI.

## Uji di PC target
1. Buka link HTTPS di Chrome/Edge yang benar-benar dipakai pada PC kerja.
2. Klik 'Jalankan Semua Tes'. Catat hasil lokalStorage, IndexedDB, SW, Cache.
3. Isi data DUMMY lalu klik 'Simpan Lokal'. Tutup seluruh browser, buka lagi link, klik 'Baca Kembali'.
4. Jika diizinkan, instal via tombol instal atau menu browser; jalankan dari shortcut untuk melihat mode Standalone.
5. Jika kebijakan kantor membolehkan, tes offline dengan mematikan jaringan secara normal setelah halaman selesai di-cache, lalu buka lagi PWA dan baca data. Jangan mengubah konfigurasi administrator.
6. Unduh 'Laporan JSON' lalu periksa isinya sebelum membagikan.

## Interpretasi
- Tulis/baca OK tidak membuktikan data tetap ada setelah restart/logout PC. Ulangi tes setelah restart PC dan keesokan harinya.
- Prompt install tidak muncul bukan bukti pasti bahwa instalasi dilarang; gunakan menu browser atau minta verifikasi TI.
- Persistent Storage TERBATAS tidak berarti IndexedDB gagal; backup tetap perlu.
- Jaringan intranet mungkin memblokir GitHub Pages; izin TI dibutuhkan untuk domain produksi.
- Tidak ada data yang dikirim ke server oleh JavaScript, tetapi hosting dan jaringan kantor dapat memiliki access logs standar (misalnya IP dan permintaan halaman).
- Jangan masukkan informasi pekerjaan atau dokumen asli ke alat uji.
