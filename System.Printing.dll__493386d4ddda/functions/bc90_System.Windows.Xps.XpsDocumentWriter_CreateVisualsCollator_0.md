# System.Windows.Xps.XpsDocumentWriter::CreateVisualsCollator_0

- ea: `0xbc90`
- end: `0xbcf2`
- name: `System.Windows.Xps.XpsDocumentWriter::CreateVisualsCollator_0`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xbc90`
- `0xcae0`
- `0xcc10`
- `0xcc70`
- `0xd700`

## string_xrefs

- `0xbcbc`: `XPSWriter.BatchMode`
- `0xbcb0`: `XPSWriter.DoneWriting`

## pseudocode

```c

```

## disassembly

```asm
0xbc90  ldarg.0
0xbc91  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xbc96  ldnull
0xbc97  stloc.0
0xbc98  ldarg.0
0xbc99  ldfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbc9e  stloc.2
0xbc9f  ldloca.s 2
0xbca1  ldind.i4
0xbca2  brfalse.s loc_BCC8
0xbca4  ldloca.s 2
0xbca6  ldind.i4
0xbca7  ldc.i4.1
0xbca8  beq.s    loc_BCBC
0xbcaa  ldloca.s 2
0xbcac  ldind.i4
0xbcad  ldc.i4.2
0xbcae  bne.un.s loc_BCF0
0xbcb0  ldstr    aXpswriterDonew// "XPSWriter.DoneWriting"
0xbcb5  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbcba  br.s     loc_BCF0
0xbcbc  ldstr    aXpswriterBatch// "XPSWriter.BatchMode"
0xbcc1  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbcc6  br.s     loc_BCF0
0xbcc8  ldarg.0
0xbcc9  ldc.i4.1
0xbcca  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbccf  ldarg.0
0xbcd0  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xbcd5  stloc.1
0xbcd6  ldloc.1
0xbcd7  brfalse.s loc_BCE3
0xbcd9  ldarg.0
0xbcda  ldloc.1
0xbcdb  newobj   instance void System.Windows.Xps.VisualsToXpsDocument::.ctor(class System.Windows.Xps.XpsDocumentWriter writer, class System.Printing.PrintQueue printQueue)
0xbce0  stloc.0
0xbce1  br.s     loc_BCF0
0xbce3  ldarg.0
0xbce4  dup
0xbce5  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xbcea  newobj   instance void System.Windows.Xps.VisualsToXpsDocument::.ctor(class System.Windows.Xps.XpsDocumentWriter writer, class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument document)
0xbcef  stloc.0
0xbcf0  ldloc.0
0xbcf1  ret
```
