# baitap1-web
# TẠO SOLUTION GỒM CÁC DỰ ÁN SAU:

1 DLL đa năng, từ khóa: thư viện cửa sổ c# -> Thư viện lớp (.NET Framework) bắt buộc sử dụng .NET Framework 2.0: giải bài toán bất kỳ, độc lạ càng tốt, phải có dấu ấn cá nhân trong kết quả, biên dịch ra DLL. DLL độc lập vì nó không nhập, không xuất, nó nhận đầu vào truyền vào thuộc tính của nó và trả về dữ liệu thuộc tính khác hoặc thông tin trả về giá trị của hàm. Nó độc lập sẽ được sử dụng trên bảng điều khiển dạng ứng dụng (lệnh giao diện dòng - đen sì), cũng được sử dụng trên màn hình ứng dụng (dạng cửa sổ), và cũng được sử dụng trên biểu mẫu web (web chạy qua iis). <br>
2 Console app, bắt buộc sử dụng .NET Framework 2.0, sử dụng DLL trên: nhập dữ liệu đầu vào, gọi DLL, hiển thị kết quả, phải có dấu cá nhân. từ khóa: c# window Console => Console App (.NET Framework), biên dịch ra EXE <br>
3 Windows Form Application, bắt buộc sử dụng .NET Framework 2.0**, sử dụng đa năng DLL trên, kéo các điều khiển vào để có thể lấy đầu vào, gọi đầu vào truyền DLL để lấy kq, hiển thị biểu mẫu cửa sổ kq ra, phải có dấu cá nhân; từ khóa: c# window Desktop => Windows Form Application (.NET Framework), biên dịch ra EXE <br>
4 Web đơn giản, bắt buộc sử dụng .NET Framework 2.0, sử dụng máy chủ web là IIS, sử dụng filehost để tự tạo miền, gắn tên miền này vào iis, file index.html có sử dụng html css js để xây dựng giao diện đầu vào cho bài toán, sử dụng mã js để xử lý dữ liệu, js để gửi phụ trợ. backend là api.aspx, trong code của api.aspx.cs sẽ lấy các đầu vào mà js gửi lên, sau đó sử dụng đa năng DLL ở trên. kết quả gửi lại json cho khách hàng, js phía khách hàng sẽ nhận được hậu xử lý json này để thay đổi giao diện theo dữ liệu nhận dược, phải có dấu hiệu cá nhân. từ khóa: c# window web => Ứng dụng web ASP.NET (.NET Framework) + link tham khảo chatgpt thầy gửi. dự án web này được biên dịch bằng DLL, phải kết hợp với IIS mới được chạy. <br>
# BÀI LÀM 
bài toán: Tạo “chữ ký số” dựa trên tên và ngày sinh

Sử dụng Visual Studio 2022 

# Tạo Project 1 — Class Library (.NET Framework 2.0):
Viết class chính (nhận input qua thuộc tính, sinh kết quả qua thuộc tính / trả về hàm).
Không dùng cú pháp C# > 2.0 (ví dụ không dùng var, auto-property mới, string interpolation…).
Build để tạo DLL (ví dụ TAPersonalToolkit.dll).

# Tạo Project 2 — Console App (.NET Framework 2.0):
Thêm reference tới DLL (project hoặc file .dll).
Viết UI console: nhập tên, ngày sinh → tạo instance class từ DLL → gán input → gọi phương thức → in kết quả.
Build và test.

chuột phải vào DigitalSignatureLib chọn set as project rồi ấn start hoặc  để chạy <br> 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/496a0fd8-45e1-4169-b554-c6c796329220" />


# ẢNH KẾT QUẢ <br>

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3c92f757-4fd3-4672-967e-21a62bb7d022" /> 

# Tạo Project 3 — Windows Forms App (.NET Framework 2.0): 
Thêm reference tới DLL.
Tạo form có textbox nhập, textbox ngày sinh, button, vùng hiển thị (multiline textbox).
Khi nhấn button: lấy input, gọi DLL, hiển thị Result.
Build và test.

# dùng code để xây dựng giao diện 
MainForm.cs <br> 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/35815005-a0c2-42d8-ab7c-6ea57af50de5" />

chuột phải vào DigitalSignatureWinForm chọn set as project rồi ấn start hoặc F5 để chạy <br> 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fef3d672-af87-4bbf-910b-389142427391" />


# ẢNH KẾT QUẢ <br>

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/44549546-b5a0-4bad-9d96-db71242f6ed9" /> <br>

# Tạo Project 4 — Web (ASP.NET Web Forms, .NET Framework 2.0): 
Thêm TAPersonalToolkit.dll vào thư mục /bin của project (hoặc add reference).
Tạo index.html (giao diện, HTML/CSS/JS) — JS gửi POST tới api.aspx.
Tạo api.aspx + api.aspx.cs: lấy Request.Form, gọi DLL, trả về JSON.
Web.config: chỉ để <compilation debug="true" /> và <customErrors mode="Off"/> (KHÔNG dùng targetFramework). <br>

Viết code html, css, js cho file index.html và code-behind cho api.aspx.cs 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9bf7c3b7-70c7-4ad7-b17f-b3caa8e65349" /> <br> 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9d7377d4-3401-4fba-8001-046c92a311a3" />

chuột phải vào DigitalSignatureWeb chọn set as project rồi ấn ISS Express để chạy <br> 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cf8eba62-07db-41c5-9445-ad64aa8007ac" />

# ẢNH KẾT QUẢ <br>

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7588be04-8126-4ad1-880d-dddab19fa88f" />





