# Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState

- ea: `0xda10`
- end: `0xda29`
- name: `Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xdaa0`
- `0xe8d0`

## callees

- `0xd9c0`
- `0xda10`

## pseudocode

```c

```

## disassembly

```asm
0xda10  ldarg.0
0xda11  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xda16  stloc.0
0xda17  ldarg.0
0xda18  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::get_IsRunning()
0xda1d  brfalse.s loc_DA27
0xda1f  ldloc.0
0xda20  ldc.i4   0xEFFFFFFF
0xda25  and
0xda26  stloc.0
0xda27  ldloc.0
0xda28  ret
```
