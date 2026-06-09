# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidIISPath

- ea: `0x8ad0`
- end: `0x8adb`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InvalidIISPath`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8ad0`: `ErrorCodes_InvalidIISPath`

## pseudocode

```c

```

## disassembly

```asm
0x8ad0  ldstr    aErrorcodesInva// "ErrorCodes_InvalidIISPath"
0x8ad5  call     string Keys::GetString(string key)
0x8ada  ret
```
