# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotSupportedException

- ea: `0x6e0`
- end: `0x6eb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_NotSupportedException`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6490`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x6e0  ldstr    aNotsupportedex// "NotSupportedException"
0x6e5  call     string Keys::GetString(string key)
0x6ea  ret
```
