# Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write_0

- ea: `0x870`
- end: `0x892`
- name: `Microsoft.Diagnostics.Telemetry.EventSourceActivity::Write_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x870  ldarg.1
0x871  brtrue.s loc_87E
0x873  ldstr    aEventname// "eventName"
0x878  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x87d  throw
0x87e  ldloca.s 0
0x880  initobj  EmptyStruct
0x886  ldarg.0
0x887  ldarg.1
0x888  ldarga.s 2
0x88a  ldloca.s 0
0x88c  call     T0x2B000005
0x891  ret
```
