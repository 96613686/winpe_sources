# Microsoft.ReportingServices.Interfaces.Setting::AddValidValue

- ea: `0xd60`
- end: `0xd6e`
- name: `Microsoft.ReportingServices.Interfaces.Setting::AddValidValue`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xd70`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Interfaces.Setting::m_validValues
0xd66  ldarg.1
0xd67  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd6c  pop
0xd6d  ret
```
