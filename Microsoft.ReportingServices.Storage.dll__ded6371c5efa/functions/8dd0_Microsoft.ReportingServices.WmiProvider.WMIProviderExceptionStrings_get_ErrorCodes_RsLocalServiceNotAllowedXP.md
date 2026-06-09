# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsLocalServiceNotAllowedXP

- ea: `0x8dd0`
- end: `0x8ddb`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsLocalServiceNotAllowedXP`
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

- `0x8dd0`: `ErrorCodes_RsLocalServiceNotAllowedXP`

## pseudocode

```c

```

## disassembly

```asm
0x8dd0  ldstr    aErrorcodesRslo// "ErrorCodes_RsLocalServiceNotAllowedXP"
0x8dd5  call     string Keys::GetString(string key)
0x8dda  ret
```
