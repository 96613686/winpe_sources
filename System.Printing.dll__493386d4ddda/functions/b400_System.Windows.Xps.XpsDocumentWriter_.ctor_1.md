# System.Windows.Xps.XpsDocumentWriter::.ctor_1

- ea: `0xb400`
- end: `0xb46a`
- name: `System.Windows.Xps.XpsDocumentWriter::.ctor_1`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x103c0`
- `0x17460`

## callees

- `0xb400`
- `0xc690`

## pseudocode

```c

```

## disassembly

```asm
0xb400  ldarg.0
0xb401  ldc.i4.0
0xb402  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xb407  ldarg.0
0xb408  ldnull
0xb409  stfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xb40e  ldarg.0
0xb40f  ldnull
0xb410  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xb415  ldarg.0
0xb416  ldnull
0xb417  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xb41c  ldarg.0
0xb41d  ldc.i4.0
0xb41e  stfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xb423  ldarg.0
0xb424  ldnull
0xb425  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xb42a  ldarg.0
0xb42b  ldnull
0xb42c  stfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xb431  ldarg.0
0xb432  ldc.i4.0
0xb433  stfld    int32 System.Windows.Xps.XpsDocumentWriter::_writingCancelledEventHandlersCount
0xb438  ldarg.0
0xb439  call     instance void [PresentationFramework]System.Windows.Documents.Serialization.SerializerWriter::.ctor()
0xb43e  ldarg.1
0xb43f  brfalse.s loc_B45E
0xb441  ldarg.0
0xb442  ldnull
0xb443  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xb448  ldarg.0
0xb449  ldarg.1
0xb44a  stfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xb44f  ldarg.0
0xb450  ldc.i4.0
0xb451  stfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xb456  ldarg.0
0xb457  call     instance void System.Windows.Xps.XpsDocumentWriter::InitializeSequences()
0xb45c  br.s     loc_B469
0xb45e  ldstr    aPrintqueue_0// "printQueue"
0xb463  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb468  throw
0xb469  ret
```
