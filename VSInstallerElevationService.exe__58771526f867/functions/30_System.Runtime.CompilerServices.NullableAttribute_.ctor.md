# System.Runtime.CompilerServices.NullableAttribute::.ctor

- ea: `0x30`
- end: `0x47`
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
0x30  ldarg.0
0x31  call     instance void [mscorlib]System.Attribute::.ctor()
0x36  ldarg.0
0x37  ldc.i4.1
0x38  newarr   [mscorlib]System.Byte
0x3d  dup
0x3e  ldc.i4.0
0x3f  ldarg.1
0x40  stelem.i1
0x41  stfld    unsigned int8[] System.Runtime.CompilerServices.NullableAttribute::NullableFlags
0x46  ret
```
