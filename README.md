# 555 Adjustable Delay Timer

[![AB8XjBGvlPY](https://i.imgur.com/5LBU6FJ.png)](https://youtu.be/AB8XjBGvlPY)

The 555 timer IC is an integrated circuit (IC) that is used in a variety of timer, delay, pulse generator and oscillator circuits.
In this tutorial, I am going to show you guys how to make an "Adjustable Delay Timer Circuit" using the 555 timer IC. This circuit can automatically turn on/off any circuit after a fixed duration. This timer circuit is useful when you need to power On/Off any AC Appliances after a pre-defined duration. For example, you can use this circuit to automatically turn off a mobile charger after a certain period of time to avoid over charging, or you can turn on/off a light bulb after a certain period.

The time delay of this circuit can be adjusted by using various combinations of resistors and capacitors.
Watch this video for detailed step by step instructions on how to build this circuit and to know how this circuit works.


Components Required
-------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiKOdu3HHDFjeMuTzKj8y4Fz2tAPpZfh8-A-ONsqEPuD93Y3YJ96CyHHT9RfYfmbXQ7FaQuu5EjLbpNcAMyB8crsOWY_1HvQhmSZypJF8TVO_E0qFwbxueHyhPmP0-v2l0eMDKcYBh4icfyqMI-iad8HsJPjrsxngiTq0qzIN-ie1VGy_fPIJhGJ7L2AqA/s1054/5.png)

For this tutorial we need:

	A 555 Timer IC
	A Push Button Switch
	A Red And A Green LED
	2 x 220Ohm Current Limiting Resistors
	1 x 10K Resistor
	A Breadboard and Few Breadboard Connectors
	A 5V Power Supply
	A 470uF Capacitor
	And Few Combinations Of Resistors Or A Potentiometer


555 Timer IC In Monostable Mode
------------------------------- 
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjal2rKLnsFfriIQNVOLhzZRwit6vjs5Jj1tlih8ROyhyv7BnamjKzijCPtVJPW29PCQrCCvtcNPJMJZ4KWrH5ipQpuNJheEmikgnZF7MujMWWWRPIvz2CeXLL3GdyhZ2TlyfQIiOajb8Isv7XT2kk-pUFJwIc8ml58mQH1KpwmMc94F4Ud-IVFoKqmaQA/s1054/6.png)

Lets start by putting all the components together and lets understand how the circuit works.
In the first example, I am going to show you guys the "on-off timer circuit" with a fixed timing Resistor and Capacitor.
The heart of this circuit is the 555 timer IC.
Pin No.1 of the IC is connected to GND.
By connecting Pin 6 and 7 of the 555 timer IC, we put the IC in "Monostable Mode". In Monostable Mode, the output of the IC is stable in "One State", and it will always return to this state after a certain period of time when it gets pushed out of that state.
The output at Pin 3 of the 555 Timer IC in monostable mode is generally LOW - indicated by the green LED. When you trigger the circuit using the push button switch, the output goes HIGH - indicated by the red LED, for a certain period of time before it goes back to its LOW state.
The time the circuit stays HIGH is decided by the value of a resistor R1 and a capacitor C1. The higher the values, the longer it stays HIGH (On).

To adjust the timer duration "on-the-fly", the timing Resistor R1 can be replaced by a Potentiometer. By changing the value of the resistance of the potentiometer we can either increase or decrease the duration of the timer.


Logic Using Circuit Simulation
------------------------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhTbx8ovtR0YovQjdGQOSuEl4p14vOnDQFH7pYzc_z4Vhw0lZmUy7qIUh3lbReSJ1RO0B2KxbGVbULcmIgiQCfTxe79c0hQCPkxVnzwiPz8rNRRl_zI38th4NbWSAcGLarbZyiNpvjjWfEpMLL_6sWxVnn5AWd2wnbmgHUz7a-HlQ1uiKhvpGt1ycNYzso/s1054/7.png)

Alright, now I am going to explain how this circuit works with the help of an animation.

	- When Pin 2 of the IC detects voltage LESS than 1/3rd of the supply voltage, it turns ON the output on Pin3.
	- And, when Pin6 detects voltage MORE than 2/3rds of the supply voltage, it turns OFF the output.
	- Whenever the output of the IC is in OFF state, the Discharge Pin (Pin7) acts as ground, as it is internally grounded.
	
This is how the trigger pin (Pin2) and the threshold pin (Pin6) of the 555 timer IC sense voltages and controls the output at Pin3.

