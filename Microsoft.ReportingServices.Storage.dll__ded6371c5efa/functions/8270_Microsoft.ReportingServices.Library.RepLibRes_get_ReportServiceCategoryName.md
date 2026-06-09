# Microsoft.ReportingServices.Library.RepLibRes::get_ReportServiceCategoryName

- ea: `0x8270`
- end: `0x827b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_ReportServiceCategoryName`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x61e0`
- `0x6240`

## callees

- `0x9870`

## string_xrefs

- `0x8270`: `ReportServiceCategoryName`

## pseudocode

```c

```

## disassembly

```asm
0x8270  ldstr    aReportservicec// "ReportServiceCategoryName"
0x8275  call     string Keys::GetString(string key)
0x827a  ret
```
