---
coding: utf-8

title: A YANG Data Model for the Management of Operations, Administration, and Maintenance (OAM) Tests

abbrev: OAM Tests YANG
docname: draft-contreras-opsawg-oam-tests-yang-00
workgroup: OPSAWG Working Group
category: std
ipr: trust200902

stand_alone: yes
pi: [toc, sortrefs, symrefs, comments]

author:
  -
    name: Luis Miguel Contreras
    org: Telefonica
    email: luismiguel.contrerasmurillo@telefonica.com
  -
    name: Victor Lopez
    org: Nokia
    email: victor.lopez@nokia.com

#contributor:
#  -


--- abstract

This document defines a YANG data model for representing the view of Operations, Administration, and Maintenance (OAM) tests that are part of a Service Provider network. The data model augments ietf-network model by adding the concept of oam-test. The OAM Test concept is a OAM test instance with its life cycle, which relies on OAM node models.

The YANG data model defined in this document conforms to the Network Management Datastore Architecture (NMDA).

--- middle

# Introduction

Operations, Administration, and Maintenance (OAM) tasks are fundamental functionalities of the network management. Given the emerging of data models and their utilization in Service Provider's management, the management of OAM tests has also to be defined as a data model.

Network operator can use OAM tests for the following use cases:
* One-time on-demand validation tasks. For example, after a service is created, the network operator can create a birth certificate obtaining network parameters (latency, losses or bandwidth)
+ Proactive supervision tasks in the network. The network operators can perform continuous monitoring activities to detect, for example, SLA violations on an existing service.
+ Troubleshooting. After the detection of a problem in the network, OAM tests are performed to find the root cause for the detected issue.
- Network Optimization. Delay and loss metrics are monitored in the network to perform automated traffic optimization actions like LSP rerouting.

{{!RFC7276}} presents an overview of OAM tools, summarizes some of the tools for performance monitoring and detecting network failures. {{!RFC8531}} defines a technology-independent YANG model including the key OAM information for the connection-oriented protocols. It uses the concepts of the CFM model as a basis, but it enables the adaptation to other connection-oriented OAM protocols. Similarly, {{!RFC8532}} works in a a technology-independent YANG model, but for the connectionless protocols. {{!RFC8533}} defines presents an on-demand retrieval method YANG data model for conectionless OAM protocols.  

For the use cases presented in this section, 

An OAM test is an execution of a test that an operator want to do in its network. The OAM test as itself has a life cycle, inputs and outputs. There are two major OAM modes: on-demand and periodic. "On-demand" tests are executed once after they are configured in the node. On the other hand, "periodic" tests are those that are configured once, but they are executed several times. An OAM test executed in two different moments will provide different outcomes.

An OAM test-sequence is a set of OAM contains a set of OAM tests which are executed in parallel or sequential stages providing test grouping mechanisms. An OAM test-sequence will have aggregate results, providing a summary of the test results associated with this OAM test-sequence.

The YANG data model defined in this document conforms to the Network Management Datastore Architecture {{!RFC8342}}.

## Terminology and Notations 

This document assumes that the reader is familiar with the contents of {{!RFC7276}}, {{!RFC8531}}, {{!RFC8532}}, and {{!RFC8533}}. The document uses terms from those documents.

The terminology for describing YANG data models is found in {{!RFC7950}}.

  Following terms are used for the representation of this data model. 

  OAM test:

  > a device installed on one or several shelves and can afford some specific transmission function independently.

  OAM test-sequence:

  > a holder of the device and provides power supply for the device in it.

## Requirements Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in {{!BCP14}}, {{!RFC2119}}, {{!RFC8174}} when, and only when, they appear in all capitals, as shown here.

## Tree Diagram

Authors include a simplified graphical representation of the data model is used in {{oam-tests-tree}} of this document.
The meaning of the symbols in these diagrams is defined in {{!RFC8340}}.

## Prefix in Data Node Names

  In this document, names of data nodes and other data model objects are prefixed using the standard prefix associated with the corresponding YANG imported modules, as shown in the following table.

| Prefix | Yang Module            | Reference    |
| ------ | ---------------------- | ------------ |
| oamt   | ietf-oam-tests         | RFCXXX       |
| yang   | ietf-yang-types        | {{!RFC6991}} |
{: #tab-prefixes title="Prefixes and corresponding YANG modules"}

RFC Editor Note:
Please replace XXXX with the RFC number assigned to this document.
Please remove this note.

# YANG Data Model for OAM Tests

## YANG Model Overview



{: #oam-tests-tree}

# OAM Tests Tree Diagram

{{fig-oam-tests-tree}} below shows the tree diagram of the YANG data model defined in module ietf-oam-tests.yang ({{oam-tests-yang}}).

~~~~
{::include ./ietf-oam-tests.tree}
~~~~
{: #fig-oam-tests-tree title="OAM Tests tree diagram"}

{: #oam-tests-yang}

# YANG Model for OAM Tests

~~~~
<CODE BEGINS> file "ietf-oam-tests@2022-03-07.yang"
{::include ./ietf-oam-tests.yang}
~~~~
{: #fig-oam-tests-yang title="OAM Tests YANG module"}

# Manageability Considerations

  \<Add any manageability considerations>

# Security Considerations

  \<Add any security considerations>

# IANA Considerations

  \<Add any IANA considerations>

--- back

{: numbered="false"}

# Acknowledgments

The authors of this document would like to thank XXX.

This document was prepared using kramdown.
