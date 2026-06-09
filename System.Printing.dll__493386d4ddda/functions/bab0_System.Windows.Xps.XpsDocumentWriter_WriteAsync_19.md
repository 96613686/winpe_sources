# System.Windows.Xps.XpsDocumentWriter::WriteAsync_19

- ea: `0xbab0`
- end: `0xbb12`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_19`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0xbb20`

## callees

- `0xb670`
- `0xb920`
- `0xbab0`
- `0xcae0`
- `0xd700`

## string_xrefs

- `0xbaf6`: `XpsWriter.InvalidXps`

## pseudocode

```c

```

## disassembly

```asm
0xbab0  ldarg.0
0xbab1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xbab6  ldarg.2
0xbab7  brfalse.s loc_BB09
0xbab9  ldarg.2
0xbaba  ldc.i4.1
0xbabb  beq.s    loc_BAC3
0xbabd  ldarg.2
0xbabe  ldc.i4.2
0xbabf  beq.s    loc_BB09
0xbac1  br.s     loc_BB11
0xbac3  ldarg.0
0xbac4  ldc.i4.1
0xbac5  stfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xbaca  ldarg.1
0xbacb  ldc.i4.1
0xbacc  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::.ctor(string, valuetype [mscorlib]System.IO.FileAccess)
0xbad1  stloc.1
0xbad2  ldarg.0
0xbad3  ldloc.1
0xbad4  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xbad9  ldloc.1
0xbada  call     instance class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence()
0xbadf  stloc.2
0xbae0  ldarg.0
0xbae1  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xbae6  call     instance class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::get_FixedDocumentSequenceReader()
0xbaeb  stloc.0
0xbaec  ldarg.0
0xbaed  ldloc.0
0xbaee  stfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xbaf3  ldloc.0
0xbaf4  brtrue.s loc_BB00
0xbaf6  ldstr    aXpswriterInval// "XpsWriter.InvalidXps"
0xbafb  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xbb00  ldarg.0
0xbb01  ldloc.2
0xbb02  callvirt instance void System.Windows.Xps.XpsDocumentWriter::WriteAsync(class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence fixedDocumentSequence)
0xbb07  br.s     loc_BB11
0xbb09  ldarg.0
0xbb0a  ldarg.1
0xbb0b  ldarg.2
0xbb0c  call     instance void System.Windows.Xps.XpsDocumentWriter::Write(string documentPath, valuetype System.Windows.Xps.XpsDocumentNotificationLevel notificationLevel)
0xbb11  ret
```
