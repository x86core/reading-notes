### 1.1 开始

- echo 默认会添加换行符

- echo 转义 (\\)

- echo 双引号解析变量，单引号字符串输出

- printf 格式化输出

- echo -e 包含转义序列字符串， 色彩输出\e[{style};{foreground};{backround}m  
style: [0,7]  
foreground: [30, 37]  
background:[40,47]  
\033[0m 或 \e[0m 清除格式  

- echo -n 不输出换行符

### 1.2 变量
- 赋值  
var="value" (等号两边不能有空格)

- 输出变量  
echo $var 或 echo ${var}

- 双引号中引用变量 (printf或echo)

- 环境变量  
echo $PATH

- 获取变量长度  
length=${#var}

- 识别当前shell版本  
echo $SHELL 或 echo $0

- 超级用户  
root用户的UID是0

- Bash 提示字符  
PS1

### 1.3 数学运算
- 使用let, 变量名不需要$  
var1=1
var2=2
let sum=var1+var2
echo $sum

1. 自增  
let var1++  或 let var1+=1
2.自减  
let var2-- 或 let var2-=1

- [ ]使用  
sum=$[var1+var2]

- (( ))使用  
sum=$((var1+var2))

- expr 使用，注意运算符间的空格, 否则识别为字符串而不是运算  
sum=$(expr $var1 + $var2)
或  
sum=`expr $var1 + $var2`

注： 以上操作只能用于整数运算。

- 浮点运算 bc  
echo "12.6 * 2.3" | bc

1. 小数位 scale  
echo "scale=2; 2/3" | bc

2. 进制转换  
二进制转十进制(ibase->input, obase->output)  
no=1100100  
echo "obase=10;ibase=2;$no" | bc

3. 次方  
echo "2^3" | bc

4. 开方  
echo "sqrt(8)" |bc  #默认无小数位，需要scale参数

### 1.4 文件描述和重定向

- 标准输入（stdin), 标准输出(stdout), 标准错误(stderr)

- 文件描述符  
0 - stdin  
1 - stdout  
2 - stderr  

TODO: 仔细阅读  

#1.5 






