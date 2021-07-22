# -Two-Phase-Space-Vector-Modulation-for-three-leg-inverter-driving-two-phase-induction-motor


Single phase induction motor has one coli and squirrel cage rotor. When stator is fed from single phase supply a magnetic field build up but it does not rotate like in three phase motor, rather it becomes pulsating magnetic field as ac supply is given. For this pulsating magnetic field, transformer action occurs in short circuited cage rotor bar and a rotor magnetic field build up according to Lenz’s law having opposite direction to stator magnetic field, so there is no net torque between this two field and as a result motor don’t have any starting torque.
However when the motor starts, a torque builds up. It can be explained using double revolving field theory and cross field theory.

### Double revolving field theory:
In double revolving field theory the pulsating magnetic field can be imagined with the help of two vector rotating in opposite direction to each other.
Torque speed curve for clockwise and counterclockwise direction is added to find out the net torque. And at speed=0 there is no torque.

### Cross Field Theory:
Let’s assume the motor has been started by any means.
The region of rotor below the stator coil have maximum induced voltage .But as rotor has inductive impedance its current will lag voltage by around 90 degree. And rotor current will create rotors magnetic field. This created magnetic field of rotor has angular displacement of around 90 degree from stators magnetic field. Now this two cross fields vector addition will create net magnetic field and surprisingly the net magnetic field is rotating.


## My thinking:
To operate a induction motor rotating magnetic field is needed. In single phase IM main winding produce flux which is varying sinusoidal fashion in one axis. So to produce a rotating field we at least need another axis where there will be also a sinusoidal flux. The engineering solve of this problem arises use a coil which is spatially situated 90 from main winding, it is called auxiliary winding. So two flux`s position in space is 90 from each other. But there needs a 90 electrical phase difference between the  sinusoidally varying fluxes. We know flux is directly related with current. So in auxiliary winding there should be a current 90 degree phase displaced with main winding. To achieve this a capacitor is added in auxiliary winding. Both winding are fed from a single supply. In phase diagram, main winding`s inductive impedance will cause current to lag voltage by some degree, in auxiliary winding capacitor is chosen  so that it`s impedance will be higher than inductive impedance of auxiliary coil and current will lead supply voltage to a degree that  will make 90 degree angle with main windings current.


## Problem: 
To achieve a VFD in single phase permanent split capacitor induction motor there is a pblm. The problem is when frequency is changed of supply voltage, capacitor`s impedance will  change and that will cause phase difference between main and auxiliary coil not 90 degree .
Using Two phase supply and two phase machine:
If we remove capacitor from auxiliary winding and connect it with another supply voltage we can use it to VFD. But problem is in auxiliary winding`s coil`s turn is not equal with main winding. So asymmetry will occur. To overcome we can redesign the motor with same main and auxiliary winding


## Reading of papers:
In [1] author told that square wave with quadrature phase shift can be given to two phase machine using inverter, this process is simple but speed control range is limited and has higher harmonic distortion.
Author proposed space vector modulation for two phase symmetrical asynchronous induction machine to create a rotating magnetic field. Two coil of induction machine has same number of turn and spatially separated by 90 degree. 
Author showed that two legged full bridge 4 switched inverter can produce 90 degree phase shifted wave for two phase induction motor, but then there is 2 capacitor is needed with two resistor connected parallel to them. Thus system will be lossy . Moreover in low speed operation there will be more ripple in output due to uneven discharging of capacitors. Besides both capacitors should be rated for DC link voltage so system cost will be high. Also maximum output voltage from this method is Vdc/2.
Author generate two phase 90 degree phase displaced sinusoid by three legged 6 switched inverter. Two leg is connected with main and auxiliary winding and other leg is connected to neutral point. Now there is two zero vector and 6 active vector. Those vectors divide voltage space in 6 sectors but unlike 3 phase space vector modulation those sectors are not divided symmetrically. Rather they form hexagonal shape. Fig 1 and 2 shows connection of 4 legged and 6 legged inverter with two phase induction motor. Fig 3 shows position of active vectors and unsymmetrical sectors formed in two phase system. Table 1 shows voltage in each phase of IM for different vectors. 



![topology using 4 switches](https://user-images.githubusercontent.com/35787202/126685452-d70525dd-17e0-4e9a-a7b1-84e828606262.png)
Fig 1: Topology Using 4 switches

![6 switch](https://user-images.githubusercontent.com/35787202/126685715-1ec94cce-f752-4e56-b934-f3fcb84f3023.png)
Fig 2: Topology Using 6 switches

![active vector](https://user-images.githubusercontent.com/35787202/126685773-dea4f074-ff8c-4b28-ba1c-a32421da5b17.png)
Fig 3: Position of active vectors

<img width="486" alt="table" src="https://user-images.githubusercontent.com/35787202/126685911-073964ed-4122-442e-b40f-289e78e3180a.PNG">

Each sector has two adjacent vectors. One vector have one switch on and other vector has two switch on. Those vectors will be called as V1 and V2.Let V1 and V2 have angle 1 and θ2 .

<img width="537" alt="Calculation" src="https://user-images.githubusercontent.com/35787202/126685987-549da3b2-ec3b-4271-9dd4-c36fc980900e.PNG">

<img width="483" alt="table2" src="https://user-images.githubusercontent.com/35787202/126686047-1185da60-b0da-4ce3-bfb0-5b4a56155ca5.PNG">

Here, V1 and V2`s value is in per unit  with base value Vdc. Vref is the maximum fundamental voltage magnitude in per unit, for operation in linear region maximum value for Vref=1/√2 , so maximum voltage from dc link= Vdc/√2 which is greater than 4 leg topology. So, modulation index , m=Vref/( Vdc/√2) . So,V_refmaxL2N=(m*V_dc)/(√2) 

After getting T1,T2 and T0 we can calculate actual duty cycle for upper three leg of inverter. For minimizing switching pattern symmetrical switching method is used. In each  sector  switching  is done in this fashion V0-V1-V2-V7-V2-V1-V0 .Switching pattern is sector 1 is shown in figure 4
![sector 1](https://user-images.githubusercontent.com/35787202/126686143-bd5d5ed4-be00-4a18-a917-eb9e804336f9.png)
Fig 4. Switching pattern in sector 1
From this duty cycle for upper three leg in sector 1 is :
Ta= T1+T2+T0/2
Tb=T0/2
Tc=T2+T0/4
Table 3 shows the duty cycle value in different sectors:
<img width="503" alt="Table 3" src="https://user-images.githubusercontent.com/35787202/126686239-3ed351fd-1d79-4bfe-80ee-c63edcd22c48.PNG">


References:
1.	Space-Vector Modulation in a Two-Phase Induction Motor Drive for Constant-Power Operation
M. A. Jabbar, Senior Member, IEEE, Ashwin M. Khambadkone, Member, IEEE, and Zhang Yanfeng (2004)







