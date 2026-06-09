# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WindowsServiceAccountNotSet

- ea: `0x8b50`
- end: `0x8b5b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WindowsServiceAccountNotSet`
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

- `0x8b50`: `ErrorCodes_WindowsServiceAccountNotSet`

## pseudocode

```c

```

## disassembly

```asm
0x8b50  ldstr    aErrorcodesWind// "ErrorCodes_WindowsServiceAccountNotSet"
0x8b55  call     string Keys::GetString(string key)
0x8b5a  ret
```
