# System.Runtime.CompilerServices.CollectionBuilderAttribute::.ctor

- ea: `0x490`
- end: `0x4a5`
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
0x490  ldarg.0
0x491  call     instance void [mscorlib]System.Attribute::.ctor()
0x496  ldarg.0
0x497  ldarg.1
0x498  stfld    class [mscorlib]System.Type System.Runtime.CompilerServices.CollectionBuilderAttribute::<BuilderType>k__BackingField
0x49d  ldarg.0
0x49e  ldarg.2
0x49f  stfld    string System.Runtime.CompilerServices.CollectionBuilderAttribute::<MethodName>k__BackingField
0x4a4  ret
```
