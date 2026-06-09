# Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId

- ea: `0xd600`
- end: `0xd607`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId`
- size: `7`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c40`
- `0xd420`
- `0xd460`
- `0xd510`
- `0xd820`
- `0xd8f0`
- `0xd970`
- `0xdad0`
- `0xdc10`
- `0xddd0`

## pseudocode

```c

```

## disassembly

```asm
0xd600  ldarg.0
0xd601  ldfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_jobId
0xd606  ret
```
