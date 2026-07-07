# Bài 1: Phân tích & Lựa chọn (Áp dụng 5 thành phần Prompt để giải quyết nghiệp vụ)

## Yêu cầu đầu ra:

### 1. Đáp án lựa chọn
**Đáp án: Phương án B**

### 2. Phân tích chi tiết phương án B
Phương án B là lựa chọn tối ưu nhất vì nó áp dụng đầy đủ và xuất sắc cấu trúc 5 thành phần cốt lõi (Role - Goal - Context - Constraint - Format):

*   **Role (Vai trò):** "Hãy đóng vai trò là một Java Developer chuyên nghiệp." -> Giúp AI xác định văn phong, trình độ và góc nhìn kỹ thuật chuyên sâu khi sinh mã.
*   **Goal (Mục tiêu):** "Yêu cầu viết class UserService xử lý đăng ký tài khoản (registerUser)." -> Xác định rõ ràng công việc cần làm, không lan man.
*   **Context (Bối cảnh):** "Dự án sử dụng Spring Boot 3.x và Java 17." -> Cung cấp môi trường công nghệ cụ thể để AI dùng đúng các thư viện, annotation tương thích với phiên bản này.
*   **Constraint (Ràng buộc):** "Ràng buộc nghiệp vụ: Phải kiểm tra trùng email qua `userRepository.existsByEmail()`, nếu trùng ném ra `DuplicateEmailException`; mật khẩu phải được mã hóa bằng `PasswordEncoder`." -> Đảm bảo AI không tự bịa ra logic kiểm tra hay bỏ sót việc bảo mật mật khẩu.
*   **Format (Định dạng đầu ra):** "Hãy trình bày kết quả dưới dạng khối mã nguồn Java kèm chú thích tiếng Việt rõ ràng ở từng bước." -> Đảm bảo kết quả dễ đọc, dễ tích hợp và giải thích rõ logic đúng như yêu cầu nghiệp vụ.

### 3. Phân tích tại sao các phương án còn lại chưa đạt chuẩn

*   **Phương án A:** "Hãy viết code Java Spring Boot xử lý đăng ký tài khoản người dùng, nhớ mã hóa mật khẩu và kiểm tra xem email đã tồn tại chưa."
    *   **Thiếu Role:** AI sẽ viết mã với văn phong chung chung, không chuẩn chuyên gia.
    *   **Thiếu Context:** Không rõ phiên bản Java hay Spring Boot nào, dễ sinh code lỗi thời (ví dụ dùng `javax` thay vì `jakarta` trong Spring Boot 3.x).
    *   **Thiếu Constraint:** Không yêu cầu cụ thể ném lỗi `DuplicateEmailException` hay dùng phương thức nào cụ thể, AI có thể viết mã tùy ý gây khó khăn khi tích hợp.
    *   **Thiếu Format:** AI có thể trả về text dài dòng không cần thiết mà thiếu chú thích trong code.
*   **Phương án C:** "Đang có một dự án Spring Boot. Hãy tạo hàm đăng ký tài khoản. Ràng buộc là phải check trùng email và ném lỗi DuplicateEmailException. Định dạng là code Java."
    *   **Thiếu Role:** Thiếu vai trò chuyên gia.
    *   **Context chưa đủ:** Chỉ nói "Spring Boot" mà không nói bản mấy, dễ sinh mã không tương thích.
    *   **Thiếu Constraint:** Bỏ sót yêu cầu vô cùng quan trọng: mã hóa mật khẩu (`PasswordEncoder`), một lỗ hổng bảo mật nghiêm trọng.
    *   **Format lỏng lẻo:** Chỉ nói "code Java" nhưng không yêu cầu chú thích tiếng Việt ở từng bước.
