# Dokumen Kebutuhan Bisnis (Business Requirements Document - BRD)

## 1. Ikhtisar Proyek
Sistem Pembayaran adalah platform berbasis web yang dirancang untuk mempermudah pengelolaan pembayaran, transaksi, dan manajemen hak akses pengguna. Sistem ini mendukung tiga jenis pengguna utama: Pengguna, Admin, dan Sistem. Setiap peran memiliki izin dan tanggung jawab spesifik untuk memastikan pengelolaan yang terstruktur dan efisien.

## 2. Tujuan
- Mempermudah proses pembayaran dengan otomatisasi dan integrasi yang aman.
- Memberikan pengguna metode untuk membuat, melacak, dan mengelola pembayaran.
- Memungkinkan admin untuk mengelola peran dan izin pengguna.
- Menjamin pelaporan yang transparan terkait status pembayaran dan transaksi.

## 3. Ruang Lingkup
Sistem ini mencakup:
- **Manajemen Pembayaran**: Pembuatan, pembaruan, dan pembatalan pembayaran.
- **Manajemen Transaksi**: Proses pembayaran dan penyimpanan data transaksi.
- **Manajemen Peran dan Izin**: Pengelolaan peran pengguna dan hak akses terkait.
- **Pelaporan**: Menyediakan laporan terkait status pembayaran dan rincian transaksi.

## 4. Peran Pengguna dan Izin

### Pengguna
- Membuat pembayaran.
- Melihat status pembayaran.
- Membuat transaksi.

### Admin
- Mengelola peran pengguna.
- Mengatur izin untuk setiap pengguna.
- Melihat laporan terkait pembayaran dan transaksi.

### Sistem
- Memproses pembayaran.
- Memberikan notifikasi kepada pengguna terkait status transaksi.

## 5. Kebutuhan Fungsional

### 5.1 Manajemen Pembayaran
- **Pembuatan Pembayaran**: Pengguna dapat membuat pembayaran dengan mengisi detail seperti jumlah, metode pembayaran, dan tanggal jatuh tempo.
- **Melihat Status Pembayaran**: Pengguna dapat memeriksa status pembayaran (pending, completed, failed).
- **Pembaruan Status Pembayaran**: Admin dapat memperbarui status pembayaran berdasarkan hasil transaksi.

### 5.2 Manajemen Transaksi
- **Proses Transaksi**: Sistem memproses pembayaran berdasarkan detail yang dimasukkan pengguna.
- **Rincian Transaksi**: Pengguna dapat melihat rincian transaksi seperti jumlah yang dibayar, metode pembayaran, dan waktu transaksi.

### 5.3 Manajemen Peran dan Izin
- **Pengaturan Peran**: Admin dapat menetapkan peran tertentu kepada pengguna.
- **Pengaturan Izin**: Admin dapat mengatur hak akses untuk setiap peran.
- **Melihat Hak Akses**: Admin dapat melihat izin yang telah diberikan kepada pengguna.

## 6. Analisis Model Data

### Entitas dan Atribut
1. **User (Pengguna)**
   - Atribut: `id`, `name`, `email`, `password`, `created_at`, `updated_at`
2. **Payment (Pembayaran)**
   - Atribut: `id`, `invoice_number`, `amount`, `due_date`, `status`, `created_at`, `updated_at`
3. **Transaction (Transaksi)**
   - Atribut: `id`, `payment_id`, `amount_paid`, `payment_method`, `paid_at`, `created_at`, `updated_at`
4. **Role (Peran)**
   - Atribut: `id`, `name`, `guard_name`, `created_at`, `updated_at`
5. **Permission (Izin)**
   - Atribut: `id`, `name`, `guard_name`, `created_at`, `updated_at`

### Relasi
- **User - Role**: Satu pengguna dapat memiliki banyak peran.
- **Role - Permission**: Satu peran dapat memiliki banyak izin.
- **Payment - Transaction**: Satu pembayaran dapat memiliki banyak transaksi.

## 7. Analisis Use Case

### Pengguna
1. Membuat pembayaran.
2. Melihat status pembayaran.
3. Membuat transaksi.

### Admin
1. Mengelola peran pengguna.
2. Mengelola izin pengguna.
3. Melihat laporan transaksi.

### Sistem
1. Memproses pembayaran.
2. Memberikan notifikasi status transaksi.

## 8. Kebutuhan Non-Fungsional
- **Keamanan**: Sistem harus melindungi data pengguna dan transaksi dari akses yang tidak sah.
- **Keandalan**: Sistem harus bekerja secara konsisten dengan minimal waktu henti.
- **Skalabilitas**: Sistem harus dapat menangani peningkatan jumlah pengguna dan transaksi.
- **Kemudahan Penggunaan**: Antarmuka harus intuitif dan ramah pengguna.

## 9. Risiko
- **Kehilangan Data**: Risiko kehilangan data karena kegagalan sistem.
- **Pelanggaran Keamanan**: Risiko akses tidak sah terhadap data pengguna dan transaksi.
- **Ketidakcocokan Sistem**: Potensi masalah saat integrasi dengan metode pembayaran eksternal.
