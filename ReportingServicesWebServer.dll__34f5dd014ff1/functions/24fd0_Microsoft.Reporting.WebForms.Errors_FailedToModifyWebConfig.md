# Microsoft.Reporting.WebForms.Errors::FailedToModifyWebConfig

- ea: `0x24fd0`
- end: `0x24fdc`
- name: `Microsoft.Reporting.WebForms.Errors::FailedToModifyWebConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3ba00`

## string_xrefs

- `0x24fd0`: `FailedToModifyWebConfig`

## pseudocode

```c

```

## disassembly

```asm
0x24fd0  ldstr    aFailedtomodify// "FailedToModifyWebConfig"
0x24fd5  ldarg.0
0x24fd6  call     string Keys::GetString(string key, object arg0)
0x24fdb  ret
```
