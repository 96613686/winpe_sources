# Microsoft.ReportingServices.Library.QueuePollWorker::get_HeartbeatInterval

- ea: `0x13e0`
- end: `0x13e7`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::get_HeartbeatInterval`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1590`
- `0x1e10`
- `0x1f50`

## pseudocode

```c

```

## disassembly

```asm
0x13e0  ldarg.0
0x13e1  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_heartbeatInterval
0x13e6  ret
```
