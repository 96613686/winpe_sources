# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidContent

- ea: `0xcd0`
- end: `0xcdb`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_InvalidContent`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c0`

## callees

- `0x2280`

## string_xrefs

- `0xcd0`: `ComponentItem_InvalidContent`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldstr    aComponentitemI_0// "ComponentItem_InvalidContent"
0xcd5  call     string Keys::GetString(string key)
0xcda  ret
```
