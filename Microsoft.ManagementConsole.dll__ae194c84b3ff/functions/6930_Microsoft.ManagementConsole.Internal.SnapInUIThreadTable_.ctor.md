# Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::.ctor

- ea: `0x6930`
- end: `0x6942`
- name: `Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4340`

## pseudocode

```c

```

## disassembly

```asm
0x6930  ldarg.0
0x6931  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::.ctor()
0x6936  stfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x693b  ldarg.0
0x693c  call     instance void [mscorlib]System.Object::.ctor()
0x6941  ret
```
