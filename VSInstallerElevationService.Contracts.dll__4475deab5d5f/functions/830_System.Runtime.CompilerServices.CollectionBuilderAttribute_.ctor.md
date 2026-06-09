# System.Runtime.CompilerServices.CollectionBuilderAttribute::.ctor

- ea: `0x830`
- end: `0x845`
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
0x830  ldarg.0
0x831  call     instance void [mscorlib]System.Attribute::.ctor()
0x836  ldarg.0
0x837  ldarg.1
0x838  stfld    class [mscorlib]System.Type System.Runtime.CompilerServices.CollectionBuilderAttribute::<BuilderType>k__BackingField
0x83d  ldarg.0
0x83e  ldarg.2
0x83f  stfld    string System.Runtime.CompilerServices.CollectionBuilderAttribute::<MethodName>k__BackingField
0x844  ret
```
