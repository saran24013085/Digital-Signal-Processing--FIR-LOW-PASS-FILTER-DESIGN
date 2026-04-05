# Digital-Signal-Processing--FIR-LOW-PASS-FILTER-DESIGN
## AIM:
To generate design of low pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Low Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
clc; % clear screen
clear all; % clear workspace
close all; % close all figures

wc = input('Enter the value of cut off frequency (in radians): ');
N  = input('Enter the value of filter length: ');

alpha = (N-1)/2;
eps = 0.001;

% Low Pass Filter Coefficient (Ideal Impulse Response)
n = 0:1:N-1;
hd = sin(wc*(n - alpha + eps)) ./ (pi*(n - alpha + eps));

% Bartlett Window (Triangular Window)
n = 0:1:N-1;
wb = 1 - abs((n - alpha)/alpha);

% Apply Window
hn = hd .* wb;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot
plot(w/pi, abs(h), 'm', 'LineWidth', 2);
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('Magnitude');
title('Low Pass Filter using Bartlett Window');
grid on;['' ...
    '[]']
```


## OUTPUT:

<img width="651" height="519" alt="image" src="https://github.com/user-attachments/assets/039b2ca1-79e7-4e36-90cb-8ca19dd846b1" />


## RESULT:

![WhatsApp Image 2026-04-01 at 14 39 34](https://github.com/user-attachments/assets/a5d7e0bc-09a4-496c-a975-dceeccaca40f)

