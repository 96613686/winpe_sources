# Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData

- ea: `0xf380`
- end: `0xf388`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData`
- size: `8`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xf5e0`
- `0xf5f0`
- `0xf610`
- `0xf630`
- `0xf660`
- `0xf680`

## pseudocode

```c

```

## disassembly

```asm
0xf380  ldarg.0
0xf381  ldarg.1
0xf382  stfld    class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::m_triggerData
0xf387  ret
```