When we power on the circuit, the output is in OFF state. Hence, the discharge pin (Pin7) will be internally grounded discharging the capacitor.

Pressing the push button switch activates the delay timer and the following sequence starts:

	- Trigger Pin (Pin2) gets grounded 
	- Since this applied voltage at Pin2 (0V) is less than 1/3rd of the supply voltage (5V), the output at Pin3 turns ON
	- And at the same time, the Discharge Pin (Pin7) disconnects internally from 0V
	- This causes the capacitor to charge via the resistor or potentiometer
	- Now, the voltage across Pin6 starts increasing
	- As soon as the capacitor charges to 2/3rds of the supply voltage, Pin6 turns OFF the output
	- When the output turns OFF, Pin7 gets internally grounded discharging the capacitor.
	
The above steps are repeated each time you push the push button switch.
The time period for which the capacitor charges from 0V to 2/3rds of supply voltage is the "delay time".


Calculations 
------------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEges9Rb3Ii9F8A4mxiJwyNvPywqenE0DzuSvkAziniQJu81vIm-acelwNMo8KMEBVc9q2Zlp83IQYLw4MVj_pbNcRqUfIgJI74yogXh5S6s3G2Dlo1gK1pGW-4ouakgW7xMRp3YsTzHMKrIADjne5-jSwoIL9tWRqrNt8U4DEmUDDz4oTneNOu97y7PCKU/s1054/8.png)

A discussed earlier, the time period for which the capacitor charges from 0V to 2/3rds of supply voltage is the "delay time".
We can calculate this time using the formula: T = 1.1 * R * C
Where T is the time period in seconds, R is the value of timing resistor in ohms and C is the value of the capacitor in Farad.

In the previous example we used a 33K resistor and 470uF capacitor which gives us a delay period of: 
T = 1.1 * (33000) * (0.000470) = 17 seconds.


The Board
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEib5hsPOzp9oKIjxnROnfnubvh1QQ2-XA3Fj8QPrShhPqyKY38a9ut62nLYng5xwqJAHlfYdFwiRMFMvaK_hvGOb9XTU2U2wpjVG2zsNwQ4uYg7ca8OxIpWihHYRxXhCfOeNW5_Omzwp3fWQZlP3h0Xti96-KhKlSXYTMi6NDzbc4sPbFsYLrtREZ9h62k/s1054/9.png)

To make things easy, I designed a PCB for this setup.
So, this is how my PCB looks like in 2D and 3D.
You can either add a resistance or a potentiometer to the board to control the delay time.

I have created 2 versions of this board:
	V1: Without A Relay Module
	V2: With A Relay Module
 
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhZpDI2YhNUK_GUVpkbL3AtYbvBlOAvmQYs3ZjJcosV2bKLNiHaUvkJdWPPXgRn8EiMdI8McpxcgJHZUrZey5Q64WtDiUKwfzPZxRe3VO6B_Ila23lKTtk9mY7Ij-wTb8nCFvFBItPXxp5HTEwGRfuKAnHPXJ_DXB_jk0t0b9QIDxx5tLyLhxbjS99p8qI/s1054/10.png)

Using the board with the relay module, you can control other DC Circuits or AC Appliances.
For a quick reference, I added the delay period calculator on the board.


Soldering
---------
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgMwyPjqIYjuAi5p8SmjxRzsxmBc2qtr5-5oyM7vTLvu4TV5Shpvd8-lsUDstB2eXoiyyhNg85SZMST_k6X4Bxq2qPQM89iyRZLZdloRlUcuSH1jX7L9wxN36QnYpwip0WaknNjMQtB3VWpcxIMkQBKWcGbSjKky-9T7h-0We8SmrsCh83wkaJ7KrguUmg/s1054/11.png)

Alright, now, lets solder the components to the board.
In this setup, I am going to solder a potentiometer to the board and hence I will leave the resistor bit as is.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiXgzmJREO77AtYMdMNczk0Nz8SD7o3BDmZSdTd6ppjzGoJasJIg16KJVZQvsnuKw82GP4AjCD5SQp32oj8DYqFycyvft-f9f9OcJ9p85b-A59VAaoN8eqepQabTXEEzvLYf2UX8PRjhjVYsaYY5Syv3XqIqgZ_Xe-OchiBPe5qDQyp1_mPHMvt-namueI/s1054/12.png)

