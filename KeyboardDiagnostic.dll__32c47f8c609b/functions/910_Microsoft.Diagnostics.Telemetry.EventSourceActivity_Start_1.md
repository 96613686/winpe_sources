# Microsoft.Diagnostics.Telemetry.EventSourceActivity::Start_1

- ea: `0x910`
- end: `0x95d`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::Start_1`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x910`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldarg.0
0x911  ldfld    valuetype State Microsoft.Diagnostics.Telemetry.EventSourceActivity::state
0x916  brfalse.s loc_91E
0x918  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x91d  throw
0x91e  ldarg.0
0x91f  ldc.i4.1
0x920  stfld    valuetype State Microsoft.Diagnostics.Telemetry.EventSourceActivity::state
0x925  ldarg.0
0x926  ldflda   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Diagnostics.Telemetry.EventSourceActivity::startStopOptions
0x92b  ldc.i4.1
0x92c  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSourceOptions::set_Opcode(valuetype [mscorlib]System.Diagnostics.Tracing.EventOpcode)
0x931  ldarg.0
0x932  ldfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x937  ldarg.1
0x938  ldarg.0
0x939  ldflda   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Diagnostics.Telemetry.EventSourceActivity::startStopOptions
0x93e  ldarg.0
0x93f  ldflda   valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x944  ldarg.0
0x945  ldflda   valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::relatedId
0x94a  ldarg.2
0x94b  callvirt T0x2B000008
0x950  ldarg.0
0x951  ldflda   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Diagnostics.Telemetry.EventSourceActivity::startStopOptions
0x956  ldc.i4.2
0x957  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSourceOptions::set_Opcode(valuetype [mscorlib]System.Diagnostics.Tracing.EventOpcode)
0x95c  ret
```
