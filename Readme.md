# Remote dan Root SSH di Linux Ubuntu

## Pada Ubuntu Server:

1. **Instalasi OpenSSH Server**: Pastikan OpenSSH Server sudah terinstal dan berjalan di Ubuntu Server. Jika belum, Anda dapat menginstalnya dengan perintah:

   ```bash
   sudo apt update
   sudo apt install openssh-server
   ```

2. **Konfigurasi OpenSSH Server (opsional)**: Anda dapat mengkonfigurasi OpenSSH Server untuk mengizinkan akses root atau remote login dengan mengedit file konfigurasi SSH di `/etc/ssh/sshd_config` dan menyesuaikan pengaturan sesuai kebutuhan.

3. **Restart OpenSSH Server**: Setelah mengubah konfigurasi, pastikan untuk merestart layanan OpenSSH agar perubahan berlaku:

   ```bash
   sudo systemctl restart ssh
   ```

4. **Periksa Alamat IP**: Pastikan Anda mengetahui alamat IP dari Ubuntu Server. Anda dapat melihatnya dengan perintah:
   ```bash
   ip a
   ```

## Pada Ubuntu Desktop:

1. **Instalasi OpenSSH Client**: Pastikan Anda memiliki klien SSH terinstal di Ubuntu Desktop. Jika belum, Anda dapat menginstalnya dengan perintah:

   ```bash
   sudo apt update
   sudo apt install openssh-client
   ```

2. **Remote ke Ubuntu Server**: Gunakan perintah SSH untuk terhubung ke Ubuntu Server dari Ubuntu Desktop:

   ```bash
   ssh username@alamat_ip_server
   ```

   Ganti `username` dengan nama pengguna di Ubuntu Server dan `alamat_ip_server` dengan alamat IP dari Ubuntu Server.

3. **Masukkan Kata Sandi**: Jika koneksi SSH berhasil, Anda akan diminta memasukkan kata sandi untuk akun pengguna di Ubuntu Server.

4. **Akses Root (opsional)**: Jika perlu, Anda dapat mengakses akun root di Ubuntu Server setelah terhubung sebagai pengguna reguler dengan menggunakan perintah `sudo su` atau `sudo -i`.

Dengan mengikuti langkah-langkah ini, Anda dapat melakukan remote dan mengakses akun root melalui SSH antara Ubuntu Desktop dan Ubuntu Server. Pastikan untuk menjaga keamanan sistem dengan menggunakan kata sandi yang kuat dan mengonfigurasi server SSH dengan benar.

**Catatan**: Aktivasi akses root melalui SSH tidak disarankan karena meningkatkan risiko keamanan. Disarankan untuk menggunakan pengguna reguler dan hanya mengalihkan ke root saat diperlukan.
