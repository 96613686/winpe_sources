# Microsoft.Reporting.WebForms.Errors::get_SessionOrConfig

- ea: `0x24ea0`
- end: `0x24eab`
- name: `Microsoft.Reporting.WebForms.Errors::get_SessionOrConfig`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2cf0`

## callees

- `0x3b9e0`

## string_xrefs

- `0x24ea0`: `SessionOrConfig`

## pseudocode

```c

```

## disassembly

```asm
0x24ea0  ldstr    aSessionorconfi// "SessionOrConfig"
0x24ea5  call     string Keys::GetString(string key)
0x24eaa  ret
```
