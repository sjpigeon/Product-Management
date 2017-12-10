## Monitoring


### **EPIC:** 
- As an application team, I need an automated solution that enables monitoring of cloud-based resources so that I'm enabled to create custom dashboards, reports and alerts and respond in a way that reflects the needs of my customer.

### **What is the corporate strategic benefit?**
- Standardized monitoring enables reliable and repeatable processes. Application teams can use standardized monitoring to generate a unified view of their entire stack. This enables application teams to optimize their performance and responds in a way that reflects the needs of their customers.

### **What is the problem being solved?**
- MHE does not have a standard for enabling application monitoring for cloud-based resources.

### **What is the customer (developer/application team) benefit?**
- DevOps delivery of standardized monitoring for all application teams.
- Monitoring across the entire stack - from the hypervisor and host through the container and to the application itself.
- With monitoring enabled across the entire stack, metrics are gathered and teams can use reports to evaluate the performance of their software via:  
 - Using default dashboards, provided out-of-the box.   
 - Creating customized dashboards - edit the existing dashboard or create a new dashboard to focus on specific metrics.
 - Creating alerts - proactively set resource thresholds and configure notifications (email, IM, etc).

### **What is the capability?**
- Full-stack monitoring occurs at three levels account, container and application. 
- Account-level monitoring will be enabled by DevOps engineering via automation with zero work done by application teams. Specifically, this is monitoring at the virtual host level (hypervisor, OS).
- Container-level monitoring will be enabled by DevOps via 'sample' code. This code provides automated agent installation for a container and is intended to be modified by application teams for use with their specific AWS infrastructure (account ID, credentials, etc) to enable monitoring at the container-level (OS, container, application). Ex: 
  - Cluster Utilization Metrics
  - Cluster Reservation Metrics
  - Service Utilization Metrics
- Application-level monitoring will be enabled by DevOps via documentation. This enables instrumentation of the application to send custom metrics to a monitoring service.

### **What are we doing?**
- For the Account-level, DevOps is creating automation, process and documentation for: 
  - Updating existing MHE Turbot AWS accounts to enable monitoring.
  - Provisioning new MHE Turbot AWS accounts during the on-boarding process to enable monitoring.
- For the Container-level, DevOps is creating sample code and documentation for application teams.  
- For the Application-level, DevOps is creating sample code and documentation for application teams.

### **How are we doing it?**
- Datadog is a monitoring service for cloud-scale applications, bringing together data from servers, databases, tools, and services to present a unified view of an entire stack. These capabilities are provided on a SaaS-based data analytics platform.   
 - Enable metrics collection by Datadog at the account-level using automation:   
   - Updating - Python.  
    - HRM-1053, code run via a Jenkins job with approval from application team (non-Prod) and CAB (Prod).  
    - Automating DataDog AWS Integration  
   - Provisioning - Python.  DONE:  Automating DataDog AWS Integration.  
- Enable metrics collection by Datadog at the container-level using automation: 
  - Terraform sample code  DONE -  
   - Configuration of Data Dog for EC2 Container Service (ECS) Using Terraform
   - Datadog-Docker Integration
- Enable metrics collection by Datadog at the host-level using automation: 
  - Automated Datadog Agent Installation via User Data script - DONE:  HRM-1082, HRM-1083, HRM-1084, HRM-1085, HRM-1086. Instructions for applying script in Terraform listed under 'Code Snippets/Template Library'. 
 - Also fulfills Datapipe on-boarding requirements by installing the following agents:  DONE 
   - Datadog
   - Alertlogic IDS
   - NOD32 Antivirus
   - Tivoli BigFix BES
 - Enable metrics collection by Datadog at the application-level using automation:  
  - Terraform sample code - Won't Fix as teams are using New Relic for APM.
