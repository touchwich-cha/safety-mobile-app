# Safety Mobile App — เว็บหน้าแอป (Static Host)

หน้านี้เป็น **front-end ไฟล์เดียว** ของระบบ Safety Mobile App
หลังบ้าน (Google Sheet + Apps Script) ไม่ได้ย้ายที่ ยังใช้งานตัวเดิม

## ใช้งาน

เปิด `index.html` ผ่าน host → หน้าแอปจะเรียก API ที่
`https://script.google.com/macros/s/AKfycbwGq48ueEERbtGYT553mZQCGBlXS4VpuLVhira03MuLUO258GpAG4-48gEhu96sx5-GHQ/exec`

## เปิด GitHub Pages

Settings → Pages → Source: **Deploy from a branch** → Branch: **main** / **(root)** → Save
รอ ~1 นาที จะได้ลิงก์ `https://<username>.github.io/<repo>/`

## อัปเดตหน้าเว็บ

1. แก้ที่ `AppsScript/Index.html` (ตัวหลักในโปรเจกต์ Apps Script)
2. คัดลอกมาทับ `index.html` ในโฟลเดอร์นี้ อย่าลืมว่าไฟล์นี้ต้องเป็น **static** คือ
   บรรทัด `const API_URL` ต้องเป็น URL เต็ม (ไม่ใช่ `<?= ScriptApp.getService().getUrl() ?>`)
3. commit + push

## ข้อควรระวัง

- ถ้าสร้าง **New deployment** ใหม่ใน Apps Script (ไม่ใช่ New version) URL จะเปลี่ยน → ต้องแก้ `API_URL` แล้ว push ใหม่
- `.nojekyll` ต้องมี เพื่อไม่ให้ GitHub แปลงไฟล์ผ่าน Jekyll
