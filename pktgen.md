Tìm hiểu và sử dụng pktgen
https://git.dpdk.org/apps/pktgen-dpdk/
1.	Basic
1.1.	Networking
-	Review OSI model: Layer 2 – 7.
-	Frame size, packet size, MTU là gì?
-	Tìm hiểu về NIC. Khái niệm NIC port. 
-	Thuật ngữ half-duplex, full-duplex, 10GbE, 1GbE NIC có ý nghĩa như thế nào?
-	Packet rate, bitrate là gì? Line rate của một NIC là gì?
-	Tại sao packet rate tối đa của một NIC 10GbE là 14Mpps (chỉ ra công thức tính) 
1.2.	Traffic generator
-	Dùng để làm gì? 
-	Stateful và stateless traffic generator khác nhau thế nào?
-	Liệt kê tính các tính năng cơ bản của pktgen
-	DPDK là gì?  DPDK có liên quan thế nào đến pktgen.
2.	Cài đặt và chạy pktgen
2.1.	Build pktgen
-	Build DPDK
-	Build pktgen
2.2.	System requirement
-	Bind driver DPDK cho NIC port
-	Cấu hình hugepage cho DPDK 
2.3.	Chạy pktgen
-	Yêu cầu: truy nhập được vào CLI của pktgen
3.	Các tính năng cơ bản trên giao diện CLI
Test các tính năng cơ bản của pktgen. Yêu cầu: demo được các tính năng; trình bày các bước và command cụ thể trong báo cáo.
-	Đọc hiểu các thông số cơ bản trên page main
-	Các command cơ bản: start, stop, clear, help, page
-	Cấu hình được địa chỉ MAC, địa chỉ IP của gói tin gửi đi
-	Cấu hình được loại gói tin (TCP, UDP, ICMP, VLAN, MPLS)
-	Cấu hình được tốc độ gửi bitrate, burst size
-	Cấu hình số lượng gói tin tối đa gửi đi
-	Gửi và nhận được gói tin giữa 2 port theo mô hình loopback như sau
 
Port 1 nhận được gói tin do port 2 gửi đến và ngược lại.
-	Sử dụng tcpdump để verify nội dung gói tin khi thay đổi từng cấu hình (test theo mô hình one direction)
 
Tcpdump trên port 2 nhận được gói tin đúng như cấu hình trên port 1 trong pktgen.
4.	Các tính năng nâng cao trên CLI
Test các tính năng nâng cao của pktgen. Yêu cầu: demo được các tính năng; trình bày các bước và command cụ thể để test trong báo cáo.
Mô hình test: loopback hoặc one direction như ở phần 3.
-	Pcap
o	Bắn packet đọc từ file pcap
o	Lưu pcap các gói tin nhận được
-	Sequence: bắn tuần tự packet theo danh sách cấu hình từ trước
-	Range: bắn theo dải
-	Random: bắn gói tin nội dung random
5.	Lua script
-	Đọc hiểu và chạy được các lua example trong thư mục /script.
6.	Testing methodology
-	Tìm hiểu về RFC2544: zero packet loss throughput test
