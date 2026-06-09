# Microsoft.ReportingServices.Diagnostics.Task::set_NextRunTime

- ea: `0xdaa0`
- end: `0xdb05`
- name: `Microsoft.ReportingServices.Diagnostics.Task::set_NextRunTime`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`

## callees

- `0xda10`
- `0xda30`
- `0xdaa0`

## pseudocode

```c

```

## disassembly

```asm
0xdaa0  ldarg.0
0xdaa1  ldarga.s 1
0xdaa3  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xdaa8  ldarga.s 1
0xdaaa  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xdaaf  ldarga.s 1
0xdab1  call     instance int32 [mscorlib]System.DateTime::get_Day()
0xdab6  ldarga.s 1
0xdab8  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0xdabd  ldarga.s 1
0xdabf  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0xdac4  ldc.i4.0
0xdac5  ldc.i4.0
0xdac6  ldc.i4.2
0xdac7  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTimeKind)
0xdacc  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_nextRunTime
0xdad1  ldarg.0
0xdad2  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_nextRunTime
0xdad7  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xdadc  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdae1  brfalse.s loc_DAF4
0xdae3  ldarg.0
0xdae4  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xdae9  ldc.i4.2
0xdaea  beq.s    loc_DB04
0xdaec  ldarg.0
0xdaed  ldc.i4.3
0xdaee  stfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xdaf3  ret
0xdaf4  ldarg.0
0xdaf5  call     instance valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState()
0xdafa  ldc.i4.2
0xdafb  beq.s    loc_DB04
0xdafd  ldarg.0
0xdafe  ldc.i4.1
0xdaff  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_ScheduleState(valuetype Microsoft.ReportingServices.Diagnostics.TaskState value)
0xdb04  ret
```
