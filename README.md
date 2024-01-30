# Outline for Microsoft SC-900 Exam Study Guide

## 1. Describe the concepts of security, compliance, and identity (10–15%)
### Describe security and compliance concepts
#### Shared Responsibility Model:
- On-premises: Customer handles everything.
- IaaS: Customer not responsible for physical components.
- PaaS: Cloud provider manages hardware and OS; customer handles applications and data.
- SaaS: Cloud provider manages everything except data, devices, accounts, and identities.
- Customer Responsibilities: Information, devices (mobile and PCs), accounts, and identities.<br>


![Screenshot 2024-01-27 104929](https://github.com/w4kery/SC-900_Study_Guide/assets/32207684/bff36ad4-ce94-46d2-9631-ada4594d0b93)

#### Defense in Depth:
- Multilayered security approach.
- Layers include physical security, identity controls, perimeter security, network security, compute layer security, application layer security, and data layer security.
- Emphasizes confidentiality, integrity, and availability.

#### Zero Trust Model:
- Guiding Principle: "Trust no one, verify everything."
- Principles: Verify explicitly, least privileged access, assume breach.
- Six Foundational Pillars: Identities, devices, applications, data, infrastructure, networks.

#### Governance, Risk, and Compliance (GRC) Concepts:
- Governance: Rules and practices for directing activities.
- Risk Management: Identifying, assessing, and responding to threats.
- Compliance: Adherence to laws and regulations.
- Compliance-Related Concepts: Data residency, data sovereignty, data privacy.

### Define identity concepts

#### Identity as the Primary Security Perimeter:
  - Considers identity as the primary factor in security.
  - Four Pillars: Administration, authentication, authorization, auditing.
#### Identity Provider:
  - Manages identity information and provides authentication, authorization, and auditing services.
  - Modern Authentication: Client-server authentication using security tokens.
  - Example: Microsoft Entra ID.
#### Directory Services and Active Directory:
  - Directory Services: Hierarchical structure storing network object information.
  - Active Directory (AD): Microsoft's on-premises directory service.
  - AD DS Functionality: Manages on-premises infrastructure components using a single user identity.
  - Microsoft Entra ID: Cloud-based identity provider.
#### Federation:
  - Enables service access across domain boundaries.
  - Example: User logging into a third-party site with a social media account.

## 2. Describe the capabilities of Microsoft Entra (25–30%)
### Describe function and identity types of Microsoft Entra ID
#### Describe Microsoft Entra ID:
- Formerly Azure Active Directory.
- Cloud-based identity and access management service.
- Enables user access to resources.
- Key Features: Unified identity system, secure access to personal devices, collaboration with partners.
- Identity Secure Score: Percentage indicating security alignment.

![Screenshot 2024-01-29 201942](https://github.com/w4kery/SC-900_Study_Guide/assets/32207684/f28dd12a-4b6f-471a-bec7-4bc482de344d)


#### Types of Identities in Microsoft Entra ID:
- User Identities: Internal members, external guests, external members, internal guests.
- Device Identities: Registered, joined, hybrid joined devices.
- Workload Identities: Applications, service principals, managed identities.
- Groups: Security groups, Microsoft 365 groups.

#### Hybrid Identities:
- Combines on-premises and cloud-based capabilities.
- Components: Provisioning and synchronization.
- Microsoft Entra Cloud Sync: Facilitates provisioning and synchronization.
- SCIM Specification: Utilizes System for Cross-domain Identity Management.

##### External Identities:
- B2B Collaboration, B2B Direct Connect, External ID for Customers (Preview), Multi-tenant Organizations.

### Describe authentication capabilities of Microsoft Entra ID

#### Authentication Methods for Microsoft Entra ID:
- Passwords, phone (SMS and voice call), OATH (TOTP), Passwordless (Windows Hello, FIDO2, Authenticator App, Certificate-based).
- OATH Hardware Token (Preview).
- Certificate-based Authentication (CBA) utilizes X.509 certificates.

#### Multi-Factor Authentication (MFA):
- Requires multiple forms of identification during sign-in.
- Components: Something you know, have, and are.
- Methods: Authenticator app, Windows Hello, FIDO2 key, OATH hardware token, OATH software token, SMS, voice call.
- Security Defaults recommended for basic security.
- Self-Service Password Reset (SSPR) enables users to change or reset passwords.
- SSPR Authentication Methods: Mobile app, email, security questions.
- Password Write-Back updates on-premises Active Directory. <br>


![Screenshot 2024-01-29 165842](https://github.com/w4kery/SC-900_Study_Guide/assets/32207684/2d874dff-02d2-485e-9536-b2eb4109f128)



#### Password Protection and Management Capabilities in Microsoft Entra ID:
##### Global Banned Password List:
- Microsoft Entra ID employs a Global Banned Password List automatically updated and enforced by Microsoft.
- This list blocks known weak passwords and their variations, maintained by the Microsoft Entra ID Protection team using security telemetry data.
- Examples of blocked passwords include P@$$w0rd or Passw0rd1 and their variations, created through case transpositions and letter-to-number substitutions.

##### Custom Banned Password Lists:
- Admins can create custom lists aligning with specific business security needs.
- These lists prohibit passwords related to organizational terms, enhancing security by focusing on organization-specific terms in addition to the global banned password list.

##### Protection Against Password Spray:
- Defending against password spray attacks, Microsoft Entra ID efficiently blocks millions of common weak passwords using real-world security telemetry data.
- Fuzzy-matching techniques identify approximate pattern matches, ensuring robust protection.

##### Hybrid Security Integration:
- Integrating Microsoft Entra password protection within on-premises Active Directory environments ensures consistent password protection across both cloud and on-premises environments.
- This integration involves a component installed in the on-premises environment that receives global banned password lists and custom password protection policies, used by domain controllers to process password change events.

*Note: Banned password lists are part of Microsoft Entra ID P1 or P2 licensing, providing an effective defense against password spray attacks and offering flexibility through custom lists.*

### Describe access management capabilities of Microsoft Entra ID
#### Describe Microsoft Entra ID Conditional Access
- The assignments section controls the who, what, where, and when of the Conditional Access policy.
- It specifies users, groups, cloud apps or actions, and conditions such as sign-in risk, user risk, devices platform, IP location information, client apps, and filters for devices.

##### Access Controls:
- Access controls determine how a policy is enforced after application.
- This includes blocking access, granting access with or without additional controls, and session controls like Conditional Access App Control for specific application restrictions.

##### Conditional Access Overview:
- Microsoft Entra ID's Conditional Access policies automate access decisions based on signals like user attributes, location, device information, applications, and risk factors.
- The combination of assignments (who, what, where, when) and access controls (how) provides a granular and adaptive approach to securing access.

#### Describe Microsoft Entra roles and role-based access control (RBAC)
- Microsoft Entra roles control permissions, utilizing Role-Based Access Control (RBAC).
- This involves built-in roles like Global Administrator, User Administrator, and Billing Administrator, as well as custom roles that grant specific permissions.
- Adhering to the least privilege principle, these roles ensure secure access management.

##### Role Categories:
- Roles are categorized into Microsoft Entra specific roles, service-specific roles, and cross-service roles.
- This categorization aids in providing tailored access control across Microsoft 365 services.

##### Granting Access Using Custom Roles:
- Custom roles involve defining role permissions, assigning these permissions to users or groups, and specifying the scope of access, whether organization-wide or at the object level.

##### Categories of Microsoft Entra Roles:
- Roles are categorized based on Microsoft 365 services, service-specific roles, and cross-service roles, ensuring a flexible approach to access management.

##### Microsoft Entra RBAC vs. Azure RBAC:
- Microsoft Entra RBAC controls access to Microsoft Entra-specific resources, while Azure RBAC controls access to Azure resources.
- The distinction lies in storage and data stores, as well as policy decision points.

*Note: Custom roles in Microsoft Entra require a Microsoft Entra ID P1 or P2 license, offering a flexible approach to secure access control.*

### Describe identity protection and governance capabilities of Microsoft Entra
#### Describe Microsoft Entra ID Governance:
##### Identity Lifecycle Management:
- The identity lifecycle management process involves join, move, and leave processes, ensuring consistency in user accounts.
- Integration with HR systems maintains alignment with properties like department or employment status.

##### Access Lifecycle Management:
- Utilizing dynamic groups and role-based access, Microsoft Entra ID automates access lifecycle processes.
- Dynamic groups use attribute-based rules for automated evaluation, adapting access rights throughout a user's organizational journey.

##### Privileged Access Lifecycle (Microsoft Entra Privileged Identity Management - PIM):
- Monitoring privileged access is crucial, and Microsoft Entra PIM provides additional controls for securing access rights.
- Governance controls help minimize access, reducing the risk associated with privileged access.

*Summary: Microsoft Entra ID Governance focuses on identity and access lifecycle management, ensuring efficiency, and integration with HR systems, dynamic groups, and Microsoft Entra PIM contribute to a robust governance framework.*

#### Describe Microsoft Access Reviews:
##### Key Use Cases:
- Access reviews play a crucial role in evaluating privileged roles, critical data access, policy exceptions, guest user necessity, and recurring validation at specified frequencies.

##### Management with Access Reviews:
- Participants, recertification, review stages, smart recommendations, and progress tracking are essential aspects of access review management.
- It ensures a comprehensive and intelligent approach to validating access.

##### Entitlement Management: Capabilities:
- Entitlement management automates access request workflows, assignments, reviews, and expiration.
- It addresses challenges related to managing the identity and access lifecycle, ensuring secure and controlled access to resources.

##### Microsoft Entra Terms of Use: Key Features:
- Terms of use in PDF format with conditional access integration ensure user acknowledgment before accessing applications.
- Admin visibility allows tracking user acceptance or rejection of terms.

*Summary: Access reviews, entitlement management, and terms of use collectively contribute to a robust identity governance framework within Microsoft Entra ID, ensuring security, compliance, and efficient access management.*

#### Describe the capabilities of Microsoft Entra Privileged Identity Management (PIM) Overview:
- PIM in Microsoft Entra ID ensures controlled, monitored, and just-in-time privileged access.
- Its capabilities include just-in-time access, time-bound assignments, approval-based activations, visible notifications, auditable access history, and oversight of administrator privileges.

##### Why Use PIM?
- PIM reduces risks associated with misuse and unnecessary access, providing oversight of administrator privileges.

##### Workflow:
- The PIM workflow involves assigning roles, activating roles with specified durations and reasons, approving/denying access by delegated approvers, and extending/renewing role assignments.

##### Audit:
- PIM audit history tracks role assignments and activations for privileged roles, ensuring transparency and accountability.

#### Describe MicrosofT Entra ID Protection
##### Capabilities:
- Automating risk detection and remediation, Microsoft Entra ID Protection focuses on identity-based risks.
- It uses signals from Entra ID, Microsoft Accounts, and Xbox for risk analysis, offering flexible data export options for further analysis.

##### Detect Risks:
- Identifying sign-in and user risks, Microsoft Entra ID Protection ensures proactive identification of potential compromises.

##### Investigate Risks:
- Reports and risk factor analysis provide visibility into risk factors, facilitating informed decisions on potential compromise.

##### Remediate Risks:
- Automated actions and manual reviews based on risk policies allow flexible and effective risk mitigation.

*Note: Microsoft Entra ID Protection now includes workload identity protection for applications and service principals, managing risks associated with their unique characteristics.*

#### Describe Microsoft Entra Permissions Management:
##### Overview:
- Cloud Infrastructure Entitlement Management (CIEM) for Azure, AWS, and GCP supports Zero Trust least privilege access.
- It addresses multicloud challenges, risk complexity, and security compliance.

##### Capabilities:
- CIEM capabilities include cross-cloud permissions discovery, automated deletion of unused permissions, on-demand permissions, ML-powered anomaly detections, and forensic reports for enhanced security monitoring.

##### Microsoft Entra Verified ID: Overview:
- Managed verifiable credentials service automates identity credential verification with privacy protection.
- It addresses challenges of online transactions and digital identity control.

##### Key Features:
- Verifiable credentials are cryptographically secure, privacy-compliant, and machine-readable.
- They enable control over when and how digital identities are used.

##### Working Mechanism:
- Issuers provide digitally signed credentials, users receive, approve, and store credentials, and verifiers request and verify credential claims.

##### Verifiable Data Registry:
- A collection of systems for metadata supports scenarios like credential expiration and revocation, ensuring a trust system for verifying credentials.

##### Benefits:
- Automated verification of secure and privacy-protected credentials enhances online transactions' security and privacy compliance.

*Summary: Access reviews, entitlement management, terms of use, PIM, Microsoft Entra ID Protection, permissions management, and verified ID collectively contribute to a comprehensive identity and access management framework within Microsoft Entra ID.*

## Describe the capabilities of Microsoft security solutions (35–40%)

### Describe core infrastructure security services in Azure

#### Azure DDoS Protection

##### Overview
- Counteracts Distributed Denial of Service (DDoS) attacks targeting applications and servers.
- Addresses three common DDoS attack types: Volumetric, Protocol, Resource layer.

##### Azure DDoS Protection
1. **Protection Layers:**
   - Network layer (Layer 3) and transport layer (Layer 4) defense.
   - Adaptive real-time tuning for intelligent traffic profiling.
   - Continuous traffic monitoring for proactive defense.

2. **Telemetry and Monitoring:**
   - DDoS Protection telemetry, monitoring, and alerting.
   - Integration with Azure Monitor for advanced analysis.
   - Configurable alerts tied to Azure Monitor metrics.

3. **Service Tiers:**
   - DDoS Network Protection: Automatic defense for Azure resources.
   - DDoS IP Protection: Pay-per-protected IP model with specific features.
      - Higher threshold, no telemetry or alerting.
      - Application-specific monitoring and defense.

##### Benefits
- Mitigates DDoS attacks at the network and transport layers.
- Adapts to changing traffic patterns through adaptive profiling.
- Utilizes telemetry, monitoring, and alerting for proactive defense.

#### Describe Azure Firewall

##### Overview
- Managed, cloud-based network security service within Azure.
- Ensures threat protection for cloud workloads and resources.

##### Key Features
1. **Deployment Model:**
   - Scalable deployment on any virtual network.
   - Centralized deployment recommended for effective network traffic control.

2. **Firewall SKUs:**
   - Standard, Premium, and Basic SKUs.
   - Built-in high availability and availability zones.
   - Network and application-level filtering.

3. **Traffic Handling:**
   - Outbound SNAT and inbound DNAT for internet communication.
   - Multiple public IP addresses associated with Azure Firewall.

4. **Threat Intelligence:**
   - Enables threat intelligence-based filtering.
   - Alerts and denies traffic to/from known malicious IP addresses and domains.

5. **Integration:**
   - Integrated with Azure Monitor for telemetry collection.
   - Supports Azure Monitor logs for in-depth analysis and action.

#### Describe Web Application Firewall (WAF)

##### Overview
- Centralized protection against web application exploits.
- Simplifies security management and enhances response time.
- Addresses vulnerabilities in a centralized manner.

##### Key Features
1. **Protection Scope:**
   - Centralized protection for web applications.
   - Guards against common exploits and vulnerabilities.

2. **Security Benefits:**
   - Distributed denial of service (DDoS) protection at the application layer.
   - Simplifies security management for application administrators.

3. **Application Layer Protection:**
   - Defends against application-layer DDoS attacks (e.g., HTTP Floods).
   - Ensures robust protection against application threats.

#### Describe Network Segmentation in Azure

##### Overview
- Division of the network into smaller segments.
- Supports the Zero Trust model and a defense in depth strategy.
- Enhances security posture and facilitates breach containment.

##### Benefits
1. **Containment and Control:**
   - Enables precise control of communication paths.
   - Contains the impact in case of a compromised segment.

2. **Zero Trust Model:**
   - Aligns with Zero Trust principles to prevent lateral spreading of attacks.
   - Ensures stringent access controls and verification.

3. **Azure Virtual Network (VNet):**
   - Fundamental building block for private networks in Azure.
   - Provides network-level containment and isolation.
   - Supports multiple VNets and subnets for effective segmentation.

##### Implementation
- Explicit provisioning of communication paths for enhanced control.
- Better management of resource interactions.
- Strengthens security posture and minimizes lateral spread of attacks.

#### Describe Azure Network Security Groups (NSGs)

##### Overview
- Filters network traffic to and from Azure resources within a virtual network.
- Comprises inbound and outbound security rules for effective traffic filtering.
- Associated with virtual network subnets and network interfaces.

##### Inbound and Outbound Rules
- Inbound: Rules for incoming traffic to resources.
- Outbound: Rules for outgoing traffic from resources.

##### NSG Properties
1. **Rule Components:**
   - Name, Priority, Source/Destination, Protocol, Direction, Port Range, Action.
   - Unique name for rule identification.
   - Priority for rule evaluation; lower numbers processed first.
   - Source/Destination specified as IP addresses, ranges, or service tags.
   - Protocol: TCP, UDP, ICMP, or Any.
   - Direction: Inbound or Outbound.
   - Port Range: Individual or range of ports.
   - Action: Allow or Deny.

2. **Default Rules:**
   - Inbound: AllowVNetInBound, AllowAzureLoadBalancerInBound, DenyAllInBound.
   - Outbound: AllowVNetOutBound, AllowInternetOutBound, DenyAllOutBound.
   - Default rules can't be removed but can be overridden.

##### Difference from Azure Firewall
- NSGs provide distributed traffic filtering within virtual networks.
- Azure Firewall serves as a centralized, stateful firewall for network and application-level protection.
- NSGs complement Azure Firewall for an integrated approach to network security.

#### Describe Azure Bastion

##### Overview
- Facilitates secure RDP and SSH connectivity to VMs from the Azure portal.
- PaaS service provisioned within the virtual network.
- Utilizes TLS for secure connectivity without public IP or agent.

##### Key Benefits
1. **Direct Azure Portal Connectivity:**
   - Enables RDP and SSH directly within the Azure portal.
   - Eliminates the need for a public IP on Azure VMs.
   - Ensures secure RDP/SSH with firewall traversal.

2. **No NSG Management Hassle:**
   - Fully managed platform with no NSG management required.
   - Provides secure connectivity without applying NSGs on the Bastion subnet.

3. **Protection Against Port Scanning:**
   - Prevents exposure of VMs to the internet.
   - Ensures security against port scanning attacks.

4. **Hardening in One Place:**
   - Centralized hardening against zero-day exploits.
   - Azure platform ensures Bastion is always up-to-date.

5. **SKUs:**
   - Basic and Standard SKUs available for Azure Bastion.

#### Describe Azure Key Vault

##### Overview
- Cloud service for securely storing and accessing secrets.
- Manages API keys, passwords, certificates, and cryptographic keys.
- Addresses secrets, key, and certificate management.

##### Key Features
1. **Secrets Management:**
   - Ensures secure storage and controlled access.
   - Centralized management of application secrets.

2. **Key Management:**
   - Simplifies creation and control of encryption keys.
   - Supports creation and control of cryptographic keys.

3. **Certificate Management:**
   - Facilitates provisioning, management, and deployment of SSL/TLS certificates.
   - Ensures secure management of both public and private certificates.

4. **Service Tiers:**
   - Standard: Encrypts with a software key.
   - Premium: Includes HSM-protected keys.

##### Why Use Key Vault
- Centralizes application secrets securely.
- Manages encryption keys for robust data protection.
- Simplifies SSL/TLS certificate management.
- Implements proper authentication and authorization.
- Provides monitoring and logging for access and usage.
- Simplifies administration of application secrets.


### Describe security management capabilities of Azure
#### Describe Microsoft Defender for Cloud

##### Overview
- Cloud-native application protection platform (CNAPP).
- Integrates DevSecOps, Cloud Security Posture Management (CSPM), and Cloud Workload Protection Platform (CWPP).
- Shields against cyber threats and vulnerabilities.

##### Components
1. **DevSecOps:**
   - Unifies security management at the code level across multicloud and multiple-pipeline environments.
   - Safeguards code management environments and pipelines.
   - Offers insights into the security posture of development environments.

2. **CSPM:**
   - Surfaces actions to prevent breaches.
   - Assesses systems, alerts on vulnerabilities, and monitors security enhancements.
   - Supports security management across various cloud environments.

3. **CWPP:**
   - Provides specific protections for servers, containers, storage, databases, and other workloads.
   - Delivers security alerts to detect and respond to threats promptly.

#### Describe how security policies and initiatives improve the cloud security posture

##### Azure Policy Definitions and Initiatives
- Azure Policy Definitions: Rules specifying particular security conditions.
- Security Initiative: A collection of Azure Policy definitions grouped towards a specific security goal.
- Assignable to various scopes, including management groups, subscriptions, and resource groups.

##### Microsoft Cloud Security Benchmark (MCSB)
- Microsoft-authored guidelines for security and compliance.
- Builds on controls from CIS and NIST, focusing on cloud-centric security.
- Comprises ID, Control Domain, Mapping to industry frameworks, Recommendations, Azure Guidance, AWS Guidance.

##### Security Recommendations
- Arise from assessing resources against policies.
- Periodically analyzed for compliance status.
- Offer insights into security misconfigurations, including descriptions, remediation steps, and affected resources.

#### Describe Cloud Security Posture Management (CSPM)

##### Secure Score
- Central feature providing visibility into security posture.
- Aggregates findings into a single score, where a higher score indicates a lower risk level.
- Reflects compliance with MCSB and other standards.

##### Hardening Recommendations
- Offers guidance to enhance security posture.
- Grouped into security controls.
- Implementing all recommendations in a control improves the overall score.

##### CSPM Plan Options
- Foundational CSPM: Includes asset discovery, continuous assessment, security recommendations, compliance with MCSB, and secure score (free).
- Optional Defender CSPM Plan: Provides advanced capabilities, tools, and assessment for a broad range of benchmarks, regulatory standards, and custom security policies.

##### Defender Plans
- Microsoft Defender for servers, App Service, Storage, SQL, Kubernetes, Container Registries, Key Vault, Resource Manager, DNS, open-source relational protections.
- Workload-specific plans with advanced protections.

#### Describe enhanced security features provided by cloud workload protection
- Comprehensive endpoint detection and response (EDR).
- Vulnerability scanning for virtual machines, container registries, and SQL resources.
- Multicloud and hybrid security.
- Threat protection alerts, compliance tracking, access and application controls.

##### Integration with Microsoft Defender Plans
- Plans run simultaneously for comprehensive defense.
- Advanced features tailored to specific resource types.

##### DevOps Security Management

##### Overview
- Merges development (Dev) and operations (Ops) for unified application planning, development, delivery, and operations.
- Defender for DevOps empowers security teams in multi-pipeline environments (GitHub, Azure DevOps).

##### Key Capabilities
1. **Unified Visibility:**
   - Provides full visibility into DevOps inventory and security posture.
   - Offers a single view for security administrators.

2. **Infrastructure as Code (IaC) Security:**
   - Focuses on securing Infrastructure as Code templates to prevent misconfigurations.
   - Minimizes misconfigurations reaching production environments.

3. **Remediation Prioritization:**
   - Applies contextual insights within Defender for Cloud.
   - Prioritizes critical code fixes with Pull Request annotations.
   - Triggers custom workflows for developers.

##### Defender for DevOps Console
- Manages connected DevOps environments.
- Provides security teams with an overview of discovered issues.
- Integrates with Defender for Cloud for contextual insights.

### Describe capabilities of Microsoft Sentinel

#### Define the Concepts of SIEM and SOAR
- SIEM and SOAR enhance threat visibility and response.
  - **SIEM:**
    - Collects and analyzes data for alerts and incidents.
  - **SOAR:**
    - Takes alerts, triggers automated workflows to mitigate issues.

####  Describe Threat Detection and Mitigation in Microsoft Sentinel
- **Microsoft Sentinel:**
  - Cloud-native SIEM/SOAR solution.
  - Collects data across users, devices, applications.
  - Detects threats using analytics and threat intelligence.
  - Investigates, responds rapidly, and automates security tasks.
  - Features connectors, workbooks, analytics, and playbooks.

#####  Describe Microsoft Security Copilot
- **Security Copilot:**
  - Generative AI security tool.
  - Defends at machine speed and scale.
  - Key use cases: security posture management, incident response, security reporting.
  - Utilizes a prompt bar for natural language queries.
  - Ensures data privacy and integrates with Microsoft Sentinel.

---

### Describe threat protection with Microsoft 365 Defender

#### Microsoft Defender XDR Simplified
**Microsoft Defender XDR:**
- Enterprise defense suite against cyberattacks.
- Coordinates detection, prevention, investigation, and response.
- Protects endpoints, identities, email, and applications.

#### Endpoint Protection (Microsoft Defender for Endpoint)
- Unified platform for prevention, detection, investigation, and response.
- Core Defender Vulnerability Management.
- Attack Surface Reduction.
- Next-gen protection.
- Endpoint Detection and Response (EDR).
- Automated Investigation and Remediation (AIR).
- Microsoft Secure Score for Devices.
- Microsoft Threat Experts.
- Integrates with Microsoft Defender suite, Intune, and Defender for Cloud.

##### Vulnerability Management (Defender Vulnerability Management)
- Continuous asset visibility and risk-based assessments.
- Asset discovery, monitoring, and inventories.
- Risk-based prioritization.
- Remediation and tracking.
- Dashboard insights.

#### Email Protection (Microsoft Defender for Office 365)
- Safeguards against email threats.
- Preset security policies.
- Threat protection policies.
- Real-time reports.
- Threat investigation and response.
- Automated investigation and response.

#### Identity Protection (Microsoft Defender for Identity)
- Uses Active Directory signals.
- Monitors user behavior.
- Protects user identities and credentials.
- Identifies suspicious activities.
- Incident information on a timeline.

#### Cloud App Protection (Microsoft Defender for Cloud Apps)
- Comprehensive cross-SaaS solution.
- Cloud Access Security Broker (CASB) functionality.
- SaaS Security Posture Management (SSPM).
- Advanced threat protection.
- App-to-app protection.

#### Describe Microsoft Defender Threat Intelligence (Defender TI)
- Access threat intelligence from Defender portal.
- Aggregates critical threat information.
- Vulnerability articles.
- Data sets for infrastructure analysis.
- Reputation scoring and analyst insights.

#### Describe the Microsoft 365 Defender portal
- Centralizes protection, detection, investigation, and response.
- Tailored for security teams.
- Customizable navigation.
- Requires appropriate role in Microsoft Entra ID.

##### Incidents and Alerts
- Alerts form incidents.
- Incident summary includes attack details, alerts, assets, and investigations.

##### Hunting
- Custom detection rules.
- Query-based threat hunting tool.

##### Secure Score
- Representation of security posture.
- Monitors Microsoft 365 identities, apps, and devices.
- Higher score indicates better protection.
- Learning hub for official guidance.
- Unified reports in Microsoft Defender XDR.

##### Differences in Secure Score
- Microsoft Defender XDR: Azure subscription security.
- Microsoft Defender Portal: Organization-wide security across apps, devices, and identities.

## Describe the capabilities of Microsoft compliance solutions (20–25%)
### Describe Microsoft Service Trust Portal and privacy principles

#### Service Trust Portal (STP) and Privacy Principles

##### Service Trust Portal (STP) Content Categories
1. **Certifications, Regulations, Standards:**
   - Security info aiding regulatory compliance.
2. **Reports, Whitepapers, Artifacts:**
   - Documents covering topics like business continuity, penetration tests, privacy, and FAQs.
3. **Industry and Regional Resources:**
   - Industry-specific and regional compliance documents.

##### My Library
- Users can add documents to their library for easy access.
- Notifications alert users about document updates.

#### Microsoft's Privacy Principles
Microsoft prioritizes privacy with six principles:
1. **Control:**
   - Users control their data, and Microsoft complies with privacy laws.
2. **Transparency:**
   - Clearly communicate data collection and use.
3. **Security:**
   - Employ strong encryption to protect data.
4. **Legal Protections:**
   - Respect local privacy laws and fight for legal protection.
5. **No Content-based Targeting:**
   - No use of personal content for targeted advertising.
6. **Benefits to Users:**
   - Collected data aims to benefit users through troubleshooting, feature improvement, and personalized experiences.

#### Microsoft Priva
Privacy concerns rise globally, requiring organizations to adopt a "privacy by default" approach. Microsoft Priva helps organizations meet regulatory requirements, build trust, and address challenges such as:
- Employee data handling practices.
- Understanding risks in stored personal data.
- Efficiently fulfilling data subject requests.

##### Priva Solutions
1. **Priva Privacy Risk Management:**
   - Automates discovery of personal data, provides visualizations, and allows policy setup for risk reduction.
2. **Priva Subject Rights Requests:**
   - Automates and streamlines responses to data subject requests.

---

### Describe compliance management capabilities of Microsoft Purview

#### Microsoft Purview Compliance Portal
- Centralizes tools and data for organization compliance.
- Accessible to Microsoft 365 roles: Global admin, Compliance admin, Compliance data admin.
- Home page cards display compliance status, solutions, and active alerts.
- Default cards include Compliance Manager, Solutions Catalog, and Active Alerts.

#### Compliance Manager
- Part of Microsoft Purview Compliance Portal.
- Aids in managing compliance requirements.
- Features prebuilt assessments, workflow capabilities, and improvement actions.
- Measures compliance with a risk-based score.
- Tracks controls, assessments, templates, and improvement actions.

##### Controls
- Define how to meet a specific regulation, standard, or policy.
- Types: Microsoft-managed, Your controls, Shared controls.
- Continuous assessment in Microsoft 365 environment.

##### Assessments
- Grouping of controls for a specific regulation or standard.
- Components: In-scope services, Microsoft, Your, Shared controls, Assessment score.

##### Templates
- Provided by Compliance Manager for quick assessment creation.
- Admins can modify templates or create custom assessments.

##### Improvement Actions
- Centralize compliance activities.
- Assign to users for implementation and testing.
- Store documentation and track status updates.

##### Benefits of Compliance Manager
- Simplifies complex regulations and policies.
- Offers a variety of assessments for unique needs.
- Maps regulatory controls to improvement actions.
- Provides step-by-step guidance for regulatory compliance.
- Prioritizes actions based on impact.

##### Compliance Score
- Measures progress in completing improvement actions.
- Helps understand current compliance posture.
- Prioritizes actions based on risk reduction potential.
- Categorized as mandatory, discretionary, preventative, detective, or corrective.

##### Difference Between Compliance Manager and Compliance Score
- **Compliance Manager:**
  - Manages and tracks compliance activities.
- **Compliance Score:**
  - Overall compliance posture calculation available through Compliance Manager.
- Both contribute to understanding and improving an organization's compliance.

---

### Describe information protection, data lifecycle management, and data governance capabilities of Microsoft Purview

####  Data Discovery and Classification
##### Overview
- Microsoft Purview helps organizations discover, classify, and protect data.
##### Capabilities
- Discover and understand data landscape.
- Tools: Trainable classifiers, activity explorer, content explorer.
##### Use Cases
- Identify sensitive content.
- Classify data through trainable classifiers, Sensitive Information Types (SIT).

#### Information Protection
##### Overview
- Purview Information Protection ensures data protection throughout its lifecycle.
##### Capabilities
- Know, protect, and prevent data loss.
- Flexible protection actions: encryption, access restrictions.
- Risk detection and prevention.
##### Governance
- Automate data management for compliance.
- Tools: Retention policies, labels, records management.

#### Data Classification in Compliance Portal
##### Overview
- Purview Compliance Portal aids in data classification.
##### Capabilities
- Data classification tools: SIT, trainable classifiers, content explorer, activity explorer.

####  Sensitivity Labels and Policies
##### Overview
- Safeguard data with sensitivity labels and policies.
##### Sensitivity Labels
- Customizable categories (e.g., Personal, Public, Confidential).
- Persistent, clear text labels for content.
##### Policies
- Apply, justify, and enforce label changes.
- Link to custom help pages.

####  Data Loss Prevention (DLP)
##### Overview
- Prevent data loss with DLP policies in Purview.
##### Implementation
- Define policies for Microsoft 365, Office apps, Windows, Cloud apps, and more.
- Deep content analysis and machine learning.
##### Protective Actions
- Policy tips, blocking, quarantine, and monitoring.

####  Endpoint DLP
##### Overview
- Audit and manage user activities on sensitive items on Windows and macOS devices.
##### Examples
- Creation, renaming, copying, printing, accessing through unallowed apps.

#### Retention Policies and Labels
##### Overview
- Manage content lifecycle with retention policies and labels.
##### Actions
- Retain, delete, or retain and then delete.
- Settings for SharePoint, Teams, Viva Engage, Exchange.

####  Records Management
##### Overview
- Purview Records Management for legal and regulatory compliance.
##### Features
- Labeling content as a record.
- Event-based retention, disposition review.

####  Unified Data Governance
##### Overview
- Microsoft Purview provides unified data governance.
##### Components
- Data Map, Data Catalog, Data Estate Insights, Data Policy.
- Addresses challenges in data discovery, security, and documentation.

####  Data Sharing (Preview)
##### Overview
- Purview Data Sharing for secure data sharing within or across organizations.
##### Capabilities
- Centralized management, monitoring, and revocation of data sharing relationships.

### Describe insider risk, eDiscovery, and audit capabilities in Microsoft Purview
#### Insider Risk Management
Microsoft Purview helps detect and address internal risks by configuring policies, managing alerts, triaging, investigating, and taking actions. It covers scenarios like data theft, leaks, and offensive behavior.

##### Communication Compliance
Microsoft Purview scans messages, detects policy violations, and enables admins to configure, investigate, remediate, and monitor compliance. It ensures adherence to corporate, risk, and regulatory policies.

#### eDiscovery Solutions
Microsoft Purview offers Content Search, eDiscovery (Standard), and eDiscovery (Premium) to search, hold, and export electronic evidence. Premium adds advanced workflow, analytics, and machine learning.

#### Audit Solutions
Microsoft Purview provides Audit (Standard) and Audit (Premium) for logging and searching audited activities. Premium offers longer retention, intelligent insights, and enhanced access. Admins need appropriate roles for access.
