SQL injection vulnerability exists in ibos oa v4.5.5

official website:http://www.ibos.com.cn/

verison:4.5.5

1. Log in to the background. Personal office => Work logs => Delete logs => Delete logs to capture packets
![WPS图片(1)](https://github.com/wudidike/cve/assets/76437404/7ba725bf-5f9a-4996-b953-ed8df5643cc6)
![WPS图片(2)](https://github.com/wudidike/cve/assets/76437404/206db383-7125-4a4e-b8bb-fbd9f3ec0d1b)
Delayed injection success
![WPS图片(3)](https://github.com/wudidike/cve/assets/76437404/2f7fa908-5f25-4100-9e56-0cf292a28029)
![WPS图片(4)](https://github.com/wudidike/cve/assets/76437404/a8a2dabe-f51f-4b49-b6c9-8528548f41a1)

2. Find the corresponding code through the route for analysis
![WPS图片(5)](https://github.com/wudidike/cve/assets/76437404/37d21f36-4649-48d7-882a-927bbfbecbec)
Enter the actionDel() method in DefaultController.php, receive the parameter through getRequest, concatenate the parameter through $diaryids into the sql statement to execute.
![WPS图片(6)](https://github.com/wudidike/cve/assets/76437404/c9a2c1bc-7ffb-432d-93a1-ce03eea14eb4)
deleteALL() executes the complete sql statement
![WPS图片(7)](https://github.com/wudidike/cve/assets/76437404/e3b4f413-6fb0-4983-802f-5621211e04f0)