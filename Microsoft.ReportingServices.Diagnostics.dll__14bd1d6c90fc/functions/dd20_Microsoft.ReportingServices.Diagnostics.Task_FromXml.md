# Microsoft.ReportingServices.Diagnostics.Task::FromXml

- ea: `0xdd20`
- end: `0xdf54`
- name: `Microsoft.ReportingServices.Diagnostics.Task::FromXml`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd570`

## callees

- `0xd830`
- `0xd840`
- `0xdd20`
- `0xdf60`
- `0xdf70`
- `0xdfd0`
- `0xe030`
- `0xe0b0`
- `0xe140`
- `0xe510`
- `0xf350`
- `0xf390`
- `0xf3a0`
- `0xf3e0`
- `0xf3f0`

## string_xrefs

- `0xdd98`: `ScheduleDefinition`

## pseudocode

```c

```

## disassembly

```asm
0xdd20  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xdd25  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0xdd2a  stloc.0
0xdd2b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xdd30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdd35  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0xdd3a  ldarg.1
0xdd3b  brfalse.s loc_DD4A
0xdd3d  ldarg.1
0xdd3e  ldstr    asc_126C2// ""
0xdd43  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdd48  brfalse.s loc_DD51
0xdd4a  ldnull
0xdd4b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0xdd50  throw
0xdd51  ldarg.0
0xdd52  newobj   instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::.ctor()
0xdd57  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_Trigger(class Microsoft.ReportingServices.Diagnostics.TaskTrigger value)
0xdd5c  ldnull
0xdd5d  stloc.1
0xdd5e  ldarg.1
0xdd5f  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(string)
0xdd64  stloc.1
0xdd65  ldloc.1
0xdd66  ldc.i4.2
0xdd67  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0xdd6c  ldloc.1
0xdd6d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xdd72  brtrue.s loc_DD7A
0xdd74  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xdd79  throw
0xdd7a  ldloc.1
0xdd7b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xdd80  ldc.i4.s 0x11
0xdd82  bne.un.s loc_DD92
0xdd84  ldloc.1
0xdd85  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xdd8a  brtrue.s loc_DD92
0xdd8c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xdd91  throw
0xdd92  ldloc.1
0xdd93  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdd98  ldstr    aScheduledefini// "ScheduleDefinition"
0xdd9d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xdda2  brfalse  loc_DEB7
0xdda7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xddac  throw
0xddad  ldloc.1
0xddae  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xddb3  ldc.i4.s 0xF
0xddb5  beq      loc_DEB7
0xddba  ldloc.1
0xddbb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xddc0  ldstr    aEnddate// "EndDate"
0xddc5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xddca  brfalse.s loc_DDE3
0xddcc  ldarg.0
0xddcd  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xddd2  ldarg.0
0xddd3  ldloc.1
0xddd4  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::GetDateTimeValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xddd9  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_EndDate(valuetype [mscorlib]System.DateTime value)
0xddde  br       loc_DEB7
0xdde3  ldloc.1
0xdde4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdde9  ldstr    aStartdatetime// "StartDateTime"
0xddee  call     bool [mscorlib]System.String::op_Equality(string, string)
0xddf3  brfalse.s loc_DE0C
0xddf5  ldarg.0
0xddf6  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xddfb  ldarg.0
0xddfc  ldloc.1
0xddfd  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::GetDateTimeValue(class [System.Xml]System.Xml.XmlTextReader reader)
0xde02  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_StartDate(valuetype [mscorlib]System.DateTime value)
0xde07  br       loc_DEB7
0xde0c  ldloc.1
0xde0d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde12  ldstr    aScheduleflags// "ScheduleFlags"
0xde17  call     bool [mscorlib]System.String::op_Equality(string, string)
0xde1c  brfalse.s loc_DE2A
0xde1e  ldarg.0
0xde1f  ldloc.1
0xde20  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadTaskFlags(class [System.Xml]System.Xml.XmlTextReader reader)
0xde25  br       loc_DEB7
0xde2a  ldloc.1
0xde2b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde30  ldstr    aMinuterecurren// "MinuteRecurrence"
0xde35  call     bool [mscorlib]System.String::op_Equality(string, string)
0xde3a  brfalse.s loc_DE45
0xde3c  ldarg.0
0xde3d  ldloc.1
0xde3e  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadMinutes(class [System.Xml]System.Xml.XmlTextReader reader)
0xde43  br.s     loc_DEB7
0xde45  ldloc.1
0xde46  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde4b  ldstr    aDailyrecurrenc// "DailyRecurrence"
0xde50  call     bool [mscorlib]System.String::op_Equality(string, string)
0xde55  brfalse.s loc_DE60
0xde57  ldarg.0
0xde58  ldloc.1
0xde59  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadDaily(class [System.Xml]System.Xml.XmlTextReader reader)
0xde5e  br.s     loc_DEB7
0xde60  ldloc.1
0xde61  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde66  ldstr    aWeeklyrecurren// "WeeklyRecurrence"
0xde6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xde70  brfalse.s loc_DE7B
0xde72  ldarg.0
0xde73  ldloc.1
0xde74  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadWeekly(class [System.Xml]System.Xml.XmlTextReader reader)
0xde79  br.s     loc_DEB7
0xde7b  ldloc.1
0xde7c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde81  ldstr    aMonthlyrecurre// "MonthlyRecurrence"
0xde86  call     bool [mscorlib]System.String::op_Equality(string, string)
0xde8b  brfalse.s loc_DE96
0xde8d  ldarg.0
0xde8e  ldloc.1
0xde8f  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadMonthly(class [System.Xml]System.Xml.XmlTextReader reader)
0xde94  br.s     loc_DEB7
0xde96  ldloc.1
0xde97  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xde9c  ldstr    aMonthlydowrecu// "MonthlyDOWRecurrence"
0xdea1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdea6  brfalse.s loc_DEB1
0xdea8  ldarg.0
0xdea9  ldloc.1
0xdeaa  call     instance void Microsoft.ReportingServices.Diagnostics.Task::ReadMonthlyDOW(class [System.Xml]System.Xml.XmlTextReader reader)
0xdeaf  br.s     loc_DEB7
0xdeb1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xdeb6  throw
0xdeb7  ldloc.1
0xdeb8  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xdebd  brtrue   loc_DDAD
0xdec2  leave.s  loc_DED4
0xdec4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0xdec9  throw
0xdeca  ldloc.1
0xdecb  brfalse.s loc_DED3
0xdecd  ldloc.1
0xdece  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0xded3  endfinally
0xded4  ldarg.0
0xded5  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdeda  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xdedf  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xdee4  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdee9  brfalse.s loc_DEF6
0xdeeb  ldstr    aStartdatetime// "StartDateTime"
0xdef0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0xdef5  throw
0xdef6  ldarg.0
0xdef7  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdefc  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdf01  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xdf06  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdf0b  brfalse.s loc_DF45
0xdf0d  ldarg.0
0xdf0e  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdf13  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdf18  stloc.2
0xdf19  ldloca.s 2
0xdf1b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xdf20  ldarg.0
0xdf21  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdf26  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xdf2b  stloc.2
0xdf2c  ldloca.s 2
0xdf2e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xdf33  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdf38  brfalse.s loc_DF45
0xdf3a  ldstr    aEnddate// "EndDate"
0xdf3f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xdf44  throw
0xdf45  leave.s  loc_DF53
0xdf47  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xdf4c  ldloc.0
0xdf4d  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0xdf52  endfinally
0xdf53  ret
```
