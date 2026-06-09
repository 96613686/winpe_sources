# Microsoft.ReportingServices.Diagnostics.Task::ReadDaysOfWeek

- ea: `0xe360`
- end: `0xe4a8`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadDaysOfWeek`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe030`
- `0xe140`

## callees

- `0xe360`
- `0xe4b0`

## pseudocode

```c

```

## disassembly

```asm
0xe360  ldc.i4.0
0xe361  stloc.0
0xe362  br       loc_E48D
0xe367  ldarg.1
0xe368  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe36d  ldc.i4.s 0xF
0xe36f  bne.un.s loc_E38B
0xe371  ldarg.1
0xe372  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe377  ldstr    aDaysofweek// "DaysOfWeek"
0xe37c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe381  brfalse  loc_E48D
0xe386  br       loc_E498
0xe38b  ldarg.1
0xe38c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe391  ldstr    aSunday// "Sunday"
0xe396  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe39b  brfalse.s loc_E3B2
0xe39d  ldarg.0
0xe39e  ldarg.1
0xe39f  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe3a4  brfalse  loc_E48D
0xe3a9  ldloc.0
0xe3aa  ldc.i4.1
0xe3ab  or
0xe3ac  stloc.0
0xe3ad  br       loc_E48D
0xe3b2  ldarg.1
0xe3b3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe3b8  ldstr    aMonday// "Monday"
0xe3bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe3c2  brfalse.s loc_E3D9
0xe3c4  ldarg.0
0xe3c5  ldarg.1
0xe3c6  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe3cb  brfalse  loc_E48D
0xe3d0  ldloc.0
0xe3d1  ldc.i4.2
0xe3d2  or
0xe3d3  stloc.0
0xe3d4  br       loc_E48D
0xe3d9  ldarg.1
0xe3da  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe3df  ldstr    aTuesday// "Tuesday"
0xe3e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe3e9  brfalse.s loc_E400
0xe3eb  ldarg.0
0xe3ec  ldarg.1
0xe3ed  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe3f2  brfalse  loc_E48D
0xe3f7  ldloc.0
0xe3f8  ldc.i4.4
0xe3f9  or
0xe3fa  stloc.0
0xe3fb  br       loc_E48D
0xe400  ldarg.1
0xe401  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe406  ldstr    aWednesday// "Wednesday"
0xe40b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe410  brfalse.s loc_E421
0xe412  ldarg.0
0xe413  ldarg.1
0xe414  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe419  brfalse.s loc_E48D
0xe41b  ldloc.0
0xe41c  ldc.i4.8
0xe41d  or
0xe41e  stloc.0
0xe41f  br.s     loc_E48D
0xe421  ldarg.1
0xe422  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe427  ldstr    aThursday// "Thursday"
0xe42c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe431  brfalse.s loc_E443
0xe433  ldarg.0
0xe434  ldarg.1
0xe435  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe43a  brfalse.s loc_E48D
0xe43c  ldloc.0
0xe43d  ldc.i4.s 0x10
0xe43f  or
0xe440  stloc.0
0xe441  br.s     loc_E48D
0xe443  ldarg.1
0xe444  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe449  ldstr    aFriday// "Friday"
0xe44e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe453  brfalse.s loc_E465
0xe455  ldarg.0
0xe456  ldarg.1
0xe457  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe45c  brfalse.s loc_E48D
0xe45e  ldloc.0
0xe45f  ldc.i4.s 0x20
0xe461  or
0xe462  stloc.0
0xe463  br.s     loc_E48D
0xe465  ldarg.1
0xe466  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe46b  ldstr    aSaturday// "Saturday"
0xe470  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe475  brfalse.s loc_E487
0xe477  ldarg.0
0xe478  ldarg.1
0xe479  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::IsTrueXmlValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe47e  brfalse.s loc_E48D
0xe480  ldloc.0
0xe481  ldc.i4.s 0x40
0xe483  or
0xe484  stloc.0
0xe485  br.s     loc_E48D
0xe487  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe48c  throw
0xe48d  ldarg.1
0xe48e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe493  brtrue   loc_E367
0xe498  ldloc.0
0xe499  brtrue.s loc_E4A6
0xe49b  ldstr    aDaysofweek// "DaysOfWeek"
0xe4a0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xe4a5  throw
0xe4a6  ldloc.0
0xe4a7  ret
```
