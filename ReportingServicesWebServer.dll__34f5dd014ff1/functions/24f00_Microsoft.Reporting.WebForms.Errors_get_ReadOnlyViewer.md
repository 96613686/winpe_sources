# Microsoft.Reporting.WebForms.Errors::get_ReadOnlyViewer

- ea: `0x24f00`
- end: `0x24f0b`
- name: `Microsoft.Reporting.WebForms.Errors::get_ReadOnlyViewer`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12020`
- `0x15580`

## callees

- `0x3b9e0`

## string_xrefs

- `0x24f00`: `ReadOnlyViewer`

## pseudocode

```c

```

## disassembly

```asm
0x24f00  ldstr    aReadonlyviewer// "ReadOnlyViewer"
0x24f05  call     string Keys::GetString(string key)
0x24f0a  ret
```
