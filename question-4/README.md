## سوال ۴ - باشگاه مشتریان

### صورت مسئله

محاسبه کاربران ممتاز از دیتای فراهم شده و گروه بندی کاربران
به شکل درخواستی کاربر و اعمال تخفیف‌های هر گروه.


### حل

 ابتدا دیتا را که نمونه آن در فایل 
`trade.xlsx`
 مشخص شده دریافت کرده و
برای هر کاربر امتیازی در نظر میگیریم.

چون مقدار کارمزد درصد ثابتی از هر تراکنش است، از ارزش کل برای امتیاز دهی به هر کاربر استفاده میکنم.

امتیاز هر کاربر میانگین ارزش کل تمام تراکنش‌های کاربر است.

گروه‌های تخفیفی به صورت زیر مشخص می‌شوند:

```python
discount_groups = {
    50: 20,
    40: 30,
    30: 50,
    20: 100,
}
```
که key ها مقدار تخفیف به درصد و
value ها تعداد کاربرانی‌است که شامل این تخفیف میشوند

کاربران ممتاز از بیشترین امتیاز به کمترین امتیاز مرتب شده و
به ترتیب از بالاترین درصد به پایین ترین درصد گروه بندی می‌شوند.

## تست

برای تست از دیتای موجود در فایل اکسل ارائه شده در سوال استفاده شده و نتیجه به صورت زیر می‌باشد:

```
group_0 :       Discount percent:  50% 
Users: (20)

70380   40471   70381   40719   19975   40788   40740   8879    70308   41660   16105   40814   40726   3605    40588   40866   45266   40842   15894   24327

group_1 :       Discount percent:  40% 
Users: (30)

22428   617     13658   616     26512   40565   30262   27605   21152   40863   17570   40473   57693   9069    1573    40714   16920   30587   22837   494     12901   31363   11069     102     6372    15141   24884   40339   9796    716

group_2 :       Discount percent:  30% 
Users: (50)

40368   28939   10746   30536   21435   679     13223   26821   655     41259   31505   70309   22496   41061   40415   70330   3676    14706   40966   40833   15574   21800   30238     41089   40350   7347    70366   1786    24613   11106   406     26671   27143   70182   8617    22854   1018    40944   23539   15150   6157    517     24372   20236   14198     15451   40383   374     573     500

group_3 :       Discount percent:  20% 
Users: (100)

20203   40586   23206   22740   19193   31323   11062   29062   31200   540     41202   405     20440   18096   17582   8555    40511   24976   6002    22468   22426   11607   8523      25382   41218   22009   7501    603     20343   10625   41215   40308   70345   23381   3313    7655    31209   25470   20281   8198    25711   10014   31575   20561   24583     20489   24695   52316   41205   69790   67      4848    4317    1486    18984   70068   16065   41077   26431   12071   28268   20975   10309   22952   13733   31767   686       2034    13802   22522   6363    629     17772   41208   13210   24687   32035   41164   8102    69091   12379   20930   19793   3020    12344   598     40686   31804   17656     21395   27579   17981   12383   10640   41138   15122   2213    8621    28812   28937
```