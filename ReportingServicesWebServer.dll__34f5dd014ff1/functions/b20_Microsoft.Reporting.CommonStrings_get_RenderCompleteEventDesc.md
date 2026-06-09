# Microsoft.Reporting.CommonStrings::get_RenderCompleteEventDesc

- ea: `0xb20`
- end: `0xb2b`
- name: `Microsoft.Reporting.CommonStrings::get_RenderCompleteEventDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xb20`: `RenderCompleteEventDesc`

## pseudocode

```c

```

## disassembly

```asm
0xb20  ldstr    aRendercomplete// "RenderCompleteEventDesc"
0xb25  call     string Keys::GetString(string key)
0xb2a  ret
```
