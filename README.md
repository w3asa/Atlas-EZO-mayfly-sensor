# Atlas-EZO-mayfly-sensor
Low cost Electrical Conductivity sensor using the Mayfly platform to interface with the Atlas Scientific EZO circuit
Mayfly Setup Proceedure: 
1.	Set RTC to local standard time for consistency.  Note that opening the serial monitor will reset the time unless the rtc.setDateTime(dt) is commented out.
2.	Load the “Atlas EZO setup” code to calibrate the EC probe per the Atlas EZO datasheet.  A two point calibration is recommended using 84µS and 1413µS cal fluids.  Remember to use the value of the fluid at the ambient temperature of the fluid when doing the calibration procedure.  For example if the ambient temperature of the cal fluid is 20ºC then “cal,high, xxxx” should be entered.
3.	The RTD in the Sensorex probe seems to have fairly consistant calibration using the m and b coefficients in the code (float m = -.0927, b = 72.653;).  The accuracy can be checked at two points; typically, an ice bath at 0ºC and warm water at about 40ºC with errors used to correct the coeficients.
4.	Before loading the “EC Monitor” code be sure to set the EZO to continuous update of 2 seconds (“c,2”).  It was found that with a 1 second update some devices would produce a zero reading for unknown reasons.  However, when the update was set to two seconds the problem did not reoccur.
5.	Load the “EC monitor” code with the values of sleepMinutes, FILE_NAME,  and LOGGERNAME set to user preference. 

 
