# Microsoft.ReportingServices.Diagnostics.Task::ReadWeekly

- ea: `0xe030`
- end: `0xe0aa`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadWeekly`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xdd20`

## callees

- `0xd830`
- `0xe030`
- `0xe360`
- `0xe4e0`
- `0xf630`

## pseudocode

```c

```

## disassembly

```asm
0xe030  ldc.i4.0
0xe031  conv.i8
0xe032  stloc.0
0xe033  ldc.i4.0
0xe034  stloc.1
0xe035  br.s     loc_E094
0xe037  ldarg.1
0xe038  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe03d  ldc.i4.s 0xF
0xe03f  bne.un.s loc_E055
0xe041  ldarg.1
0xe042  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe047  ldstr    aWeeklyrecurren// "WeeklyRecurrence"
0xe04c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe051  brfalse.s loc_E094
0xe053  br.s     loc_E09C
0xe055  ldarg.1
0xe056  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe05b  ldstr    aWeeksinterval// "WeeksInterval"
0xe060  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe065  brfalse.s loc_E072
0xe067  ldarg.0
0xe068  ldarg.1
0xe069  call     instance int32 Microsoft.ReportingServices.Diagnostics.Task::GetIntElementValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xe06e  conv.i8
0xe06f  stloc.0
0xe070  br.s     loc_E094
0xe072  ldarg.1
0xe073  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe078  ldstr    aDaysofweek// "DaysOfWeek"
0xe07d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe082  brfalse.s loc_E08E
0xe084  ldarg.0
0xe085  ldarg.1
0xe086  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Task::ReadDaysOfWeek(class [System.Xml]System.Xml.XmlTextReader reader)
0xe08b  stloc.1
0xe08c  br.s     loc_E094
0xe08e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe093  throw
0xe094  ldarg.1
0xe095  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe09a  brtrue.s loc_E037
0xe09c  ldarg.0
0xe09d  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe0a2  ldloc.0
0xe0a3  ldloc.1
0xe0a4  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToWeekly(int64 weeksInterval, unsigned int32 daysOfWeek)
0xe0a9  ret
```
