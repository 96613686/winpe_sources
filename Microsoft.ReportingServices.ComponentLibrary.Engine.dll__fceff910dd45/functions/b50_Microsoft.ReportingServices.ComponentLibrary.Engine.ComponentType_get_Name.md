# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Name

- ea: `0xb50`
- end: `0xb5c`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_Name`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x80`
- `0xa70`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldarg.0
0xb51  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_RdlType()
0xb56  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb5b  ret
```
