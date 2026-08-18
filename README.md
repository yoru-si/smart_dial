# Smart Dial
## Phase - 1
Need to make a smart knob for my mirror light and desk lamp. Very annoying to control through app each time. Commerical knobs are kinda pricey. Will be a learning experience if I build one on my own. Let's see how cheap I can make it for, or will have to end up buying one? Maybe not, let's just build it.

#### What do we need?
Adjust brightness for multiple lights from the comfort of your table. A display of which light you're adjusting will also be helpful. A mode for switching on for certain ambience will be good. 
Extras:
Focus mode, spotify widget, timer, display control, audio control, video seeking.

### Existing Solutions:
- [Link 1](https://youtu.be/nZa-Vqu-_fU?si=lMTd3ZH6neU1eF7T)
- [Haptic Feedback link](https://github.com/scottbez1/smartknob)
- [Commercial](https://www.robbshop.nl/aqara-touchscreen-dial-v1)


### Concept:
We have a display showing the light in question, the media, the timer and the widget or wtv on top. Surrounding it is the dial/knob that changes the value. This dial is either changed through an offset gear or if budget permits: a [hollow encoder](https://nl.mouser.com/en/ProductDetail/Bourns/PER561-P115-N0015?qs=IS%252B4QmGtzzrAUR9c1BGEfg%3D%3D). 

The switch on the encoder (initial prototype) will be a means of confirming a choice, while the dial acts as a medium to browse. The different applications or settings are considered a mode. To enter a mode, you press down the screen once. To exit, you press down twice within a timeframe. To choose between modes, you scroll the dial.

Mechanically, there are some challenges, but it's pretty simple and will be done over due time. Software... well this will take some time, but we live in the age of AI and I have a good coder friend, so not much of a problem.


### Prototype:
	
##### Components needed:
- ESP32-C3 SuperMini Plus Development Board -Soldered Headers
- 1.28 inch Round IPS-TFT Display - 240*240 pixels - SPI - GC9A01 - 3.3V
- BH1750 16bit Digital I2C Light Sensor Module
- DFRobot Fermion EC11 Rotary Encoder Module


- **ESP32-C3 `GPIO 6`** $\rightarrow$ **Encoder Phase A (CLK)**
    
- **ESP32-C3 `GPIO 5`** $\rightarrow$ **Encoder Phase B (DT)**
    
- **ESP32-C3 `GPIO 4`** $\rightarrow$ **Encoder Switch (SW)**





Freed up boot strapping pins cuz I'm not sure if certain pull ups can alter the state during every boot of the device. Also set CS pin of display at GND cuz there is only one SPI interface device which needs to be toggled.


Bill of materials for the prototype:

| Product Name                                                           | SKU    | Quantity | Unit Price | Total Price |
| :--------------------------------------------------------------------- | :----- | :------- | :--------- | :---------- |
| ESP32-C3 SuperMini Plus Development Board - Soldered Headers           | 007206 | 1        | €5.00      | €5.00       |
| DFRobot Fermion EC11 Rotary Encoder Module                             | 006241 | 1        | €3.50      | €3.50       |
| 1.28 inch Round IPS-TFT Display - 240*240 pixels - SPI - GC9A01 - 3.3V | 005282 | 1        | €7.00      | €7.00       |
| BH1750 16bit Digital I2C Light Sensor Module                           | 000193 | 1        | €3.50      | €3.50       |
| 40 Pins header Male                                                    | 000160 | 1        | €0.40      | €0.40       |
| Breadboard 400 points                                                  | 000070 | 1        | €2.25      | €2.25       |
| DuPont Jumper wire Male-Female 10cm 10 wires                           | 000542 | 2        | €0.50      | €1.00       |
| DuPont Jumper wire Male-Male 10cm 10 wires                             | 000544 | 2        | €0.50      | €1.00       |
|                                                                        |        |          | Sub-total  | €19.55      |
|                                                                        |        |          | Delivery   | €4.09       |
|                                                                        |        |          | VAT        | €4.96       |
|                                                                        |        |          | Total      | €28.60      |
