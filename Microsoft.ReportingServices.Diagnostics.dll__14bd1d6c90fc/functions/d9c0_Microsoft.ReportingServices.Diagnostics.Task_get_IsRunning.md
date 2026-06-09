# Microsoft.ReportingServices.Diagnostics.Task::get_IsRunning

- ea: `0xd9c0`
- end: `0xd9d5`
- name: `Microsoft.ReportingServices.Diagnostics.Task::get_IsRunning`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xda10`
- `0xda30`
- `0xe8d0`

## callees

- `0xd9c0`

## pseudocode

```c

```

## disassembly

```asm
0xd9c0  ldc.i4.0
0xd9c1  stloc.0
0xd9c2  ldarg.0
0xd9c3  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xd9c8  ldc.i4   0x10000000
0xd9cd  and
0xd9ce  ldc.i4.0
0xd9cf  ble.s    loc_D9D3
0xd9d1  ldc.i4.1
0xd9d2  stloc.0
0xd9d3  ldloc.0
0xd9d4  ret
```
