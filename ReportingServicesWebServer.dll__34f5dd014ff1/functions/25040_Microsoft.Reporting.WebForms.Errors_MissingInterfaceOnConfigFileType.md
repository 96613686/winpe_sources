# Microsoft.Reporting.WebForms.Errors::MissingInterfaceOnConfigFileType

- ea: `0x25040`
- end: `0x2504d`
- name: `Microsoft.Reporting.WebForms.Errors::MissingInterfaceOnConfigFileType`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c30`

## callees

- `0x3ba20`

## string_xrefs

- `0x25040`: `MissingInterfaceOnConfigFileType`

## pseudocode

```c

```

## disassembly

```asm
0x25040  ldstr    aMissinginterfa// "MissingInterfaceOnConfigFileType"
0x25045  ldarg.0
0x25046  ldarg.1
0x25047  call     string Keys::GetString(string key, object arg0, object arg1)
0x2504c  ret
```
