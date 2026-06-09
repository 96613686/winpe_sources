# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_MustCreateVirtualDirectory

- ea: `0x8c80`
- end: `0x8c8b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_MustCreateVirtualDirectory`
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

- `0x8c80`: `ErrorCodes_MustCreateVirtualDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x8c80  ldstr    aErrorcodesMust// "ErrorCodes_MustCreateVirtualDirectory"
0x8c85  call     string Keys::GetString(string key)
0x8c8a  ret
```
