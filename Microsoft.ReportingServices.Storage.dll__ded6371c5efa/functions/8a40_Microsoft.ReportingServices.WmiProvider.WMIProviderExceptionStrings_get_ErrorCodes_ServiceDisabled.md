# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceDisabled

- ea: `0x8a40`
- end: `0x8a4b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceDisabled`
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

- `0x8a40`: `ErrorCodes_ServiceDisabled`

## pseudocode

```c

```

## disassembly

```asm
0x8a40  ldstr    aErrorcodesServ_0// "ErrorCodes_ServiceDisabled"
0x8a45  call     string Keys::GetString(string key)
0x8a4a  ret
```
