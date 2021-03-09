# Modeling transport through porous electrode
Rosa Zhang, mentored by Anamika Chowdhury & Adam Weber
Lawrence Berkeley National Lab

## Introduction
Degradation in PEMFC catalyst layers is a major barrier to commercialization of fuel cell (FC) vehicles, 
especially due to voltage cycling from vehicle operations. Degradation results in multiple morphological 
effects in the catalyst layer (CL), including:
a.	Reduced Pt surface area (ECSA) due to Pt particle dissolution and coalescence
b.	Alloy metal dissolution in ionomer causing changes in ionomer properties
c.	Carbon support corrosion resulting in thinning and reduced porosity
d.	Ionomer degradation and thinning
e.	Membrane pinhole and crack formation
In this project, we combine the transport at the two different length-scales i.e., the electrode thickness and agglomerate, and study the impact of transport parameters such as agglomerate size, ionomer gas-diffusivity etc. The diffusion and simultaneous reaction in the agglomerate are modeled separately, which feeds into the model for gas-transport through the electrode thickness. The hydrogen anode was chosen as the basis for this model so that oxygen effects from water, oxide, and hydroxide production.

## Objective
This project seeks to develop a computation model to simulate CL operation. Analysis using this model will be performed to understand the magnitude and location of on the aforementioned morphological changes, and their corresponding impact on the operating CL.

## Premise
Gas transport is facilitated by the ionomer film surrounding the carbon agglomerates in the catalyst layer. Hence, this involves transport through multiple phases and length-scales: (i) gas-phase transport through electrode pores at the length scale of electrode thickness (microns), and (ii) diffusion into the agglomerate through an ionomer film at the length scale of agglomerate radius (nanometers).

## Simplistic Model
We began with a derived form of a mole balance relating diffusive transport and reaction within the CL for a steady-state hydrogen anode.
D_CL^eff  (∂^2 c_CL (x))/(∂x^2 )=(a_v∙i(x))/nF
Where D_CL^eff is the effective diffusion coefficient or hydrogen in the catalyst layer, c_CL is the position-dependent concentration of hydrogen in the catalyst layer, n is the moles of electrons generated per mole of hydrogen reacted, F is the Faraday constant, a_v is the effective active surface area of Pt available per volume of CL, and i(x) is the position-dependent electrode current density.
Using the general Butler-Volmer equation without considering diffusion near the agglomerate, one can substitute:
i(x)=i_0∙{〖(c_o (x=0,t))/(c_o^* ) exp〗⁡(αzF/RT η)-(c_r (x=0,t))/(c_r^* )  exp⁡(-αzF/RT η)  }
Where j is electrode current density, j_0 is exchange current density, T is temperature, c_o and c_r are respectively the concentration of hydrogen gas and protons (species to be oxidized and reduced), z is number of electrons involved in the electrode reaction, R is the universal gas constant, and α is the dimensionless anodic charge transfer coefficient. The local overpotential η is expressed as follows:
η=(Φ_1-Φ_2 )-(U_1-U_2 )
η=(E-E_eq )_agglomerate-(E-E_eq )_film
Substituting into the governing equation and solving for C_{CL}(x) gives the following, with stand-in variables of beta and gamma.
C_CL (x)=c_r (0)∙e^(-2β)+(c_in-c_r (0)∙e^(-2β))/e^(-2L√γ)  [e^(-2L√γ) e^(x√γ)+e^(-x√γ) ]
β=αzF/RT η
γ=(a_v i_0)/(nFD_CL^eff ) e^β


Full report:
https://1drv.ms/w/s!AnOlGasVBmjsapGcvZkJTSkahIc
