# System.Windows.Xps.XpsDocumentWriter::CreateVisualsCollator

- ea: `0xbc20`
- end: `0xbc86`
- name: `System.Windows.Xps.XpsDocumentWriter::CreateVisualsCollator`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xbc20`
- `0xcae0`
- `0xcb30`
- `0xcba0`
- `0xd700`

## string_xrefs

- `0xbc4c`: `XPSWriter.BatchMode`
- `0xbc40`: `XPSWriter.DoneWriting`

## pseudocode

```c

```

## disassembly

```asm
0xbc20  ldarg.0
0xbc21  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xbc26  ldnull
0xbc27  stloc.0
0xbc28  ldarg.0
0xbc29  ldfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbc2e  stloc.2
0xbc2f  ldloca.s 2
0xbc31  ldind.i4
0xbc32  brfalse.s loc_BC58
0xbc34  ldloca.s 2
0xbc36  ldind.i4
0xbc37  ldc.i4.1
0xbc38  beq.s    loc_BC4C
0xbc3a  ldloca.s 2
0xbc3c  ldind.i4
0xbc3d  ldc.i4.2
0xbc3e  bne.un.s loc_BC84
0xbc40  ldstr    aXpswriterDonew// "XPSWriter.DoneWriting"
0xbc45  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbc4a  br.s     loc_BC84
0xbc4c  ldstr    aXpswriterBatch// "XPSWriter.BatchMode"
0xbc51  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbc56  br.s     loc_BC84
0xbc58  ldarg.0
0xbc59  ldc.i4.1
0xbc5a  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xbc5f  ldarg.0
0xbc60  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xbc65  stloc.1
0xbc66  ldloc.1
0xbc67  brfalse.s loc_BC75
0xbc69  ldarg.0
0xbc6a  ldloc.1
0xbc6b  ldarg.1
0xbc6c  ldarg.2
0xbc6d  newobj   instance void System.Windows.Xps.VisualsToXpsDocument::.ctor(class System.Windows.Xps.XpsDocumentWriter writer, class System.Printing.PrintQueue printQueue, class [ReachFramework]System.Printing.PrintTicket documentSequencePrintTicket, class [ReachFramework]System.Printing.PrintTicket documentPrintTicket)
0xbc72  stloc.0
0xbc73  br.s     loc_BC84
0xbc75  ldarg.0
0xbc76  dup
0xbc77  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xbc7c  ldarg.1
0xbc7d  ldarg.2
0xbc7e  newobj   instance void System.Windows.Xps.VisualsToXpsDocument::.ctor(class System.Windows.Xps.XpsDocumentWriter writer, class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument document, class [ReachFramework]System.Printing.PrintTicket documentSequencePrintTicket, class [ReachFramework]System.Printing.PrintTicket documentPrintTicket)
0xbc83  stloc.0
0xbc84  ldloc.0
0xbc85  ret
```
