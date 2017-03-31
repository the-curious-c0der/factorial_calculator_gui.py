# factorial_calculator_gui.py
#Calculator factorial of any number on GUI 
#created by utkarsh


#! /usr/bin/python
from Tkinter import *

def clear_all():
    """clears all the content in the Entry widget"""
    display.delete(0, END)

def fact():
	a = display.get()
	x = int (a)
	y = x
	for i in range(x):
		if i > 0 :
			y = y*(x-i)
	clear_all()
	display.insert(0,y)
	
j =0	

window = Tk()

window.title("FACTORIAL CALCULATOR")

window.geometry("300x300")
"""
a = Label(window, text = "Calculate the factorial")
a.grid(row = 1)
"""
display = Entry(window)
display.grid( row = 1)

def get_variables(num):
    """Gets the user input for operands and puts it inside the entry widget"""
    global j
    display.insert(j, num)
    j += 1
	



one = Button(window, text = "1", command = lambda : get_variables(1), font=("Calibri", 12))
one.grid(row = 2, column = 0)
two = Button(window, text = "2", command = lambda : get_variables(2), font=("Calibri", 12))
two.grid(row = 2, column = 1)
three = Button(window, text = "3", command = lambda : get_variables(3), font=("Calibri", 12))
three.grid(row = 2, column = 2)

four = Button(window, text = "4", command = lambda : get_variables(4), font=("Calibri", 12))
four.grid(row = 3 , column = 0)
five = Button(window, text = "5", command = lambda : get_variables(5), font=("Calibri", 12))
five.grid(row = 3, column = 1)
six = Button(window, text = "6", command = lambda : get_variables(6), font=("Calibri", 12))
six.grid(row = 3, column = 2)

seven = Button(window, text = "7", command = lambda : get_variables(7), font=("Calibri", 12))
seven.grid(row = 4, column = 0)
eight = Button(window, text = "8", command = lambda : get_variables(8), font=("Calibri", 12))
eight.grid(row = 4, column = 1)
nine = Button(window , text = "9", command = lambda : get_variables(9), font=("Calibri", 12))
nine.grid(row = 4, column = 2)


CLR = Button(window, text = "CLR", font=("Calibri", 12), command = clear_all)
CLR.grid(row = 5, column =2 )


result = Button(window, text = "!", font=("Calibri", 12), command = fact)
result.grid(row = 5, column =1)


window.mainloop()
