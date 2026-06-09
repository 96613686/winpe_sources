# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_CreationFailed

- ea: `0xd00`
- end: `0xd0b`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_CreationFailed`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x580`
- `0x5e0`

## callees

- `0x2280`

## string_xrefs

- `0xd00`: `ComponentItem_CreationFailed`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldstr    aComponentitemC// "ComponentItem_CreationFailed"
0xd05  call     string Keys::GetString(string key)
0xd0a  ret
```
