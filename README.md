from tkinter import *
from tkinter import filedialog,messagebox
import random
import time

#Functions

def reset():
    textReceipt.delete(1.0,END)

    e_bokkeumbab.set('0')
    e_jjajangmyeon.set('0')
    e_bulgogi.set('0')
    e_ongshimi.set('0')
    e_rabokki.set('0')
    e_nakji.set('0')
    e_yangnyeom.set('0')
    e_dak.set('0')
    e_tteokbokki.set('0')
    e_family.set('0')
    e_chingu.set('0')

    e_soju.set('0')
    e_water.set('0')
    e_orange.set('0')
    e_bingsoo.set('0')
    e_maekju.set('0')
    e_sikhye.set('0')
    e_makgeolli.set('0')
    e_mojito.set('0')
    e_milkis.set('0')
    e_chilsungcider.set('0')
    e_somaek.set('0')

    e_kimbab.set('0')
    e_eomuk.set('0')
    e_gimmari.set('0')
    e_ramyeon.set('0')
    e_hotdog.set('0')
    e_bungeoppang.set('0')
    e_hotteok.set('0')
    e_tteokkochi.set('0')
    e_sotteok.set('0')
    e_sundae.set('0')
    e_gyeranppang.set('0')


    textjjajangmyeon.config(state=DISABLED)
    textbulgogi.config(state=DISABLED)
    textongshimi.config(state=DISABLED)
    textrabokki.config(state=DISABLED)
    textnakji.config(state=DISABLED)
    textyangnyeom.config(state=DISABLED)
    textdak.config(state=DISABLED)
    texttteokbokki.config(state=DISABLED)
    textfamily.config(state=DISABLED)
    textchingu.config(state=DISABLED)

    textsoju.config(state=DISABLED)
    textwater.config(state=DISABLED)
    textorange.config(state=DISABLED)
    textbingsoo.config(state=DISABLED)
    textmaekju.config(state=DISABLED)
    textsikhye.config(state=DISABLED)
    textmakgeolli.config(state=DISABLED)
    textmojito.config(state=DISABLED)
    textmilkis.config(state=DISABLED)
    textchilsungcider.config(state=DISABLED)
    textsomaek.config(state=DISABLED)

    textkimbab.config(state=DISABLED)
    texteomuk.config(state=DISABLED)
    textgimmari.config(state=DISABLED)
    textramyeon.config(state=DISABLED)
    texthotdog.config(state=DISABLED)
    textbungeoppang.config(state=DISABLED)
    texthotteok.config(state=DISABLED)
    texttteokkochi.config(state=DISABLED)
    textsotteok.config(state=DISABLED)
    textsundae.config(state=DISABLED)
    textgyeranppang.config(state=DISABLED)


#MILA

    var1.set(0)
    var2.set(0)
    var3.set(0)
    var4.set(0)
    var5.set(0)
    var6.set(0)
    var7.set(0)
    var8.set(0)
    var9.set(0)
    var10.set(0)
    var11.set(0)
    var12.set(0)
    var13.set(0)
    var14.set(0)
    var15.set(0)
    var16.set(0)
    var17.set(0)
    var18.set(0)
    var19.set(0)
    var20.set(0)
    var21.set(0)
    var22.set(0)
    var23.set(0)
    var24.set(0)
    var25.set(0)
    var26.set(0)
    var27.set(0)
    var28.set(0)
    var29.set(0)
    var30.set(0)
    var31.set(0)
    var32.set(0)
    var33.set(0)

    costoffoodvar.set('')
    costofdrinkvar.set('')
    costofsnackvar.set('')
    subtotalvar.set('')
    servicetaxvar.set('')
    totalcostvar.set('')

def save():
    if textReceipt.get(1.0,END)=='\n':
        pass
    else:
        url=filedialog.asksaveasfile(mode='w',defaultextension='.txt')
        if url==None:
            pass
        else:

            bill_data=textReceipt.get(1,0,END)
            url.write(bill_data)
            url.close()
            messagebox.showinfo('Information','Your Bill is Succesfully Saved')

