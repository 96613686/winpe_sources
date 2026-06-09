# System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::.ctor

- ea: `0x680`
- end: `0x697`
- name: `System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::.ctor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldarg.0
0x681  call     instance void [mscorlib]System.Attribute::.ctor()
0x686  ldarg.0
0x687  ldc.i4.1
0x688  newarr   [mscorlib]System.String
0x68d  dup
0x68e  ldc.i4.0
0x68f  ldarg.1
0x690  stelem.ref
0x691  stfld    string[] System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::<Arguments>k__BackingField
0x696  ret
```
