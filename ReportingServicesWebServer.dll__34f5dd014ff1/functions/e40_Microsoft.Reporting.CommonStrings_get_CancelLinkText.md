# Microsoft.Reporting.CommonStrings::get_CancelLinkText

- ea: `0xe40`
- end: `0xe4b`
- name: `Microsoft.Reporting.CommonStrings::get_CancelLinkText`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4ac0`

## callees

- `0x3a3e0`

## string_xrefs

- `0xe40`: `CancelLinkText`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldstr    aCancellinktext// "CancelLinkText"
0xe45  call     string Keys::GetString(string key)
0xe4a  ret
```
