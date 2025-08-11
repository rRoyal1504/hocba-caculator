# 📊 Công cụ Tính điểm học bạ & Ước lượng điểm

## 📝 Giới thiệu
Công cụ tính toán điểm học bạ THPT và ước lượng điểm các năm còn lại để đạt mục tiêu xét tuyển.  
Hỗ trợ **giao diện dark mode**, thiết kế tối giản, chạy **thuần HTML + CSS + JS** (không cần framework).

## 🌐 Live
- https://rroyal1504.github.io/hocba-calculator/

## ✨ Tính năng chính
- **Tính điểm học bạ**: Tự động tính trung bình từng môn (3 năm), cộng thành tổng (thang 30).
- **Cộng điểm ưu tiên**: Khu vực, đối tượng, thành tích học tập (có bảng tra).
- **Công thức giảm ưu tiên**: MOET hoặc tùy chỉnh (CUSTOM).
- **Ước lượng điểm tương lai**:
  - Chọn mục tiêu là **học bạ thuần** hoặc **tổng cuối cùng**.
  - Tự tính điểm cần đạt cho các môn còn lại.
  - 3 chiến lược phân bổ:
    1. **Chia đều** – chia đều nhu cầu tăng/giảm cho các môn chưa khóa.
    2. **Theo năng lực quá khứ** – phân bổ theo điểm trung bình các năm trước.
    3. **Giới hạn tối đa công sức (minimax)** – giảm chênh lệch so với mức chuẩn (vd: 8.0).
  - Cho phép **khóa môn** đã chắc chắn điểm.
  - **Giới hạn min/max** cho từng môn.
- **Lưu trạng thái**: Tự động lưu vào `localStorage`, mở lại không mất dữ liệu.
- **Ước lượng khả thi**: Báo nếu mục tiêu không đạt và gợi ý mục tiêu gần nhất.

## 🧮 Công thức tính

### 1. Trung bình môn
TB_môn = (Điểm lớp 10 + Điểm lớp 11 + Điểm lớp 12) / 3

### 2. Tổng học bạ (thang 30)
B = KV + ĐT + Σ(Thành tích)

### 4. Công thức giảm ưu tiên
#### MOET (chuẩn Bộ GD&ĐT)
Nếu T < 22.5: P = B
Nếu T ≥ 22.5: P = ((30 − T) / 7.5) × B

#### CUSTOM
Nếu T < thr: P = B
Nếu T ≥ thr: P = ((30 − T) / den) × B

### 5. Tổng cuối
F(T) = T + P(T)


## 📐 Cách ước lượng điểm
- **Bước 1:** Giải ngược từ mục tiêu → tìm T cần đạt.
- **Bước 2:** Tính tổng điểm lớp 12 cần thiết.
- **Bước 3:** Phân bổ điểm cần cho các môn chưa khóa theo chiến lược đã chọn.
- **Bước 4:** Áp dụng giới hạn min/max cho từng môn.
- **Bước 5:** Nếu không khả thi → báo và đưa mục tiêu gần nhất.

## 💻 Sử dụng (nếu muốn chạy local, còn không bạn có thể vào web: https://rroyal1504.github.io/hocba-calculator/ )
1. Mở file `index.html` trong trình duyệt.
2. Nhập điểm lớp 10, 11, 12 (nếu có).
3. Chọn **khu vực**, **đối tượng**, **thành tích**.
4. Nhấn **Tính** để xem kết quả.
5. (Tùy chọn) Vào mục **Ước lượng điểm** để đặt mục tiêu và nhận gợi ý.

## ⚖️ Giấy phép
MIT License
