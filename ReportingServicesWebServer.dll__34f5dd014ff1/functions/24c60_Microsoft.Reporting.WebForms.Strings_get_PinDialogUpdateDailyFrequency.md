# Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateDailyFrequency

- ea: `0x24c60`
- end: `0x24c6b`
- name: `Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateDailyFrequency`
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

- `0x24c60`: `PinDialogUpdateDailyFrequency`

## pseudocode

```c

```

## disassembly

```asm
0x24c60  ldstr    aPindialogupdat_0// "PinDialogUpdateDailyFrequency"
0x24c65  call     string Keys::GetString(string key)
0x24c6a  ret
```