def receipt():
    global billnumber,date
    if costoffoodvar.get() !=''or costofsnackvar.get() !=''or costofdrinkvar.get() !='':
        textReceipt.delete(1.0,END)
        x=random.randint(100,1000)
        billnumber='BILL'+str(x)
        date=time.strftime('%d/%m/%Y')
        textReceipt.insert(END,'Receipt Ref:\t\t'+billnumber+'\t\t'+date+'\n')
        textReceipt.insert(END,'*****************************************************\n')
        textReceipt.insert(END,'Items:\t\t Cost of Items(Rp)\n')
        textReceipt.insert(END,'*****************************************************\n')
        if e_bokkeumbab.get()!='0':
            textReceipt.insert(END,f'BK.BAB\t\t\t{int(e_bokkeumbab.get())*35000}\n\n')

        if e_jjajangmyeon.get()!='0':
            textReceipt.insert(END,f'JJ.MYEON\t\t\t{int(e_jjajangmyeon.get())*38000}\n\n')

        if e_bulgogi.get()!='0':
            textReceipt.insert(END,f'BULGOGI\t\t\t{int(e_bulgogi.get())*60000}\n\n')

        if e_ongshimi.get()!='0':
            textReceipt.insert(END,f'ONGSHIMI\t\t\t{int(e_ongshimi.get())*26000}\n\n')

        if e_rabokki.get()!='0':
            textReceipt.insert(END,f'RABOKKI\t\t\t{int(e_rabokki.get())*33000}\n\n')

        if e_nakji.get()!='0':
            textReceipt.insert(END,f'NAKJI BK\t\t\t{int(e_nakji.get())*77000}\n\n')

        if e_yangnyeom.get()!='0':
            textReceipt.insert(END,f'Y.CHICKEN\t\t\t{int(e_yangnyeom.get())*56000}\n\n')

        if e_dak.get()!='0':
            textReceipt.insert(END,f'DAKBAL\t\t\t{int(e_dak.get())*33000}\n\n')

        if e_tteokbokki.get()!='0':
            textReceipt.insert(END,f'TK.BOKKI\t\t\t{int(e_tteokbokki.get())*35000}\n\n')

        if e_family.get()!='0':
            textReceipt.insert(END,f'FAM PCKG\t\t\t{int(e_family.get())*199000}\n\n')

        if e_chingu.get()!='0':
            textReceipt.insert(END,f'CHINGU PCKG\t\t\t{int(e_chingu.get())*119000}\n\n')

        if e_soju.get()!='0':
            textReceipt.insert(END,f'SOJU\t\t\t{int(e_soju.get())*100000}\n\n')

        if e_water.get()!='0':
            textReceipt.insert(END,f'WATER\t\t\t{int(e_water.get())*13000}\n\n')

        if e_orange.get()!='0':
            textReceipt.insert(END,f'ORENJI\t\t\t{int(e_orange.get())*13000}\n\n')

        if e_bingsoo.get()!='0':
            textReceipt.insert(END,f'BINGSOO\t\t\t{int(e_bingsoo.get())*25000}\n\n')

        if e_maekju.get()!='0':
            textReceipt.insert(END,f'MAEKJU\t\t\t{int(e_maekju.get())*88000}\n\n')

        if e_sikhye.get()!='0':
            textReceipt.insert(END,f'SIKHYE\t\t\t{int(e_sikhye.get())*32000}\n\n')

        if e_makgeolli.get()!='0':
            textReceipt.insert(END,f'MAKGEOLLI\t\t\t{int(e_makgeolli.get())*50000}\n\n')

        if e_mojito.get()!='0':
            textReceipt.insert(END,f'MOJITO\t\t\t{int(e_mojito.get())*24000}\n\n')

        if e_milkis.get()!='0':
            textReceipt.insert(END,f'MILKIS\t\t\t{int(e_milkis.get())*15000}\n\n')

        if e_chilsungcider.get()!='0':
            textReceipt.insert(END,f'C.CIDER\t\t\t{int(e_chilsungcider.get())*15000}\n\n')

        if e_somaek.get()!='0':
            textReceipt.insert(END,f'SOMAEK\t\t\t{int(e_somaek.get())*144000}\n\n')

        if e_kimbab.get()!='0':
            textReceipt.insert(END,f'KIMBAB\t\t\t{int(e_kimbab.get())*15000}\n\n')

        if e_gimmari.get()!='0':
            textReceipt.insert(END,f'GIMMARI\t\t\t{int(e_gimmari.get())*12000}\n\n')

        if e_eomuk.get()!='0':
            textReceipt.insert(END,f'EOMUK\t\t\t{int(e_eomuk.get())*15000}\n\n')

        if e_ramyeon.get()!='0':
            textReceipt.insert(END,f'RAMYEON\t\t\t{int(e_ramyeon.get())*25000}\n\n')

        if e_hotdog.get()!='0':
            textReceipt.insert(END,f'HOTDOG\t\t\t{int(e_hotdog.get())*12000}\n\n')

        if e_bungeoppang.get()!='0':
            textReceipt.insert(END,f'BUNGEO PG\t\t\t{int(e_bungeoppang.get())*14000}\n\n')

        if e_hotteok.get()!='0':
            textReceipt.insert(END,f'HOTTEOK\t\t\t{int(e_hotteok.get())*13000}\n\n')

        if e_tteokkochi.get()!='0':
            textReceipt.insert(END,f'TK.KOCHI\t\t\t{int(e_tteokkochi.get())*12000}\n\n')

        if e_sotteok.get()!='0':
            textReceipt.insert(END,f'SOTTEOK\t\t\t{int(e_sotteok.get())*12000}\n\n')

        if e_sundae.get()!='0':
            textReceipt.insert(END,f'SUNDAE\t\t\t{int(e_sundae.get())*22000}\n\n')

        if e_gyeranppang.get()!='0':
            textReceipt.insert(END,f'GYERAN P\t\t\t{int(e_gyeranppang.get())*15000}\n\n')

        textReceipt.insert(END, '*****************************************************\n')
        if costoffoodvar.get()!='0':
            textReceipt.insert(END,f'Cost of Foods\t\t\t{priceofFoods}\n\n')
        if costoffoodvar.get()!='0':
            textReceipt.insert(END,f'Cost of Drinks\t\t\t{priceofDrinks}\n\n')
        if costoffoodvar.get()!='0':
            textReceipt.insert(END,f'Cost of Snacks\t\t\t{priceofSnacks}\n\n')

        textReceipt.insert(END,f'Sub Total\t\t\t{subtotalofItems}\n\n')
        textReceipt.insert(END, f'Service Tax\t\t\t{10000}\n\n')
        textReceipt.insert(END, f'Total Cost\t\t\t{subtotalofItems+10000}\n\n')
        textReceipt.insert(END, '*****************************************************\n')

    else:
        messagebox.showerror('Error','No Item is Selected')


