# 287_project_synthesizer


This is the README page, please notify that the copyright is reserved for <xuh14@miamioh.edu> <xud4@miamioh.edu>[2018]. If you have any question, this email address is available. 


i2c files in WM8931 and PS/2 interface are adaptive from the following provider. Please notify that they have reserved the right, and thanks to their good work!

Scott Larson https://www.digikey.com/eewiki/pages/viewpage.action?pageId=28278929
AntonZero https://github.com/AntonZero/WM8731-Audio-codec-on-DE10Standard-FPGA-board



Description:

The project is a music synthesizer that essentially detects a button press on the keyboard and then outputs a self-generated sound stored in the settings. The project is based on Quartus development environment and is coded via VHDL.

Different keys pressed will resulte into different key tone being played, (asdfghj correspondes to ABCDEFG)
The output sound is selected by sw(9) and sw(10), "00" will output pure sine wave, "01" will output square wave and "10" will output sawtooth wave.

The tone of the sound is generated by passing the selected clock to the wave generater and in order to move to the note in higher band, a two time faster clock will be passed and vice versa. As a result, key range for this project is from C1 to C9.

Mute and volume up & down function is provided, to initialize the synthesizer, an order to sw has to be pressed.
The order followed by, sw6 high, sw0 high, sw1 high, sw2 high, sw3 high, then if sw5 is highed, sound will be mute, a led will also led up indicating the process. with switch 01236 high, press button3 will lower the volume, while button4 will increase the volume.

To reach to lower or higher band of the sound, press button1 or button2. LEDs will light up to indicate the selected band.




Warning:

The project is still a going on progress. Several issues have been reported with regard of its functionality and difference with the actual conmertial music synthesizer.

1. Tone is not decimal precision. Move into higher band will result into more tone deviation of the original sound.
2. sound sample is only 8-bit in width, this results into distortion when moving into lower frequencies. It can be dealed partially by edit the prescaler value in the aud_gen file. 
3. sound is sometimes came out delayed


