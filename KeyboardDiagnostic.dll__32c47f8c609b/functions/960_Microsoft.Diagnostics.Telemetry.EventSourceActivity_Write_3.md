# Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write_3

- ea: `0x960`
- end: `0x989`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write_3`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x960`

## pseudocode

```c

```

## disassembly

```asm
0x960  ldarg.0
0x961  ldfld    valuetype State Microsoft.Diagnostics.Telemetry.EventSourceActivity::state
0x966  ldc.i4.1
0x967  beq.s    loc_96F
0x969  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x96e  throw
0x96f  ldarg.0
0x970  ldfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x975  ldarg.1
0x976  ldarg.2
0x977  ldarg.0
0x978  ldflda   valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x97d  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::emptyGuid
0x982  ldarg.3
0x983  callvirt T0x2B000008
0x988  ret
```