#FUTARI

def totalcost():
    global priceofFoods,priceofDrinks,priceofSnacks,subtotalofItems

    if var1.get()!=0 or var2.get()!=0 or var2.get()!=0 or var3.get()!=0 or var4.get()!=0 or var5.get()!=0 or \
        var6.get()!=0 or var7.get()!=0  or var8.get()!=0 or var9.get()!=0 or var10.get()!=0 or \
        var11.get()!=0  or var12.get()!=0 or var13.get()!=0 or var14.get()!=0 or var15.get()!=0 or \
        var16.get()!=0 or var17.get()!=0 or var18.get()!=0 or var19.get()!=0 or var20.get()!=0 or \
        var21.get()!=0 or var22.get()!=0 or  var23.get()!=0 or var24.get()!=0 or var25.get()!=0 or \
        var26.get()!=0 or var27.get()!=0 or var28.get()!=0 or var29.get()!=0 or var30.get()!=0 or \
        var31.get()!=0 or var32.get()!=0 or var33.get()!=0 :

        item1=int(e_bokkeumbab.get())
        item2=int(e_jjajangmyeon.get())
        item3=int(e_bulgogi.get())
        item4=int(e_ongshimi.get())
        item5=int(e_rabokki.get())
        item6=int(e_nakji.get())
        item7=int(e_yangnyeom.get())
        item8=int(e_dak.get())
        item9=int(e_tteokbokki.get())
        item10=int(e_family.get())
        item11=int(e_chingu.get())

        item12=int(e_soju.get())
        item13=int(e_water.get())
        item14=int(e_orange.get())
        item15=int(e_bingsoo.get())
        item16=int(e_maekju.get())
        item17=int(e_sikhye.get())
        item18=int(e_makgeolli.get())
        item19=int(e_mojito.get())
        item20=int(e_milkis.get())
        item21=int(e_chilsungcider.get())
        item22=int(e_somaek.get())

        item23=int(e_kimbab.get())
        item24=int(e_gimmari.get())
        item25=int(e_eomuk.get())
        item26=int(e_ramyeon.get())
        item27=int(e_hotdog.get())
        item28=int(e_bungeoppang.get())
        item29=int(e_hotteok.get())
        item30=int(e_tteokkochi.get())
        item31=int(e_sotteok.get())
        item32=int(e_sundae.get())
        item33=int(e_gyeranppang.get())

   
        priceofFoods=(item1*35000)+(item2*38000)+(item3*60000)+(item4*26000)+(item5*33000)+(item6*77000)+(item7*56000)\
                     +(item8*33000)+(item9*35000)+(item10*199000)+(item11*119000)
        priceofDrinks=(item12*100000)+(item13*13000)+(item14*13000)+(item15*25000)+(item16*88000)+(item17*32000)+(item18*50000)\
                      +(item19*24000)+(item20*15000)+(item21*15000)+(item22*144000)
        priceofSnacks=(item23*15000)+(item24*12000)+(item25*15000)+(item26*25000)+(item27*12000)+(item28*14000)+(item29*13000)\
                      +(item30*12000)+(item31*12000)+(item32*22000)+(item33*15000)

        costoffoodvar.set(str(priceofFoods))
        costofdrinkvar.set(str(priceofDrinks))
        costofsnackvar.set(str(priceofSnacks))

        subtotalofItems=priceofFoods+priceofDrinks+priceofSnacks
        subtotalvar.set(str(subtotalofItems))

        servicetaxvar.set('10000')

        totalcost=subtotalofItems+10000
        totalcostvar.set(str(totalcost))

    else :
        messagebox.showerror('Error','No Item Is Selected')

#ADORA

def bokkeumbab():
    if var1.get()==1:
        textbokkeumbab.config(state=NORMAL)
        textbokkeumbab.delete(0,END)
        textbokkeumbab.focus()
    else :
        textbokkeumbab.config(state=DISABLED)
        e_bokkeumbab.set('0')

def jjajangmyeon():
    if var2.get()==1:
        textjjajangmyeon.config(state=NORMAL)
        textjjajangmyeon.delete(0,END)
        textjjajangmyeon.focus()
    else :
        textjjajangmyeon.config(state=DISABLED)
        e_jjajangmyeon.set('0')

def bulgogi():
    if var3.get()==1:
        textbulgogi.config(state=NORMAL)
        textbulgogi.delete(0,END)
        textbulgogi.focus()
    else :
        textbulgogi.config(state=DISABLED)
        e_bulgogi.set('0')

def ongshimi():
    if var4.get() == 1:
        textongshimi.config(state=NORMAL)
        textongshimi.delete(0, END)
        textongshimi.focus()
    else:
        textongshimi.config(state=DISABLED)
        e_ongshimi.set('0')

