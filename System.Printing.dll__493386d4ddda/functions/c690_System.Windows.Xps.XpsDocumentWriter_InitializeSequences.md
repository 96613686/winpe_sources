# System.Windows.Xps.XpsDocumentWriter::InitializeSequences

- ea: `0xc690`
- end: `0xc6df`
- name: `System.Windows.Xps.XpsDocumentWriter::InitializeSequences`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0xb320`
- `0xb390`
- `0xb400`

## callees

- `0xc690`

## pseudocode

```c

```

## disassembly

```asm
0xc690  ldarg.0
0xc691  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xc696  stfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc69b  ldc.i4.4
0xc69c  stloc.1
0xc69d  ldarg.0
0xc69e  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc6a3  ldc.i4.1
0xc6a4  box      [mscorlib]System.Int32
0xc6a9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc6ae  pop
0xc6af  ldloc.1
0xc6b0  ldc.i4.m1
0xc6b1  add
0xc6b2  stloc.1
0xc6b3  ldloc.1
0xc6b4  ldc.i4.0
0xc6b5  bgt.un.s loc_C69D
0xc6b7  ldarg.0
0xc6b8  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xc6bd  stfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc6c2  ldc.i4.4
0xc6c3  stloc.0
0xc6c4  ldarg.0
0xc6c5  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_writingProgressSequences
0xc6ca  ldc.i4.1
0xc6cb  box      [mscorlib]System.Int32
0xc6d0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc6d5  pop
0xc6d6  ldloc.0
0xc6d7  ldc.i4.m1
0xc6d8  add
0xc6d9  stloc.0
0xc6da  ldloc.0
0xc6db  ldc.i4.0
0xc6dc  bgt.un.s loc_C6C4
0xc6de  ret
```
