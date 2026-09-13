# Namichii Staff Task V2

Aplikasi PWA untuk alur kerja **Admin → Staff → Review → Selesai**, menggunakan Supabase project `gwxfjxbpeymffnzjaasw`.

## Fitur

- Login akun Admin/Staff yang sudah tersedia di Supabase
- Dashboard dan daftar tugas berbasis peran
- Admin membuat dan menugaskan pekerjaan beserta checklist dan deadline
- Staff menyelesaikan checklist, menambah item, upload foto/PDF bukti, dan mengirim laporan
- Admin melihat laporan, menyetujui tugas atau mengembalikan untuk revisi
- Admin mengelola peran dan status aktif pengguna
- PWA: dapat dipasang ke layar utama dari browser seluler

## Deploy ke GitHub Pages

Workflow pada `.github/workflows/deploy-pages.yml` akan menerbitkan aplikasi setiap ada push ke `main`.

Jika deployment pertama menunggu pengaturan Pages, buka repository GitHub → **Settings → Pages** → pada **Build and deployment**, pilih **GitHub Actions**. Setelah itu jalankan ulang workflow **Deploy static content to Pages**. URL akhirnya akan berbentuk:

`https://sudeecorp-eng.github.io/namichii-staff-task/`

## Catatan keamanan

Kode ini hanya memakai **Supabase publishable key**, yang memang aman untuk aplikasi browser bila RLS telah dikonfigurasi. Tidak ada service-role/secret key di repository.

Bucket `task-evidence` bersifat privat. Saat pengguna membuka bukti, aplikasi membuat URL bertanda tangan yang berlaku 5 menit.