def rabokki():
    if var5.get()==1:
        textrabokki.config(state=NORMAL)
        textrabokki.delete(0,END)
        textrabokki.focus()
    else :
        textrabokki.config(state=DISABLED)
        e_rabokki.set('0')

def nakji():
    if var6.get()==1:
        textnakji.config(state=NORMAL)
        textnakji.delete(0,END)
        textnakji.focus()
    else :
        textnakji.config(state=DISABLED)
        e_nakji.set('0')

def yangnyeom():
    if var7.get()==1:
        textyangnyeom.config(state=NORMAL)
        textyangnyeom.delete(0,END)
        textyangnyeom.focus()
    else :
        textyangnyeom.config(state=DISABLED)
        e_yangnyeom.set('0')

def dak():
    if var8.get()==1:
        textdak.config(state=NORMAL)
        textdak.delete(0,END)
        textdak.focus()
    else :
        textdak.config(state=DISABLED)
        e_dak.set('0')

def tteokbokki():
    if var9.get()==1:
        texttteokbokki.config(state=NORMAL)
        texttteokbokki.delete(0,END)
        texttteokbokki.focus()
    else :
        texttteokbokki.config(state=DISABLED)
        e_tteokbokki.set('0')

def family():
    if var10.get()==1:
        textfamily.config(state=NORMAL)
        textfamily.delete(0,END)
        textfamily.focus()
    else :
        textfamily.config(state=DISABLED)
        e_family.set('0')

def chingu():
    if var11.get()==1:
        textchingu.config(state=NORMAL)
        textchingu.delete(0,END)
        textchingu.focus()
    else :
        textchingu.config(state=DISABLED)
        e_chingu.set('0')

def soju():
    if var12.get()==1:
        textsoju.config(state=NORMAL)
        textsoju.delete(0,END)
        textsoju.focus()
    else :
        textsoju.config(state=DISABLED)
        e_soju.set('0')

def water():
    if var13.get()==1:
        textwater.config(state=NORMAL)
        textwater.delete(0,END)
        textwater.focus()
    else :
        textwater.config(state=DISABLED)
        e_water.set('0')

def orange():
    if var14.get()==1:
        textorange.config(state=NORMAL)
        textorange.delete(0,END)
        textorange.focus()
    else :
        textorange.config(state=DISABLED)
        e_orange.set('0')

def bingsoo():
    if var15.get()==1:
        textbingsoo.config(state=NORMAL)
        textbingsoo.delete(0,END)
        textbingsoo.focus()
    else :
        textbingsoo.config(state=DISABLED)
        e_bingsoo.set('0')

def maekju():
    if var16.get()==1:
        textmaekju.config(state=NORMAL)
        textmaekju.delete(0,END)
        textmaekju.focus()
    else :
        textmaekju.config(state=DISABLED)
        e_maekju.set('0')

def sikhye():
    if var17.get()==1:
        textsikhye.config(state=NORMAL)
        textsikhye.delete(0,END)
        textsikhye.focus()
    else :
        textsikhye.config(state=DISABLED)
        e_sikhye.set('0')

def makgeolli():
    if var18.get()==1:
        textmakgeolli.config(state=NORMAL)
        textmakgeolli.delete(0,END)
        textmakgeolli.focus()
    else :
        textmakgeolli.config(state=DISABLED)
        e_makgeolli.set('0')

def mojito():
    if var19.get()==1:
        textmojito.config(state=NORMAL)
        textmojito.delete(0,END)
        textmojito.focus()
    else :
        textmojito.config(state=DISABLED)
        e_mojito.set('0')

def milkis():
    if var20.get()==1:
        textmilkis.config(state=NORMAL)
        textmilkis.delete(0,END)
        textmilkis.focus()
    else :
        textmilkis.config(state=DISABLED)
        e_milkis.set('0')

def chilsungcider():
    if var21.get()==1:
        textchilsungcider.config(state=NORMAL)
        textchilsungcider.delete(0,END)
        textchilsungcider.focus()
    else :
        textchilsungcider.config(state=DISABLED)
        e_chilsungcider.set('0')

def somaek():
    if var22.get()==1:
        textsomaek.config(state=NORMAL)
        textsomaek.delete(0,END)
        textsomaek.focus()
    else :
        textsomaek.config(state=DISABLED)
        e_somaek.set('0')

def kimbab():
    if var23.get()==1:
        textkimbab.config(state=NORMAL)
        textkimbab.delete(0,END)
        textkimbab.focus()
    else :
        textkimbab.config(state=DISABLED)
        e_kimbab.set('0')

def gimmari():
    if var24.get()==1:
        textgimmari.config(state=NORMAL)
        textgimmari.delete(0,END)
        textgimmari.focus()
    else :
        textgimmari.config(state=DISABLED)
        e_gimmari.set('0')

def eomuk():
    if var25.get()==1:
        texteomuk.config(state=NORMAL)
        texteomuk.delete(0,END)
        texteomuk.focus()
    else :
        texteomuk.config(state=DISABLED)
        e_eomuk.set('0')

def ramyeon():
    if var26.get()==1:
        textramyeon.config(state=NORMAL)
        textramyeon.delete(0,END)
        textramyeon.focus()
    else :
        textramyeon.config(state=DISABLED)
        e_ramyeon.set('0')

