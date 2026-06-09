# Microsoft.Diagnostics.Telemetry.TelemetryEventSource::.ctor

- ea: `0x9f0`
- end: `0x9fe`
- name: `Microsoft.Diagnostics.Telemetry.TelemetryEventSource::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xf00`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldarg.0
0x9f1  ldarg.1
0x9f2  ldc.i4.8
0x9f3  ldsfld   string[] Microsoft.Diagnostics.Telemetry.TelemetryEventSource::MicrosoftTelemetryTraits
0x9f8  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::.ctor(string, valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceSettings, string[])
0x9fd  ret
```
