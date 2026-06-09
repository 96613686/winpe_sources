# System.Windows.Xps.XpsDocumentWriter::Write_9

- ea: `0xb670`
- end: `0xb72a`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_9`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0xb730`
- `0xbab0`

## callees

- `0xb130`
- `0xb5b0`
- `0xb670`
- `0xcae0`
- `0xd700`
- `0xe4a0`
- `0xe550`

## string_xrefs

- `0xb6a9`: `XpsWriter.InvalidXps`
- `0xb71f`: `XpsWriter.InvalidXps`

## pseudocode

```c

```

## disassembly

```asm
0xb670  ldarg.0
0xb671  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb676  ldarg.2
0xb677  brfalse.s loc_B6DE
0xb679  ldarg.2
0xb67a  ldc.i4.1
0xb67b  beq.s    loc_B686
0xb67d  ldarg.2
0xb67e  ldc.i4.2
0xb67f  beq.s    loc_B6DE
0xb681  br       loc_B729
0xb686  ldarg.0
0xb687  ldc.i4.1
0xb688  stfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xb68d  ldarg.1
0xb68e  ldc.i4.1
0xb68f  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::.ctor(string, valuetype [mscorlib]System.IO.FileAccess)
0xb694  stloc.s  4
0xb696  ldarg.0
0xb697  ldloc.s  4
0xb699  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xb69e  ldloc.s  4
0xb6a0  call     instance class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence()
0xb6a5  stloc.3
0xb6a6  ldloc.3
0xb6a7  brtrue.s loc_B6B3
0xb6a9  ldstr    aXpswriterInval// "XpsWriter.InvalidXps"
0xb6ae  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xb6b3  ldarg.0
0xb6b4  dup
0xb6b5  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xb6ba  call     instance class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::get_FixedDocumentSequenceReader()
0xb6bf  stfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xb6c4  ldarg.0
0xb6c5  ldloc.3
0xb6c6  callvirt instance void System.Windows.Xps.XpsDocumentWriter::Write(class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence fixedDocumentSequence)
0xb6cb  leave.s  loc_B729
0xb6cd  ldarg.0
0xb6ce  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xb6d3  stloc.2
0xb6d4  ldloc.2
0xb6d5  brfalse.s loc_B6DD
0xb6d7  ldloc.2
0xb6d8  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::Close()
0xb6dd  endfinally
0xb6de  ldarg.1
0xb6df  ldc.i4.1
0xb6e0  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::.ctor(string, valuetype [mscorlib]System.IO.FileAccess)
0xb6e5  stloc.1
0xb6e6  ldloc.1
0xb6e7  call     instance class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence()
0xb6ec  ldloc.1
0xb6ed  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::Close()
0xb6f2  brfalse.s loc_B71F
0xb6f4  ldarg.0
0xb6f5  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xb6fa  stloc.0
0xb6fb  ldloc.0
0xb6fc  brfalse.s loc_B719
0xb6fe  ldarg.0
0xb6ff  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xb704  ldloc.0
0xb705  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0xb70a  call     instance string System.Printing.PrintJobSettings::get_Description()
0xb70f  ldarg.1
0xb710  ldc.i4.1
0xb711  call     instance class System.Printing.PrintSystemJobInfo System.Printing.PrintQueue::AddJob(string jobName, string documentPath, [hasfieldmarshal] bool fastCopy)
0xb716  pop
0xb717  br.s     loc_B729
0xb719  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xb71e  throw
0xb71f  ldstr    aXpswriterInval// "XpsWriter.InvalidXps"
0xb724  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xb729  ret
```
