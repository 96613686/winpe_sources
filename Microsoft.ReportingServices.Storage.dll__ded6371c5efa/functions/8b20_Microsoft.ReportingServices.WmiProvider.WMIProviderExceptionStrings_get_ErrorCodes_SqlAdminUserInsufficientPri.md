# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SqlAdminUserInsufficientPrivilege

- ea: `0x8b20`
- end: `0x8b2b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_SqlAdminUserInsufficientPrivilege`
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

- `0x8b20`: `ErrorCodes_SqlAdminUserInsufficientPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x8b20  ldstr    aErrorcodesSqla// "ErrorCodes_SqlAdminUserInsufficientPriv"...
0x8b25  call     string Keys::GetString(string key)
0x8b2a  ret
```