def hotdog():
    if var27.get()==1:
        texthotdog.config(state=NORMAL)
        texthotdog.delete(0,END)
        texthotdog.focus()
    else :
        texthotdog.config(state=DISABLED)
        e_hotdog.set('0')

def bungeoppang():
    if var28.get()==1:
        textbungeoppang.config(state=NORMAL)
        textbungeoppang.delete(0,END)
        textbungeoppang.focus()
    else :
        textbungeoppang.config(state=DISABLED)
        e_bungeoppang.set('0')

def hotteok():
    if var29.get()==1:
        texthotteok.config(state=NORMAL)
        texthotteok.delete(0,END)
        texthotteok.focus()
    else :
        texthotteok.config(state=DISABLED)
        e_hotteok.set('0')

def tteokkochi():
    if var30.get()==1:
        texttteokkochi.config(state=NORMAL)
        texttteokkochi.delete(0,END)
        texttteokkochi.focus()
    else :
        texttteokkochi.config(state=DISABLED)
        e_tteokkochi.set('0')

def sotteok():
    if var31.get()==1:
        textsotteok.config(state=NORMAL)
        textsotteok.delete(0,END)
        textsotteok.focus()
    else :
        textsotteok.config(state=DISABLED)
        e_sotteok.set('0')

def sundae():
    if var32.get()==1:
        textsundae.config(state=NORMAL)
        textsundae.delete(0,END)
        textsundae.focus()
    else :
        textsundae.config(state=DISABLED)
        e_sundae.set('0')

def gyeranppang():
    if var33.get()==1:
        textgyeranppang.config(state=NORMAL)
        textgyeranppang.delete(0,END)
        textgyeranppang.focus()
    else :
        textgyeranppang.config(state=DISABLED)
        e_gyeranppang.set('0')

window = Tk()

window.geometry('1270x690+0+0')
window.resizable(0,0)
window.title('Imonim Sikdang Restaurant Management Sytem by Adora')
window.config(bg='salmon')

topFrame=Frame(window, bd=3, relief=FLAT, bg='peachpuff')
topFrame.pack(side=TOP)

topFrame2=Frame(window, bd=1, relief=GROOVE, bg='peachpuff')
topFrame2.pack(side=TOP)

labelTitle=Label(topFrame, text='Imonim Sikdang Restaurant', font=('arial',30,'bold'), fg='sienna',bd=9,bg='ivory', width=51)
labelTitle.grid(row=0, column=0)

labelTitle2=Label(topFrame2, text='We serve you a quality of Korean original Taste ♡', font=('arial',15,'italic','bold'),fg='ivory',bd=3,bg='sienna', width=40)
labelTitle2.grid(row=1, column=1)

#frames
menuFrame=Frame(window,bd=20, relief=RIDGE)
menuFrame.pack(side=LEFT)

costFrame=Frame(menuFrame,bd=4,relief=RIDGE)
costFrame.pack(side=BOTTOM)

foodsFrame=LabelFrame(menuFrame, text='Foods',font=('arial',18,'bold'),bd=10, padx=20,relief=RIDGE, fg='brown')
foodsFrame.pack(side=LEFT)

drinksFrame=LabelFrame(menuFrame, text='Drinks',font=('arial',18,'bold'),bd=10, padx= 20,relief=RIDGE, fg='brown')
drinksFrame.pack(side=LEFT)

snacksFrame=LabelFrame(menuFrame, text='Snacks',font=('arial',18,'bold'),bd=10, padx=20,relief=RIDGE, fg='brown')
snacksFrame.pack(side=LEFT)

rightFrame=Frame(window, bd=15, relief=RIDGE)
rightFrame.pack(side=RIGHT)

calculatorFrame=Frame(rightFrame, bd=1, relief=RIDGE)
calculatorFrame.pack()

receiptFrame=Frame(rightFrame, bd=4, relief=RIDGE)
receiptFrame.pack()

buttonFrame=Frame(rightFrame,bd=3,relief=RIDGE)
buttonFrame.pack()

#Variable
#untuk mendeteksi bahwa yang di input setelahnya nanti adalah berupa angka intejer
var1=IntVar()
var2=IntVar()
var3=IntVar()
var4=IntVar()
var5=IntVar()
var6=IntVar()
var7=IntVar()
var8=IntVar()
var9=IntVar()
var10=IntVar()
var11=IntVar()
var12=IntVar()
var13=IntVar()
var14=IntVar()
var15=IntVar()
var16=IntVar()
var17=IntVar()
var18=IntVar()
var19=IntVar()
var20=IntVar()
var21=IntVar()
var22=IntVar()
var23=IntVar()
var24=IntVar()
var25=IntVar()
var26=IntVar()
var27=IntVar()
var28=IntVar()
var29=IntVar()
var30=IntVar()
var31=IntVar()
var32=IntVar()
var33=IntVar()


#Untuk menyimpan karakter/variable yang dimanipulasi
e_bokkeumbab=StringVar()
e_jjajangmyeon=StringVar()
e_bulgogi=StringVar()
e_ongshimi=StringVar()
e_rabokki=StringVar()
e_nakji=StringVar()
e_yangnyeom=StringVar()
e_dak=StringVar()
e_tteokbokki=StringVar()
e_family=StringVar()
e_chingu=StringVar()

