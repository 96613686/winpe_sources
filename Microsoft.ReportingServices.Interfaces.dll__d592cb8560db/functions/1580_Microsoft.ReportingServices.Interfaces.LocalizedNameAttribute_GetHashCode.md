# Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::GetHashCode

- ea: `0x1580`
- end: `0x158c`
- name: `Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::GetHashCode`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1520`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldarg.0
0x1581  call     instance string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name()
0x1586  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x158b  ret
```
