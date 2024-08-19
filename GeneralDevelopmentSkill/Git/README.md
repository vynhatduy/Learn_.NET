# Git  
- Git là một hệ thống quản lý phiên bản phân tán mã nguồn mở được sử dụng phổ biến nhất hiện nay.
- Lưu lại lịch sử các phiên bản của  bất kì thay đổi nào của dự án. Giúp xem lại có thể khôi phục lại thay đổi trước đó.
- Dễ dàng chia sẻ code.
---
- Git sẽ coi thông tin được lưu trữ là một tập hợp các snapshot; mỗi khi "commit" sẽ tạo ra một snapshot tại thời điểm đó.
- Lợi ích của sử dụng git:
-- Dễ sử dụng, thao tác nhanh gọn và an toàn.
-- Cho phép phân nhánh và hợp nhất các nhanh lại với nhau.
-- Có thể làm việc ở bất kì đầu bằng việc clone mã nguồn từ kho và cập nhật lại thay đổi mới nhất.
-- Deployment sản phẩm dễ dàng.
---
## Các thuật ngữ quan trọng
1. Branch (nhánh)
- Mỗi branch đại diện cho một phiên bản nhất định của một kho lưu trữ được tách ra từ nhanh chính.
- Cho phép thay đổi, thử nghiệm, phát triển tính năng mới mà không ảnh hưởng đến mã nguồn chính.
2. Commit
- Mỗi commit đại diện cho một thời điểm cụ thể trong lịch sử của dự án (Mỗi commit có thể được coi là một snapshot lưu tạm thời tại máy local).
- Sử dụng commit và git add để khai báo những gì cần thay đổi tại repository local.
3. Checkout
- Git checkout để chuyển đổi qua lại giữa các nhánh
- Muốn chuyển đến nhánh nào thì gõ "Git checkout + tên nhanh". Ví dụ Git checkout master: sẽ chuyển đến nhánh master.
4. Fetch
- Tải xuống tất cả các nhánh từ repository.
5. Merge
- Lệnh git merge kết hợp với yêu cầu kéo (pull requests) để thêm các thay đổi từ nhánh này sang nhánh khác.
6. Origin
- Origin là phiên bản mặc định của repository. Origin cũng đóng vai trò là bí danh hệ thống để liên lạc với nhánh chính.
- Lệnh git push origin master để đẩy các thay đổi cục bộ đến nhánh chính.
7. Pull
- Pull requests thể hiện các đề xuất thay đổi cho nhánh chính.
- Lệnh git pull được sử dụng để thêm các thay đổi vào nhánh chính.
8. Push
- Lệnh git push được sử dụng để cập nhật các nhánh từ xa với những thay đổi mới nhất mà bạn đã commit.
9. Rebase
- Lệnh git rebase cho phép bạn phân tách, di chuyển hoặc thoát khỏi các commit. 
- Nó cũng có thể được sử dụng để kết hợp hai nhánh khác nhau.
10. Remote
- Một Remote (kho lưu trữ từ xa) là một bản sao của một chi nhánh. 
- Remote giao tiếp ngược dòng với nhánh gốc (origin branch) của chúng và các Remote khác trong kho lưu trữ.
11. Repository
- Kho lưu trữ Git chứa tất cả các tệp dự án của bạn bao gồm các branch, tags và commit.
12. Tags
- Tags cung cấp cho bạn một cách để theo dõi các commit quan trọng. 
- Các tags nhẹ chỉ đơn giản đóng vai trò là con trỏ trong khi các tags chú thích được lưu trữ dưới dạng các đối tượng đầy đủ.
13. Upstream
- Trong ngữ cảnh của Git, upstream đề cập đến nơi bạn push các thay đổi của mình, thường là nhánh chính (master branch).
---
## Các lệnh cơ bản trong 
1) git config
* Được dùng để set user name và email trong main configuration file.
* Cách dùng: `git config --global user.name = "username"`
             `git config --global user.email ="abc@123.com"`
* Ví dụ: `git config --global user.name ="Vy Nhật Duy"`
         `git config --global user.email ="vynhatduy111@gmail.com"`
2) git init
* Được dùng để khởi tạo 1 git repository từ project.
* Cách dùng: `git init` trong thư mục gốc của dự án.
3) git clone
* Được dùng để copy 1 repository từ remote source.
* Cách dùng: `git clone + url`
* Ví dụ: `git clone https://github.com/vynhatduy/Learn_.NET.git`.
4) git status
* Được dùng để kiểm tra trạng thái của những file thay đổi trong thư mục làm việc.
* Ví dụ: tất cả những thay đổi từ lần commit cuôi.
* Cách dùng: `git status`
5) git add
* Được dùng để thêm thay đổi đến stage/index trong thư mục làm việc
* Cách dùng: `git add .` để thêm tất cả thay đổi hoặc `git add "folder-name"`
* Ví dụ: Thay đổi tất cả `git add .`
         Thay đổi tại thư mục Demo `git add . Demo`
6) git commit
* Được dùng để tạo ra một snapshot các thay đổi trong thư mục làm việc.
* Thư mục được thay đổi phải nằm trong Staging Area: nghĩa là trước khi thực hiện commit thì phải thực hiện `git add`.
* Các dùng: `git commit -m "Viết message ở đây"`
7) git push/git pull
* Được dùng để thay đổi đến remote.
* Yêu cầu phải thực hiện `git add` và `git commit` trước đó
* cách dùng: `git pull <:remote:> <:branch:>` hoặc `git push <:remote:> <:branch:>`
8) git branch
* Được dùng để liệt kê các nhánh
* Cách dùng: `git branch` hoặc `git branch -a`
9) git checkout
* Được dùng để chuyển qua lại giữa các nhánh
* Cách dùng: `git checkout <: branch:>` hoặc `git checkout -b <: branch:>` nếu bạn muốn tạo và chuyển sang một chi nhánh mới.
10) git stash
* Được dùng để lưu thay đổi mà bạn không muốn commit ngay lập tức.
* Cách dùng: git stash trong thư mục làm việc.
11) git merge
* Được dùng để hợp nhất 2 nhánh với nhau
* Cách dùng: Chuyển tới branch bạn muốn merge rồi  dùng `git merge <:tên nhánh muốn hợp nhất:>`
12) git reset
* Được dùng để loại bỏ một tập tin ra khỏi staging area để khỏi bị commit theo
* Cách dùng: `git reset HEAD tên_file`
13) git remote
* Được dùng để check remote/source có thể add hoặc thêm remote
* Cách dùng: `git remote` để kiểm tra và liệt kê. Và `git remote add <: remote_url:>` để thêm.
