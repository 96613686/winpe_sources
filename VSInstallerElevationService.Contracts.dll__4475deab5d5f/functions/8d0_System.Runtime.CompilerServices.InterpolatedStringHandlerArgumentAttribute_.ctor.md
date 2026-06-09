# System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::.ctor

- ea: `0x8d0`
- end: `0x8e7`
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
0x8d0  ldarg.0
0x8d1  call     instance void [mscorlib]System.Attribute::.ctor()
0x8d6  ldarg.0
0x8d7  ldc.i4.1
0x8d8  newarr   [mscorlib]System.String
0x8dd  dup
0x8de  ldc.i4.0
0x8df  ldarg.1
0x8e0  stelem.ref
0x8e1  stfld    string[] System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::<Arguments>k__BackingField
0x8e6  ret
```
