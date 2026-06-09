# Microsoft.ReportingServices.Diagnostics.Task::ReadMonthly

- ea: `0xe0b0`
- end: `0xe133`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadMonthly`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xdd20`

## callees

- `0xd830`
- `0xe0b0`
- `0xe540`
- `0xf070`
- `0xf660`

## pseudocode

```c

```

## disassembly

```asm
0xe0b0  ldstr    asc_126C2// ""
0xe0b5  stloc.0
0xe0b6  ldc.i4.0
0xe0b7  stloc.1
0xe0b8  br.s     loc_E115
0xe0ba  ldarg.1
0xe0bb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe0c0  ldc.i4.s 0xF
0xe0c2  bne.un.s loc_E0D8
0xe0c4  ldarg.1
0xe0c5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe0ca  ldstr    aMonthlyrecurre// "MonthlyRecurrence"
0xe0cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe0d4  brfalse.s loc_E115
0xe0d6  br.s     loc_E11D
0xe0d8  ldarg.1
0xe0d9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe0de  ldstr    aDays// "Days"
0xe0e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe0e8  brfalse.s loc_E0F3
0xe0ea  ldarg.1
0xe0eb  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xe0f0  stloc.0
0xe0f1  br.s     loc_E115
0xe0f3  ldarg.1
0xe0f4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe0f9  ldstr    aMonthsofyear// "MonthsOfYear"
0xe0fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe103  brfalse.s loc_E10F
0xe105  ldarg.0
0xe106  ldarg.1
0xe107  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Task::ReadMonthsOfYear(class [System.Xml]System.Xml.XmlTextReader reader)
0xe10c  stloc.1
0xe10d  br.s     loc_E115
0xe10f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe114  throw
0xe115  ldarg.1
0xe116  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe11b  brtrue.s loc_E0BA
0xe11d  ldloc.0
0xe11e  ldloc.1
0xe11f  call     unsigned int32 Microsoft.ReportingServices.Diagnostics.Monthly::GetDayBitMap(string daysString, valuetype Microsoft.ReportingServices.Diagnostics.Months months)
0xe124  stloc.2
0xe125  ldarg.0
0xe126  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe12b  ldloc.2
0xe12c  ldloc.1
0xe12d  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthly(unsigned int32 daysOfMonth, unsigned int32 months)
0xe132  ret
```
