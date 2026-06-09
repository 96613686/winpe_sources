# Microsoft.Diagnostics.Telemetry.EventSourceActivity::.ctor_3

- ea: `0x780`
- end: `0x7bf`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::.ctor_3`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x780`

## pseudocode

```c

```

## disassembly

```asm
0x780  ldarg.0
0x781  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x786  stfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x78b  ldarg.0
0x78c  call     instance void [mscorlib]System.Object::.ctor()
0x791  ldarg.1
0x792  brtrue.s loc_79F
0x794  ldstr    aRelatedactivit// "relatedActivity"
0x799  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x79e  throw
0x79f  ldarg.0
0x7a0  ldarg.1
0x7a1  ldfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x7a6  stfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x7ab  ldarg.0
0x7ac  ldarg.2
0x7ad  stfld    valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Diagnostics.Telemetry.EventSourceActivity::startStopOptions
0x7b2  ldarg.0
0x7b3  ldarg.1
0x7b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x7b9  stfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::relatedId
0x7be  ret
```
