# System.Diagnostics.CodeAnalysis.StringSyntaxAttribute::.ctor

- ea: `0x6f0`
- end: `0x70a`
- name: `System.Diagnostics.CodeAnalysis.StringSyntaxAttribute::.ctor`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  call     instance void [mscorlib]System.Attribute::.ctor()
0x6f6  ldarg.0
0x6f7  ldarg.1
0x6f8  stfld    string System.Diagnostics.CodeAnalysis.StringSyntaxAttribute::<Syntax>k__BackingField
0x6fd  ldarg.0
0x6fe  ldc.i4.0
0x6ff  newarr   [mscorlib]System.Object
0x704  stfld    object[] System.Diagnostics.CodeAnalysis.StringSyntaxAttribute::<Arguments>k__BackingField
0x709  ret
```
