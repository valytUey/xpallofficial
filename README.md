# xPallOfficial — Vercel + Google OAuth

Website Next.js untuk `nest.pallrzki.my.id`.

## 1. Install
```bash
npm install
npm run dev
```

## 2. Google OAuth
Buat OAuth Client di Google Cloud Console sebagai **Web application**.

Production redirect URI:
`https://nest.pallrzki.my.id/api/auth/callback/google`

Tambahkan:
- Authorized JavaScript origin: `https://nest.pallrzki.my.id`
- Authorized redirect URI: `https://nest.pallrzki.my.id/api/auth/callback/google`

Masukkan di Vercel Environment Variables:
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`
- `NEXTAUTH_SECRET`
- `NEXTAUTH_URL=https://nest.pallrzki.my.id`

**Jangan pernah memasukkan GOOGLE_CLIENT_SECRET ke kode frontend atau membagikannya.**

## 3. Deploy ke Vercel
Import repository ini ke Vercel, tambahkan Environment Variables, lalu deploy.

## 4. Custom domain
Di Vercel tambahkan domain:
`nest.pallrzki.my.id`

Di DNS provider domain `pallrzki.my.id`, buat record:
- Type: `CNAME`
- Name/Host: `nest`
- Target: `cname.vercel-dns.com`

Jika Vercel menampilkan target DNS yang berbeda pada dashboard, ikuti target yang ditampilkan Vercel.

## Catatan
Login menggunakan JWT session sehingga belum membutuhkan database. Jika nanti ingin menyimpan akun, saldo, stok, order, dan testimoni secara permanen, tambahkan PostgreSQL/Supabase + Prisma.
