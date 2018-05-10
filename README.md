# on-global-variables

from Tkinter import *
root = Tk()

def move(event=None):

    global item
    canvas.move(item,10,10)
        
    xpos,_ = canvas.coords(item)
    if xpos > 100:
        item = canvas.create_text(1,1, text='spam', anchor=NW)  
    root.after(100, move)

canvas = Canvas(root, width=100, height=100)
canvas.pack(expand=YES, fill=BOTH)
canvas.bind('<Button-1>', move)

item = canvas.create_text(1,1, text='spam', anchor=NW)

root.mainloop()
