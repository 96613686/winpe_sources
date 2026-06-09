# Microsoft.Reporting.WebForms.Errors::CantFindConfigFileType

- ea: `0x25030`
- end: `0x2503c`
- name: `Microsoft.Reporting.WebForms.Errors::CantFindConfigFileType`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c20`

## callees

- `0x3ba00`

## string_xrefs

- `0x25030`: `CantFindConfigFileType`

## pseudocode

```c

```

## disassembly

```asm
0x25030  ldstr    aCantfindconfig// "CantFindConfigFileType"
0x25035  ldarg.0
0x25036  call     string Keys::GetString(string key, object arg0)
0x2503b  ret
```
