# Hardware-Based OTP Generator and Verification System (Logisim)

## Overview

This project implements a complete hardware-based One-Time Password (OTP) generation and verification system using Logisim. The design uses a 16-bit Linear Feedback Shift Register (LFSR) to generate pseudo-random values and a comparator-based verification circuit to authenticate user input. The OTP is displayed through seven-segment displays, and the system operates entirely through digital logic components without any microcontroller or software support.

This project demonstrates how secure authentication principles can be implemented at the hardware level using only combinational and sequential logic.

## Features

- Hardware-based 4-digit pseudo-random OTP generation
- LFSR implementation for randomness
- Seven-segment display output
- User input control with increment buttons
- Stable input storage using D flip-flops
- OTP validation using comparator and logic gates
- Visual status indicators for success or failure

## System Architecture

### 1. OTP Generator

The OTP generator consists of:

- Four independent 4-bit LFSR sub-circuits
- A global clock distribution bus
- A reset/start control to initialize states
- BCD-to-seven-segment decoders for display

Each LFSR sub-circuit generates a 4-bit pseudo-random value, resulting in a 4-digit OTP displayed on seven-segment modules.

### 2. OTP Verification Circuit

The verification module includes:

- Increment buttons for four-digit user input
- D flip-flops to hold the entered digits
- Comparator blocks to match each digit with the generated OTP
- A 4-input AND gate to confirm full-match authentication

Upon pressing the submit button, the system checks whether all digits match the generated OTP.

### 3. Indicator System

- **Green LED**: OTP matched successfully
- **Red LED**: OTP not submitted or incorrect

## How the System Works

1. Enable clock ticks in Logisim: `Simulate → Tick Enabled`
2. Press the **Reset** button until the OTP displayed is no longer `0000`
3. Observe the generated 4-digit OTP on the seven-segment displays
4. Use the input buttons to manually enter the same digits
5. Press the **Submit** button to validate the OTP
6. Check the status indicator:
   - **Green LED** indicates a correct OTP
   - **Red LED** indicates incorrect or unsubmitted OTP

## Components Used

- D Flip-Flops
- XOR Gates
- Multiplexers
- Binary Comparators
- AND Gates
- BCD to 7-Segment Decoders
- Seven-Segment Displays
- Push Buttons (Reset, Increment, Submit)
- LEDs (Green and Red status indicators)

## Results

- The system reliably generates new pseudo-random OTPs on resets or clock cycles
- User-entered OTPs are validated accurately
- LFSR ensures efficient and lightweight randomness generation
- All modules function consistently in Logisim simulation

## Advantages

- Entirely hardware-driven (no microcontroller required)
- Low-cost and simple digital components
- Real-time OTP generation and checking
- Demonstrates practical use of LFSR-based randomness

## Limitations

- LFSR-generated sequences can repeat due to deterministic behavior
- No time-based OTP expiration
- OTP length fixed at 4 digits
- Manual input process is slower compared to automated systems

## Future Improvements

- [ ] Add timer-based automatic OTP refresh
- [ ] Use seed-based initialization for improved randomness
- [ ] Expand OTP length for stronger security
- [ ] Implement lockout mechanisms after repeated failures
- [ ] Integrate with microcontrollers or communication modules for external validation

## Conclusion

This project demonstrates how secure authentication logic can be implemented solely through digital hardware. By using LFSR-based pseudo-random sequence generation and comparator-based validation, the system successfully delivers a complete OTP generation and verification mechanism in Logisim. Such hardware security designs can be applied in embedded systems, digital locks, and low-power IoT devices.

## License

This project is open source and available under the [MIT License](LICENSE).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Author

[Your Name]

## Acknowledgments

- Built with [Logisim](http://www.cburch.com/logisim/)
- Inspired by hardware security principles and digital logic design
