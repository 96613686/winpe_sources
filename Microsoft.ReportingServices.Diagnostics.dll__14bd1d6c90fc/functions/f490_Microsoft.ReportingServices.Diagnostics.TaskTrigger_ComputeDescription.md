# Microsoft.ReportingServices.Diagnostics.TaskTrigger::ComputeDescription

- ea: `0xf490`
- end: `0xf5d9`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::ComputeDescription`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0xf480`

## callees

- `0xbd70`
- `0xbd80`
- `0xbdb0`
- `0xbdf0`
- `0xbe30`
- `0xbe80`
- `0xbed0`
- `0xed20`
- `0xede0`
- `0xeeb0`
- `0xeed0`
- `0xefd0`
- `0xeff0`
- `0xf090`
- `0xf210`
- `0xf230`
- `0xf250`
- `0xf370`
- `0xf390`
- `0xf3e0`
- `0xf420`
- `0xf490`

## pseudocode

```c

```

## disassembly

```asm
0xf490  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xf495  newobj   instance void Microsoft.ReportingServices.Diagnostics.ScheduleDescription::.ctor(class [mscorlib]System.Globalization.CultureInfo culture)
0xf49a  stloc.0
0xf49b  ldarg.0
0xf49c  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xf4a1  stloc.1
0xf4a2  ldarg.0
0xf4a3  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xf4a8  stloc.2
0xf4a9  ldarg.1
0xf4aa  brfalse.s loc_F4EA
0xf4ac  ldarg.1
0xf4ad  conv.r8
0xf4ae  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xf4b3  stloc.3
0xf4b4  ldloc.1
0xf4b5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xf4ba  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xf4bf  brfalse.s loc_F4CF
0xf4c1  ldloca.s 1
0xf4c3  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xf4c8  ldloc.3
0xf4c9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xf4ce  stloc.1
0xf4cf  ldloc.2
0xf4d0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xf4d5  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xf4da  brfalse.s loc_F4EA
0xf4dc  ldloca.s 2
0xf4de  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xf4e3  ldloc.3
0xf4e4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xf4e9  stloc.2
0xf4ea  ldarg.0
0xf4eb  call     instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xf4f0  stloc.s  4
0xf4f2  ldloc.s  4
0xf4f4  ldc.i4.1
0xf4f5  sub
0xf4f6  switch   loc_F518, loc_F521, loc_F53E, loc_F55B, loc_F57F, loc_F5A8
0xf513  br       loc_F5D3
0xf518  ldloc.0
0xf519  ldloc.1
0xf51a  ldloc.2
0xf51b  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::OnceDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0xf520  ret
0xf521  ldarg.0
0xf522  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf527  castclass Microsoft.ReportingServices.Diagnostics.Minutes
0xf52c  stloc.s  5
0xf52e  ldloc.0
0xf52f  ldloc.1
0xf530  ldloc.2
0xf531  ldloc.s  5
0xf533  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.Minutes::get_MinutesInterval()
0xf538  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MinutesDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, int32 minutes)
0xf53d  ret
0xf53e  ldarg.0
0xf53f  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf544  castclass Microsoft.ReportingServices.Diagnostics.Daily
0xf549  stloc.s  6
0xf54b  ldloc.0
0xf54c  ldloc.1
0xf54d  ldloc.2
0xf54e  ldloc.s  6
0xf550  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.Daily::get_DaysInterval()
0xf555  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::DailyDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, int64 daysInterval)
0xf55a  ret
0xf55b  ldarg.0
0xf55c  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf561  castclass Microsoft.ReportingServices.Diagnostics.Weekly
0xf566  stloc.s  7
0xf568  ldloc.0
0xf569  ldloc.1
0xf56a  ldloc.2
0xf56b  ldloc.s  7
0xf56d  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Weekly::get_DaysOfWeek()
0xf572  ldloc.s  7
0xf574  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.Weekly::get_WeeksInterval()
0xf579  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::WeeklyDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, unsigned int32 daysOfWeek, int64 weeksInterval)
0xf57e  ret
0xf57f  ldarg.0
0xf580  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf585  castclass Microsoft.ReportingServices.Diagnostics.Monthly
0xf58a  stloc.s  8
0xf58c  ldloc.0
0xf58d  ldloc.1
0xf58e  ldloc.2
0xf58f  ldloc.s  8
0xf591  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Monthly::get_DaysOfMonth()
0xf596  call     string Microsoft.ReportingServices.Diagnostics.Monthly::GetDayRange(unsigned int32 dayBitMap)
0xf59b  ldloc.s  8
0xf59d  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Monthly::get_Months()
0xf5a2  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, string daysOfMonth, unsigned int32 months)
0xf5a7  ret
0xf5a8  ldarg.0
0xf5a9  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf5ae  castclass Microsoft.ReportingServices.Diagnostics.MonthlyDOW
0xf5b3  stloc.s  9
0xf5b5  ldloc.0
0xf5b6  ldloc.1
0xf5b7  ldloc.2
0xf5b8  ldloc.s  9
0xf5ba  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_DaysOfWeek()
0xf5bf  ldloc.s  9
0xf5c1  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Week()
0xf5c6  ldloc.s  9
0xf5c8  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Months()
0xf5cd  callvirt instance string Microsoft.ReportingServices.Diagnostics.ScheduleDescription::MonthlyDOWDescription(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, unsigned int32 daysOfWeek, valuetype Microsoft.ReportingServices.Diagnostics.WeeksOfMonth weeks, unsigned int32 months)
0xf5d2  ret
0xf5d3  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xf5d8  throw
```
