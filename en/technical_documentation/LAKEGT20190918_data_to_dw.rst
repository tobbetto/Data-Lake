==========
Data to DW
==========

.. centered:: |image0|

==================== =================================
Date: 12 August 2019 Responsible area: Technology Area
==================== =================================

`1.INTRODUCTION 2 <#introduction>`__

`1.1 Data Views 2 <#data-views>`__

`1.1.1. Bounces 2 <#bounces>`__

`1.1.2. Clicks 2 <#clicks>`__

`1.1.3. Complaint 2 <#complaint>`__

`1.1.4. Opens 2 <#opens>`__

`1.1.5. Sent 2 <#sent>`__

`1.1.6. Job 2 <#job>`__

`1.2 Data Views complementary 2 <#data-views-complementary>`__

`1.2.1. Subscribers 2 <#subscribers>`__

`1.2.2. Unsubscribers 2 <#unsubscribers>`__

`2. DEVELOPMENT 3 <#development>`__

`2.1 Generate the Data Extensions 3 <#generate-the-data-extensions>`__

`2.2 Generate the Automation 3 <#generate-the-automation>`__

1.INTRODUCTION 
===============

This document describes the development process followed for generating 6 files, which will contain information from certain Data Views in the Salesforce Marketing Cloud environment. Once the files are generated they will be stored in the Marketing Cloud FTP.

Data Views 
-----------

The Data Views that will be extracted and saved to the Marketing Cloud FTP are listed below.

1.1.1. Bounces 
~~~~~~~~~~~~~~~

   This Data View shows all the hard and soft bounces occurring within a specified date range.

1.1.2. Clicks
~~~~~~~~~~~~~

   This Data View shows all instances of a clicked link in an email occurring within the specified date range.

1.1.3. Complaint
~~~~~~~~~~~~~~~~

   This Data View shows spam complaints from subscribers about email sends ocurring within a specified date range.

1.1.4. Opens
~~~~~~~~~~~~

   This Data View shows open instances of an HTML email during the date range.

1.1.5. Sent
~~~~~~~~~~~

   This Data View shows instances of an email send occurring during a specified date range.

1.1.6. Job
~~~~~~~~~~

   This Data View shows the email send Jobs occurring within the specified date range.

Data Views complementary
-------------------------

The following Data Views have been used for the proper development and operation of the process:

1.2.1. Subscribers 
~~~~~~~~~~~~~~~~~~~

   This Data View contains people subscribed to receive email and/or SMS communication in Marketing Cloud.

1.2.2. Unsubscribers 
~~~~~~~~~~~~~~~~~~~~~

   This Data View contains people not subscribed to receive email and/or SMS communication in Marketing Cloud.

2. DEVELOPMENT
==============

The development process has been divided into two parts:

Generate the Data Extensions
----------------------------

   Data Extensions have been created to store the information of each of the Data View used.

   The Data Extensions created for the process are below:

-  VT_DataView_Unsubscribe_today

-  VT_DataView_Unsubscribe

-  VT_DataView_Subscriber_unsubscribed

-  VT_DataView_Subscriber_held

-  VT_DataView_Subscriber_All

-  VT_DataView_Sent_today

-  VT_DataView_Sent

-  VT_DataView_Open_today

-  VT_DataView_Open

-  VT_DataView_Job

-  VT_DataView_Complaint_today

-  VT_DataView_Complaint

-  VT_DataView_Click_today

-  VT_DataView_Click

-  VT_DataView_Bounce_today

-  VT_DataView_Bounce

   2. .. rubric:: Generate the Automation
         :name: generate-the-automation

..

   An Automation has been created that during its execution fills the Data Extensions with the information about Data Views, then creates a file for each of Data Extension and store in FTP Marketing Cloud.

   In this tool each steps corresponds to a column.

|image1|

-  The two first steps fills the Data Extensions with the Data Views information. This part of the process has been divided because in some case an error of “timeout” happend during the query execution.

For the query the field “EventDate” has been used to select the record that happend in the process execution date.

-  In the third step a file is created for each Data Extension.

The kind of file created is .csv, and its name is composed by Data Extension name and the process execution date with the next format: yyyymmdd.

-  In the fourth step the file created is send to FTP Marketing Cloud.

.. |image0| image:: media/image1.png
   :width: 2.73333in
   :height: 3.15357in
.. |image1| image:: media/image6.png
   :width: 6.36042in
   :height: 4.53403in
