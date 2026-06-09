# Microsoft.Reporting.CommonStrings::get_ReportNotReadyException

- ea: `0xe00`
- end: `0xe0b`
- name: `Microsoft.Reporting.CommonStrings::get_ReportNotReadyException`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xe00`: `ReportNotReadyException`

## pseudocode

```c

```

## disassembly

```asm
0xe00  ldstr    aReportnotready_0// "ReportNotReadyException"
0xe05  call     string Keys::GetString(string key)
0xe0a  ret
```
