# Bài 7: Thiết kế Quy trình Che mờ (Data Masking) Khách VIP

## Phần A: Bảng Masking

| Thông tin PII thật | Nhãn che mờ (Placeholder) | Loại dữ liệu |
|---|---|---|
| Phạm Minh C | [TÊN_KH] | Họ tên |
| 0988.111.222 | [SĐT_KH] | Số điện thoại |
| minhc@gmail.com | [EMAIL_KH] | Email |
| Căn hộ 502 Chung cư Sunrise, Q7 | [ĐỊA_CHỈ_KH] | Địa chỉ nhà |

Các thông tin còn lại (ngày 20/09, thịt bò Wagyu, 4.500.000 VNĐ, MartX District 7, giao chậm 3 tiếng) giữ nguyên để AI hiểu ngữ cảnh.

## Phần B: Văn bản đã che mờ (Masked Input)

> "Tôi là [TÊN_KH] (SĐT: [SĐT_KH], Email: [EMAIL_KH]), ở [ĐỊA_CHỈ_KH]. Ngày 20/09 tôi mua 2kg thịt bò Wagyu giá 4.500.000 VNĐ tại MartX District 7 nhưng bị giao chậm 3 tiếng làm hỏng tiệc gia đình. Tôi yêu cầu bồi thường 100%!"

## Phần C: Prompt gửi AI

> "Bạn là nhân viên CSKH chuyên nghiệp của MartX. Dựa vào khiếu nại sau, hãy soạn thư xin lỗi lịch sự, đồng cảm, thừa nhận lỗi giao chậm, đề xuất hướng giải quyết bồi thường và giữ nguyên các nhãn như [TÊN_KH]. Thư dài khoảng 150 từ.
> Khiếu nại: [dán Masked Input]"

## Phần D: Văn bản De-mask (sau khi thay lại thông tin thật)

> Kính gửi anh/chị **Phạm Minh C**,
>
> MartX chân thành xin lỗi vì đơn hàng 2kg thịt bò Wagyu (4.500.000 VNĐ) ngày 20/09 tại MartX District 7 đã giao chậm 3 tiếng, làm ảnh hưởng đến bữa tiệc gia đình của anh/chị. Đây là thiếu sót của chúng tôi.
>
> MartX sẽ kiểm tra nguyên nhân và đề xuất phương án bồi thường phù hợp. Nhân viên CSKH sẽ liên hệ anh/chị qua số điện thoại **0988.111.222** hoặc email **minhc@gmail.com** trong vòng 24 giờ để thống nhất hướng xử lý. Chúng tôi cũng sẽ gửi thông báo về địa chỉ **Căn hộ 502 Chung cư Sunrise, Q7** nếu cần hoàn trả hàng hoặc quà xin lỗi.
>
> Trân trọng cảm ơn sự thông cảm của anh/chị.
> Đội ngũ CSKH MartX
