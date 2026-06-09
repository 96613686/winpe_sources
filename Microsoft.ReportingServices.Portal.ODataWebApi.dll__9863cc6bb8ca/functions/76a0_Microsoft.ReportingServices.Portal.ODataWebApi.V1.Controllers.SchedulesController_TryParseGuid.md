# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::TryParseGuid

- ea: `0x76a0`
- end: `0x76b7`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController::TryParseGuid`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x74b0`
- `0x74e0`
- `0x7520`

## pseudocode

```c

```

## disassembly

```asm
0x76a0  ldarg.0
0x76a1  ldstr    asc_1043E// "'"
0x76a6  ldsfld   string [mscorlib]System.String::Empty
0x76ab  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x76b0  ldarg.1
0x76b1  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x76b6  ret
```
