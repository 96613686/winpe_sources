# Microsoft.Reporting.CommonStrings::get_ServerReportPathDesc

- ea: `0xb90`
- end: `0xb9b`
- name: `Microsoft.Reporting.CommonStrings::get_ServerReportPathDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xb90`: `ServerReportPathDesc`

## pseudocode

```c

```

## disassembly

```asm
0xb90  ldstr    aServerreportpa// "ServerReportPathDesc"
0xb95  call     string Keys::GetString(string key)
0xb9a  ret
```
