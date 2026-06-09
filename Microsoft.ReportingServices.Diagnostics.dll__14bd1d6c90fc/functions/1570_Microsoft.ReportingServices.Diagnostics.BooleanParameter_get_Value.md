# Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value

- ea: `0x1570`
- end: `0x157c`
- name: `Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30e0`
- `0x4bd0`

## callees

- `0x1240`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldarg.0
0x1571  callvirt instance object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_BaseValue()
0x1576  unbox.any [mscorlib]System.Boolean
0x157b  ret
```
