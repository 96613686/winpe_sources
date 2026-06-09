# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidSchema

- ea: `0xce0`
- end: `0xceb`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidSchema`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f20`

## callees

- `0x2280`

## string_xrefs

- `0xce0`: `ComponentItem_InvalidSchema`

## pseudocode

```c

```

## disassembly

```asm
0xce0  ldstr    aComponentitemI_1// "ComponentItem_InvalidSchema"
0xce5  call     string Keys::GetString(string key)
0xcea  ret
```
