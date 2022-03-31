# Wave Intensity Data

This repository contains the data used in the paper 'Wave intensity analysis combined with machine learning can detect impaired stroke volume in simulations of heart failure' [1].

It contains the complete .csv files of the wave intensity metrics (the S, R and D wave intensities [cm^2/s^3] and energies [cm^2/s^2], the reflection coefficient and the SD delay [s]) and the training and test sets used for the machine learning.

It also contains the simulated waveforms for the three arteries used in the study in the .txt files, as well as the Nektar++ [2] input files required to reproduce the simulations. The simulations were initially conducted for three seconds (long enough for the wave intensity waveforms to converge) to permit some preliminary analysis and restarted for five seconds to allow the other waveforms (particularly pressure, area and wave speed) time to converge, which is why the waveforms lose their smoothness at three seconds. To reproduce the exact waveforms provided here, run these commands (Unix):

```
PulseWaveSolver model_3.xml     # runs the first three seconds and produces the given model_3.fld file
cp model_3.fld model.rst        # renames to produce the given model.rst file
PulseWaveSolver model_rst.xml   # restarts the simulation for another five seconds
```

The following command can be used to produce data without the loss of smoothness at three seconds:

```
PulseWaveSolver model.xml       # runs the simulation for the full eight seconds
```

Please cite both [1] and [2] if you use this data for further analysis.

[1] Reavette RM, Sherwin SJ, Tang MX, Weinberg PD. Wave Intensity Analysis Combined With Machine Learning can Detect Impaired Stroke Volume in Simulations of Heart Failure. Front Bioeng Biotechnol. 2021 Dec 24;9:737055. doi: 10.3389/fbioe.2021.737055. PMID: 35004634; PMCID: PMC8740183.

[2] Cantwell CD, Moxey D, Comerford A, Bolis A, Rocco G, Mengaldo G, De Grazia D, Yakovlev S, Lombard JE, Ekelschot D, Jordi B, Xu H, Mohamied Y, and Sherwin SJ. Nektar++: An open-source spectral/hp element framework. Comput. Phys. Commun. 192:205–219, 2015.
