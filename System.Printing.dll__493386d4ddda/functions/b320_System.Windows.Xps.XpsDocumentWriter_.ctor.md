# System.Windows.Xps.XpsDocumentWriter::.ctor

- ea: `0xb320`
- end: `0xb38a`
- name: `System.Windows.Xps.XpsDocumentWriter::.ctor`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x11910`

## callees

- `0xb320`
- `0xc690`

## pseudocode

```c

```

## disassembly

```asm
0xb320  ldarg.0
0xb321  ldc.i4.0
0xb322  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xb327  ldarg.0
0xb328  ldnull
0xb329  stfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xb32e  ldarg.0
0xb32f  ldnull
0xb330  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xb335  ldarg.0
0xb336  ldnull
0xb337  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xb33c  ldarg.0
0xb33d  ldc.i4.0
0xb33e  stfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xb343  ldarg.0
0xb344  ldnull
0xb345  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xb34a  ldarg.0
0xb34b  ldnull
0xb34c  stfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xb351  ldarg.0
0xb352  ldc.i4.0
0xb353  stfld    int32 System.Windows.Xps.XpsDocumentWriter::_writingCancelledEventHandlersCount
0xb358  ldarg.0
0xb359  call     instance void [PresentationFramework]System.Windows.Documents.Serialization.SerializerWriter::.ctor()
0xb35e  ldarg.1
0xb35f  brfalse.s loc_B37E
0xb361  ldarg.0
0xb362  ldarg.1
0xb363  stfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xb368  ldarg.0
0xb369  ldnull
0xb36a  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xb36f  ldarg.0
0xb370  ldc.i4.0
0xb371  stfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xb376  ldarg.0
0xb377  call     instance void System.Windows.Xps.XpsDocumentWriter::InitializeSequences()
0xb37c  br.s     loc_B389
0xb37e  ldstr    aPrintqueue_0// "printQueue"
0xb383  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb388  throw
0xb389  ret
```
