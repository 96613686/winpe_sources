# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_IISNotInstalled

- ea: `0x8ae0`
- end: `0x8aeb`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_IISNotInstalled`
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

- `0x8ae0`: `ErrorCodes_IISNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x8ae0  ldstr    aErrorcodesIisn// "ErrorCodes_IISNotInstalled"
0x8ae5  call     string Keys::GetString(string key)
0x8aea  ret
```
