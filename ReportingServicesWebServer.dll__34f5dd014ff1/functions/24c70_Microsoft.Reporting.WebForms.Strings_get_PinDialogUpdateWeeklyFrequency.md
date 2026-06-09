# Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateWeeklyFrequency

- ea: `0x24c70`
- end: `0x24c7b`
- name: `Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateWeeklyFrequency`
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

- `0x24c70`: `PinDialogUpdateWeeklyFrequency`

## pseudocode

```c

```

## disassembly

```asm
0x24c70  ldstr    aPindialogupdat_1// "PinDialogUpdateWeeklyFrequency"
0x24c75  call     string Keys::GetString(string key)
0x24c7a  ret
```
