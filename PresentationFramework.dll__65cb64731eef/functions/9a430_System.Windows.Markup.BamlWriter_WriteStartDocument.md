# System.Windows.Markup.BamlWriter::WriteStartDocument

- ea: `0x9a430`
- end: `0x9a489`
- name: `System.Windows.Markup.BamlWriter::WriteStartDocument`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x212d20`

## callees

- `0x38c40`
- `0x94120`
- `0x9a430`
- `0x9b360`
- `0xb0400`

## string_xrefs

- `0x9a438`: `BamlWriterClosed`
- `0x9a450`: `BamlWriterStartDoc`

## pseudocode

```c

```

## disassembly

```asm
0x9a430  ldarg.0
0x9a431  ldfld    bool System.Windows.Markup.BamlWriter::_closed
0x9a436  brfalse.s loc_9A448
0x9a438  ldstr    aBamlwriterclos// "BamlWriterClosed"
0x9a43d  call     string System.Windows.SR::Get(string id)
0x9a442  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a447  throw
0x9a448  ldarg.0
0x9a449  ldfld    bool System.Windows.Markup.BamlWriter::_startDocumentWritten
0x9a44e  brfalse.s loc_9A460
0x9a450  ldstr    aBamlwriterstar// "BamlWriterStartDoc"
0x9a455  call     string System.Windows.SR::Get(string id)
0x9a45a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a45f  throw
0x9a460  ldc.i4.0
0x9a461  ldc.i4.0
0x9a462  ldarg.0
0x9a463  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9a468  newobj   instance void System.Windows.Markup.XamlDocumentStartNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth)
0x9a46d  stloc.0
0x9a46e  ldarg.0
0x9a46f  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a474  ldloc.0
0x9a475  callvirt instance void System.Windows.Markup.BamlRecordWriter::WriteDocumentStart(class System.Windows.Markup.XamlDocumentStartNode xamlDocumentNode)
0x9a47a  ldarg.0
0x9a47b  ldc.i4.1
0x9a47c  stfld    bool System.Windows.Markup.BamlWriter::_startDocumentWritten
0x9a481  ldarg.0
0x9a482  ldc.i4.1
0x9a483  call     instance void System.Windows.Markup.BamlWriter::Push(valuetype System.Windows.Markup.BamlRecordType recordType)
0x9a488  ret
```
