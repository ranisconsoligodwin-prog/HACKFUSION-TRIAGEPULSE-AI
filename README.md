# Emergency Triage Network — Hospital Operations Platform

An AI-assisted emergency triage decision-support platform and connected hospital resource network designed for rapid emergency intake, dynamic acuity prioritization, and statewide healthcare resource coordination during normal operations and mass-casualty disaster incidents.

---

## 🚀 Quick Start & Running Locally

The application is built with **Vite + React + TypeScript + Tailwind CSS + Lucide Icons**.

### 1. Start the Development Server:
```bash
npm run dev
```
By default, the Vite dev server will host the application at `http://localhost:5173/` (or the next available port).

### 2. Build for Production:
```bash
npm run build
```
The compiled, optimized static assets will be located in the `dist/` directory.

### 3. Preview Production Build:
```bash
npm run preview
```

---

## 🏥 Core Workflows & Clinical Features

1. **Normal Triage Workflow**:
   - Comprehensive clinical registration with demographics and arrival method.
   - Rapid emergency symptom chips (Chest pain, severe bleeding, altered consciousness, etc.).
   - Objective physiological vitals entry (SpO2, Systolic/Diastolic BP, Heart Rate, Respiratory Rate, Core Temp, GCS, Glucose).
   - Live **Triage Risk Engine** with transparent trigger explanations ("Why this category?").
   - Clinician Urgency Override with mandatory reason documentation.

2. **Red-Only Emergency Mode (Mass-Casualty Disaster Protocol)**:
   - Ultra-fast 3-second rapid intake for mass-casualty collisions and disaster events.
   - Strips down non-essential forms to emergency checkboxes: Unconscious, Not Breathing Normally, Severe Bleeding, Major Trauma.
   - Generates emergency IDs (e.g. `PT-RED-XXX`) and dispatches directly into the Resuscitation Bay queue.

3. **Live Urgency Patient Queue**:
   - Ordered strictly by clinical acuity: `RED (Immediate)` > `YELLOW (Urgent)` > `GREEN (Non-Urgent)`.
   - Filterable by acuity, department, and searchable by patient ID, name, or presenting symptoms.
   - Quick one-click operational actions: Reassess, Assign Bed, Specialist Request, Transfer Review, View Chart.

4. **Clinical Reassessment**:
   - Re-runs the deterministic rules with updated vital signs and observed clinical progression.
   - Shows evolution delta (e.g., Yellow -> Red escalation) and preserves immutable history records.

5. **Local-Resource-First Matching Philosophy**:
   - Prioritizes stabilizing and treating patients locally.
   - If specialized expertise is absent on site, coordinates **Remote Specialist Tele-Consultation** or **Physical Specialist Rapid Deployment** under institutional resource sharing compacts.
   - Only triggers **Inter-Hospital Transfer Review** if critical care life-support beds or ventilators are verified at zero capacity locally.

6. **Major Mass-Casualty Incident Command**:
   - Incident command dashboard for mass casualty events (e.g., NH-45 Highway Multi-Vehicle Collision).
   - Real-time casualty distribution tally across Red, Yellow, and Green tiers.
   - Statewide bed, ICU, and ventilator capacity aggregation.
   - Priority broadcast alert transmission to all connected facilities.

7. **Government & Central Health Desk Coordination**:
   - Role-restricted aggregated regional surveillance.
   - Privacy-safe anonymized hospital network telemetry.
   - Simulated alert transmission to the State Emergency Operations Center (SEOC).

8. **Interactive 9 Demo Scenarios**:
   - One-click execution of 9 realistic clinical walkthroughs (Normal Triage, Critical Red, Deterioration Reassessment, Specialist Matching, Bed Allocation, Transfer Decision Support, Disaster Command, Grid Telemetry, and Govt Telemetry).

---

## 🔒 Privacy, Security & Production Integration Readiness

1. **Where Real Backend Integration Occurs**:
   - `src/services/storageService.ts`: Replace local storage calls with authenticated REST/GraphQL API endpoints.
   - `src/services/triageEngine.ts`: Can be extended with hospital-validated machine learning microservices or EHR predictive risk models.

2. **Where Real Hospital & EHR Interoperability Occurs**:
   - HL7 FHIR v4 resource bundles for Patient, Observation, Encounter, and Condition can be mapped in `src/types/index.ts`.
   - `src/services/resourceMatching.ts`: Connect to state-level bed tracking systems (e.g. HIMS / ABDM interfaces).

3. **Security & Governance Required Before Live Clinical Deployment**:
   - Role-Based Access Control (RBAC) integrated with Hospital Active Directory / OAuth2 / OIDC providers.
   - TLS 1.3 encryption in transit and AES-256 encryption at rest for all Protected Health Information (PHI).
   - Strict audit trail immutability and compliance with HIPAA / DISHA guidelines.

4. **Clinical Safety Disclaimer**:
   - This application is an AI-assisted decision-support prototype.
   - Final clinical triage decisions, medication orders, and inter-hospital transfers remain the legal responsibility of licensed attending healthcare professionals.
