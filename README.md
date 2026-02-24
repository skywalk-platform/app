# SkyWalk Platform

**Professional Aviation Flight Planning & Performance Analysis**

[![App](https://img.shields.io/badge/App-Live-blue)](https://skywalk-aviation.github.io/app/)
[![Docs](https://img.shields.io/badge/Docs-Available-green)](https://skywalk-aviation.github.io/docs/)
[![License](https://img.shields.io/badge/License-Proprietary-red)](LICENSE)

SkyWalk is a flight planning tool designed for general aviation pilots. It provides real-time runway performance calculations, weight & balance analysis, METAR integration, and aerodrome information management to help pilots make informed go/no-go decisions.

---

## 🚀 Quick Start

**Access the application:** [https://skywalk-aviation.github.io/app/](https://skywalk-aviation.github.io/app/)

**Read the documentation:** [https://skywalk-aviation.github.io/docs/](https://skywalk-aviation.github.io/docs/)

---

## ✨ Key Features

### 🛫 Runway Performance Analysis
- **POH-Based Calculations**: Automatic runway length computation using Pilot Operating Handbook data
- **Multi-Factor Corrections**: Accounts for temperature, altitude, weight, wind, runway surface, slope, and safety margins
- **Dual Distance Modes**: Calculates both threshold and 50ft obstacle clearance distances
- **Real-Time Analysis**: Instant performance updates based on current conditions

### 🌤️ Weather Integration
- **Live METAR Data**: Automatic retrieval from nearby stations
- **TAF Support**: Future weather trend analysis
- **Cloud Ceiling Visualization**: Interactive cloud layer charts with circuit/CTR altitude overlays
- **Wind Envelope Analysis**: Visual assessment of crosswind and headwind limits across variable wind conditions

### ⚖️ Weight & Balance
- **Interactive Charts**: Visual center of gravity plotting against aircraft envelope
- **Multi-Point Validation**: Supports departure, arrival, and custom weight scenarios
- **Real-Time Calculations**: Automatic updates as fuel burn and passenger weights change
- **Compliance Checking**: Instant feedback on envelope limits

### 🗺️ Aerodrome Information
- **Comprehensive Database**: Detailed information for departure and arrival aerodromes
- **Runway Visualization**: SVG-based runway layout diagrams
- **ATC Frequencies**: Tower, ground, approach, radio, and information frequencies
- **Custom Annotations**: User-specific notes and images for each aerodrome
- **Route Planning**: Entry/exit points, altitudes, and circuit patterns

### 📊 Visual Analytics
- **Runway SVG Overlays**: Color-coded runway diagrams based on surface type
- **Performance Plots**: Linear regression models fitted to POH data
- **Weather Visualization**: Cloud coverage and wind component charts
- **Interactive Maps**: Folium-based aerodrome location mapping

---

## 🎯 Use Cases

- **Pre-Flight Planning**: Comprehensive flight briefing with all essential aerodrome and weather data
- **Go/No-Go Decisions**: Data-driven assessment of flight feasibility based on performance limits
- **Weight & Balance Compliance**: Ensure aircraft loading meets certification requirements
- **Runway Performance**: Verify adequate runway length for current conditions
- **Weather Assessment**: Quick METAR/TAF analysis with visual cloud ceiling information
- **Training & Education**: Teaching runway performance calculations and weather interpretation

---

#### `runway.py`
Runway performance calculations including:
- POH data fitting and regression modeling
- Wind correction (headwind/tailwind/crosswind)
- Surface and condition corrections (dry/wet, hard/soft)
- Slope adjustments
- Safety margin application

#### `runway.js`
Client-side runway visualization:
- SVG generation for runway layouts
- Surface-based color coding
- Runway geometry normalization and centering
- Interactive runway overview diagrams

#### `weightbalance.js`
Weight & balance calculations:
- Moment and CG computation
- Envelope boundary checking
- Chart.js integration for visual plotting
- Multi-scenario support (departure/arrival/settings)

#### `tab_aerodrome.py`
Aerodrome information management:
- METAR/TAF retrieval and parsing
- ATC frequency management
- Runway condition tracking
- Route and circuit altitude planning
- Cloud ceiling and wind envelope visualization

---

## 📐 Calculation Methodology

### Runway Performance Calculation Pipeline

1. **POH Correction**
   - Input: Temperature, altitude (field elevation), aircraft weight
   - Method: Linear regression model fitted to POH table data
   - Output: Base distance requirement

2. **Wind Correction**
   - Input: Wind direction, speed, runway heading
   - Calculation: Headwind/tailwind component
   - Factor: Variable based on wind strength (from POH data)

3. **Runway Surface Correction**
   - Factors: Surface type (hard/soft/other) × condition (dry/wet)
   - Multipliers defined in aircraft performance settings

4. **Slope Correction**
   - Input: Runway slope percentage
   - Calculation: Additive correction per percent slope

5. **Safety Margin**
   - Final multiplier for operational safety buffer
   - Typically 1.3-1.5× depending on operation type

### Weight & Balance Algorithm

```
CG = (Σ(weight × arm)) / Σ(weight)

Components:
- Empty weight × empty arm
- Pilot weight × pilot arm
- Copilot weight × copilot arm
- Rear passengers × rear arm(s)
- Baggage × baggage arm
- Fuel × fuel arm
```

## 🔧 Configuration

### Aircraft Setup
Users must configure:
- **POH Tables**: Takeoff/landing performance data (minimum 3 data points)
- **Weight Limits**: Empty weight, max takeoff weight, useful load
- **Arms & Moments**: CG reference datum and station arms
- **Performance Factors**: Surface corrections, slope factors, safety margins
- **Envelope Points**: Weight & balance envelope boundary coordinates

### Aerodrome Customization
Per-aerodrome settings include:
- Preferred parking position
- Default ATC frequencies
- Runway slope overrides
- Custom entry/exit routes
- Circuit altitude preferences
- Additional notes and images


---

## 📚 Documentation

Comprehensive documentation is available at: [https://skywalk-aviation.github.io/docs/](https://skywalk-aviation.github.io/docs/)

Documentation covers:
- Getting started guide
- Aircraft configuration
- Flight planning workflow
- Performance calculations explained
- Weight & balance procedures
- METAR interpretation
- Troubleshooting

---

## 🔒 Security & Privacy

- **User Data**: Stored securely in Firestore with user-specific access
- **Session Isolation**: Flight plan data isolated per user session
- **No Sharing**: Flight plans and custom settings remain private
- **HTTPS**: All communications encrypted

---

## ⚠️ Important Disclaimers

**FOR EDUCATIONAL PURPOSES ONLY**

- This software is **NOT certified** for operational flight planning
- Always verify all calculations with the official aircraft POH
- METAR/TAF data should be always be manually verified
- Runway and aerodrome data should be verified with current NOTAM and charts
- The developer assumes **NO LIABILITY** for use of this software

**REGULATORY COMPLIANCE**: Pilots must comply with all applicable aviation regulations and always maintain appropriate safety margins.

---

## 🐛 Known Limitations

- **METAR Coverage**: Limited to stations with publicly available data
- **Runway Database**: May not include all smaller aerodromes
- **VRB Winds**: Variable wind (VRB) prevents accurate wind corrections
- **POH Fitting**: Requires a minimum of 3 data points for accurate modelling
- **Surface Types**: Generic classifications may not match specific runway conditions

---


## 📄 License

**Copyright (C) 2024-2025, E.Taskesen - All Rights Reserved**

Unauthorized copying, modification, or distribution of this software, via any medium, is strictly prohibited. This software is proprietary and confidential.

---

## 👤 Author

**Erdogan Taskesen**  
Year: 2024-2025

---



## 📝 Version History

- **v0.1** (April 2024): Initial release with core runway performance and weight & balance features
- **v0.2** (February 2026): Enhanced METAR integration, wind envelope analysis, and cloud ceiling visualization

---

**Safe Flying! ✈️**
