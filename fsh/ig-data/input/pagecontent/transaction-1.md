This section describes the PULL-TX of this guide. This transaction is used by the Measure Source and Measure Consumer actors.

### Scope

The Query Measure transaction allows a Measure Consumer to
periodically query about the availability of a resource from an Measure Source.


### Actors Roles

![Figure 2.1-1: Query Measure Use Case Diagram](transaction-1-uc.svg "Figure 2.1-1: Query Measure Use Case Diagram")

**Figure 2.1-1: Query Measure Use Case Diagram**

<table border='1' borderspacing='0'>
<caption><b>Table 2.1-1: Actor Roles</b></caption>
<thead><tr><th>Actor</th><th>Role</th></tr></thead>
<tbody><tr><td><a href="actors_and_transactions.html#measure-source">Measure Source</a></td>
<td>Reports on selected data in response to a query.</td>
</tr>
        <tr><td><a href="actors_and_transactions.html#measure-consumer">Measure Consumer</a></td>
<td>Collects data for reporting</td>
</tr>
        
</tbody>
</table>

### Referenced Standards

<table border='1' borderspacing='0'>
<caption><b>Table 3.71.3-1: Referenced Standards</b></caption>
<thead><tr><th>Standard</th><th>Name</th></tr></thead>
<tbody>
            <tr><td>FHIR-R4</td><td><a href='http://www.hl7.org/FHIR/R4'>HL7 FHIR Release 4.0</a></td></tr>
        
            <tr><td>RFC-7230</td><td><a href='https://ietf.org/rfc/rfc7230.html'>Hypertext Transfer Protocol - HTTP/1.1</a></td></tr>
        
            <tr><td>NDJSON</td><td><a href='http://ndjson.org/'>Newline Delimited JSON</a></td></tr>
        
</tbody>
</table>

### Interactions
        
![Figure 2.1-2: Query Measure Interactions](transaction-1-seq.svg "Figure 2.1-2: Query Measure Interactions")

**Figure 2.1-2: Query Measure Interactions**


#### Search Request





##### Trigger Event - Periodic Reporting Interval Elapsed, or a Query is Initiated by User/System

##### Message Semantics

##### Expected Actions

###### Measure Consumer requests data from a Measure Source.

When the API Option is implemented, the Measure Consumer performs a FHIR Search operation
to retrieve the selected resources.  When the Storage Option is implemented, the Measure Consumer reads resources from external
storage specified by the Measure Source.
                





#### Search Response


The Measure Source returns the results.


##### Trigger Event - Resources have been requested by a Measure Consumer.

##### Message Semantics

##### Expected Actions

###### Measure Source returns Resources

The Measure Source returns the requested resource.


When the API Option is used, the Measure Source will return the selected resources and
an appropriate success response in a Bundle resource following the protocol for the Search operation.  When the Dump
option is used, the Measure Source will return all resources requested by the Measure Consumer.
                    

