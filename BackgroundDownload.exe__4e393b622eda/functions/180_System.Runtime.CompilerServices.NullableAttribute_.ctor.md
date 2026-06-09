# System.Runtime.CompilerServices.NullableAttribute::.ctor

- ea: `0x180`
- end: `0x197`
- name: `System.Runtime.CompilerServices.NullableAttribute::.ctor`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.0
0x181  call     instance void [mscorlib]System.Attribute::.ctor()
0x186  ldarg.0
0x187  ldc.i4.1
0x188  newarr   [mscorlib]System.Byte
0x18d  dup
0x18e  ldc.i4.0
0x18f  ldarg.1
0x190  stelem.i1
0x191  stfld    unsigned int8[] System.Runtime.CompilerServices.NullableAttribute::NullableFlags
0x196  ret
```
