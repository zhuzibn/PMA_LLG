This repository is not maintained, pls refer to new repository "ODE_LLG_integral" for the information of LLG integral (https://github.com/zhuzibn/ODE_LLG_integral.git)

to do list
1. add switch mode (constant current, constant voltage)
2. add area control (rectangular, ellipse)
3. add torque efficiency (multi-reflection)

# PMA_LLG
integrate LLG in PMA materials via RK4 method

parameters
%% dimension
  FL_length=25e-9;FL_width=25*pi*1e-9;FL_thickness=1.4e-9; %free layer geometry [m]
  alpha=0.028;
  P1=0.8;P2=0.3;%[P1:pin layer, P2: free layer]
  kB=1.38e-23;%[J.K-1]
  Ea=56*kB*300;%[J]
  Ms=700; %emu/cm3
initial states
  theta_init=179.9*pi/180;
  mz=cos(theta_init); %0.1 degree tilt.
  m_init=[sqrt(1-mz^2),0,mz];
input current  
  Ie=100e-6;
time step is 1 ps
  t1=3e-9;%s
  num_step=3000;%number of steps
rectangular shape 
  cross_area=FL_length*FL_width*1e-14;%[cm2]
only have Hk (benchmark of Hd, Hext are required)
    hh=hk; %total field
torque efficiency divided by 2
    beta=Je/Jp*b/2;


