# System.Runtime.CompilerServices.CollectionBuilderAttribute::.ctor

- ea: `0x5e0`
- end: `0x5f5`
- name: `System.Runtime.CompilerServices.CollectionBuilderAttribute::.ctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  call     instance void [mscorlib]System.Attribute::.ctor()
0x5e6  ldarg.0
0x5e7  ldarg.1
0x5e8  stfld    class [mscorlib]System.Type System.Runtime.CompilerServices.CollectionBuilderAttribute::<BuilderType>k__BackingField
0x5ed  ldarg.0
0x5ee  ldarg.2
0x5ef  stfld    string System.Runtime.CompilerServices.CollectionBuilderAttribute::<MethodName>k__BackingField
0x5f4  ret
```
