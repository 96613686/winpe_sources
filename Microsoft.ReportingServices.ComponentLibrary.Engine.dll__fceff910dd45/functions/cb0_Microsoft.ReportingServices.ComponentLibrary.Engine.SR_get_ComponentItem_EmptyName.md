# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_EmptyName

- ea: `0xcb0`
- end: `0xcbb`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_EmptyName`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x120`

## callees

- `0x2280`

## string_xrefs

- `0xcb0`: `ComponentItem_EmptyName`

## pseudocode

```c

```

## disassembly

```asm
0xcb0  ldstr    aComponentitemE// "ComponentItem_EmptyName"
0xcb5  call     string Keys::GetString(string key)
0xcba  ret
```
