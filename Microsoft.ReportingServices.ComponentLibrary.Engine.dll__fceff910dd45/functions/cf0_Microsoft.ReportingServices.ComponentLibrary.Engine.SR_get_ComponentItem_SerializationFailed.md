# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_SerializationFailed

- ea: `0xcf0`
- end: `0xcfb`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_SerializationFailed`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x350`

## callees

- `0x2280`

## string_xrefs

- `0xcf0`: `ComponentItem_SerializationFailed`

## pseudocode

```c

```

## disassembly

```asm
0xcf0  ldstr    aComponentitemS// "ComponentItem_SerializationFailed"
0xcf5  call     string Keys::GetString(string key)
0xcfa  ret
```
