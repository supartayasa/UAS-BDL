# UAS-BDL

## Databases Pendataan Absensi Siswa

1. entity relationship diagram

   ## Penjelasan Struktur Tabel

Berikut adalah penjelasan struktur tabel yang diberikan:

**Tabel Siswa**

Tabel `siswa` menyimpan informasi tentang siswa yang terdaftar di sistem. Tabel ini memiliki empat kolom:

* `id_siswa`: Merupakan nomor identitas siswa yang bersifat unik dan dibuat secara otomatis oleh sistem (auto-increment). Tipe datanya adalah integer (INT) dengan panjang maksimum 11 karakter.
* `nis`: Merupakan nomor induk siswa (NIS) yang bersifat unik dan tidak boleh sama antar siswa. Tipe datanya adalah varchar dengan panjang maksimum 10 karakter.
* `nama_lengkap`: Merupakan nama lengkap siswa. Tipe datanya adalah varchar dengan panjang maksimum 50 karakter.
* `kelas`: Merupakan kelas siswa. Tipe datanya adalah varchar dengan panjang maksimum 10 karakter.

**Tabel Mata Pelajaran**

Tabel `mata_pelajaran` menyimpan informasi tentang mata pelajaran yang diajarkan di sekolah. Tabel ini memiliki dua kolom:

* `id_pelajaran`: Merupakan nomor identitas mata pelajaran yang bersifat unik dan dibuat secara otomatis oleh sistem (auto-increment). Tipe datanya adalah integer (INT) dengan panjang maksimum 11 karakter.
* `nama_pelajaran`: Merupakan nama mata pelajaran. Tipe datanya adalah varchar dengan panjang maksimum 50 karakter.

**Tabel Absensi**

Tabel `absensi` menyimpan informasi tentang absensi siswa dalam mata pelajaran tertentu. Tabel ini memiliki enam kolom:

* `id_absensi`: Merupakan nomor identitas absensi yang bersifat unik dan dibuat secara otomatis oleh sistem (auto-increment). Tipe datanya adalah integer (INT) dengan panjang maksimum 11 karakter.
* `id_siswa`: Merupakan nomor identitas siswa yang menghubungkan tabel absensi dengan tabel siswa. Tipe datanya adalah integer (INT) dengan panjang maksimum 11 karakter.
* `id_pelajaran`: Merupakan nomor identitas mata pelajaran yang menghubungkan tabel absensi dengan tabel mata pelajaran. Tipe datanya adalah integer (INT) dengan panjang maksimum 11 karakter.
* `tanggal`: Merupakan tanggal absensi. Tipe datanya adalah date.
* `status`: Merupakan status absensi siswa, yang bisa berupa "H" (Hadir), "I" (Izin), "S" (Sakit), atau "A" (Alpha). Tipe datanya adalah enum dengan pilihan "HTS", "A".
* `FOREIGN KEY`: Digunakan untuk menghubungkan tabel absensi dengan tabel siswa dan tabel mata pelajaran.
    * `FOREIGN KEY (id_siswa) REFERENCES siswa(id_siswa)`: Kolom `id_siswa` pada tabel absensi harus ada di tabel siswa.
    * `FOREIGN KEY (id_pelajaran) REFERENCES mata_pelajaran(id_pelajaran)`: Kolom `id_pelajaran` pada tabel absensi harus ada di tabel mata pelajaran.

**Hubungan Antar Tabel**

* **Satu ke Banyak (One to Many):**
    * **Siswa - Absensi:** Satu siswa dapat memiliki banyak absensi.
    * **Mata Pelajaran - Absensi:** Satu mata pelajaran dapat memiliki banyak absensi.
* **Tanpa Hubungan:**
    * **Siswa - Mata Pelajaran:** Tidak ada hubungan langsung antara tabel siswa dan tabel mata pelajaran. Hubungan antar keduanya terjalin melalui tabel absensi.




![image](https://github.com/supartayasa/UAS-BDL/assets/173659267/1112f4f2-38ce-414d-a594-4a1a9811a08c)

2. deskripsi projek 

databases ini memudahkan guru dalam melakukan absensi di sebuah sekolah dasar dan terdapat beberapa tabel di dalam database diantaranya 

tb_siswa

tb_mata_pelajaran

tb_absensi

tb_rekap_absensi

3. Mekanisme database

   dalam database ini berisikan 4 tabel dimana terdapat yaitu siswa, mata pelajaran, absensi dan rekap absensi yang dimana rekap absensi ini berisikan nis dari
   tb_siswa kemudian nama pelajaran berasal tb mata pelajaran dan rekap disini memudahkan untuk mengkalkulasikan 

4. Penjelasan trigger dan view

view disini berguna untuk menggabungkan dan mengkalkulasi 

![image](https://github.com/supartayasa/UAS-BDL/assets/173659267/62c3ab1c-75f4-44c9-a163-dab37e5b8d0e)

trigger

trigger ini berfungsi melakukan auto insert apabila terdapat data baru 

![image](https://github.com/supartayasa/UAS-BDL/assets/173659267/fc9c57fd-50d8-4f9b-b2ae-0cbd9dc81a01)

