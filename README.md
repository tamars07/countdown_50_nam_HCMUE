# Màn hình đếm ngược 50 năm HCMUE

Màn hình đếm ngược trình chiếu trên màn LED cho **Lễ kỉ niệm 50 năm Ngày truyền thống Trường Đại học Sư phạm Thành phố Hồ Chí Minh**: 08g30, ngày 24/10/2026, Hội trường Chất lượng.

![Màn hình đếm ngược trên màn LED](docs/man-hinh-dem-nguoc.jpg)

> Bản Word của tài liệu này: [HUONG-DAN-TRIEN-KHAI.docx](HUONG-DAN-TRIEN-KHAI.docx)

## Mục lục

1. [Thông tin chung](#1-thông-tin-chung)
2. [Nội dung thư mục](#2-nội-dung-thư-mục)
3. [Yêu cầu thiết bị](#3-yêu-cầu-thiết-bị)
4. [Các bước cài đặt](#4-các-bước-cài-đặt)
5. [Diễn biến hiển thị](#5-diễn-biến-hiển-thị)
6. [Diễn tập trước sự kiện](#6-diễn-tập-trước-sự-kiện)
7. [Tùy chỉnh nội dung](#7-tùy-chỉnh-nội-dung)
8. [Kiểm tra trước giờ trình chiếu](#8-kiểm-tra-trước-giờ-trình-chiếu)
9. [Xử lý sự cố](#9-xử-lý-sự-cố)

## 1. Thông tin chung

| Hạng mục | Thông số |
|---|---|
| Màn LED | Rộng 4160 mm × cao 2240 mm, màn ngang, tỉ lệ khoảng 13:7 |
| Khung thiết kế | 2080 × 1120 điểm ảnh, tự co giãn vừa mọi độ phân giải cùng tỉ lệ |
| Hình thức | Trang web tĩnh (HTML) chạy trên Google Chrome hoặc Microsoft Edge |
| Kết nối mạng | Không cần. Toàn bộ hình ảnh, logo và font chữ nằm sẵn trong thư mục |
| Thời điểm đếm | 08g30 ngày 24/10/2026, tính theo giờ Việt Nam (UTC+7), không phụ thuộc múi giờ của máy |
| Nguồn hình ảnh | Tách từ file thiết kế gốc `Countdown.ai` (ảnh nền, tòa nhà, chữ 3D, logo) |

## 2. Nội dung thư mục

| Thành phần | Mô tả |
|---|---|
| `index.html` | Trang trình chiếu. Đây là file cần mở |
| `assets/` | Ảnh nền, hình tòa nhà, chữ 3D "còn", "ngày" và số "3" |
| `logos/` | Logo Trường, logo 50 năm và 26 logo đơn vị tài trợ, đánh số theo thứ tự hiển thị |
| `fonts/` | Font Montserrat (giấy phép OFL, miễn phí) để chạy không cần mạng |
| `docs/` | Ảnh chụp màn hình dùng trong tài liệu này |
| `HUONG-DAN-TRIEN-KHAI.docx` | Bản Word của tài liệu này |

**Tải về:** bấm nút **Code › Download ZIP** trên trang GitHub, hoặc chạy:

```bash
git clone https://github.com/tamars07/countdown_50_nam_HCMUE.git countdown-50nam
```

> [!IMPORTANT]
> Luôn giữ nguyên cấu trúc thư mục. Nếu chỉ chép riêng file `index.html`, trang sẽ mất ảnh, logo và font.

## 3. Yêu cầu thiết bị

- **Máy tính trình chiếu:** Windows 10/11 (hoặc macOS), có cổng HDMI/DVI nối vào bộ điều khiển màn LED (NovaStar, Colorlight, Linsn…).
- **Trình duyệt:** Google Chrome hoặc Microsoft Edge bản mới.
- **Đồng hồ máy:** phải đúng giờ đến từng giây, vì trang đếm ngược theo đồng hồ của máy.
- **Độ phân giải màn LED:** phụ thuộc loại module. Bảng dưới là số ước tính theo khoảng cách điểm ảnh (pitch); số chính xác cần hỏi đơn vị lắp đặt LED.

| Loại module | Độ phân giải ước tính | Ghi chú |
|---|---|---|
| P1.86 | 2236 × 1204 | Nét nhất |
| P2.0 | 2080 × 1120 | Trùng khớp khung thiết kế |
| P2.5 | 1664 × 896 | Phổ biến cho sân khấu trong nhà |
| P3.91 | 1064 × 573 | Chữ nhỏ có thể kém sắc nét |

## 4. Các bước cài đặt

### Bước 1. Chép và giải nén

1. Chép file zip sang máy trình chiếu, ví dụ vào ổ `D:\`.
2. Nhấp phải vào file, chọn **Extract All… (Giải nén tất cả)** để được thư mục `D:\countdown-50nam\`.
3. Không mở `index.html` trực tiếp từ bên trong file zip khi chưa giải nén.

> [!NOTE]
> File tải bằng **Download ZIP** trên GitHub sẽ giải nén ra thư mục tên `countdown_50_nam_HCMUE-main`. Nên đổi tên thành `countdown-50nam` cho khớp với các lệnh bên dưới.

### Bước 2. Đồng bộ đồng hồ máy tính

1. Vào **Settings › Time & language › Date & time** (Cài đặt › Thời gian & ngôn ngữ › Ngày & giờ).
2. Chọn múi giờ **(UTC+07:00) Bangkok, Hanoi, Jakarta**.
3. Bật **Set time automatically** và bấm **Sync now**. Bước này cần mạng một lần, có thể dùng Wi-Fi phát từ điện thoại.
4. Nếu hoàn toàn không có mạng: chỉnh giờ thủ công theo đồng hồ điện thoại, khớp đến từng giây, và kiểm tra lại vào sáng ngày sự kiện.

### Bước 3. Thiết lập xuất hình ra màn LED

1. Đề nghị kỹ thuật viên LED đặt **độ phân giải đầu vào (EDID) của bộ điều khiển** đúng bằng số điểm ảnh thật của màn LED (xem bảng ở mục 3).
2. Trên Windows: **Settings › System › Display**, chọn màn LED, đặt độ phân giải trùng với giá trị trên và **Scale = 100%**.
3. Nếu dùng thêm một màn hình để điều khiển, chọn chế độ **Extend** và kéo cửa sổ trình duyệt sang màn LED trước khi bật toàn màn hình. Hoặc chọn **Show only on 2** để chỉ xuất ra màn LED.

> [!TIP]
> Khi không đặt được độ phân giải riêng: dùng 1920 × 1080 và để bộ điều khiển co hình vừa màn. Trang vẫn hiển thị đầy đủ nhưng có thể có dải màu xanh đậm mỏng ở mép trên và dưới, hoặc hình bị kéo giãn nhẹ khoảng 4%.

### Bước 4. Tắt các tính năng gây gián đoạn

- **Chế độ ngủ:** Settings › System › Power & battery › Screen and sleep: chọn **Never** cho tất cả các mục.
- **Màn hình chờ (screen saver):** chọn None.
- **Thông báo:** bật **Do not disturb** (Không làm phiền) để không hiện thông báo lên màn LED.
- **Windows Update:** bấm **Pause updates** (Tạm dừng cập nhật) 1 tuần để máy không tự khởi động lại.

### Bước 5. Mở trang trình chiếu

**Cách nhanh:** nhấp đúp file `index.html` để mở bằng Chrome, sau đó nhấn phím **F** hoặc nhấp chuột một lần để vào toàn màn hình. Con trỏ chuột tự ẩn sau 2,5 giây không di chuyển.

**Cách khuyến nghị (chế độ kiosk):** toàn màn hình, không có thanh địa chỉ và tab, không thoát nhầm khi lỡ bấm phím. Tạo shortcut trên Desktop: nhấp phải › **New › Shortcut**, dán lệnh sau vào ô vị trí, viết trên **một dòng**:

```text
"C:\Program Files\Google\Chrome\Application\chrome.exe" --kiosk "file:///D:/countdown-50nam/index.html" --user-data-dir="D:\countdown-50nam-chrome" --no-first-run --noerrdialogs --disable-session-crashed-bubble --disable-pinch --overscroll-history-navigation=0
```

Nếu máy dùng Microsoft Edge:

```text
"C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --kiosk "file:///D:/countdown-50nam/index.html" --edge-kiosk-type=fullscreen --user-data-dir="D:\countdown-50nam-edge" --no-first-run
```

- Sửa đường dẫn `D:/countdown-50nam` nếu giải nén ở nơi khác. Trong phần `file:///` dùng dấu gạch chéo xuôi `/`.
- Tham số `--user-data-dir` giúp chế độ kiosk hoạt động kể cả khi đang mở sẵn một cửa sổ Chrome khác.
- Thoát chế độ kiosk: nhấn **Alt + F4**.
- Tự chạy khi bật máy (tùy chọn): nhấn **Win + R**, gõ `shell:startup`, chép shortcut vào thư mục vừa mở.

## 5. Diễn biến hiển thị

Số lớn bên trái tự đổi đơn vị theo thời gian còn lại. Bốn ô Ngày, Giờ, Phút, Giây bên phải luôn chạy liên tục.

| Thời gian còn lại | Nội dung hiển thị |
|---|---|
| Từ 1 ngày trở lên | "còn N ngày" (ví dụ: còn 3 ngày) |
| Dưới 1 ngày | "còn N giờ" |
| Dưới 1 giờ | "còn N phút" |
| Dưới 1 phút | "còn N giây", số nhảy theo từng giây |
| Từ 08g30 ngày 24/10/2026 | "Chào mừng quý vị đại biểu" và "Lễ kỉ niệm 50 năm Ngày truyền thống đang diễn ra" |

![Màn hình tự chuyển sang lời chào khi đến giờ khai mạc](docs/man-hinh-chao-mung.jpg)

## 6. Diễn tập trước sự kiện

Có thể giả lập giờ hiện tại để xem trước các cảnh chuyển. Thêm `?now=…` vào sau `index.html` trong đường dẫn mở trang (hoặc trong lệnh kiosk). Ký hiệu `%2B` là dấu cộng của múi giờ `+07:00`.

| Muốn xem | Thêm vào sau `index.html` |
|---|---|
| Chuyển từ "ngày" sang "giờ" | `?now=2026-10-23T08:29:50%2B07:00` |
| Chuyển từ "giờ" sang "phút" | `?now=2026-10-24T07:29:50%2B07:00` |
| Chuyển từ "phút" sang "giây" | `?now=2026-10-24T08:28:50%2B07:00` |
| 10 giây cuối và lời chào | `?now=2026-10-24T08:29:50%2B07:00` |

Ví dụ: `file:///D:/countdown-50nam/index.html?now=2026-10-24T08:29:50%2B07:00`

> [!CAUTION]
> Diễn tập xong phải xóa phần `?now=…` khỏi đường dẫn hoặc shortcut. Nếu không, trang sẽ đếm theo giờ giả lập chứ không theo giờ thật.

## 7. Tùy chỉnh nội dung

Mở `index.html` bằng Notepad (nhấp phải › Open with › Notepad). Phần cấu hình nằm ở đầu khối `<script>`. Khi lưu, chọn mã hóa **UTF-8** để giữ đúng tiếng Việt.

| Muốn thay đổi | Cách làm |
|---|---|
| Giờ khai mạc | Sửa dòng `EVENT_TIME = "2026-10-24T08:30:00+07:00"` |
| Thêm, bớt, đổi thứ tự logo | Chép file PNG vào `logos/`, sửa danh sách `SPONSOR_LOGOS` (ghi tên file, không cần đuôi `.png`) |
| Chữ số 3D cho mọi số | Đặt 10 file `so-0.png` … `so-9.png` (PNG nền trong suốt) vào `assets/`. Trang tự dùng khi có đủ ảnh cho các chữ số cần hiển thị |
| Chữ 3D giờ/phút/giây | Đặt `gio.png`, `phut.png`, `giay.png` vào `assets/` |
| Font SVN-Gilroy Black | Font có bản quyền, chưa kèm theo. Khi có file, đặt `SVN-Gilroy-Black.otf` vào `fonts/` hoặc cài lên máy. Khi chưa có, trang dùng Montserrat thay thế |

## 8. Kiểm tra trước giờ trình chiếu

- [ ] Thư mục `countdown-50nam` đầy đủ `index.html`, `assets/`, `logos/`, `fonts/`.
- [ ] Rút mạng và mở thử: hình, logo và chữ hiển thị đầy đủ, đúng font.
- [ ] Đồng hồ máy đúng giờ Việt Nam đến từng giây.
- [ ] Hình phủ kín màn LED, không méo, không viền đen.
- [ ] Đã tắt chế độ ngủ, màn hình chờ, thông báo và tạm dừng cập nhật.
- [ ] Đã diễn tập các cảnh chuyển và đã xóa `?now=…` khỏi đường dẫn.
- [ ] Đang chạy ở chế độ kiosk, không còn thanh địa chỉ, con trỏ chuột đã ẩn.
- [ ] Có phương án dự phòng: máy tính thứ hai cài sẵn cùng thư mục.

## 9. Xử lý sự cố

| Hiện tượng | Nguyên nhân thường gặp | Cách xử lý |
|---|---|---|
| Chỉ thấy nền xanh, mất logo hoặc ảnh | Chép thiếu thư mục con, hoặc mở file từ bên trong zip | Chép nguyên thư mục, giải nén trước khi mở |
| Chữ hiển thị sai kiểu font | Thiếu thư mục `fonts/` | Kiểm tra `fonts/` có 2 file Montserrat `.ttf` |
| Số đếm lệch giờ thực tế | Đồng hồ hoặc múi giờ của máy sai | Làm lại [Bước 2](#bước-2-đồng-bộ-đồng-hồ-máy-tính) |
| Trang đếm theo giờ diễn tập | Đường dẫn còn `?now=…` | Xóa phần `?now=…` trong đường dẫn hoặc shortcut |
| Có viền đen hoặc dải xanh đậm ở mép | Độ phân giải xuất hình khác tỉ lệ màn LED | Làm lại [Bước 3](#bước-3-thiết-lập-xuất-hình-ra-màn-led) cùng kỹ thuật viên LED |
| Hình bị kéo méo | Bộ điều khiển kéo giãn hình không giữ tỉ lệ | Đặt đúng độ phân giải đầu vào theo màn LED |
| Còn thanh địa chỉ hoặc tab | Chưa vào toàn màn hình | Nhấn **F** (hoặc **F11**), hoặc mở bằng shortcut kiosk |
| Lệnh kiosk không có tác dụng | Chrome đang chạy sẵn với hồ sơ khác | Đóng hết Chrome hoặc giữ tham số `--user-data-dir` |
| Màn hình tự tắt | Chế độ ngủ của Windows | Làm lại [Bước 4](#bước-4-tắt-các-tính-năng-gây-gián-đoạn) |
| Thông báo hiện đè lên màn LED | Thông báo Windows hoặc ứng dụng | Bật Do not disturb, tắt ứng dụng chạy nền |
| Con trỏ chuột hiện trên màn | Chuột vừa bị di chuyển | Để yên chuột, con trỏ tự ẩn sau 2,5 giây |

---

Font Montserrat được phân phối theo giấy phép [SIL Open Font License](fonts/OFL.txt). Hình ảnh và logo thuộc quyền sở hữu của Trường Đại học Sư phạm Thành phố Hồ Chí Minh và các đơn vị tài trợ, đồng hành.
