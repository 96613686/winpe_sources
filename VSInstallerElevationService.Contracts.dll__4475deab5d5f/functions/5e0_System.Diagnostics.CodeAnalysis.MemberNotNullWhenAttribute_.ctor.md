# System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute::.ctor

- ea: `0x5e0`
- end: `0x5fe`
- name: `System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  call     instance void [mscorlib]System.Attribute::.ctor()
0x5e6  ldarg.0
0x5e7  ldarg.1
0x5e8  stfld    bool System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute::<ReturnValue>k__BackingField
0x5ed  ldarg.0
0x5ee  ldc.i4.1
0x5ef  newarr   [mscorlib]System.String
0x5f4  dup
0x5f5  ldc.i4.0
0x5f6  ldarg.2
0x5f7  stelem.ref
0x5f8  stfld    string[] System.Diagnostics.CodeAnalysis.MemberNotNullWhenAttribute::<Members>k__BackingField
0x5fd  ret
```
