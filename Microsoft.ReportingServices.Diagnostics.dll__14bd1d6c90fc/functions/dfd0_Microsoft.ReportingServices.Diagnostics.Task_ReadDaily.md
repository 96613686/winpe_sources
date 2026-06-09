# Microsoft.ReportingServices.Diagnostics.Task::ReadDaily

- ea: `0xdfd0`
- end: `0xe02b`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadDaily`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xdd20`

## callees

- `0xd830`
- `0xdfd0`
- `0xe4e0`
- `0xf610`

## pseudocode

```c

```

## disassembly

```asm
0xdfd0  ldc.i4.0
0xdfd1  conv.i8
0xdfd2  stloc.0
0xdfd3  br.s     loc_E016
0xdfd5  ldarg.1
0xdfd6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xdfdb  ldc.i4.s 0xF
0xdfdd  bne.un.s loc_DFF3
0xdfdf  ldarg.1
0xdfe0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdfe5  ldstr    aDailyrecurrenc// "DailyRecurrence"
0xdfea  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfef  brfalse.s loc_E016
0xdff1  br.s     loc_E01E
0xdff3  ldarg.1
0xdff4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdff9  ldstr    aDaysinterval// "DaysInterval"
0xdffe  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe003  brfalse.s loc_E010
0xe005  ldarg.0
0xe006  ldarg.1
0xe007  call     instance int32 Microsoft.ReportingServices.Diagnostics.Task::GetIntElementValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe00c  conv.i8
0xe00d  stloc.0
0xe00e  br.s     loc_E016
0xe010  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe015  throw
0xe016  ldarg.1
0xe017  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe01c  brtrue.s loc_DFD5
0xe01e  ldarg.0
0xe01f  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe024  ldloc.0
0xe025  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToDaily(int64 daysInterval)
0xe02a  ret
```
