# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException

- ea: `0x690`
- end: `0x69b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException`
- size: `11`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4cb0`
- `0x5090`
- `0x8550`
- `0x8610`
- `0x9510`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x690  ldstr    aPropertynullex// "PropertyNullException"
0x695  call     string Keys::GetString(string key)
0x69a  ret
```
