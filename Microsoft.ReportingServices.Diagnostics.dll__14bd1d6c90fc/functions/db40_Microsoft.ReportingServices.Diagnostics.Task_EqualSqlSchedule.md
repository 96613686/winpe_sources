# Microsoft.ReportingServices.Diagnostics.Task::EqualSqlSchedule

- ea: `0xdb40`
- end: `0xdc32`
- name: `Microsoft.ReportingServices.Diagnostics.Task::EqualSqlSchedule`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0xd830`
- `0xd890`
- `0xd8b0`
- `0xdb40`
- `0xf370`
- `0xf3e0`
- `0xf420`

## pseudocode

```c

```

## disassembly

```asm
0xdb40  ldc.i4.1
0xdb41  stloc.0
0xdb42  ldarg.1
0xdb43  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.TaskFlags Microsoft.ReportingServices.Diagnostics.Task::get_Flags()
0xdb48  ldarg.0
0xdb49  call     instance valuetype Microsoft.ReportingServices.Diagnostics.TaskFlags Microsoft.ReportingServices.Diagnostics.Task::get_Flags()
0xdb4e  beq.s    loc_DB57
0xdb50  ldc.i4.0
0xdb51  stloc.0
0xdb52  br       loc_DC30
0xdb57  ldarg.1
0xdb58  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.Task::get_MaxRunTime()
0xdb5d  ldarg.0
0xdb5e  call     instance int64 Microsoft.ReportingServices.Diagnostics.Task::get_MaxRunTime()
0xdb63  beq.s    loc_DB6C
0xdb65  ldc.i4.0
0xdb66  stloc.0
0xdb67  br       loc_DC30
0xdb6c  ldarg.1
0xdb6d  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdb72  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdb77  ldarg.0
0xdb78  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdb7d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdb82  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdb87  brfalse.s loc_DB90
0xdb89  ldc.i4.0
0xdb8a  stloc.0
0xdb8b  br       loc_DC30
0xdb90  ldarg.1
0xdb91  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdb96  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdb9b  ldarg.0
0xdb9c  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdba1  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdba6  beq.s    loc_DBAF
0xdba8  ldc.i4.0
0xdba9  stloc.0
0xdbaa  br       loc_DC30
0xdbaf  ldarg.1
0xdbb0  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdbb5  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdbba  brfalse.s loc_DC21
0xdbbc  ldarg.1
0xdbbd  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdbc2  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdbc7  ldarg.0
0xdbc8  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdbcd  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdbd2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xdbd7  brtrue.s loc_DC30
0xdbd9  ldarg.1
0xdbda  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdbdf  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdbe4  stloc.1
0xdbe5  ldloca.s 1
0xdbe7  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xdbec  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xdbf1  stloc.1
0xdbf2  ldloca.s 1
0xdbf4  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xdbf9  sub
0xdbfa  ldc.i4.1
0xdbfb  bge.s    loc_DC1D
0xdbfd  ldarg.1
0xdbfe  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdc03  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdc08  ldc.i4.5
0xdc09  beq.s    loc_DC30
0xdc0b  ldarg.1
0xdc0c  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdc11  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdc16  ldc.i4.6
0xdc17  beq.s    loc_DC30
0xdc19  ldc.i4.0
0xdc1a  stloc.0
0xdc1b  br.s     loc_DC30
0xdc1d  ldc.i4.0
0xdc1e  stloc.0
0xdc1f  br.s     loc_DC30
0xdc21  ldarg.0
0xdc22  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdc27  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdc2c  brfalse.s loc_DC30
0xdc2e  ldc.i4.0
0xdc2f  stloc.0
0xdc30  ldloc.0
0xdc31  ret
```
