# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ManagementException_AccessDenied

- ea: `0x8a10`
- end: `0x8a1b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ManagementException_AccessDenied`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8660`

## callees

- `0x99b0`

## string_xrefs

- `0x8a10`: `ManagementException_AccessDenied`

## pseudocode

```c

```

## disassembly

```asm
0x8a10  ldstr    aManagementexce// "ManagementException_AccessDenied"
0x8a15  call     string Keys::GetString(string key)
0x8a1a  ret
```
