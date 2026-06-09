# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SharePointNotInstalled

- ea: `0x8c70`
- end: `0x8c7b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SharePointNotInstalled`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8c70`: `ErrorCodes_SharePointNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x8c70  ldstr    aErrorcodesShar// "ErrorCodes_SharePointNotInstalled"
0x8c75  call     string Keys::GetString(string key)
0x8c7a  ret
```