So, lets start by soldering all the resistances to the board. 
Then, lets solder the LEDs to the board followed by the Push Button Switch.
After that, lets solder the IC base and the capacitor to the board.
As discussed earlier, instead of the resistor I am soldering a Potentiometer to the board.
To finalize the setup, I am soldering few male pin headers to the board, that's it all done.

The 2nd version of the board with the relay module looks like this.


Demo
----
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjEDPWaLDL39rML13ZpZmUiSBhUyJQXWyVLwswlcJH7WsP9q3C7oRkOBALyW-jWZiFGKfwgqD8q2DDLYmUgUd_iMtTfqYRm7PY07k32x799KmZwxBdLXXkF8xjf_6MpY-nZ34ZdvwTz1NquBQ73pcHoSnaD4Yf794eZvJSVH5L23uh3GaupbqoB9wrdk_o/s1054/15.png)

For the demo purpose, I am going to use the board that has the relay module on it. 
Using this board, I can demo both the operation of the relay and the LEDs.

Lets set the resistance of the potentiometer to a desired value and then lets do the quick math to see how long this circuit will stay on.
Alright, now that we have all the values, lets start the timer on my mobile and press the push button switch both at the same time.............
Bingo, mission accomplished. 
You can use the relay in either NC or NO state in your project.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh7chIu55nX7GguoZnZiRFWP4ngJtVDwocSzPsv8ildah4D47AtfHITd8YgXXSG9v5-AnnfOJMfFWG57j3PNnHW8plSYYy6P9K7KVh0mgpkHIfu26_6rG1zyeXkK7F0mo1lXQOSHs5RV3qXAb3sqwFM3GBcophTte_t4BLmJ229QkE3xSCRJNE27pR_-DU/s1054/16.png)


Uses
----
![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgBUZGz_fO6ugxy9eyUCS0kamKn894G5gqfMFg0ctebvUfYnx6U9vub1sO_riOjdRCgSmhq1TF1vt3SbnKP7DNWGpMKIqLx1M5g7pAIypOpgPVBi2J2NsAjvFU6UniglFu570jA8Jo8HSsfpustkcJtJhM7Vu7gVPISo3TgGq4nQ9xKynyed9_iceSdrqY/s1054/17.png)

This Delay Timer Circuit can be used as a:

 - Timer for any robotics project
 - Turning off mobile chargers to prevent overcharging
 - Turning On/Off lights automatically after a set duration
 - In Auto power On/Off circuits using Relays and more..

The possibilities are endless..


Thanks
------
[![AB8XjBGvlPY](https://i.imgur.com/5LBU6FJ.png)](https://youtu.be/AB8XjBGvlPY)


Thanks again for checking my post. I hope it helps you.
If you want to support me subscribe to my YouTube Channel: https://www.youtube.com/user/tarantula3

Video: Visit https://youtu.be/AB8XjBGvlPY

Full Blog Post: Visit https://diyfactory007.blogspot.com/2023/11/555-Adjustable-Delay-Timer.html

DIY - Relay Module: Video https://youtu.be/3n69b4sdDjk

Schema: Download https://github.com/tarantula3/555-Adjustable-Delay-Timer/blob/main/8.png

Circuit: Download https://github.com/tarantula3/555-Adjustable-Delay-Timer

Gerber Files: GitHub https://github.com/tarantula3/555-Adjustable-Delay-Timer



**Support My Work:**

BTC:   1Hrr83W2zu2hmDcmYqZMhgPQ71oLj5b7v5

LTC:   LPh69qxUqaHKYuFPJVJsNQjpBHWK7hZ9TZ

DOGE:  DEU2Wz3TK95119HMNZv2kpU7PkWbGNs9K3

ETH:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

BAT:   0x9D9E77cA360b53cD89cc01dC37A5314C0113FFc3

LBC:   bZ8ANEJFsd2MNFfpoxBhtFNPboh7PmD7M2

COS:   bnb136ns6lfw4zs5hg4n85vdthaad7hq5m4gtkgf23 Memo: 572187879

BNB:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

MATIC: 0xD64fb51C74E0206cB6702aB922C765c68B97dCD4


Thanks, ca again in my next tutorial.



Odysee: https://odysee.com/@Arduino:7/555-Adjustable-Delay-On-Off-Timer-Circuit:2

Cos: https://cos.tv/videos/play/48667261956559872

Rumble: https://rumble.com/v3w7p5k-555-adjustable-delay-on-off-timer-circuit.html
