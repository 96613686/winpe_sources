# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryAlreadyExists

- ea: `0x8a80`
- end: `0x8a8b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_VirtualDirectoryAlreadyExists`
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

- `0x8a80`: `ErrorCodes_VirtualDirectoryAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  ldstr    aErrorcodesVirt_0// "ErrorCodes_VirtualDirectoryAlreadyExist"...
0x8a85  call     string Keys::GetString(string key)
0x8a8a  ret
```
