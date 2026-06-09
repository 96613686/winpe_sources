# Microsoft.Reporting.WebForms.Errors::get_TempStorageNeedsSeekReadWrite

- ea: `0x24f40`
- end: `0x24f4b`
- name: `Microsoft.Reporting.WebForms.Errors::get_TempStorageNeedsSeekReadWrite`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2c90`

## callees

- `0x3b9e0`

## string_xrefs

- `0x24f40`: `TempStorageNeedsSeekReadWrite`

## pseudocode

```c

```

## disassembly

```asm
0x24f40  ldstr    aTempstoragenee// "TempStorageNeedsSeekReadWrite"
0x24f45  call     string Keys::GetString(string key)
0x24f4a  ret
```
