# Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor

- ea: `0x1530`
- end: `0x1545`
- name: `Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30e0`
- `0x4bd0`

## callees

- `0x12c0`

## pseudocode

```c

```

## disassembly

```asm
0x1530  ldarg.0
0x1531  ldarg.1
0x1532  ldarg.2
0x1533  ldarg.3
0x1534  ldarg.s  4
0x1536  ldarg.s  5
0x1538  box      [mscorlib]System.Boolean
0x153d  ldarg.s  6
0x153f  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, object defaultValue, string units)
0x1544  ret
```
