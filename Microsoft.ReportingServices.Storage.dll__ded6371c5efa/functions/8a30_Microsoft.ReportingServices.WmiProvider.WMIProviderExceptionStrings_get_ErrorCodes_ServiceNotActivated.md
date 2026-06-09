# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceNotActivated

- ea: `0x8a30`
- end: `0x8a3b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ServiceNotActivated`
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

- `0x8a30`: `ErrorCodes_ServiceNotActivated`

## pseudocode

```c

```

## disassembly

```asm
0x8a30  ldstr    aErrorcodesServ// "ErrorCodes_ServiceNotActivated"
0x8a35  call     string Keys::GetString(string key)
0x8a3a  ret
```
