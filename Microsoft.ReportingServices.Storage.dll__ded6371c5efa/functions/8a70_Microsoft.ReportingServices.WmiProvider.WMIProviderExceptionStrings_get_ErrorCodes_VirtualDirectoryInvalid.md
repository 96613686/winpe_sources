# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryInvalid

- ea: `0x8a70`
- end: `0x8a7b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryInvalid`
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

- `0x8a70`: `ErrorCodes_VirtualDirectoryInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x8a70  ldstr    aErrorcodesVirt// "ErrorCodes_VirtualDirectoryInvalid"
0x8a75  call     string Keys::GetString(string key)
0x8a7a  ret
```
