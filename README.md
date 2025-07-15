# LV-Data
Open Source Data Collection for Creating a realistic low voltage grid and compare applications

## Data Description: 
### General 
#### base load:  
time series from source [1], phase aggregated active and reactive power in 1 min resolution 
#### ev_charge: 
time series simulated based on the load profile generator defined in [2]. Phase aggregated active power in 1 min resolution. Reactive power is set to 0 based on [2].
#### heat pumps: 
time series from source [3], phase aggregated active and reactive power in 1 min resolution 
#### pv_infeed: 
simulated PV Generation based on the global Radiation from data source [4]. Simulation is based on the PYTHON-tool pv_sim.py 

### Scenarios 
Depending on the year, we want to analyse, the data can be plugged together differently. E.g. for the year 2037, 
and grid Connection Point i, we take the base load time series gcp_i.pickle. If based on the following Scenarios
at bus i there is a heat pump, an EV or a PV System, the corresponding files contain a pickle file hp_i.pickle, 
charge_i.pickle or pv_i.pickle. Thease datasets - if they exist - have to be added to the base load file gcp_i.pickle. 
The following Scenarios are used based on [5]
#### PV: 
**2025**: 15 % (9 / 56) of all Connection Points include a PV-System that has a installed power sampled by a normal Distribution with mean 10 kWp and Standard Deviation of 3 kWp (no negatives allowed!). The orientation and Roof slope is also sampled random out of a realistic value range (see pv_sim.py)

**2037**: 51 % (29 / 56) of all Connection Points include a PV-System that has a installed power sampled by a normal Distribution with mean 10 kWp and Standard Deviation of 3 kWp (no negatives allowed!). The orientation and Roof slope is also sampled random out of a realistic value range (see pv_sim.py). PV-Systems that existed in 2025 are assumed to exist still in 2037. 

**2045**: 59 % (33 / 56) of all Connection Points include a PV-System that has a installed power sampled by a normal Distribution with mean 10 kWp and Standard Deviation of 3 kWp (no negatives allowed!). The orientation and Roof slope is also sampled random out of a realistic value range (see pv_sim.py). PV-Systems that existed in 2025 and in 2037 are assumed to exist still in 2045.
#### Heat Pumps: 
**2025**: 3% (2 / 56) of all Connection Points include a heat pump. If a heat pump exists, a random but unique profile from data source [3] is assinged to the Connection Point. 

**2037**: 20% (11 / 56) of all Connection Points include a heat pump. If a heat pump exists, a random but unique profile from data source [3] is assinged to the Connection Point. Heat pumps that existed in 2025 are assumed to exist still in 2037. 

**2045**: 30% (17 / 56) of all Connection Points include a heat pump. If a heat pump exists, a random but unique profile from data source [3] is assinged to the Connection Point. Heat pumps that existed in 2025 and in 2037 are assumed to exist still in 2045. 
#### EV: 
**2025**: 3% (2 / 56) of all Connection Points include an EV. If an EV exists, a random but unique profile from data source [4] is assinged to the Connection Point. 

**2037**: 63% (36 / 56) of all Connection Points include an EV. If an EV exists, a random but unique profile from data source [4] is assinged to the Connection Point. EVs that existed in 2025 are assumed to exist still in 2037. 

**2045**: 75% (42 / 56) of all Connection Points include an EV. If an EV exists, a random but unique profile from data source [4] is assinged to the Connection Point. EVs that existed in 2025 and in 2037 are assumed to exist still in 2045. 

### References 
[1] Tjaden, Tjarko, et al. "Repräsentative elektrische Lastprofile für Wohngebäude in Deutschland auf 1-sekündiger Datenbasis." Hochschule für Technik und Wirtschaft HTW Berlin (2015): 151.

[2] Kreutmayr, Simon. Elektromobilität in städtischen Nieder- und Mittelspannungsnetzen. PhD diss., Technical University of Munich, 2023.

[3] Schlemminger, Marlon, et al. "Dataset on electrical single-family house and heat pump load profiles in Germany." Scientific data 9.1 (2022): 56. 

[4] https://www.dwd.de/DE/klimaumwelt/cdc/cdc_node.html 

[5] Bundesnetzagentur, "Genehmigung des Szenariorahmens 2025-2037/2045” (Publisher, 2025). 

