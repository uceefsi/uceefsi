Hi, I'm currently learing and evaluating the tool in order to simulate an optical path composed of Transceivers, ROADMS, Optical Amplifiers, and fibre accross several nodes. 

I've been learning and using the Docker installation and running the "gnpy-transmission-example", and I must say i'm very impreassed and helpful with the tool.
A lot of potential indeed.  Very good work team.

I'm currently trying to map some additional Optical Amplifiers and adding some more data to create some practial simulations but i'm getting an error when running the script.  A couple of questions if i may please:

1. I'm getting "inf" for the OSNR and SNR of the first Transceiver :( 

    Propagating with input power = 0.00 dBm:
    Transceiver trx Equinix_LD8_DC
    OSNR ASE (0.1nm, dB):      inf                                           
    OSNR ASE (signal bw, dB):  inf                                           
    SNR total (signal bw, dB): inf    

2. I'm using as input Excel file "Inf_Topology_V003.xls" and I've allocated in "amp_type" fields all to be "operator_model_example", but i see the script sometimes uses it, 
and sometimes it doesn't.  Is there any way to force it to use it? 

Below just an extract of the output, but happy to share all the content.  Once again, thank so much and what a great project, good work team !!!

Any comments/suggestions must welcome:

Best Regards,

Fernando Silva
uceefsi@ucl.ac.uk

# gnpy-transmission-example -e eqpt_config.json Inf_Topology_V003.xls "Equinix_LD8_DC" "Telehouse_North_DC"
There are 76 channels propagating
Power mode is set to True
=> it can be modified in eqpt_config.json - Span

There are 5 fiber spans over 156 km between trx Equinix_LD8_DC and trx Telehouse_North_DC

Now propagating between trx Equinix_LD8_DC and trx Telehouse_North_DC:

Propagating with input power = 0.00 dBm:
Transceiver trx Equinix_LD8_DC
  OSNR ASE (0.1nm, dB):      inf                                           "<---- Expecting anything different than "inf"     
  OSNR ASE (signal bw, dB):  inf                                           "<---- Expecting anything different than "inf"     
  SNR total (signal bw, dB): inf                                           "<---- Expecting anything different than "inf"    
  SNR total (0.1nm, dB):     inf                                           "<---- Expecting anything different than "inf"     
  CD (ps/nm):                0.00
  PMD (ps):                  0.00
Roadm roadm Equinix_LD8_DC
  effective loss (dB):  20.00
  pch out (dBm):        -20
Edfa east edfa in Equinix_LD8_DC to BT_Vauxhall
  type_variety:           operator_model_example
  effective gain(dB):     21.00
  (before att_in and before output VOA)
  noise figure (dB):      6.36
  (including att_in)
  pad att_in (dB):        0.00
  Power In (dBm):         -1.19
  Power Out (dBm):        19.82
  Delta_P (dB):           1.0
  target pch (dBm):       1.0
  effective pch (dBm):    1.0
  output VOA (dB):        0.00
Fiber          fiber (Equinix_LD8_DC → BT_Vauxhall)-NC-DW-6907
  type_variety:                SSMF
  length (km):                 70.00
  pad att_in (dB):             0.00
  total loss (dB):             13.97
  (includes conn loss (dB) in: 0.00 out: 0.00)
  (conn loss out includes EOL margin defined in eqpt_config.json)
  pch out (dBm): -12.97
Edfa Edfa0_fiber (Equinix_LD8_DC → BT_Vauxhall)-NC-DW-6907
  type_variety:           std_low_gain                                    <---- I was expecting "operator_model_example" as defined in xls Eqpt topology file.
  effective gain(dB):     12.97
  (before att_in and before output VOA)
  noise figure (dB):      7.08
  (including att_in)
  pad att_in (dB):        0.00
  Power In (dBm):         5.86
  Power Out (dBm):        18.83
  Delta_P (dB):           0
  target pch (dBm):       0.0
  effective pch (dBm):    0.0
  output VOA (dB):        0.00
Roadm roadm BT_Vauxhall
  effective loss (dB):  20.00
  pch out (dBm):        -20
  ....
