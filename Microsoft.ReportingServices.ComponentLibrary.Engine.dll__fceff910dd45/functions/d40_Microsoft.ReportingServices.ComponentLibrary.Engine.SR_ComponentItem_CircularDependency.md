# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependency

- ea: `0xd40`
- end: `0xd4c`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependency`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a60`

## callees

- `0x22a0`

## string_xrefs

- `0xd40`: `ComponentItem_CircularDependency`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldstr    aComponentitemC_2// "ComponentItem_CircularDependency"
0xd45  ldarg.0
0xd46  call     string Keys::GetString(string key, object arg0)
0xd4b  ret
```
