# Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData

- ea: `0xf370`
- end: `0xf377`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xdb40`
- `0xdc40`
- `0xe800`
- `0xf420`
- `0xf490`

## pseudocode

```c

```

## disassembly

```asm
0xf370  ldarg.0
0xf371  ldfld    class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::m_triggerData
0xf376  ret
```
