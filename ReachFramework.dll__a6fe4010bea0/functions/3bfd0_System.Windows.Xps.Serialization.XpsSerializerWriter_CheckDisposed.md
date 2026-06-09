# System.Windows.Xps.Serialization.XpsSerializerWriter::CheckDisposed

- ea: `0x3bfd0`
- end: `0x3bfe9`
- name: `System.Windows.Xps.Serialization.XpsSerializerWriter::CheckDisposed`
- size: `25`
- prototype: ``
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x3b990`
- `0x3b9b0`
- `0x3b9d0`
- `0x3b9f0`
- `0x3ba10`
- `0x3ba30`
- `0x3ba50`
- `0x3ba70`
- `0x3ba90`
- `0x3bab0`
- `0x3bad0`
- `0x3baf0`
- `0x3bb10`
- `0x3bb30`
- `0x3bb50`
- `0x3bb70`
- `0x3bb90`
- `0x3bbb0`
- `0x3bbd0`
- `0x3bbf0`
- `0x3bc10`
- `0x3bc30`
- `0x3bc50`
- `0x3bc70`
- `0x3bc90`
- `0x3bcb0`
- `0x3bcd0`
- `0x3bcf0`
- `0x3bd10`
- `0x3bd30`
- `0x3bd50`
- `0x3bd70`
- `0x3bda0`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x3bfd0`

## string_xrefs

- `0x3bfd8`: `XpsSerializerFactory_WriterIsClosed`

## pseudocode

```c

```

## disassembly

```asm
0x3bfd0  ldarg.0
0x3bfd1  ldfld    class [System.Printing]System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.Serialization.XpsSerializerWriter::_xpsDocumentWriter
0x3bfd6  brtrue.s loc_3BFE8
0x3bfd8  ldstr    aXpsserializerf_2// "XpsSerializerFactory_WriterIsClosed"
0x3bfdd  call     string System.Windows.Xps.SR::Get(string id)
0x3bfe2  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x3bfe7  throw
0x3bfe8  ret
```
