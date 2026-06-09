# Microsoft.Diagnostics.Telemetry.TelemetryEventSource::MeasuresOptions

- ea: `0xa50`
- end: `0xa6a`
- name: `Microsoft.Diagnostics.Telemetry.TelemetryEventSource::MeasuresOptions`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xfc0`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldloca.s 0
0xa52  initobj  [mscorlib]System.Diagnostics.Tracing.EventSourceOptions
0xa58  ldloca.s 0
0xa5a  ldc.i8   0x400000000000
0xa63  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSourceOptions::set_Keywords(valuetype [mscorlib]System.Diagnostics.Tracing.EventKeywords)
0xa68  ldloc.0
0xa69  ret
```
