# System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::.ctor

- ea: `0x530`
- end: `0x547`
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
0x530  ldarg.0
0x531  call     instance void [mscorlib]System.Attribute::.ctor()
0x536  ldarg.0
0x537  ldc.i4.1
0x538  newarr   [mscorlib]System.String
0x53d  dup
0x53e  ldc.i4.0
0x53f  ldarg.1
0x540  stelem.ref
0x541  stfld    string[] System.Runtime.CompilerServices.InterpolatedStringHandlerArgumentAttribute::<Arguments>k__BackingField
0x546  ret
```
