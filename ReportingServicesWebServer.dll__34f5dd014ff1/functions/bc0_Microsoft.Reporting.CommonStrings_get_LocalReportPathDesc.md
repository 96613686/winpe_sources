# Microsoft.Reporting.CommonStrings::get_LocalReportPathDesc

- ea: `0xbc0`
- end: `0xbcb`
- name: `Microsoft.Reporting.CommonStrings::get_LocalReportPathDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xbc0`: `LocalReportPathDesc`

## pseudocode

```c

```

## disassembly

```asm
0xbc0  ldstr    aLocalreportpat// "LocalReportPathDesc"
0xbc5  call     string Keys::GetString(string key)
0xbca  ret
```
