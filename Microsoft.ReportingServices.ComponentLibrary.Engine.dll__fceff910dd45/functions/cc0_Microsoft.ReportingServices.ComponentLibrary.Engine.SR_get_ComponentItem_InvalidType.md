# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidType

- ea: `0xcc0`
- end: `0xccb`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidType`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x80`
- `0x160`

## callees

- `0x2280`

## string_xrefs

- `0xcc0`: `ComponentItem_InvalidType`

## pseudocode

```c

```

## disassembly

```asm
0xcc0  ldstr    aComponentitemI// "ComponentItem_InvalidType"
0xcc5  call     string Keys::GetString(string key)
0xcca  ret
```
