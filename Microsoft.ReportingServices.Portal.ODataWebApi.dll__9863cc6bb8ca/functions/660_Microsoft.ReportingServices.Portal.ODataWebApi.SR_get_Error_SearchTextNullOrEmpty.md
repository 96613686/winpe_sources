# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_Error_SearchTextNullOrEmpty

- ea: `0x660`
- end: `0x66b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_Error_SearchTextNullOrEmpty`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x44c0`
- `0x7fa0`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x660  ldstr    aErrorSearchtex// "Error_SearchTextNullOrEmpty"
0x665  call     string Keys::GetString(string key)
0x66a  ret
```
