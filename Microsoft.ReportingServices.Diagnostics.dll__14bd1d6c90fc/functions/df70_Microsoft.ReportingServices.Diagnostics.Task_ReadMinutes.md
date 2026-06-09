# Microsoft.ReportingServices.Diagnostics.Task::ReadMinutes

- ea: `0xdf70`
- end: `0xdfc9`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadMinutes`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xdd20`

## callees

- `0xd830`
- `0xdf70`
- `0xe4e0`
- `0xf5f0`

## pseudocode

```c

```

## disassembly

```asm
0xdf70  ldc.i4.0
0xdf71  stloc.0
0xdf72  br.s     loc_DFB4
0xdf74  ldarg.1
0xdf75  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xdf7a  ldc.i4.s 0xF
0xdf7c  bne.un.s loc_DF92
0xdf7e  ldarg.1
0xdf7f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdf84  ldstr    aMinuterecurren// "MinuteRecurrence"
0xdf89  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdf8e  brfalse.s loc_DFB4
0xdf90  br.s     loc_DFBC
0xdf92  ldarg.1
0xdf93  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdf98  ldstr    aMinutesinterva// "MinutesInterval"
0xdf9d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfa2  brfalse.s loc_DFAE
0xdfa4  ldarg.0
0xdfa5  ldarg.1
0xdfa6  call     instance int32 Microsoft.ReportingServices.Diagnostics.Task::GetIntElementValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xdfab  stloc.0
0xdfac  br.s     loc_DFB4
0xdfae  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xdfb3  throw
0xdfb4  ldarg.1
0xdfb5  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xdfba  brtrue.s loc_DF74
0xdfbc  ldarg.0
0xdfbd  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdfc2  ldloc.0
0xdfc3  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMinutes(int32 minutesInterval)
0xdfc8  ret
```
