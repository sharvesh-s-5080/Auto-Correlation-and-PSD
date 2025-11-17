# Auto-Correlation-and-PSD

### Aim:

Write a program for Autocorrelation anmd PSD of signals in SCILAB and verify Wiener-Khinchin relation.

---

### Apparatus Required:

- Computer with i3 processor
- SCILAB

---

### Theory:

The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function.

$$PSD = S_{xx}(\omega) = FT[R_{xx}(\tau)] = \int_{-\infty}^{\infty} R_{xx} (\tau) e^{-j \omega t} dt$$

$$ACF = R_{xx}(\tau) = l FT [S_{xx}(\omega)] = \frac{1}{2 \pi} \int_{-\infty}^{\infty} S_{xx} (\omega) e^{j \omega t} d \omega$$

---

### Algorithm:

1. Load or Define the Signal: Input uor time-domain signal.
2. Computa Autocorrelation: Calculate the autocorrelation function of the signal.
3. Compute Power Spectral Density (PSD): Estimate the PSD of the signal, either directly using a method like Welch's periodogram or by using the Fourier transform of the autocorrelation.
4. Plot Results: Visualize the autocorrelation function and PSD.

---

### Procedure:

- Refer Algorithms and write code for the experiment.
- Open SCILAB in System.
- Type your code in New Editor.
- Save the file.
- Execute the code.
- If any error, correct it in code and execute again.
- Verify the generated waveform using Tabulation and Model Waveform.

---

### Program:

```sci
function fx = pdfx(u)
    z = 9*(1+u)^2;
    fx = u*z;
endfunction
a = 0;
b = 1;
EX = intg(a, b, pdfx);
function fy = pdfy(v)
    z = 9*(1+v)^2;
    fy = v*z;
endfunction
EY = intg(a, b, pdfy);

disp("1)Mean of X =");
disp(EX);

disp("2)Mean of Y =");
disp(EY);

function p = f1(u)
    q = 5*(1-u)^2;
    p = u^2 * q;
endfunction

a = 0;
b = 1;

EX2 = intg(a, b, f1);

function r = f2(v)
    s = 10*(1+v)^2;
    r = v^2 * s;
endfunction

EY2 = intg(a, b, f2);

vX2 = EX2 - (EX)^2;
vY2 = EY2 - (EY)^2;

disp("3) Variance of X =");
disp(vX2);

disp("4)Variance of Y =");
disp(vY2);

x= input("type in the reference sequence=");
y= input("type in the second sequence=");
S1=max(size(y))-1;
S2=max(size(x))-1;
r=corr(x,y,S1);
plot2d3('gnn',r);

```

---

### Output:

<img width="1919" height="1022" alt="Screenshot 2025-11-18 045939" src="https://github.com/user-attachments/assets/61f5051a-65b2-4ae6-84e5-74edf759b614" />


---

### Result:

Thus the Autocorrelation and PSD are executed in Scilab and output is verified.
