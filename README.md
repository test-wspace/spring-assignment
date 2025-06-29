# spring-assignment

This project is a RESTful API built using Java and Spring Boot that allows users to:
- Search drug application records from the [OpenFDA API](https://open.fda.gov/apis/drug/drugsfda/how-to-use-the-endpoint/)
- Store selected records locally in a MongoDB database

---

# Features
1.Search drug application records by **substance name** and not yet approved by FDA in paginated response.
2.Store drug record details locally:
  - Application number (used as ID)
  - Substance name
  - Sponsor name

---

# Technologies
- Java 17
- Spring Boot
- Spring Web
- Spring Data MongoDB
- MongoDB (local or Atlas)
- Maven
 
 ---
 
# External API
 
- **OpenFDA Drug Applications API**  
  https://open.fda.gov/apis/drug/drugsfda/how-to-use-the-endpoint/
 
---

# Getting Started

# Prerequisites
 
- Java 17
- MongoDB installed locally or a MongoDB Atlas account
- Maven
 
# Setup Instructions
1. **Clone the Repository**
 
git clone https://github.com/test-wspace/spring-assignment.git
cd spring-assignment
 
# Configure MongoDB
spring.data.mongodb.uri=mongodb://localhost:27017/drugrecords
spring.data.mongodb.database=drugrecords
server.port=8080
 
#run the application
./mvnw spring-boot:run
 
#API Endpoints
GET /api/drugs/search?substanceName=aspirin&pageNumber=1&pageSize=10
 
POST /api/drugs/save
 
{
  "applicationNumber": "ANDA123456",
  "substanceName": "aspirin",
  "sponsorName": "Pfizer"
}
 
{
  "_id": "ANDA123456",
  "substanceName": "aspirin",
  "sponsorName": "Pfizer"
}