# 小代码
## 伪装下载
```phthon
import time
import random

input('下载并安装tan.exe（按下Enter继续）')
print('开始下载'+'\n'+'--------------------------')
for i in range(11):
    a = '进度条:[' +'#' * i + '-' * (10 - i) + ']' +str(i*10) +'%'
    print(f'\r{a}',end = '')
    t = random.randint(1,20) * 0.1
    time.sleep(t)
print('\n' + '下载完毕' + '\n' + '--------------------------')
for i in range(6):
    a = '准备安装' + '.' * i
    print(f'\r{a}',end = '')
    time.sleep(random.randint(1,7) * 0.1)
a = '准备完毕'
print(f'\r{a}',end = '')

print('\n'+'--------------------------')
while True:
    a = '下载地址：'+ '\n' + \
        '1.C:\Program Files'+ '\n'+\
        '2.E:\App' +'\n'+\
        '地址（打编号）：'
    b = input(a)
    if b == '1' or b == '2':
        break
input('开始安装（按下Enter继续）' )
print('--------------------------')
for i in range(11):
    a = '进度条:[' +'#' * i + '-' * (10 - i) + ']' +str(i*10) +'%'
    print(f'\r{a}',end = '')
    t = random.randint(1,15) * 0.1
    time.sleep(t)
input('\n'+'安装完毕（按下Enter退出）')
```
## 图形生成器
```python
import turtle

# 设置窗口和画笔
screen = turtle.Screen()
pen = turtle.Turtle()

# 清除背景，设置画布为白色
screen.bgcolor("white")

def draw_polygon(sides, length):
    # 计算每个角度
    angle = 360 / sides

    # 绘制正多边形
    for _ in range(sides):
        pen.forward(length)
        pen.left(angle)

def main():
    while True:
        # 获取用户输入
        sides = int(input("请输入正多边形的边数（输入 0 退出）："))
        if sides == 0:
            break  # 输入 0 时退出

        length = int(input("请输入每条边的长度："))

        # 清除之前的图形
        pen.reset()

        # 绘制新图形
        draw_polygon(sides, length)

    # 完成绘制
    print("绘图结束")
    turtle.done()

# 运行主程序
main()
```