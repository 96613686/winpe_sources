# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_InvalidAggregation

- ea: `0x6f0`
- end: `0x6fb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_InvalidAggregation`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4cb0`
- `0x8610`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldstr    aInvalidaggrega// "InvalidAggregation"
0x6f5  call     string Keys::GetString(string key)
0x6fa  ret
```
