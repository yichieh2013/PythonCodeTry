import random

# 比較兩字串  傳出 ?A ?B
def compare(string1,string2):  
    RnumRpla = 0
    for i in range(4):
        if(string1[i]==string2[i]):
            RnumRpla += 1
    
    RnumFpla = int(len(set(string1).intersection(set(string2)))-RnumRpla)

    return [RnumRpla,RnumFpla]

# 確定四個字元
def exam_4num(number1):
    if (len(number1) == 4):
        return True
    else:
        print("要輸入四個字元喔")
        return 4

# 確定是整數
def exam_int(number1):
    try:
        int(number1)
        return True
    except ValueError:
        print("不是整數喔")
        pass

    return 5

# 確定數字是否有重複
def exam_repeat(number1):
    try:
        num = int(number1)
        num1 = num//1000
        num2 = num//100 - num1*10
        num3 = num//10 - num1*100 - num2*10
        num4 = num % 10
        test = (num1 - num2) * (num1 - num3) * (num1 - num4) * \
            (num2 - num3) * (num2 - num4)*(num3 - num4) 
        if(test!=0):
            return True
        else:
            print("數字有重複喔")
            return 6
    except ValueError:
        pass

    return 61

# 確定數字範圍
def exam_range(number1):
    try:
        if ((int(number1)>=123) & (int(number1) <=9876)):
            return True
        else:
            print("數字範圍不對喔")
            return 7
    except ValueError:
        pass

    return 77
    
# 組合前四個函數
def exam_num(number1):
    test_num = exam_4num(number1) * exam_int(number1) * exam_repeat(number1) * exam_range(number1)
    if test_num==1:
        return True
    else:
        return False


 # 初設題目
TrueAns = random.sample(range(10),k=4)
TrueAns = [ str(i) for i in TrueAns]
TrueAns = "".join(TrueAns)
print(TrueAns)


# 主程式
print("猜數字，請輸入四個不重複的數字(0~9)，您將有 10 次機會。(可按q退出)")

count = 1
AnsList = []
ABList = []

while(True):
    Ans = input(f"第{count}次猜測,請輸入:")

    if Ans == 'q':
        print("正確答案是: %s" % (TrueAns))
        break
    elif(exam_num(Ans)==True):
        pass
    else:
        continue

    AnsList.append(Ans)
    output = compare(Ans,TrueAns)
    ABList.append(output)

    if (output[0]==4):
        print("恭喜您完全答對了，以下是您的答案及結果列表")
        for j, k in enumerate(AnsList):
            print(f" {k} , " ,end="")
            print(ABList[j][0],end="")
            print(" A ",end="")
            print(ABList[j][1],end="")
            print(" B ")

        break
    else:
        print("您的第 %s 次猜測是 %s，猜測結果是 %d A %d B"  % (count,Ans,output[0],output[1]))
        count += 1
        if count==11:
            print("已經猜10次囉，正確答案是: %s" % (TrueAns))
            print("以下是您的答案及結果列表")
        for j, k in enumerate(AnsList):
            print(f" {k} , " ,end="")
            print(ABList[j][0],end="")
            print(" A ",end="")
            print(ABList[j][1],end="")
            print(" B ")
                
            break
        continue
