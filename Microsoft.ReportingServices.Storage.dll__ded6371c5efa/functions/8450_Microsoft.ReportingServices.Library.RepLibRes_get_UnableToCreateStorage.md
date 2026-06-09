# Microsoft.ReportingServices.Library.RepLibRes::get_UnableToCreateStorage

- ea: `0x8450`
- end: `0x845b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_UnableToCreateStorage`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8450`: `UnableToCreateStorage`

## pseudocode

```c

```

## disassembly

```asm
0x8450  ldstr    aUnabletocreate// "UnableToCreateStorage"
0x8455  call     string Keys::GetString(string key)
0x845a  ret
```