e_soju=StringVar()
e_water=StringVar()
e_orange=StringVar()
e_bingsoo=StringVar()
e_maekju=StringVar()
e_sikhye=StringVar()
e_makgeolli=StringVar()
e_mojito=StringVar()
e_milkis=StringVar()
e_chilsungcider=StringVar()
e_somaek=StringVar()

e_kimbab=StringVar()
e_eomuk=StringVar()
e_gimmari=StringVar()
e_ramyeon=StringVar()
e_hotdog=StringVar()
e_bungeoppang=StringVar()
e_hotteok=StringVar()
e_tteokkochi=StringVar()
e_sotteok=StringVar()
e_sundae=StringVar()
e_gyeranppang=StringVar()

costoffoodvar=StringVar()
costofdrinkvar=StringVar()
costofsnackvar=StringVar()
subtotalvar=StringVar()
servicetaxvar=StringVar()
totalcostvar=StringVar()


e_bokkeumbab.set('0')
e_jjajangmyeon.set('0')
e_bulgogi.set('0')
e_ongshimi.set('0')
e_rabokki.set('0')
e_nakji.set('0')
e_yangnyeom.set('0')
e_dak.set('0')
e_tteokbokki.set('0')
e_family.set('0')
e_chingu.set('0')

e_soju.set('0')
e_water.set('0')
e_orange.set('0')
e_bingsoo.set('0')
e_maekju.set('0')
e_sikhye.set('0')
e_makgeolli.set('0')
e_mojito.set('0')
e_milkis.set('0')
e_chilsungcider.set('0')
e_somaek.set('0')

e_kimbab.set('0')
e_eomuk.set('0')
e_gimmari.set('0')
e_ramyeon.set('0')
e_hotdog.set('0')
e_bungeoppang.set('0')
e_hotteok.set('0')
e_tteokkochi.set('0')
e_sotteok.set('0')
e_sundae.set('0')
e_gyeranppang.set('0')


#Felin

#Food
bokkeumbab=Checkbutton(foodsFrame, text='BK.BAB', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var1
                       ,command=bokkeumbab)
bokkeumbab.grid(row=0, column=0,sticky=W)

jjajangmyeon=Checkbutton(foodsFrame, text='JJ.MYEON', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var2
                         ,command=jjajangmyeon)
jjajangmyeon.grid(row=1, column=0,sticky=W)

bulgogi=Checkbutton(foodsFrame, text='BULGOGI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var3
                    ,command=bulgogi)
bulgogi.grid(row=2, column=0,sticky=W)

ongshimi=Checkbutton(foodsFrame, text='ONGSHIMI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var4
                     ,command=ongshimi)
ongshimi.grid(row=3, column=0, sticky=W)

rabokki=Checkbutton(foodsFrame, text='RABOKKI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var5
                    ,command=rabokki)
rabokki.grid(row=4, column=0, sticky=W)

nakji=Checkbutton(foodsFrame, text='NAKJI BK', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var6
                  ,command=nakji)
nakji.grid(row=5, column=0, sticky=W)

yangnyeom=Checkbutton(foodsFrame, text='Y. CHICKEN', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var7
                      ,command=yangnyeom)
yangnyeom.grid(row=6, column=0, sticky=W)

dak=Checkbutton(foodsFrame, text='DAKBAL', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var8
                ,command=dak)
dak.grid(row=7, column=0, sticky=W)

tteokbokki=Checkbutton(foodsFrame, text='TK. BOKKI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var9
                       ,command=tteokbokki)
tteokbokki.grid(row=8, column=0, sticky=W)

family=Checkbutton(foodsFrame, text='FAM PCKG', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var10
                   ,command=family)
family.grid(row=9, column=0, sticky=W)

chingu=Checkbutton(foodsFrame, text='CHINGU PCKG', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var11
                   ,command=chingu)
chingu.grid(row=10, column=0, sticky=W)

#Entry Fields for Food Items

textbokkeumbab=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_bokkeumbab)
textbokkeumbab.grid(row=0, column=1)

textjjajangmyeon=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_jjajangmyeon)
textjjajangmyeon.grid(row=1, column=1)

textbulgogi=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_bulgogi)
textbulgogi.grid(row=2, column=1)

textongshimi=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_ongshimi)
textongshimi.grid(row=3, column=1)

textrabokki=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_rabokki)
textrabokki.grid(row=4, column=1)

textnakji=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_nakji)
textnakji.grid(row=5, column=1)

textyangnyeom=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_yangnyeom)
textyangnyeom.grid(row=6, column=1)

textdak=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_dak)
textdak.grid(row=7, column=1)

texttteokbokki=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_tteokbokki)
texttteokbokki.grid(row=8, column=1)

textfamily=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_family)
textfamily.grid(row=9, column=1)

textchingu=Entry(foodsFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_chingu)
textchingu.grid(row=10, column=1)

#Drinks
soju=Checkbutton(drinksFrame, text='SOJU', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var12
                 ,command=soju)
soju.grid(row=0, column=0,sticky=W)

water=Checkbutton(drinksFrame, text='WATER', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var13
                  ,command=water)
water.grid(row=1, column=0,sticky=W)

