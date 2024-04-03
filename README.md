# SRAM-BIST-DESIGN

Write behavioral verilog descriptions of each component of a 256 x 4b SRAM that has 
a BIST engine operating at speed (same CLK as SRAM) and can test the SRAM with 4 test 
patterns (i) Blanket 0 and 1, (ii) Checkerboard and reverse Checkerboard 
(iii) March C- (iv) March A  
Verify the functionality of your Behavioral RTL with ModelSim simulations followed by 
Synthesis and optimization using GENUS. Assert Timing Constraints of a 50 ns CLK cycle 
time with SDC on CLK as follows: 
create_clock  -period 0.6 -name clk [get_ports clk] 
set_input_delay 0.1 -clock clk [all_inputs] 
set_output_delay 0.15 -clock clk [all_outputs] 
set_load 0.1 [all_outputs] 
set_max_fanout 1 [all_inputs] 
set_fanout_load 8 [all_outputs] 
set_clock_uncertainty .01 [all_clocks ] 
set_clock_latency 0.01 -source [get_ports clk] 
Identify and fix all max (setup) and min(hold) delay timing violations.  Min Delay 
violations using GENUS and Max delay violations by either redesign or increase in cycle 
time of Clock.     
The BIST should ‘self-disable’ when it completes its relevant coverage of address and 
pattern vectors. 
