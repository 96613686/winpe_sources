# Microsoft.Reporting.CommonStrings::get_ReportNotReady

- ea: `0x830`
- end: `0x83b`
- name: `Microsoft.Reporting.CommonStrings::get_ReportNotReady`
- size: `11`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23ef0`
- `0x23ff0`
- `0x24020`
- `0x24050`
- `0x24080`
- `0x240b0`
- `0x240f0`
- `0x241b0`

## callees

- `0x3a3e0`

## string_xrefs

- `0x830`: `ReportNotReady`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldstr    aReportnotready// "ReportNotReady"
0x835  call     string Keys::GetString(string key)
0x83a  ret
```
