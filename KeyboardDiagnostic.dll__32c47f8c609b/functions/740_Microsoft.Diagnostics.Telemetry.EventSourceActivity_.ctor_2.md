# Microsoft.Diagnostics.Telemetry.EventSourceActivity::.ctor_2

- ea: `0x740`
- end: `0x778`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::.ctor_2`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x740`

## pseudocode

```c

```

## disassembly

```asm
0x740  ldarg.0
0x741  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x746  stfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x74b  ldarg.0
0x74c  call     instance void [mscorlib]System.Object::.ctor()
0x751  ldarg.1
0x752  brtrue.s loc_75F
0x754  ldstr    aRelatedactivit// "relatedActivity"
0x759  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x75e  throw
0x75f  ldarg.0
0x760  ldarg.1
0x761  ldfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x766  stfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x76b  ldarg.0
0x76c  ldarg.1
0x76d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x772  stfld    valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::relatedId
0x777  ret
```
