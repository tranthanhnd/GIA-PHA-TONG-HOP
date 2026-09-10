# Gia Phả Việt — Bản Tổng Hợp (dự án đóng gói Tauri)

Đây là bộ khung để đóng gói app Gia Phả Việt (bản Tổng hợp) thành file cài đặt
cho Windows (.msi/.exe) và macOS (.dmg), tự động qua GitHub Actions.

## Cách dùng

1. Đẩy toàn bộ thư mục này lên một repository GitHub của anh (private hoặc public đều được).
2. Vào tab **Actions** trên GitHub, hoặc chỉ cần đẩy code lên nhánh `release`
   — hệ thống sẽ tự động build song song cho Windows và macOS (2 kiến trúc: Apple Silicon + Intel).
3. Sau khi build xong (vài phút), vào tab **Releases** trên GitHub để tải file cài đặt.

## Về việc ký số macOS (không bắt buộc)

Nếu anh có tài khoản Apple Developer Program (99 USD/năm), thêm các secret sau
vào repo (Settings → Secrets and variables → Actions) để bản macOS được ký số +
công chứng, người dùng cài đặt không bị cảnh báo:

- APPLE_CERTIFICATE, APPLE_CERTIFICATE_PASSWORD, APPLE_SIGNING_IDENTITY
- APPLE_ID, APPLE_PASSWORD, APPLE_TEAM_ID

Chưa có cũng không sao — bản macOS vẫn build và chạy được, chỉ là lần đầu mở
người dùng cần vào System Settings → Privacy & Security để bấm "Mở" thủ công.

## Cập nhật phiên bản sau này

Khi anh sửa code trong `src/` (app.js, index.html, css...), chỉ cần đẩy code
mới lên nhánh `release`, hệ thống sẽ tự build lại và tạo bản Release mới —
không cần làm lại từ đầu.
