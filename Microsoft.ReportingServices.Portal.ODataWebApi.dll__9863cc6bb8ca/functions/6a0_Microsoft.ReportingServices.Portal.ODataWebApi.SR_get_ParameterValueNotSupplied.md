# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied

- ea: `0x6a0`
- end: `0x6ab`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ParameterValueNotSupplied`
- size: `11`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6da0`
- `0x7fe0`
- `0x8040`
- `0x98d0`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldstr    aParametervalue// "ParameterValueNotSupplied"
0x6a5  call     string Keys::GetString(string key)
0x6aa  ret
```
