# microbit project

#This is to minimise crowd in quiet places (eg libraries) so that the noise level/ the number of people can be maintained(covid19)
#This is my code for the first microbit

from microbit import *
import music
import radio


radio.on()
number = 0
while True:

  if button_a.was_pressed():
    music.play('F')
    number = number + 1
    display.scroll(str(number))
    
  if button_b.was_pressed():
    music.play('C')
    number = number - 1
    display.scroll(str(number))
    
  if number > 150:
    display.show(Image.NO)
    
  #sending
  radio.send(str(number))
  
  #receiving
  message = radio.receive()
  if message:
    display.scroll(message)

#this is my code for the second microbit

from microbit import *
import music
import radio


radio.on()
number = 0
while True:
  if button_a.was_pressed():
    music.play('F')
    number = number + 1
    display.scroll(str(number))
  if button_b.was_pressed():
    music.play('C')
    number = number - 1
    display.scroll(str(number))
  if number > 150:
    display.show(Image.NO)
    
  #sending
  radio.send(str(number))
  
  #receiving
  message = radio.receive()
  if message:
    display.scroll(message)
