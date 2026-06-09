# Microsoft.Diagnostics.Telemetry.EventSourceActivity::Dispose

- ea: `0x8d0`
- end: `0x90c`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::Dispose`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8d0`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  ldarg.0
0x8d1  ldfld    valuetype State Microsoft.Diagnostics.Telemetry.EventSourceActivity::state
0x8d6  ldc.i4.1
0x8d7  bne.un.s loc_90B
0x8d9  ldarg.0
0x8da  ldc.i4.2
0x8db  stfld    valuetype State Microsoft.Diagnostics.Telemetry.EventSourceActivity::state
0x8e0  ldloca.s 0
0x8e2  initobj  EmptyStruct
0x8e8  ldarg.0
0x8e9  ldfld    class [mscorlib]System.Diagnostics.Tracing.EventSource Microsoft.Diagnostics.Telemetry.EventSourceActivity::eventSource
0x8ee  ldstr    aDispose// "Dispose"
0x8f3  ldarg.0
0x8f4  ldflda   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Diagnostics.Telemetry.EventSourceActivity::startStopOptions
0x8f9  ldarg.0
0x8fa  ldflda   valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::id
0x8ff  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Diagnostics.Telemetry.EventSourceActivity::emptyGuid
0x904  ldloca.s 0
0x906  callvirt T0x2B000007
0x90b  ret
```
