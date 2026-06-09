# Microsoft.Diagnostics.Telemetry.TelemetryEventSource::.cctor

- ea: `0xa70`
- end: `0xaa7`
- name: `Microsoft.Diagnostics.Telemetry.TelemetryEventSource::.cctor`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldc.i4.2
0xa71  newarr   [mscorlib]System.String
0xa76  dup
0xa77  ldc.i4.0
0xa78  ldstr    aEtwGroup// "ETW_GROUP"
0xa7d  stelem.ref
0xa7e  dup
0xa7f  ldc.i4.1
0xa80  ldstr    a4f50731a89cf47// "{4f50731a-89cf-4782-b3e0-dce8c90476ba}"
0xa85  stelem.ref
0xa86  stsfld   string[] Microsoft.Diagnostics.Telemetry.TelemetryEventSource::MicrosoftTelemetryTraits
0xa8b  ldc.i4.2
0xa8c  newarr   [mscorlib]System.String
0xa91  dup
0xa92  ldc.i4.0
0xa93  ldstr    aEtwGroup// "ETW_GROUP"
0xa98  stelem.ref
0xa99  dup
0xa9a  ldc.i4.1
0xa9b  ldstr    aC7de053a0c2e4a// "{c7de053a-0c2e-4a44-91a2-5222ec2ecdf1}"
0xaa0  stelem.ref
0xaa1  stsfld   string[] Microsoft.Diagnostics.Telemetry.TelemetryEventSource::WindowsCoreTelemetryTraits
0xaa6  ret
```
