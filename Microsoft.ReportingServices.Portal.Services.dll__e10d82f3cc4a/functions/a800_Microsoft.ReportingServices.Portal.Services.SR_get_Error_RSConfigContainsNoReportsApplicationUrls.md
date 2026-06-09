# Microsoft.ReportingServices.Portal.Services.SR::get_Error_RSConfigContainsNoReportsApplicationUrls

- ea: `0xa800`
- end: `0xa80b`
- name: `Microsoft.ReportingServices.Portal.Services.SR::get_Error_RSConfigContainsNoReportsApplicationUrls`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x20b30`

## string_xrefs

- `0xa800`: `Error_RSConfigContainsNoReportsApplicationUrls`

## pseudocode

```c

```

## disassembly

```asm
0xa800  ldstr    aErrorRsconfigc// "Error_RSConfigContainsNoReportsApplicat"...
0xa805  call     string Keys::GetString(string key)
0xa80a  ret
```