orange=Checkbutton(drinksFrame, text='ORENJI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var14
                   ,command=orange)
orange.grid(row=2, column=0,sticky=W)

bingsoo=Checkbutton(drinksFrame, text='BINGSOO', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var15
                    ,command=bingsoo)
bingsoo.grid(row=3, column=0,sticky=W)

maekju=Checkbutton(drinksFrame, text='MAEKJU', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var16
                   ,command=maekju)
maekju.grid(row=4, column=0,sticky=W)

sikhye=Checkbutton(drinksFrame, text='SIKHYE', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var17
                   ,command=sikhye)
sikhye.grid(row=5, column=0,sticky=W)

makgeolli=Checkbutton(drinksFrame, text='M.GEOLLI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var18
                   ,command=makgeolli)
makgeolli.grid(row=6, column=0,sticky=W)

mojito=Checkbutton(drinksFrame, text='MOJITO', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var19
                   ,command=mojito)
mojito.grid(row=7, column=0,sticky=W)

milkis=Checkbutton(drinksFrame, text='MILKIS', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var20
                   ,command=milkis)
milkis.grid(row=8, column=0,sticky=W)

chilsungcider=Checkbutton(drinksFrame, text='C.CIDER', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var21
                          ,command=chilsungcider)
chilsungcider.grid(row=9, column=0,sticky=W)

somaek=Checkbutton(drinksFrame, text='SOMAEK', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var22
                   ,command=somaek)
somaek.grid(row=10, column=0,sticky=W)

#Entry Fields for Drink Items
textsoju=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_soju)
textsoju.grid(row=0, column=1)

textwater=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_water)
textwater.grid(row=1, column=1)

textorange=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_orange)
textorange.grid(row=2, column=1)

textbingsoo=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_bingsoo)
textbingsoo.grid(row=3, column=1)

textmaekju=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_maekju)
textmaekju.grid(row=4, column=1)

textsikhye=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_sikhye)
textsikhye.grid(row=5, column=1)

textmakgeolli=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_makgeolli)
textmakgeolli.grid(row=6, column=1)

textmojito=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_mojito)
textmojito.grid(row=7, column=1)

textmilkis=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_milkis)
textmilkis.grid(row=8, column=1)

textchilsungcider=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_chilsungcider)
textchilsungcider.grid(row=9, column=1)

textsomaek=Entry(drinksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_somaek)
textsomaek.grid(row=10, column=1)

#Snacks
kimbab=Checkbutton(snacksFrame, text='KIMBAB', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var23
                   ,command=kimbab)
kimbab.grid(row=0, column=0,sticky=W)

gimmari=Checkbutton(snacksFrame, text='GIMMARI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var24
                    ,command=gimmari)
gimmari.grid(row=1, column=0,sticky=W)

eomuk=Checkbutton(snacksFrame, text='EOMUK', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var25
                  ,command=eomuk)
eomuk.grid(row=2, column=0,sticky=W)

ramyeon=Checkbutton(snacksFrame, text='RAMYEON', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var26
                    ,command=ramyeon)
ramyeon.grid(row=3, column=0,sticky=W)

hotdog=Checkbutton(snacksFrame, text='HOTDOG', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var27
                   ,command=hotdog)
hotdog.grid(row=4, column=0,sticky=W)

bungeoppang=Checkbutton(snacksFrame, text='BUNGEO PG', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var28
                        ,command=bungeoppang)
bungeoppang.grid(row=5, column=0,sticky=W)

hotteok=Checkbutton(snacksFrame, text='HOTTEOK', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var29
                    ,command=hotteok)
hotteok.grid(row=6, column=0,sticky=W)

tteokkochi=Checkbutton(snacksFrame, text='TK.KOCHI', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var30
                       ,command=tteokkochi)
tteokkochi.grid(row=7, column=0,sticky=W)

sotteok=Checkbutton(snacksFrame, text='SOTTEOK', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var31
                    ,command=sotteok)
sotteok.grid(row=8, column=0,sticky=W)

sundae=Checkbutton(snacksFrame, text='SUNDAE', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var32
                   ,command=sundae)
sundae.grid(row=9, column=0,sticky=W)

gyeranppang=Checkbutton(snacksFrame, text='GYERAN P', font=('arial',12,'bold'), onvalue=1, offvalue=0, variable=var33
                        ,command=gyeranppang)
gyeranppang.grid(row=10, column=0,sticky=W)

#Entry Fields for Snack Items
textkimbab=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_kimbab)
textkimbab.grid(row=0, column=1)

textgimmari=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_gimmari)
textgimmari.grid(row=1, column=1)

texteomuk=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_eomuk)
texteomuk.grid(row=2, column=1)

textramyeon=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_ramyeon)
textramyeon.grid(row=3, column=1)

texthotdog=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_hotdog)
texthotdog.grid(row=4, column=1)

textbungeoppang=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_bungeoppang)
textbungeoppang.grid(row=5, column=1)

texthotteok=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_hotteok)
texthotteok.grid(row=6, column=1)

texttteokkochi=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_tteokkochi)
texttteokkochi.grid(row=7, column=1)

textsotteok=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_sotteok)
textsotteok.grid(row=8, column=1)

textsundae=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_sundae)
textsundae.grid(row=9, column=1)

