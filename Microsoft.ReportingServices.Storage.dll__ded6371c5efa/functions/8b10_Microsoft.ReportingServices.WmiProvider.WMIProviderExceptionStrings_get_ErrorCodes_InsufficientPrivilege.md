# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InsufficientPrivilege

- ea: `0x8b10`
- end: `0x8b1b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_InsufficientPrivilege`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8b10`: `ErrorCodes_InsufficientPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x8b10  ldstr    aErrorcodesInsu// "ErrorCodes_InsufficientPrivilege"
0x8b15  call     string Keys::GetString(string key)
0x8b1a  ret
```
