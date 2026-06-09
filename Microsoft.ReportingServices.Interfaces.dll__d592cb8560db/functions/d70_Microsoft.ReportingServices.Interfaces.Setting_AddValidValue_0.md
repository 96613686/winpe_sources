# Microsoft.ReportingServices.Interfaces.Setting::AddValidValue_0

- ea: `0xd70`
- end: `0xd8c`
- name: `Microsoft.ReportingServices.Interfaces.Setting::AddValidValue_0`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xbe0`
- `0xc00`
- `0xc10`
- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd70  newobj   instance void Microsoft.ReportingServices.Interfaces.ValidValue::.ctor()
0xd75  stloc.0
0xd76  ldloc.0
0xd77  ldarg.2
0xd78  callvirt instance void Microsoft.ReportingServices.Interfaces.ValidValue::set_Value(string value)
0xd7d  ldloc.0
0xd7e  ldarg.1
0xd7f  callvirt instance void Microsoft.ReportingServices.Interfaces.ValidValue::set_Label(string value)
0xd84  ldarg.0
0xd85  ldloc.0
0xd86  call     instance void Microsoft.ReportingServices.Interfaces.Setting::AddValidValue(class Microsoft.ReportingServices.Interfaces.ValidValue val)
0xd8b  ret
```
