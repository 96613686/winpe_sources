# Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write

- ea: `0x840`
- end: `0x86a`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldarg.1
0x841  brtrue.s loc_84E
0x843  ldstr    aEventname// "eventName"
0x848  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x84d  throw
0x84e  ldloca.s 0
0x850  initobj  [mscorlib]System.Diagnostics.Tracing.EventSourceOptions
0x856  ldloca.s 1
0x858  initobj  EmptyStruct
0x85e  ldarg.0
0x85f  ldarg.1
0x860  ldloca.s 0
0x862  ldloca.s 1
0x864  call     T0x2B000005
0x869  ret
```
