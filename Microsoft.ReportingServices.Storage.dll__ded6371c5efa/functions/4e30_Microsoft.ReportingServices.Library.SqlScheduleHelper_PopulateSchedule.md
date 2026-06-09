# Microsoft.ReportingServices.Library.SqlScheduleHelper::PopulateSchedule

- ea: `0x4e30`
- end: `0x5280`
- name: `Microsoft.ReportingServices.Library.SqlScheduleHelper::PopulateSchedule`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x6970`

## callees

- `0x4e30`
- `0x5280`
- `0x52b0`
- `0x52e0`
- `0x5300`
- `0x5cc0`
- `0x5ce0`

## pseudocode

```c

```

## disassembly

```asm
0x4e30  ldarg.0
0x4e31  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4e36  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::.ctor()
0x4e3b  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Trigger(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger)
0x4e40  ldarg.0
0x4e41  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4e46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x4e4b  stloc.2
0x4e4c  ldloca.s 2
0x4e4e  constrained. [mscorlib]System.Guid
0x4e54  callvirt instance string [mscorlib]System.Object::ToString()
0x4e59  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e5e  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x4e63  stloc.0
0x4e64  ldc.i4.1
0x4e65  stloc.1
0x4e66  br       loc_5274
0x4e6b  ldarg.1
0x4e6c  ldc.i4.3
0x4e6d  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e72  stloc.3
0x4e73  ldarg.1
0x4e74  ldc.i4.4
0x4e75  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e7a  stloc.s  4
0x4e7c  ldarg.1
0x4e7d  ldc.i4.5
0x4e7e  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e83  stloc.s  5
0x4e85  ldarg.1
0x4e86  ldc.i4.6
0x4e87  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e8c  stloc.s  6
0x4e8e  ldarg.1
0x4e8f  ldc.i4.7
0x4e90  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e95  stloc.s  7
0x4e97  ldarg.1
0x4e98  ldc.i4.8
0x4e99  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4e9e  stloc.s  8
0x4ea0  ldarg.1
0x4ea1  ldc.i4.s 9
0x4ea3  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4ea8  stloc.s  9
0x4eaa  ldarg.1
0x4eab  ldc.i4.s 0xA
0x4ead  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4eb2  stloc.s  0xA
0x4eb4  ldarg.1
0x4eb5  ldc.i4.s 0xB
0x4eb7  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4ebc  stloc.s  0xB
0x4ebe  ldarg.1
0x4ebf  ldc.i4.s 0xC
0x4ec1  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4ec6  pop
0x4ec7  ldloc.1
0x4ec8  brfalse  loc_50F6
0x4ecd  ldc.i4.0
0x4ece  stloc.1
0x4ecf  ldloc.s  0xB
0x4ed1  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlTime(int32 time)
0x4ed6  stloc.s  0xC
0x4ed8  ldloc.s  9
0x4eda  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x4edf  stloc.s  0xD
0x4ee1  ldloca.s 0xE
0x4ee3  ldloca.s 0xD
0x4ee5  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x4eea  ldloca.s 0xD
0x4eec  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x4ef1  ldloca.s 0xD
0x4ef3  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x4ef8  ldloca.s 0xC
0x4efa  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x4eff  ldloca.s 0xC
0x4f01  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x4f06  ldloca.s 0xC
0x4f08  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x4f0d  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x4f12  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x4f17  stloc.s  0xF
0x4f19  ldloc.s  0xA
0x4f1b  ldc.i4   0x5F5BEBF
0x4f20  beq.s    loc_4F47
0x4f22  ldloc.s  0xA
0x4f24  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x4f29  stloc.s  0xD
0x4f2b  ldloca.s 0xF
0x4f2d  ldloca.s 0xD
0x4f2f  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x4f34  ldloca.s 0xD
0x4f36  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x4f3b  ldloca.s 0xD
0x4f3d  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x4f42  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x4f47  ldarg.0
0x4f48  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4f4d  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x4f52  ldloc.s  0xE
0x4f54  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_StartDate(valuetype [mscorlib]System.DateTime)
0x4f59  ldarg.0
0x4f5a  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4f5f  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x4f64  ldloc.s  0xF
0x4f66  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_EndDate(valuetype [mscorlib]System.DateTime)
0x4f6b  ldloc.s  5
0x4f6d  ldc.i4.1
0x4f6e  beq.s    loc_4F84
0x4f70  ldloc.3
0x4f71  ldc.i4.1
0x4f72  beq.s    loc_4F84
0x4f74  ldloc.3
0x4f75  ldc.i4.4
0x4f76  beq.s    loc_4F84
0x4f78  ldloc.s  4
0x4f7a  ldc.i4.1
0x4f7b  beq.s    loc_4F84
0x4f7d  ldloc.0
0x4f7e  newobj   instance void Microsoft.ReportingServices.Library.InvalidSqlAgentJobException::.ctor(string taskName)
0x4f83  throw
0x4f84  ldloc.3
0x4f85  stloc.s  0x10
0x4f87  ldloc.s  0x10
0x4f89  ldc.i4.4
0x4f8a  bgt.s    loc_4F9B
0x4f8c  ldloc.s  0x10
0x4f8e  ldc.i4.1
0x4f8f  beq.s    loc_4FB4
0x4f91  ldloc.s  0x10
0x4f93  ldc.i4.4
0x4f94  beq.s    loc_4FC9
0x4f96  br       loc_50EA
0x4f9b  ldloc.s  0x10
0x4f9d  ldc.i4.8
0x4f9e  beq.s    loc_4FFD
0x4fa0  ldloc.s  0x10
0x4fa2  ldc.i4.s 0x10
0x4fa4  beq.s    loc_5017
0x4fa6  ldloc.s  0x10
0x4fa8  ldc.i4.s 0x20
0x4faa  beq      loc_5050
0x4faf  br       loc_50EA
0x4fb4  ldarg.0
0x4fb5  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4fba  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x4fbf  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToOnce()
0x4fc4  br       loc_5274
0x4fc9  ldloc.s  5
0x4fcb  ldc.i4.1
0x4fcc  bne.un.s loc_4FE6
0x4fce  ldarg.0
0x4fcf  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4fd4  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x4fd9  ldloc.s  4
0x4fdb  conv.i8
0x4fdc  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToDaily(int64)
0x4fe1  br       loc_5274
0x4fe6  ldarg.0
0x4fe7  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x4fec  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x4ff1  ldloc.s  6
0x4ff3  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMinutes(int32)
0x4ff8  br       loc_5274
0x4ffd  ldarg.0
0x4ffe  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5003  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5008  ldloc.s  8
0x500a  conv.i8
0x500b  ldloc.s  4
0x500d  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToWeekly(int64, unsigned int32)
0x5012  br       loc_5274
0x5017  ldloc.s  4
0x5019  call     unsigned int32 Microsoft.ReportingServices.Library.SqlScheduleHelper::GetDayBit(int32 day)
0x501e  stloc.s  0x11
0x5020  ldloc.s  9
0x5022  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x5027  stloc.s  0x13
0x5029  ldloca.s 0x13
0x502b  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x5030  call     unsigned int32 Microsoft.ReportingServices.Library.SqlScheduleHelper::ConvertToMonths(int32 month)
0x5035  stloc.s  0x12
0x5037  ldarg.0
0x5038  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x503d  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5042  ldloc.s  0x11
0x5044  ldloc.s  0x12
0x5046  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthly(unsigned int32, unsigned int32)
0x504b  br       loc_5274
0x5050  ldc.i4.0
0x5051  stloc.s  0x14
0x5053  ldloc.s  7
0x5055  stloc.s  0x17
0x5057  ldloc.s  0x17
0x5059  ldc.i4.1
0x505a  sub
0x505b  switch   loc_507D, loc_5082, loc_5096, loc_5087
0x5070  ldloc.s  0x17
0x5072  ldc.i4.8
0x5073  beq.s    loc_508C
0x5075  ldloc.s  0x17
0x5077  ldc.i4.s 0x10
0x5079  beq.s    loc_5091
0x507b  br.s     loc_5096
0x507d  ldc.i4.1
0x507e  stloc.s  0x14
0x5080  br.s     loc_50A2
0x5082  ldc.i4.2
0x5083  stloc.s  0x14
0x5085  br.s     loc_50A2
0x5087  ldc.i4.3
0x5088  stloc.s  0x14
0x508a  br.s     loc_50A2
0x508c  ldc.i4.4
0x508d  stloc.s  0x14
0x508f  br.s     loc_50A2
0x5091  ldc.i4.5
0x5092  stloc.s  0x14
0x5094  br.s     loc_50A2
0x5096  ldloc.0
0x5097  ldstr    aInvalidFreqRel// "invalid freq_relative_interval in FillT"...
0x509c  newobj   instance void Microsoft.ReportingServices.Library.InvalidSqlAgentJobException::.ctor(string taskName, string additionalTraceMessage)
0x50a1  throw
0x50a2  ldc.r8   2.0
0x50ab  ldloc.s  4
0x50ad  ldc.i4.1
0x50ae  sub
0x50af  conv.r8
0x50b0  call     float64 [mscorlib]System.Math::Pow(float64, float64)
0x50b5  conv.u4
0x50b6  stloc.s  0x15
0x50b8  ldloc.s  9
0x50ba  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x50bf  stloc.s  0x13
0x50c1  ldloca.s 0x13
0x50c3  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x50c8  call     unsigned int32 Microsoft.ReportingServices.Library.SqlScheduleHelper::ConvertToMonths(int32 month)
0x50cd  stloc.s  0x16
0x50cf  ldarg.0
0x50d0  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x50d5  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x50da  ldloc.s  0x14
0x50dc  ldloc.s  0x15
0x50de  ldloc.s  0x16
0x50e0  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthlyDOW(unsigned int32, unsigned int32, unsigned int32)
0x50e5  br       loc_5274
0x50ea  ldloc.0
0x50eb  ldstr    aInvalidTrigger// "invalid TriggerType in FillTriggerFromS"...
0x50f0  newobj   instance void Microsoft.ReportingServices.Library.InvalidSqlAgentJobException::.ctor(string taskName, string additionalTraceMessage)
0x50f5  throw
0x50f6  ldloc.3
0x50f7  ldc.i4.s 0x10
0x50f9  beq.s    loc_5107
0x50fb  ldloc.3
0x50fc  ldc.i4.s 0x20
0x50fe  beq.s    loc_5107
0x5100  ldloc.0
0x5101  newobj   instance void Microsoft.ReportingServices.Library.InvalidSqlAgentJobException::.ctor(string taskName)
0x5106  throw
0x5107  ldarg.0
0x5108  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x510d  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5112  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x5117  ldc.i4.5
0x5118  bne.un.s loc_5172
0x511a  ldloc.3
0x511b  ldc.i4.s 0x10
0x511d  bne.un.s loc_5172
0x511f  ldloc.s  9
0x5121  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x5126  stloc.s  0x18
0x5128  ldarg.0
0x5129  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x512e  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5133  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BaseTriggerData [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0x5138  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly
0x513d  ldloc.s  4
0x513f  call     unsigned int32 Microsoft.ReportingServices.Library.SqlScheduleHelper::GetDayBit(int32 day)
0x5144  stloc.s  0x19
0x5146  dup
0x5147  dup
0x5148  callvirt instance unsigned int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::get_DaysOfMonth()
0x514d  ldloc.s  0x19
0x514f  or
0x5150  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::set_DaysOfMonth(unsigned int32)
0x5155  dup
0x5156  callvirt instance unsigned int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::get_Months()
0x515b  ldloca.s 0x18
0x515d  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x5162  call     unsigned int32 Microsoft.ReportingServices.Library.SqlScheduleHelper::ConvertToMonths(int32 month)
0x5167  or
0x5168  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::set_Months(unsigned int32)
0x516d  br       loc_5274
0x5172  ldarg.0
0x5173  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5178  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x517d  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x5182  ldc.i4.6
0x5183  bne.un   loc_526D
  ... truncated ...
```
