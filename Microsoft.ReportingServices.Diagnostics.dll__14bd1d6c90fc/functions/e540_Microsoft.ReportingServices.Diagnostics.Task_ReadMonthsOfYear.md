# Microsoft.ReportingServices.Diagnostics.Task::ReadMonthsOfYear

- ea: `0xe540`
- end: `0xe75f`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadMonthsOfYear`
- size: `543`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe0b0`
- `0xe140`

## callees

- `0xe4b0`
- `0xe540`

## pseudocode

```c

```

## disassembly

```asm
0xe540  ldc.i4.0
0xe541  stloc.0
0xe542  br       loc_E744
0xe547  ldarg.1
0xe548  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe54d  ldc.i4.s 0xF
0xe54f  bne.un.s loc_E56B
0xe551  ldarg.1
0xe552  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe557  ldstr    aMonthsofyear// "MonthsOfYear"
0xe55c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe561  brfalse  loc_E744
0xe566  br       loc_E74F
0xe56b  ldarg.1
0xe56c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe571  ldstr    aJanuary// "January"
0xe576  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe57b  brfalse.s loc_E592
0xe57d  ldarg.0
0xe57e  ldarg.1
0xe57f  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe584  brfalse  loc_E744
0xe589  ldloc.0
0xe58a  ldc.i4.1
0xe58b  or
0xe58c  stloc.0
0xe58d  br       loc_E744
0xe592  ldarg.1
0xe593  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe598  ldstr    aFebruary// "February"
0xe59d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe5a2  brfalse.s loc_E5B9
0xe5a4  ldarg.0
0xe5a5  ldarg.1
0xe5a6  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe5ab  brfalse  loc_E744
0xe5b0  ldloc.0
0xe5b1  ldc.i4.2
0xe5b2  or
0xe5b3  stloc.0
0xe5b4  br       loc_E744
0xe5b9  ldarg.1
0xe5ba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe5bf  ldstr    aMarch// "March"
0xe5c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe5c9  brfalse.s loc_E5E0
0xe5cb  ldarg.0
0xe5cc  ldarg.1
0xe5cd  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe5d2  brfalse  loc_E744
0xe5d7  ldloc.0
0xe5d8  ldc.i4.4
0xe5d9  or
0xe5da  stloc.0
0xe5db  br       loc_E744
0xe5e0  ldarg.1
0xe5e1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe5e6  ldstr    aApril// "April"
0xe5eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe5f0  brfalse.s loc_E607
0xe5f2  ldarg.0
0xe5f3  ldarg.1
0xe5f4  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe5f9  brfalse  loc_E744
0xe5fe  ldloc.0
0xe5ff  ldc.i4.8
0xe600  or
0xe601  stloc.0
0xe602  br       loc_E744
0xe607  ldarg.1
0xe608  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe60d  ldstr    aMay// "May"
0xe612  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe617  brfalse.s loc_E62F
0xe619  ldarg.0
0xe61a  ldarg.1
0xe61b  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe620  brfalse  loc_E744
0xe625  ldloc.0
0xe626  ldc.i4.s 0x10
0xe628  or
0xe629  stloc.0
0xe62a  br       loc_E744
0xe62f  ldarg.1
0xe630  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe635  ldstr    aJune// "June"
0xe63a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe63f  brfalse.s loc_E657
0xe641  ldarg.0
0xe642  ldarg.1
0xe643  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe648  brfalse  loc_E744
0xe64d  ldloc.0
0xe64e  ldc.i4.s 0x20
0xe650  or
0xe651  stloc.0
0xe652  br       loc_E744
0xe657  ldarg.1
0xe658  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe65d  ldstr    aJuly// "July"
0xe662  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe667  brfalse.s loc_E67F
0xe669  ldarg.0
0xe66a  ldarg.1
0xe66b  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe670  brfalse  loc_E744
0xe675  ldloc.0
0xe676  ldc.i4.s 0x40
0xe678  or
0xe679  stloc.0
0xe67a  br       loc_E744
0xe67f  ldarg.1
0xe680  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe685  ldstr    aAugust// "August"
0xe68a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe68f  brfalse.s loc_E6AA
0xe691  ldarg.0
0xe692  ldarg.1
0xe693  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe698  brfalse  loc_E744
0xe69d  ldloc.0
0xe69e  ldc.i4   0x80
0xe6a3  or
0xe6a4  stloc.0
0xe6a5  br       loc_E744
0xe6aa  ldarg.1
0xe6ab  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe6b0  ldstr    aSeptember// "September"
0xe6b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6ba  brfalse.s loc_E6CF
0xe6bc  ldarg.0
0xe6bd  ldarg.1
0xe6be  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe6c3  brfalse.s loc_E744
0xe6c5  ldloc.0
0xe6c6  ldc.i4   0x100
0xe6cb  or
0xe6cc  stloc.0
0xe6cd  br.s     loc_E744
0xe6cf  ldarg.1
0xe6d0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe6d5  ldstr    aOctober// "October"
0xe6da  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe6df  brfalse.s loc_E6F4
0xe6e1  ldarg.0
0xe6e2  ldarg.1
0xe6e3  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe6e8  brfalse.s loc_E744
0xe6ea  ldloc.0
0xe6eb  ldc.i4   0x200
0xe6f0  or
0xe6f1  stloc.0
0xe6f2  br.s     loc_E744
0xe6f4  ldarg.1
0xe6f5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe6fa  ldstr    aNovember// "November"
0xe6ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe704  brfalse.s loc_E719
0xe706  ldarg.0
0xe707  ldarg.1
0xe708  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe70d  brfalse.s loc_E744
0xe70f  ldloc.0
0xe710  ldc.i4   0x400
0xe715  or
0xe716  stloc.0
0xe717  br.s     loc_E744
0xe719  ldarg.1
0xe71a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe71f  ldstr    aDecember// "December"
0xe724  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe729  brfalse.s loc_E73E
0xe72b  ldarg.0
0xe72c  ldarg.1
0xe72d  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe732  brfalse.s loc_E744
0xe734  ldloc.0
0xe735  ldc.i4   0x800
0xe73a  or
0xe73b  stloc.0
0xe73c  br.s     loc_E744
0xe73e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe743  throw
0xe744  ldarg.1
0xe745  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe74a  brtrue   loc_E547
0xe74f  ldloc.0
0xe750  brtrue.s loc_E75D
0xe752  ldstr    aMonthsofyear// "MonthsOfYear"
0xe757  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xe75c  throw
0xe75d  ldloc.0
0xe75e  ret
```
