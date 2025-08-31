# Data-Center-Grid-Connection-Mapping-GIS-ETL
GIS and ETL workflows for data center grid connection mapping

This repository contains a dataset mapping **30 data centers** across Virginia, Pennsylvania, and Ohio.  
The objective was to identify and document key grid connection details for these facilities, including substation proximity and transmission infrastructure.

## Project Objective
- Map 30 data centers (10 per state).  
- Record location, capacity, grid connection points, and transmission details.  
- Identify nearest substations and evaluate potential grid access.  
- Ensure accurate geolocation using satellite imagery.



## Methodology
1. **Site Selection**  
   - Selected 30 facilities using open data sources (DataCenterMap, OpenInfraMap, Google Maps, provider websites).  
   - Removed duplicates and confirmed facilities are operational or planned.

2. **Data Collection**  
   - Extracted MW capacity from spec sheets, press releases, or public datasets (`N/A` where unavailable).  
   - Used **GIS tools** and Google Maps for precise latitude/longitude pinning.  
   - Validated substation and transmission data via **OpenInfraMap and ISO/RTO utility maps**.

3. **Distance & Grid Verification**  
   - Computed straight-line distances to substations using Python (`geopy`) as part of an **ETL workflow**.  
   - Visually verified grid connections with Google Earth satellite imagery.  
   - Classified grid connection evidence as `Yes`, `No`, or `?`.



## Data Dictionary (16 Columns)

1. **Data Center Name** – Official facility name.  
2. **Company / Vendor Name** – Owner or operator.  
3. **Street Address** – Full facility address (if public).  
4. **City** – City or metro location.  
5. **State** – VA, PA, or OH.  
6. **MW Capacity** – Published IT load or rated capacity.  
7. **Latitude** – Decimal coordinate (GIS precision).  
8. **Longitude** – Decimal coordinate (GIS precision).  
9. **ISO/RTO Region** – e.g., PJM.  
10. **Nearest Substation Name** – Utility or map-listed substation.  
11. **Distance to Substation (mi)** – Calculated geodesic distance.  
12. **Transmission Line Name** – If identifiable.  
13. **Transmission Voltage (kV)** – e.g., 138, 230, 500 kV.  
14. **Operator (Line/Substation)** – Utility or transmission company.  
15. **Grid Connection Observed** – `Yes`, `No`, or `?` based on imagery.  
16. **Source Links** – Public references and verification links.  

---

## File Structure
- `DataCenter_Mapping.xlsx` → Main dataset (30 rows × 16 columns).



## Tools & Skills Demonstrated
- **GIS mapping & geolocation validation**  
- **ETL workflow** (extract → transform → load) using Python and Excel  
- **Geospatial distance calculations** with `geopy`  
- **Data cleaning and enrichment** using open-source datasets  
- **Satellite imagery verification** (Google Earth, OpenInfraMap)  



## Notes
- Facilities with missing MW data are marked as `N/A`.  
- Transmission details are estimated if not publicly disclosed.  
- Distances shown are straight-line approximations, not cable routing paths.  



**Prepared by:** Tomiwa Ayanwale 
