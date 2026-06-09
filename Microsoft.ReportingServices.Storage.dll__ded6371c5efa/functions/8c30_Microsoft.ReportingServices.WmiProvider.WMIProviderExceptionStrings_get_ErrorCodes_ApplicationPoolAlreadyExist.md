# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ApplicationPoolAlreadyExists

- ea: `0x8c30`
- end: `0x8c3b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ApplicationPoolAlreadyExists`
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

- `0x8c30`: `ErrorCodes_ApplicationPoolAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x8c30  ldstr    aErrorcodesAppl// "ErrorCodes_ApplicationPoolAlreadyExists"
0x8c35  call     string Keys::GetString(string key)
0x8c3a  ret
```
