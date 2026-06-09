# Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Dispose

- ea: `0x71f0`
- end: `0x7209`
- name: `Microsoft.ReportingServices.Library.InstrumentedSqlCommand::Dispose`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9480`
- `0x94e0`

## callees

- `0x6f20`
- `0x71f0`

## pseudocode

```c

```

## disassembly

```asm
0x71f0  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MeasureSql::.ctor()
0x71f5  stloc.0
0x71f6  ldarg.0
0x71f7  call     instance void Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::Dispose()
0x71fc  leave.s  loc_7208
0x71fe  ldloc.0
0x71ff  brfalse.s loc_7207
0x7201  ldloc.0
0x7202  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7207  endfinally
0x7208  ret
```
