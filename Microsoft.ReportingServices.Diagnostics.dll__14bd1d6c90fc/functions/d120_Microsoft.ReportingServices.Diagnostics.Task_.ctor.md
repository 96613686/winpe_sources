# Microsoft.ReportingServices.Diagnostics.Task::.ctor

- ea: `0xd120`
- end: `0xd1ad`
- name: `Microsoft.ReportingServices.Diagnostics.Task::.ctor`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd570`

## callees

- `0xd120`
- `0xf350`

## pseudocode

```c

```

## disassembly

```asm
0xd120  ldarg.0
0xd121  newobj   instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::.ctor()
0xd126  stfld    class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::m_trigger
0xd12b  ldarg.0
0xd12c  ldc.i4.1
0xd12d  stfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xd132  ldarg.0
0xd133  ldstr    asc_126C2// ""
0xd138  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_name
0xd13d  ldarg.0
0xd13e  ldstr    asc_126C2// ""
0xd143  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_lastRunStatus
0xd148  ldarg.0
0xd149  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xd14e  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_lastRunTime
0xd153  ldarg.0
0xd154  ldstr    asc_126C2// ""
0xd159  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_eventType
0xd15e  ldarg.0
0xd15f  ldstr    asc_126C2// ""
0xd164  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_eventData
0xd169  ldarg.0
0xd16a  ldc.i4.1
0xd16b  stfld    valuetype Microsoft.ReportingServices.Diagnostics.ScheduleType Microsoft.ReportingServices.Diagnostics.Task::m_type
0xd170  ldarg.0
0xd171  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd176  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::m_id
0xd17b  ldarg.0
0xd17c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xd181  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_nextRunTime
0xd186  ldarg.0
0xd187  call     instance void [mscorlib]System.Object::.ctor()
0xd18c  ldarg.1
0xd18d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd192  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd197  brfalse.s loc_D1A1
0xd199  ldarg.0
0xd19a  ldarg.1
0xd19b  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::m_id
0xd1a0  ret
0xd1a1  ldarg.0
0xd1a2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xd1a7  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::m_id
0xd1ac  ret
```
