# Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate

- ea: `0xf3e0`
- end: `0xf3e7`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate`
- size: `7`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xdb40`
- `0xdc40`
- `0xdd20`
- `0xe7d0`
- `0xe800`
- `0xf490`

## pseudocode

```c

```

## disassembly

```asm
0xf3e0  ldarg.0
0xf3e1  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::m_endDate
0xf3e6  ret
```
