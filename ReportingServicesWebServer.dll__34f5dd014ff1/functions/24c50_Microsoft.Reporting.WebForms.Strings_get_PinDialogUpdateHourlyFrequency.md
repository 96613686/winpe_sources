# Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateHourlyFrequency

- ea: `0x24c50`
- end: `0x24c5b`
- name: `Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateHourlyFrequency`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x38070`

## callees

- `0x3b900`

## string_xrefs

- `0x24c50`: `PinDialogUpdateHourlyFrequency`

## pseudocode

```c

```

## disassembly

```asm
0x24c50  ldstr    aPindialogupdat// "PinDialogUpdateHourlyFrequency"
0x24c55  call     string Keys::GetString(string key)
0x24c5a  ret
```
