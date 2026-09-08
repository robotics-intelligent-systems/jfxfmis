# jfxfmis

## OpenTwin AI Farm Management Information System

> An open, modular reference architecture for AI-assisted farm
> management, agricultural digital twins, IoT/edge sensing, geospatial
> intelligence, simulation, automation, robotics, vertical farming,
> aquaculture, livestock, renewable energy, and traceable agri-food
> operations.

## Table of Contents

-   [Description and Context](#description-and-context)
-   [Vision](#vision)
-   [Objectives](#objectives)
-   [Reference Architecture](#reference-architecture)
-   [Core Domains](#core-domains)
-   [Digital Twin Architecture](#digital-twin-architecture)
-   [AI and Decision Intelligence](#ai-and-decision-intelligence)
-   [IoT and Edge](#iot-and-edge)
-   [Geospatial Intelligence](#geospatial-intelligence)
-   [Vertical and Floating Farming](#vertical-and-floating-farming)
-   [Aquaculture](#aquaculture)
-   [Livestock and Grazing](#livestock-and-grazing)
-   [Farm Robotics and Automation](#farm-robotics-and-automation)
-   [Energy Water and Circular
    Resources](#energy-water-and-circular-resources)
-   [Supply Chain and Traceability](#supply-chain-and-traceability)
-   [MBSE and Simulation](#mbse-and-simulation)
-   [Open Modular Interfaces](#open-modular-interfaces)
-   [Data Architecture](#data-architecture)
-   [Security Privacy and Governance](#security-privacy-and-governance)
-   [Technology Compendium](#technology-compendium)
-   [User Guide](#user-guide)
-   [Installation Guide](#installation-guide)
-   [Dependencies](#dependencies)
-   [Recommended Repository
    Structure](#recommended-repository-structure)
-   [MVP](#mvp)
-   [Development Roadmap](#development-roadmap)
-   [How to Contribute](#how-to-contribute)
-   [Code of Conduct](#code-of-conduct)
-   [Authors and Maintainers](#authors-and-maintainers)
-   [Additional Information](#additional-information)
-   [Intellectual Property and Open
    Design](#intellectual-property-and-open-design)
-   [Disclaimer](#disclaimer)
-   [License](#license)

------------------------------------------------------------------------

## Description and Context

**jfxfmis / OpenTwin AI Farm Management Information System**
consolidates a broad agricultural software and engineering compendium
into an interoperable reference architecture for modern farm operations.

The project is intended to connect:

``` text
Farm Assets
    |
Sensors / IoT / Weather / GIS / Machines
    |
OpenTwin Digital Twin Layer
    |
Farm Management + ERP + Knowledge
    |
AI / ML / Simulation / Optimization
    |
Decision Support + Automation
    |
Robotics / Irrigation / Energy / Logistics
    |
Traceability + Sustainability + Outcomes
```

The architecture is designed for conventional farms, precision
agriculture, agroindustry, greenhouses, vertical farms, floating farms,
aquaculture, livestock operations, research farms, and
community-oriented food systems.

The repository should be treated as a **reference architecture,
integration compendium, and experimental engineering platform**.
Technologies listed in the compendium are not automatically mandatory
runtime dependencies.

------------------------------------------------------------------------

## Vision

OpenTwin FMIS aims to provide an open agricultural digital backbone in
which physical assets, operational records, environmental measurements,
models, AI services, and automation can be integrated without making the
farm dependent on a single vendor.

``` text
                    OPENTWIN FMIS

        Physical Farm          Digital Farm
             |                      |
   Crops / Animals / Water     Digital Twins
   Machines / Buildings       Models / History
             |                      |
             +----------+-----------+
                        |
                Farm Data Platform
                        |
       +----------------+----------------+
       |                |                |
      AI/ML         Simulation       Management
       |                |                |
 Forecasting       What-if Models    Planning / ERP
 Vision            Modelica          Inventory
 Optimization      MBSE              Finance
       |                |                |
       +----------------+----------------+
                        |
                Decision & Control
                        |
         Human Operators + Automation
```

### Design Principles

-   Open source where practical.
-   Open standards and documented interfaces.
-   Replaceable modules.
-   Human-centered decision support.
-   Traceable AI and model outputs.
-   Local-first and edge-capable operation.
-   Cloud-native scalability where required.
-   Reproducible simulation and analytics.
-   Interoperability with existing FMIS and ERP systems.
-   Sustainable use of energy, water, land, and marine resources.
-   No intentional vendor lock-in.
-   Original and sufficiently abstract reference designs.

------------------------------------------------------------------------

## Objectives

-   Create a modular FMIS architecture.
-   Integrate agricultural digital twins with operational farm data.
-   Connect IoT, weather, soil, water, crop, livestock, machinery, and
    geospatial data.
-   Enable AI-assisted forecasting and decision support.
-   Support precision agriculture and controlled-environment
    agriculture.
-   Support vertical and floating farming.
-   Support recirculating aquaculture systems.
-   Integrate farm robotics and autonomous equipment.
-   Connect agricultural operations with ERP and warehouse management.
-   Enable renewable-energy and resource optimization.
-   Preserve traceability from observations to decisions and outcomes.
-   Support MBSE using Arcadia/Capella.
-   Support Modelica and other simulation environments.
-   Provide open APIs for external applications.
-   Separate mandatory components from optional integrations and
    research references.

------------------------------------------------------------------------

## Reference Architecture

``` text
┌───────────────────────────────────────────────────────────┐
│                    EXPERIENCE LAYER                       │
│ Web UI | Mobile | Dashboards | GIS | CLI | External Apps │
└──────────────────────────┬────────────────────────────────┘
                           │
┌──────────────────────────▼────────────────────────────────┐
│                 FARM MANAGEMENT LAYER                     │
│ Farm | Field | Crop | Livestock | Aquaculture | Inventory│
│ Work Orders | Finance | Warehouse | Supply Chain         │
└──────────────────────────┬────────────────────────────────┘
                           │
┌──────────────────────────▼────────────────────────────────┐
│                  OPENTWIN CORE                            │
│ Asset Registry | Twin Registry | State | Events | Models │
│ Relationships | Provenance | Rules | Workflow            │
└──────────────────────────┬────────────────────────────────┘
                           │
┌──────────────────────────▼────────────────────────────────┐
│              INTELLIGENCE & SIMULATION                    │
│ AI/ML | RAG | Forecasting | Optimization | Modelica      │
│ GIS Analytics | Computer Vision | What-if Simulation     │
└──────────────────────────┬────────────────────────────────┘
                           │
┌──────────────────────────▼────────────────────────────────┐
│                   DATA & EVENTS                           │
│ SQL | Time Series | Object | Vector | Geospatial | Queue │
└──────────────────────────┬────────────────────────────────┘
                           │
┌──────────────────────────▼────────────────────────────────┐
│                    EDGE / OT LAYER                        │
│ IoT | Weather | PLC | Robots | Irrigation | Cameras      │
│ Energy | Water | Aquaculture | Machinery | Gateways      │
└───────────────────────────────────────────────────────────┘
```

Cross-cutting concerns:

**Security · Privacy · Identity · Audit · Observability · Data Quality ·
Licensing · Sustainability · Safety · Versioning**

------------------------------------------------------------------------

## Core Domains

### Farm and Organization

Canonical entities can include:

``` text
Organization
 └─ Farm
     ├─ Site
     ├─ Field / Plot
     ├─ Greenhouse
     ├─ Vertical Farm
     ├─ Floating Farm
     ├─ Aquaculture Unit
     ├─ Livestock Unit
     ├─ Warehouse
     ├─ Energy System
     └─ Equipment
```

### Production

``` text
Season
 └─ Production Plan
     ├─ Crop Cycle
     ├─ Livestock Cycle
     ├─ Aquaculture Cycle
     ├─ Tasks
     ├─ Inputs
     ├─ Observations
     ├─ Harvest
     └─ Outcomes
```

### Operational Records

The platform can record:

-   planting and crop cycles;
-   soil observations;
-   irrigation;
-   fertilizer and nutrient applications;
-   pests and diseases;
-   weather;
-   animal groups and grazing;
-   aquaculture water conditions;
-   machinery activity;
-   labor and work orders;
-   inventory;
-   warehouse movements;
-   energy consumption and production;
-   harvests;
-   quality records;
-   distribution and traceability events.

------------------------------------------------------------------------

## Digital Twin Architecture

The digital twin is a synchronized digital representation of farm assets
and processes.

``` text
Physical Asset
     |
Sensors / Observations / Events
     |
Twin Adapter
     |
Digital Twin State
     |
+----+-------------------+
|                        |
Models                 History
|                        |
Simulation             Analytics
|                        |
+------------+-----------+
             |
      Decision Support
             |
 Human Approval / Automation
```

### Twin Types

-   farm twin;
-   field twin;
-   crop twin;
-   greenhouse twin;
-   vertical-farm twin;
-   floating-farm twin;
-   aquaculture twin;
-   livestock twin;
-   irrigation twin;
-   energy twin;
-   warehouse twin;
-   robot/machine twin;
-   environmental twin.

### Example Twin Schema

``` yaml
twin:
  id:
  type:
  physical_asset_id:
  location:
  geometry:
  state:
  telemetry_refs: []
  model_refs: []
  relationships: []
  control_capabilities: []
  provenance: {}
  updated_at:
```

------------------------------------------------------------------------

## AI and Decision Intelligence

AI should augment rather than obscure farm decision-making.

### Candidate Capabilities

-   crop forecasting;
-   yield estimation;
-   irrigation recommendations;
-   disease-risk estimation;
-   anomaly detection;
-   computer vision;
-   geospatial crop analysis;
-   weather-aware planning;
-   nutrient optimization;
-   livestock monitoring;
-   aquaculture monitoring;
-   predictive maintenance;
-   energy optimization;
-   logistics optimization;
-   knowledge retrieval;
-   natural-language farm assistants.

### AI Governance

``` text
Observation
    |
AI Model
    |
Recommendation
    |
Evidence / Confidence / Provenance
    |
Human Review or Bounded Automation
    |
Action
    |
Measured Outcome
```

For consequential actions, the system should retain model version, input
references, timestamps, confidence where meaningful, decision authority,
and resulting action.

------------------------------------------------------------------------

## IoT and Edge

``` text
Sensors / Machines
       |
Field Gateway
       |
Local Rules / Buffer
       |
MQTT / HTTP / Events
       |
Farm Data Platform
       |
Digital Twin
```

Typical devices:

-   soil moisture;
-   temperature and humidity;
-   weather stations;
-   water-quality probes;
-   cameras;
-   irrigation controllers;
-   tank sensors;
-   energy meters;
-   livestock tags;
-   machinery telemetry;
-   greenhouse controllers;
-   autonomous robots.

Edge operation is useful where connectivity is intermittent or
latency-sensitive.

------------------------------------------------------------------------

## Geospatial Intelligence

Geospatial data can connect farm boundaries, fields, terrain, weather,
imagery, vegetation indexes, crop observations, and machine activity.

``` text
Satellite / Drone / GIS / Weather
              |
       Geospatial Pipeline
              |
       Feature Extraction
              |
          AI / ML
              |
      Field Digital Twin
              |
      Decision Support
```

The original project compendium references **FarmVibes.AI** as a
multimodal geospatial ML resource for agriculture and **AgML** as an
agricultural machine-learning framework.

------------------------------------------------------------------------

## Vertical and Floating Farming

OpenTwin extends FMIS concepts to controlled-environment and floating
agricultural facilities.

``` text
              Floating / Vertical Farm
                        |
        +---------------+---------------+
        |               |               |
   Crop Systems      Utilities       Logistics
        |               |               |
 Hydroponics        Water Loop       Inventory
 Aeroponics         Energy           Cold Chain
 Climate            Nutrients        Distribution
 Lighting           HVAC             Traceability
        |               |               |
        +---------------+---------------+
                        |
                  Digital Twin
```

### Candidate Capabilities

-   hydroponics;
-   aeroponics;
-   environmental control;
-   LED-lighting management;
-   nutrient management;
-   water recirculation;
-   desalination integration where appropriate;
-   renewable energy;
-   AI crop management;
-   automated harvesting;
-   local distribution;
-   environmental monitoring.

Floating facilities should additionally model buoyancy-related
infrastructure, mooring interfaces, marine environmental conditions,
logistics access, corrosion/maintenance considerations, and local
regulatory requirements.

------------------------------------------------------------------------

## Aquaculture

The source compendium includes a **Modelica library for simulation of
recirculating aquaculture systems**.

OpenTwin can represent:

``` text
Water Source
   |
Treatment
   |
Fish Tank / Production Unit
   |
Water Quality Sensors
   |
Recirculation / Filtration
   |
Digital Twin
   |
Simulation + AI
   |
Operator Decision
```

Typical variables:

-   temperature;
-   dissolved oxygen;
-   pH;
-   salinity;
-   flow;
-   nutrient concentrations;
-   biomass estimates;
-   feed;
-   energy;
-   water consumption.

------------------------------------------------------------------------

## Livestock and Grazing

The architecture can integrate grazing planning and livestock
management.

Potential functions include:

-   paddock mapping;
-   herd/group records;
-   seasonal grazing plans;
-   water availability;
-   pasture observations;
-   movement records;
-   health/event records;
-   feed planning;
-   geospatial analysis;
-   environmental indicators.

The original repository references **Grazing Manager** as a map-based
seasonal planning resource.

------------------------------------------------------------------------

## Farm Robotics and Automation

The original compendium references FarmBot and autonomous warehouse
robotics.

``` text
FMIS / Digital Twin
        |
 Mission / Work Order
        |
 Automation Gateway
        |
 Robot / Machine / Controller
        |
 Telemetry + Result
        |
 Twin State Update
```

Potential automation:

-   seeding;
-   irrigation;
-   inspection;
-   crop imaging;
-   harvesting assistance;
-   warehouse transport;
-   inventory movement;
-   greenhouse operations;
-   autonomous scouting.

Safety-critical machine control must remain isolated from untrusted AI
services and should use appropriate engineering safeguards.

------------------------------------------------------------------------

## Energy Water and Circular Resources

### Renewable Energy

``` text
Solar + Wind + Grid
        |
 Energy Management
        |
 Storage / Loads
        |
 Farm Operations
```

### Water

``` text
Source → Treatment → Storage → Irrigation / Aquaculture
                         |
                    Recirculation
                         |
                    Monitoring
```

### Circular Resource Model

Possible flows:

-   nutrient recovery;
-   water reuse;
-   organic-residue management;
-   composting;
-   energy recovery;
-   aquaponic coupling;
-   optimized fertilizer use.

The goal is to measure flows before claiming sustainability benefits.

------------------------------------------------------------------------

## Supply Chain and Traceability

``` text
Input
  |
Production
  |
Harvest
  |
Processing
  |
Storage
  |
Transport
  |
Distribution
  |
Consumer / Buyer
```

Traceability records may connect lots, timestamps, locations,
transformations, quality results, certifications, custody events, and
provenance.

Blockchain is optional; traceability should not depend on blockchain
where a conventional signed event ledger or database is sufficient.

------------------------------------------------------------------------

## MBSE and Simulation

The source repository includes an `MBSE` directory and explicitly
identifies **Arcadia**, supported by **Capella**, for systems
engineering and architecture.

``` text
Stakeholder Needs
      |
Operational Analysis
      |
System Analysis
      |
Logical Architecture
      |
Physical Architecture
      |
Interfaces
      |
Implementation
      |
Simulation & Validation
```

### Engineering Domains

-   **MBSE** --- system architecture and traceability.
-   **CAD** --- physical design.
-   **CAM** --- manufacturing/assembly planning where relevant.
-   **CAS** --- end-to-end simulation and performance analysis.
-   **Modelica** --- equation-based multidomain simulation.

Digital twins should reference engineering models through adapters
rather than requiring one modeling tool.

------------------------------------------------------------------------

## Open Modular Interfaces

A key goal is to keep digital-twin and farm-management components
replaceable.

### API Families

``` text
Organization API
Farm API
Field API
Crop API
Livestock API
Aquaculture API
Asset API
Twin API
Telemetry API
Observation API
Weather API
Geospatial API
Task API
Inventory API
Warehouse API
Traceability API
Energy API
Water API
Simulation API
AI API
Robot API
Analytics API
```

### Example Resources

``` text
/api/v1/farms
/api/v1/fields
/api/v1/assets
/api/v1/twins
/api/v1/telemetry
/api/v1/crops
/api/v1/livestock
/api/v1/aquaculture
/api/v1/tasks
/api/v1/inventory
/api/v1/simulations
/api/v1/recommendations
```

### Events

``` text
sensor.observation.created
weather.forecast.updated
twin.state.updated
crop.alert.created
irrigation.recommended
workorder.created
harvest.recorded
inventory.changed
robot.mission.completed
simulation.completed
```

OpenAPI and AsyncAPI are suitable interface-contract approaches.

------------------------------------------------------------------------

## Data Architecture

``` text
                   Farm Data Fabric
                         |
       +-----------------+------------------+
       |                 |                  |
 Relational         Time Series        Object Storage
       |                 |                  |
 FMIS Records       Telemetry          Images / Models
       |
 Geospatial
       |
 Maps / Fields / Raster / Vector
       |
 Optional Vector Store
       |
 Knowledge / RAG
```

Important data properties:

-   timestamps;
-   units;
-   coordinate reference;
-   sensor identity;
-   calibration metadata;
-   source;
-   quality;
-   license;
-   access policy;
-   provenance;
-   model version;
-   retention policy.

------------------------------------------------------------------------

## Security Privacy and Governance

Recommended controls:

-   OIDC/OAuth2-compatible identity;
-   RBAC/ABAC;
-   farm/site/asset scopes;
-   encrypted transport;
-   encrypted secrets;
-   API authentication;
-   device identity;
-   secure provisioning;
-   audit logs;
-   signed software artifacts;
-   network segmentation;
-   backups;
-   data retention;
-   dependency scanning;
-   model provenance;
-   human approval for consequential automated actions.

Operational technology and safety-critical equipment should be segmented
from public-facing application and AI layers.

------------------------------------------------------------------------

## Technology Compendium

The original repository references multiple open-source or research
projects. They are reorganized below by architectural role rather than
treated as a single mandatory stack.

  ---------------------------------------------------------------------------
  Domain                  Candidate / Reference   Architectural Role
  ----------------------- ----------------------- ---------------------------
  Humanoid robotics       HOPE Jr                 Robotics research reference

  Humanoid robotics       QingLoong               Robotics research reference

  Farm ERP                Odoo Farm               Farm/agroindustry
                                                  management

  IoT                     ThingsBoard             Telemetry and dashboards

  Grazing                 Grazing Manager         Seasonal grazing planning

  Farm platform           GrowGood                Open farming-platform
                                                  reference

  Forestry                SIMANFOR                Forest-management
                                                  simulation

  ERP                     ERPNext Agriculture     Crop, land, soil, water and
                                                  farm records

  Digital twins           farm-twin               Agricultural digital-twin
                                                  reference

  Containers              Rancher                 Container-management
                                                  reference

  Geospatial AI           FarmVibes.AI            Multimodal agricultural
                                                  geospatial ML

  FMIS                    LiteFarm                Farm management

  FMIS                    farmOS                  Farm planning and records

  Agricultural ML         AgML                    Agricultural ML framework

  Farm robotics           FarmBot                 Robot/API/MQTT reference

  FMIS                    Tania                   Farm-management reference

  FMIS                    Ekylibre                Farm-management information
                                                  system

  Analytics               Slick                   MSE
                                                  visualization/exploration
                                                  reference

  Warehouse robotics      Warehouse Worker        Autonomous logistics
                                                  reference

  Simulation              Modelica RAS library    Recirculating aquaculture
                                                  simulation

  IoT connectivity        Farm Data Relay System  Remote-device communication

  Enterprise framework    TOTVS Java Framework    Enterprise integration
                          Samples                 reference

  Weather                 Weather Service API     Weather integration

  Warehouse               Odoo Warehouse          Warehouse integration
                          Management Addons       

  Migration               Odoo → ERPNext          ERP migration research
                          resources               

  Distributed apps        Microsoft Orleans       Cloud-native distributed
                                                  architecture

  Interoperability        Agriculture data        Agricultural data exchange
                          interoperability        
                          toolkit for .NET        

  MBSE                    Capella / Arcadia       Systems architecture

  API contracts           OpenAPI / AsyncAPI      Interoperable interfaces

  Containers              Docker                  Reproducible deployment

  Orchestration           Kubernetes              Scalable deployment

  Relational data         PostgreSQL              Canonical operational
                                                  persistence

  Vector retrieval        Qdrant or equivalent    Optional agricultural RAG
  ---------------------------------------------------------------------------

Before adopting any candidate component, verify its current license,
maintenance status, compatibility, security posture, deployment
requirements, and suitability for the intended jurisdiction and
operational environment.

------------------------------------------------------------------------

## User Guide

A representative workflow is:

1.  Create an organization and farm.
2.  Register sites, fields, facilities, equipment, and production units.
3.  Define crop, livestock, aquaculture, or controlled-environment
    production plans.
4.  Connect weather, IoT, machinery, and external data sources.
5.  Create digital twins for relevant assets.
6.  Ingest observations and operational records.
7.  Configure dashboards and alerts.
8.  Run AI analysis or simulation.
9.  Review recommendations and evidence.
10. Create work orders or approved automation actions.
11. Record outcomes, harvests, inventory, and resource use.
12. Analyze performance, sustainability, and traceability.

### Example

``` text
Soil Sensor
    ↓
Telemetry
    ↓
Field Twin
    ↓
Weather + Crop Model
    ↓
Irrigation Recommendation
    ↓
Operator Approval
    ↓
Irrigation Controller
    ↓
Water Use + Outcome Recorded
```

------------------------------------------------------------------------

## Installation Guide

At its current architectural level, jfxfmis should not imply that every
project listed in the technology compendium must be installed.

### Clone

``` bash
git clone https://github.com/robotics-intelligent-systems/jfxfmis.git
cd jfxfmis
```

### Minimal Reference Deployment

``` text
Web Application
      |
Core FMIS API
      |
PostgreSQL
      |
Twin / Telemetry Service
      |
MQTT-compatible Broker
```

### Extended Deployment

``` text
Core FMIS
├─ PostgreSQL
├─ Object Storage
├─ MQTT / Event Broker
├─ IoT Platform
├─ Geospatial Service
├─ AI/ML Service
├─ Modelica Simulation Adapter
├─ ERP Adapter
├─ Robotics Gateway
├─ Vector Retrieval
└─ Observability
```

Containerized modules should provide:

-   tested operating-system versions;
-   runtime and SDK versions;
-   dependency versions;
-   environment variables;
-   database migrations;
-   build instructions;
-   test instructions;
-   network requirements;
-   persistent-storage requirements;
-   security configuration.

------------------------------------------------------------------------

## Dependencies

Dependencies should be classified explicitly.

### Required

Only components required to execute a specific jfxfmis implementation.

Example:

``` yaml
dependency:
  name: PostgreSQL
  role: operational data
  status: required
  version: tested-version
  license: verify
```

### Optional Integrations

Examples:

-   ThingsBoard;
-   Odoo;
-   ERPNext;
-   FarmBot;
-   FarmVibes.AI;
-   AgML;
-   Modelica;
-   Capella;
-   Rancher/Kubernetes;
-   vector databases;
-   weather providers;
-   GIS services.

### Research References

Projects retained for architecture comparison, experimentation, or
inspiration without becoming runtime dependencies.

This separation reduces unnecessary coupling and license ambiguity.

------------------------------------------------------------------------

## Recommended Repository Structure

``` text
jfxfmis/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── docs/
│   ├── architecture/
│   ├── user-guide/
│   ├── installation/
│   ├── security/
│   └── interoperability/
├── MBSE/
│   ├── operational-analysis/
│   ├── system-analysis/
│   ├── logical-architecture/
│   └── physical-architecture/
├── core/
│   ├── organizations/
│   ├── farms/
│   ├── fields/
│   ├── production/
│   ├── inventory/
│   └── work-orders/
├── twins/
│   ├── registry/
│   ├── state/
│   ├── relationships/
│   └── adapters/
├── agriculture/
│   ├── crops/
│   ├── vertical-farming/
│   ├── livestock/
│   └── aquaculture/
├── iot/
│   ├── devices/
│   ├── gateways/
│   └── telemetry/
├── ai/
│   ├── forecasting/
│   ├── vision/
│   ├── optimization/
│   └── rag/
├── simulation/
│   ├── modelica/
│   └── scenarios/
├── geospatial/
├── robotics/
├── energy/
├── water/
├── traceability/
├── integrations/
│   ├── erp/
│   ├── weather/
│   ├── gis/
│   └── external-fmis/
├── api/
├── events/
├── deployment/
├── tests/
└── examples/
```

------------------------------------------------------------------------

## MVP

### Goal

Deliver a small but executable OpenTwin FMIS demonstrating the complete
observation-to-decision workflow.

``` text
Sensors / Sample Data
        |
      MQTT
        |
 Telemetry Service
        |
     Farm Twin
        |
     FMIS API
        |
   PostgreSQL
        |
 Dashboard + Alerts
```

### MVP Capabilities

-   organization and farm registration;
-   fields and assets;
-   crop cycle;
-   IoT telemetry;
-   weather observations;
-   digital-twin state;
-   tasks/work orders;
-   simple rule-based recommendations;
-   optional AI recommendation service;
-   resource-use records;
-   dashboard;
-   REST API;
-   audit/provenance metadata;
-   Docker-based local deployment.

### MVP Demonstration

``` text
Temperature + Soil Moisture
           ↓
       Field Twin
           ↓
     Decision Rule
           ↓
 Irrigation Recommendation
           ↓
      Work Order
           ↓
 Outcome + Water Consumption
```

### Success Criteria

-   complete end-to-end data flow;
-   replaceable sensor adapter;
-   documented API;
-   reproducible deployment;
-   traceable recommendation;
-   recorded human decision;
-   basic analytics;
-   no dependency on a proprietary cloud service.

------------------------------------------------------------------------

## Development Roadmap

### Phase 1 --- Architecture and Documentation

-   [x] BID-inspired README structure.
-   [x] FMIS compendium consolidation.
-   [x] OpenTwin reference architecture.
-   [x] Digital-twin modular interfaces.
-   [x] Vertical/floating farming conceptual integration.
-   [ ] Architecture Decision Records.
-   [ ] Canonical schemas.
-   [ ] API specifications.

### Phase 2 --- FMIS Core

-   [ ] Organizations and farms.
-   [ ] Fields and production units.
-   [ ] Crop cycles.
-   [ ] Tasks and work orders.
-   [ ] Inventory.
-   [ ] Operational records.

### Phase 3 --- IoT and Digital Twins

-   [ ] Device registry.
-   [ ] Telemetry ingestion.
-   [ ] Twin registry.
-   [ ] Twin state/history.
-   [ ] Weather integration.
-   [ ] Alert rules.

### Phase 4 --- AI and Geospatial Intelligence

-   [ ] Geospatial data pipeline.
-   [ ] Agricultural ML adapters.
-   [ ] Forecasting.
-   [ ] Anomaly detection.
-   [ ] AI-assisted recommendations.
-   [ ] Agricultural knowledge/RAG.

### Phase 5 --- Simulation and MBSE

-   [ ] Modelica adapter.
-   [ ] Scenario manager.
-   [ ] What-if analysis.
-   [ ] Capella traceability.
-   [ ] Requirements-to-validation links.

### Phase 6 --- Controlled Environment and Aquaculture

-   [ ] Greenhouse twin.
-   [ ] Vertical-farm twin.
-   [ ] Floating-farm twin.
-   [ ] Aquaculture twin.
-   [ ] Water/nutrient models.
-   [ ] Energy integration.

### Phase 7 --- Robotics and Automation

-   [ ] Robot gateway.
-   [ ] Mission/work-order interface.
-   [ ] FarmBot-style adapter.
-   [ ] Warehouse automation.
-   [ ] Human approval controls.
-   [ ] Safety boundaries.

### Phase 8 --- Supply Chain and Sustainability

-   [ ] Lot traceability.
-   [ ] Warehouse integration.
-   [ ] Energy/water accounting.
-   [ ] Sustainability indicators.
-   [ ] Distribution integration.
-   [ ] Impact analytics.

------------------------------------------------------------------------

## How to Contribute

Contributions are welcome in:

-   FMIS architecture;
-   agriculture;
-   aquaculture;
-   livestock;
-   IoT;
-   digital twins;
-   geospatial systems;
-   AI/ML;
-   Modelica;
-   MBSE;
-   robotics;
-   ERP integration;
-   renewable energy;
-   water management;
-   supply-chain traceability;
-   cybersecurity;
-   documentation.

### Development Workflow

``` bash
git checkout -b feature/my-contribution
git add .
git commit -m "Add: description of contribution"
git push origin feature/my-contribution
```

Pull requests should explain:

-   problem;
-   proposed solution;
-   affected domain;
-   architecture impact;
-   interface/schema changes;
-   new dependencies;
-   licenses;
-   security/privacy impact;
-   operational or safety impact;
-   tests/validation;
-   documentation changes.

Do not commit credentials, private farm data, unauthorized personal
information, proprietary datasets, or third-party content without
appropriate rights.

------------------------------------------------------------------------

## Code of Conduct

Contributors should maintain a respectful, inclusive, professional, and
technically constructive environment.

A dedicated `CODE_OF_CONDUCT.md` should be maintained at the repository
root.

------------------------------------------------------------------------

## Authors and Maintainers

Maintained by the **Robotics Intelligent Systems** open-source
initiative.

Project:

`robotics-intelligent-systems/jfxfmis`

Third-party software, models, datasets, standards, trademarks, and
research projects remain the property of their respective owners.

------------------------------------------------------------------------

## Additional Information

### Primary Project Scope

**Farm Management Information Systems**

The source repository currently combines references related to:

-   AI-powered farm management;
-   farm ERP;
-   IoT;
-   grazing;
-   forestry;
-   agricultural digital twins;
-   geospatial ML;
-   FMIS;
-   agricultural ML;
-   robotics;
-   warehouse automation;
-   aquaculture simulation;
-   remote IoT;
-   weather;
-   cloud-native distributed systems;
-   agricultural interoperability;
-   MBSE.

This consolidated document turns that catalog into a layered
architecture while preserving the value of the original research
references.

------------------------------------------------------------------------

## Intellectual Property and Open Design

The project favors:

-   open standards;
-   open interfaces;
-   modular adapters;
-   replaceable implementations;
-   original reference architectures;
-   synthetic or appropriately licensed demonstration assets;
-   explicit provenance;
-   explicit third-party licenses.

Concept imagery and external models used for research or inspiration
should not be interpreted as project-owned industrial designs.

Where external concept resources are retained for reference, replace
them with original, sufficiently abstract, or appropriately licensed
assets before redistribution when required.

**Open source does not automatically mean patent-free.** No repository
description, architecture diagram, or open-source license can guarantee
absence of third-party patent rights in every jurisdiction. Contributors
and deployers remain responsible for appropriate intellectual-property
review.

The preferred architectural strategy is therefore to use open standards,
modular interfaces, original abstractions, and replaceable components
rather than copying proprietary implementations.

------------------------------------------------------------------------

## Disclaimer

jfxfmis / OpenTwin AI Farm Management Information System is a
**research, educational, engineering, and experimental project**.

Agricultural recommendations generated by software, AI, simulations, or
digital twins may be incomplete or inaccurate. They should be validated
against local conditions and appropriate professional expertise before
consequential operational use.

Deployments involving machinery, robotics, electrical systems, water
treatment, aquaculture, food production, chemicals, autonomous control,
or safety-critical infrastructure require appropriate engineering
controls and compliance with applicable regulations.

Environmental or sustainability benefits should be measured rather than
assumed.

This README uses the BID repository template as a
**documentation-structure reference only**. The project does not claim
BID/IDB funding, sponsorship, endorsement, catalog membership, or
institutional affiliation.

------------------------------------------------------------------------

## License

The actual project license should remain in the repository root as
`LICENSE`, `LICENSE.md`, or its existing equivalent.

Third-party libraries, frameworks, datasets, models, documentation, and
reference projects retain their respective licenses and terms.

Do **not** automatically apply the BID/IDB software license, copyright
notice, funding statement, or institutional disclaimer merely because
its documentation template informed the structure of this README.

------------------------------------------------------------------------

## OpenTwin FMIS Principles

**Open Source · Modular Digital Twins · Interoperability · AI-Assisted
Agriculture · Reproducibility · Sustainability · Human Oversight**

> Observe the physical farm.\
> Preserve trustworthy data.\
> Model the system.\
> Simulate before acting.\
> Use AI as decision support.\
> Keep interfaces open.\
> Keep components replaceable.\
> Measure outcomes.
