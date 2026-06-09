# Microsoft.Reporting.WebForms.Errors::get_InvalidDeviceInfoLinkTarget

- ea: `0x24f60`
- end: `0x24f6b`
- name: `Microsoft.Reporting.WebForms.Errors::get_InvalidDeviceInfoLinkTarget`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10df0`

## callees

- `0x3b9e0`

## string_xrefs

- `0x24f60`: `InvalidDeviceInfoLinkTarget`

## pseudocode

```c

```

## disassembly

```asm
0x24f60  ldstr    aInvaliddevicei// "InvalidDeviceInfoLinkTarget"
0x24f65  call     string Keys::GetString(string key)
0x24f6a  ret
```
