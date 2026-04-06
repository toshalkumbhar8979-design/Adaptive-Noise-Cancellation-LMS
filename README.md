# Adaptive-Noise-Cancellation-LMS

## 📈 Mathematical Verification & Analysis
To validate the effectiveness of the LMS Adaptive Filter, we perform a manual step-by-step calculation of the SNR improvements based on the processed results.

### **Step 1: Calculating the "Before" State**
In this stage, the "Noise" represents the high-power interference (glass breaking) mixed with the clean voice signal.

**Given Powers:**
* $P_{signal} = 0.000339$
* $P_{noise} = 0.000693$

**The Power Ratio:**
$$\frac{P_{signal}}{P_{noise}} = \frac{0.000339}{0.000693} \approx 0.489$$

**The Decibel Conversion:**
$$SNR_{before} = 10 \cdot \log_{10}(0.489) \approx \mathbf{-3.10 \ dB}$$

> **Note:** A negative SNR indicates that the noise power was initially stronger than the voice signal.

---

### **Step 2: Calculating the "After" State**
After the LMS filter converges, the "Noise" is defined as the **Residual Error**—the leftover interference the filter could not fully cancel.

**Given Powers:**
* $P_{signal} = 0.000339$
* $P_{residual\_noise} = 0.000267$

**The Power Ratio:**
$$\frac{P_{signal}}{P_{residual\_noise}} = \frac{0.000339}{0.000267} \approx 1.269$$

**The Decibel Conversion:**
$$SNR_{after} = 10 \cdot \log_{10}(1.269) \approx \mathbf{1.04 \ dB}$$

> **Note:** The SNR is now positive, confirming the voice signal is now stronger than the residual noise.

---

### **Step 3: Calculating Total Improvement ($\Delta SNR$)**
The system performance is measured by the total gain in signal clarity:

$$\Delta SNR = SNR_{after} - SNR_{before}$$

$$\Delta SNR = 1.04 \ dB - (-3.10 \ dB)$$

$$\Delta SNR = \mathbf{4.14 \ dB}$$
