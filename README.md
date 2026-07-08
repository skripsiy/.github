# Cara Memindahkan Repository ke Organisasi (Tetap Menyimpan Commit & Branch)

## 1. Migrasi Seluruh Branch dan Commit ke Repo Baru (Organisasi)
Jalankan di terminal/CMD:
```bash
git clone --bare <URL LAMA> temp-repo.git
cd temp-repo.git
git push --mirror <URL BARU>
```
*(Setelah selesai, folder `temp-repo.git` bisa dihapus, untuk paste urlnya timpa <URL LAMA> nya).*

---

## 2. Hubungkan Agar Bisa Push ke Repo Pribadi dan Organisasi Sekaligus
Jalankan perintah ini di dalam folder proyek utama Anda:
```bash
git remote set-url --add --push origin <URL LAMA>
git remote set-url --add --push origin <URL BARU>
```

Untuk mengecek apakah konfigurasi sudah masuk:
```bash
git remote -v
```
*(Setiap kali Anda melakukan `git push`, otomatis perubahan akan dikirim ke kedua repositori tersebut).*