textgyeranppang=Entry(snacksFrame, font=('arial', 12,'bold'),bd=7, width=6, state=DISABLED, textvariable=e_gyeranppang)
textgyeranppang.grid(row=10, column=1)

#Cost Label & Entry Fields
labelCostofFood=Label(costFrame,text='Cost of Foods', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelCostofFood.grid(row=0, column=0,sticky=W)

textCostofFood=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=costoffoodvar)
textCostofFood.grid(row=0,column=1,padx=35)

labelCostofDrink=Label(costFrame,text='Cost of Drink', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelCostofDrink.grid(row=1, column=0,sticky=W)

textCostofDrink=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=costofdrinkvar)
textCostofDrink.grid(row=1,column=1,padx=35)

labelCostofSnack=Label(costFrame,text='Cost of Snack', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelCostofSnack.grid(row=2, column=0,sticky=W)

textCostofSnack=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=costofsnackvar)
textCostofSnack.grid(row=2,column=1,padx=35)

labelSubTotal=Label(costFrame,text='Sub Total', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelSubTotal.grid(row=0, column=2,sticky=W)

textSubTotal=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=subtotalvar)
textSubTotal.grid(row=0,column=3,padx=35)

labelServiceTax=Label(costFrame,text='Service Tax', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelServiceTax.grid(row=1, column=2,sticky=W)

textServiceTax=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=servicetaxvar)
textServiceTax.grid(row=1,column=3,padx=35)

labelTotalCost=Label(costFrame,text='Total Cost', font=('arial', 15,'bold'), bg='ivory', fg='sienna')
labelTotalCost.grid(row=2, column=2,sticky=W)

textTotalCost=Entry(costFrame,font=('arial',15,'bold'),bd=6, width=15,state='readonly',textvariable=totalcostvar)
textTotalCost.grid(row=2,column=3,padx=35)

#Button
buttonTotal=Button(buttonFrame, text='Total', font=('arial',16,'bold'),fg='sienna',bg='ivory',bd=5,
                   command=totalcost)
buttonTotal.grid(row=0,column=0)

buttonReceipt=Button(buttonFrame, text='Receipt', font=('arial',16,'bold'),fg='sienna',bg='ivory',bd=5,
                     command=receipt)
buttonReceipt.grid(row=0,column=1)

buttonSave=Button(buttonFrame, text='Save', font=('arial',16,'bold'),fg='sienna',bg='ivory',bd=5,
                  command=save)
buttonSave.grid(row=0,column=2)

buttonReset=Button(buttonFrame, text='Reset', font=('arial',16,'bold'),fg='sienna',bg='ivory',bd=5,padx=5,
                   command=reset)
buttonReset.grid(row=0,column=4)

#Text Area for Receipt
textReceipt=Text(receiptFrame, font=('arial',13,'bold'),bd=3, width=45,height=14)
textReceipt.grid(row=0,column=0)

#Calculator
operator='' #7+9
def buttonClick(numbers): #7
    global operator
    operator=operator+numbers
    calculatorField.delete(0,END)
    calculatorField.insert(END,operator)

def clear():
    global operator
    operator=''
    calculatorField.delete(0,END)

def answer():
    global operator
    result=str(eval(operator))
    calculatorField.delete(0,END)
    calculatorField.insert(0,result)
    operator=''

calculatorField=Entry(calculatorFrame,font=('arial',16,'bold'),width=34,bd=4)
calculatorField.grid(row=0,column=0,columnspan=4)

button7=Button(calculatorFrame,text='7', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('7'))
button7.grid(row=1,column=0)

button8=Button(calculatorFrame,text='8', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('8'))
button8.grid(row=1,column=1)

button9=Button(calculatorFrame,text='9', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('9'))
button9.grid(row=1,column=2)

buttonPlus=Button(calculatorFrame,text='+', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('+'))
buttonPlus.grid(row=1,column=3)

button4=Button(calculatorFrame,text='4', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('4'))
button4.grid(row=2,column=0)

button5=Button(calculatorFrame,text='5', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('5'))
button5.grid(row=2,column=1)

button6=Button(calculatorFrame,text='6', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('6'))
button6.grid(row=2,column=2)

buttonMinus=Button(calculatorFrame,text='-', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('-'))
buttonMinus.grid(row=2,column=3)

button1=Button(calculatorFrame,text='1', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('1'))
button1.grid(row=3,column=0)

button2=Button(calculatorFrame,text='2', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('2'))
button2.grid(row=3,column=1)

button3=Button(calculatorFrame,text='3', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('3'))
button3.grid(row=3,column=2)

buttonMulti=Button(calculatorFrame,text='*', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('*'))
buttonMulti.grid(row=3,column=3)

buttonAns=Button(calculatorFrame,text='Ans', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=answer)
buttonAns.grid(row=4,column=0)

buttonClear=Button(calculatorFrame,text='Clear', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=clear)
buttonClear.grid(row=4,column=1)

button0=Button(calculatorFrame,text='0', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('0'))
button0.grid(row=4,column=2)

buttonDiv=Button(calculatorFrame,text='/', font=('arial',16,'bold'),fg='ivory',bg='orangered',bd=6,width=7,command=lambda:buttonClick('/'))
buttonDiv.grid(row=4,column=3)







window.mainloop()



