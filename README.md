
import js
p5 = js.window
angle = 0.0
rect_x = 150
rect_y = 150


def setup():
    p5.createCanvas(300, 300)   
    p5.rectMode(p5.CENTER)  # set rectangle drawing mode to CENTER

def draw():
    p5.background(255)    
    p5.fill(0)
    p5.text('p5.mouseIsPressed: ' + str(p5.mouseIsPressed), 10, 20)
    p5.text('p5.mouseButton: ' + str(p5.mouseButton), 10, 35)
    p5.fill(255)  # white
    if (p5.mouseIsPressed == True):
        # p5.mouseButton is equal to p5.LEFT with 'left' (or one-figer) click:
        if (p5.mouseButton == p5.LEFT):
            p5.fill(0)  # black
        # p5.mouseButton is equal to p5.RIGHT with 'right' (or two-finger) click:
        elif (p5.mouseButton == p5.RIGHT):
            p5.fill(255, 0, 0)
    if (p5.keyIsPressed):
        # p5.key is equal to the typed character string:
        if (p5.key == 'r') or (p5.key == 'R'):  
            p5.fill(255, 0, 0)  # red
        elif (p5.key == 'g') or (p5.key == 'G'):
            p5.fill(0, 255, 0)  # green
        elif (p5.key == 'b') or (p5.key == 'B'):
            p5.fill(0, 0, 255)  # blue
    
    global rect_x, rect_y
    
    if (p5.keyIsPressed == True): # key has been pressed
        # p5.keyCode is equal to special keys like arrows:
        if (p5.keyCode == p5.LEFT_ARROW):  # left arrow
            rect_x = rect_x - 1
        elif (p5.keyCode == p5.RIGHT_ARROW):  # right arrow
            rect_x = rect_x + 1
        elif (p5.keyCode == p5.UP_ARROW):  # up arrow
            rect_y = rect_y - 1
        elif (p5.keyCode == p5.DOWN_ARROW):  # down arrow
            rect_y = rect_y + 1

    draw_head()
    draw_body()
    
def draw_head():
    #global angle
    #p5.rotate(angle)
    #angle = angle + 0.001
    p5.rect(rect_x,rect_y, 100, 60)
    p5.ellipse(130,100,20,20)
    p5.ellipse(170,100,20,20)
    p5.rect(150,150, 40, 40)

def draw_body():
    p5.rect(150, 180, 120, 80)
    p5.rect(150, 180, 60, 30)
    p5.rect(180, 250, 30, 60)
    p5.rect(120, 250, 30, 60)
    p5.rect(120, 280, 40, 10)
    p5.rect(180, 280, 40, 10)
    p5.fill(p5.mouseY)
    p5.rect(80,180, 20, 60)
    p5.fill(p5.mouseY)
    p5.ellipse(80,p5.mouseX,20,20)
    p5.rect(220, 180, 20, 60)
    p5.fill(p5.mouseY)
    p5.ellipse(220,p5.mouseX,20,20)
