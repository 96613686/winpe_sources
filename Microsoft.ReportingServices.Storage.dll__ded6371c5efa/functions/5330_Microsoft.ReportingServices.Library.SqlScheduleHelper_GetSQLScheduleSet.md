# Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSQLScheduleSet

- ea: `0x5330`
- end: `0x59c7`
- name: `Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSQLScheduleSet`
- size: `1687`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x63e0`

## callees

- `0x49f0`
- `0x4a20`
- `0x4a90`
- `0x4ac0`
- `0x4b10`
- `0x4b40`
- `0x4b90`
- `0x4bc0`
- `0x4c00`
- `0x4c40`
- `0x4c80`
- `0x4cc0`
- `0x4de0`
- `0x5330`

## pseudocode

```c

```

## disassembly

```asm
0x5330  newobj   instance void Microsoft.ReportingServices.Library.SQLScheduleSet::.ctor()
0x5335  stloc.0
0x5336  newobj   instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::.ctor()
0x533b  stloc.1
0x533c  ldarg.0
0x533d  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5342  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5347  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x534c  ldc.i4.5
0x534d  beq      loc_54DF
0x5352  ldarg.0
0x5353  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5358  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x535d  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x5362  ldc.i4.6
0x5363  beq      loc_54DF
0x5368  ldloc.1
0x5369  ldarg.0
0x536a  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x536f  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_SQlFreqType()
0x5374  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyType(int32 type)
0x5379  ldloc.1
0x537a  ldarg.0
0x537b  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5380  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5385  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x538a  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Active_Start_Date(valuetype [mscorlib]System.DateTime date)
0x538f  ldloc.1
0x5390  ldarg.0
0x5391  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5396  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x539b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x53a0  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Active_Start_Time(valuetype [mscorlib]System.DateTime time)
0x53a5  ldarg.0
0x53a6  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x53ab  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x53b0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x53b5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x53ba  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x53bf  brfalse.s loc_53D7
0x53c1  ldloc.1
0x53c2  ldarg.0
0x53c3  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x53c8  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x53cd  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x53d2  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Active_End_Date(valuetype [mscorlib]System.DateTime date)
0x53d7  ldarg.0
0x53d8  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x53dd  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x53e2  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x53e7  stloc.2
0x53e8  ldloc.2
0x53e9  ldc.i4.1
0x53ea  sub
0x53eb  switch   loc_5490, loc_5434, loc_5405, loc_5499
0x5400  br       loc_54D2
0x5405  ldarg.0
0x5406  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x540b  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5410  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BaseTriggerData [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0x5415  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Daily
0x541a  stloc.3
0x541b  ldloc.1
0x541c  ldloc.3
0x541d  callvirt instance int64 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Daily::get_DaysInterval()
0x5422  conv.i4
0x5423  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyInterval(int32 interval)
0x5428  ldloc.1
0x5429  ldc.i4.1
0x542a  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type(int32 type)
0x542f  br       loc_54D2
0x5434  ldarg.0
0x5435  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x543a  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x543f  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BaseTriggerData [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0x5444  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Minutes
0x5449  stloc.s  4
0x544b  ldloc.1
0x544c  ldc.i4.1
0x544d  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyInterval(int32 interval)
0x5452  ldloc.1
0x5453  ldc.i4.4
0x5454  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type(int32 type)
0x5459  ldloc.1
0x545a  ldloc.s  4
0x545c  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Minutes::get_MinutesInterval()
0x5461  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_SubDay_Interval(int32 interval)
0x5466  ldloc.1
0x5467  ldarg.0
0x5468  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x546d  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5472  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x5477  stloc.s  6
0x5479  ldloca.s 6
0x547b  ldc.r8   -1.0
0x5484  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x5489  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Active_End_Time(valuetype [mscorlib]System.DateTime time)
0x548e  br.s     loc_54D2
0x5490  ldloc.1
0x5491  ldc.i4.1
0x5492  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type(int32 type)
0x5497  br.s     loc_54D2
0x5499  ldarg.0
0x549a  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x549f  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x54a4  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BaseTriggerData [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0x54a9  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Weekly
0x54ae  stloc.s  5
0x54b0  ldloc.1
0x54b1  ldloc.s  5
0x54b3  callvirt instance unsigned int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Weekly::get_DaysOfWeek()
0x54b8  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyInterval(int32 interval)
0x54bd  ldloc.1
0x54be  ldc.i4.1
0x54bf  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type(int32 type)
0x54c4  ldloc.1
0x54c5  ldloc.s  5
0x54c7  callvirt instance int64 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Weekly::get_WeeksInterval()
0x54cc  conv.i4
0x54cd  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_Recurrence_factor(int32 factor)
0x54d2  ldloc.0
0x54d3  ldloc.1
0x54d4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x54d9  pop
0x54da  br       loc_59C5
0x54df  ldarg.0
0x54e0  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x54e5  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x54ea  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RecurrenceType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0x54ef  ldc.i4.5
0x54f0  bne.un   loc_5758
0x54f5  ldarg.0
0x54f6  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x54fb  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5500  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BaseTriggerData [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0x5505  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly
0x550a  stloc.s  7
0x550c  ldloc.s  7
0x550e  callvirt instance unsigned int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::get_Months()
0x5513  stloc.s  8
0x5515  ldloc.s  7
0x5517  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::get_IsEveryMonth()
0x551c  stloc.s  9
0x551e  ldc.i4.0
0x551f  stloc.s  0xA
0x5521  ldc.i4.1
0x5522  stloc.s  0xB
0x5524  br       loc_5747
0x5529  ldloc.s  0xA
0x552b  ldc.i4.1
0x552c  add
0x552d  stloc.s  0xA
0x552f  ldloc.s  0xB
0x5531  ldc.i4.1
0x5532  ceq
0x5534  ldc.i4.0
0x5535  ceq
0x5537  ldloc.s  9
0x5539  and
0x553a  brtrue   loc_59C5
0x553f  ldloc.s  8
0x5541  conv.i8
0x5542  ldloc.s  0xB
0x5544  conv.u8
0x5545  and
0x5546  brfalse  loc_5741
0x554b  ldarg.0
0x554c  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5551  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5556  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x555b  stloc.s  0xC
0x555d  ldarg.0
0x555e  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5563  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5568  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x556d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5572  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5577  brfalse.s loc_5595
0x5579  ldloc.s  0xC
0x557b  ldarg.0
0x557c  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5581  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x5586  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x558b  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5590  brtrue   loc_5741
0x5595  ldloc.s  7
0x5597  callvirt instance unsigned int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Monthly::get_DaysOfMonth()
0x559c  stloc.s  0xD
0x559e  ldc.i4.1
0x559f  stloc.s  0xE
0x55a1  ldc.i4.0
0x55a2  stloc.s  0xF
0x55a4  ldc.i4.1
0x55a5  stloc.s  0x10
0x55a7  br       loc_5738
0x55ac  ldloc.s  0xE
0x55ae  ldloc.s  0xD
0x55b0  and
0x55b1  ldc.i4.0
0x55b2  ble.un   loc_572C
0x55b7  ldloc.s  0x10
0x55b9  stloc.s  0xF
0x55bb  ldloc.s  9
0x55bd  brtrue   loc_5661
0x55c2  ldarg.0
0x55c3  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x55c8  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x55cd  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x55d2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x55d7  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x55dc  brtrue.s loc_55F0
0x55de  ldarg.0
0x55df  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x55e4  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x55e9  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0x55ee  br.s     loc_55F5
0x55f0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x55f5  stloc.s  0x11
0x55f7  ldloc.s  0xA
0x55f9  ldloca.s 0x11
0x55fb  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x5600  blt.s    loc_5618
0x5602  ldloc.s  0xA
0x5604  ldloca.s 0x11
0x5606  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x560b  bne.un.s loc_5655
0x560d  ldloc.s  0x10
0x560f  ldloca.s 0x11
0x5611  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x5616  bge.s    loc_5655
0x5618  ldloca.s 0xC
0x561a  ldloca.s 0x11
0x561c  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x5621  ldc.i4.1
0x5622  add
0x5623  ldloc.s  0xA
0x5625  ldc.i4.1
0x5626  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x562b  ldc.i4.s 0x1D
0x562d  ldloc.s  0xF
0x562f  bne.un.s loc_5661
0x5631  ldc.i4.2
0x5632  ldloc.s  0xA
0x5634  bne.un.s loc_5661
0x5636  ldloca.s 0xC
0x5638  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x563d  ldloca.s 0xC
0x563f  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x5644  ldloc.s  0xF
0x5646  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x564b  pop
0x564c  leave.s  loc_5661
0x564e  pop
0x564f  ldc.i4.s 0x1C
0x5651  stloc.s  0xF
0x5653  leave.s  loc_5661
0x5655  ldloc.1
0x5656  ldloc.s  0xB
0x5658  ldloc.s  0x11
0x565a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SQLScheduleParameters::GetStartMonthDate(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Months month, valuetype [mscorlib]System.DateTime date)
0x565f  stloc.s  0xC
0x5661  ldarg.0
0x5662  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5667  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x566c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x5671  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5676  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x567b  brtrue.s loc_5699
0x567d  ldloc.s  0xC
0x567f  ldarg.0
0x5680  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x5685  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0x568a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0x568f  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5694  brfalse  loc_572C
0x5699  ldloc.1
0x569a  ldarg.0
0x569b  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::m_task
0x56a0  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_SQlFreqType()
0x56a5  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyType(int32 type)
0x56aa  ldloc.1
0x56ab  ldc.i4.1
0x56ac  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequency_SubDay_Type(int32 type)
0x56b1  ldloc.s  9
0x56b3  brfalse.s loc_56BE
0x56b5  ldloc.1
0x56b6  ldc.i4.1
0x56b7  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_Recurrence_factor(int32 factor)
0x56bc  br.s     loc_56C6
0x56be  ldloc.1
0x56bf  ldc.i4.s 0xC
0x56c1  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Frequency_Recurrence_factor(int32 factor)
0x56c6  ldloc.1
0x56c7  ldloc.s  0xF
0x56c9  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::AddFrequencyInterval(int32 interval)
0x56ce  ldloc.1
0x56cf  ldloc.s  0xC
0x56d1  callvirt instance void Microsoft.ReportingServices.Library.SQLScheduleParameters::Add_Active_Start_Date(valuetype [mscorlib]System.DateTime date)
0x56d6  ldloc.1
0x56d7  ldarg.0
  ... truncated ...
```
