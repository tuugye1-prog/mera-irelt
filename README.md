# Ирэлтийн баримт — нярвын зураг илгээх апп

Нярав барааг хүлээж аваад гарын үсэг зурмагц баримтын зургийг авч илгээнэ.
- Зураг → OneDrive: `Өрмийн захиалгын хяналт / Ирсэн ачааны баримт / YYYY-MM / <огноо_цаг_нийлүүлэгч_PO_нярав>/`
- Мөр → `Өрмийн захиалгын явц 2026.xlsx`-ийн **Ирсэн ачаа** sheet (`IrelLog` хүснэгт; эхний илгээлтээр автоматаар үүснэ)
- Төгөлдөр шалгаад **Төлөв**-ийг "Бүртгэсэн" болгоход нярвын апп дээр ✓ гарна.

## Байршуулах (hosting)
Статик хуудас — сервер хэрэггүй. Энэ хавтсыг бүхэлд нь аль нэгэнд тавина:
1. **Netlify Drop** — https://app.netlify.com/drop руу хавтсаа чирээд оруулна (хамгийн хялбар).
2. **GitHub Pages** — repo үүсгээд эдгээр файлыг хийж, Settings → Pages.

Гарсан URL-ээ (жишээ нь `https://mera-irelt.netlify.app/`) Entra дээр нэмнэ:
Entra → App registrations → *Mera Irelt - Storekeeper photos* → Authentication → Single-page application → **Add URI**.
URL яг таарах ёстой (төгсгөлийн `/` хүртэл).

## Тохиргоо (`index.html` доторх `CFG`)
| Түлхүүр | Утга |
|---|---|
| clientId | 78ce00ea-167e-48b4-88c5-446129e4157e |
| tenantId | fd7a51e6-7d0a-4359-ab44-0b84eb093e12 |
| driveId | Tuguldur.En OneDrive |
| irelFolderId | Өрмийн захиалгын хяналт / Ирсэн ачааны баримт |
| trackerItemId | Өрмийн захиалгын явц 2026.xlsx |

Эрх: `User.Read`, `Files.ReadWrite.All` (delegated, админ зөвшөөрөл шаардлагагүй). Нярав хавтас дээр **Can edit** эрхтэй байх ёстой.
