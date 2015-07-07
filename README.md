# Linux下gcc編譯生成動態連接庫*.so並調用

## 產生動態連接庫 
`$ gcc test_a.c test_b.c test_c.c -fPIC -shared -o libtest.so `

## 使用動態連接庫
`$ gcc test.c -L. -ltest -o test`

* -L. : 表示要連接的動態連接庫在當前目錄中
* -ltest : 編譯器查找動態連接庫時有隱含的命名規則,即在給出的名字前面加上lib,後面加上.so來確定動態連接庫的名稱
* LD_LIBRARY_PATH : 指示動態聯接器能裝載動態連接庫的路徑

## 查看動態連接過程
`$ lld test`

執行test,能看到它是怎麼調用動態連接庫中的函數的
