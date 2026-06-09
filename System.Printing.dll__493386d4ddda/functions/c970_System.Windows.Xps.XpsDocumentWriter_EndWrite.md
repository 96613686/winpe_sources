# System.Windows.Xps.XpsDocumentWriter::EndWrite

- ea: `0xc970`
- end: `0xc9d4`
- name: `System.Windows.Xps.XpsDocumentWriter::EndWrite`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0xc9e0`
- `0xc9f0`

## callees

- `0xc660`
- `0xc970`
- `0x10730`

## pseudocode

```c

```

## disassembly

```asm
0xc970  ldarg.1
0xc971  ldc.i4.1
0xc972  bne.un.s loc_C9BE
0xc974  ldarg.0
0xc975  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc97a  stloc.0
0xc97b  ldloc.0
0xc97c  brfalse.s loc_C987
0xc97e  ldloc.0
0xc97f  ldarg.2
0xc980  call     instance void System.Printing.PrintQueue::DisposeSerializationManager([hasfieldmarshal] bool abort)
0xc985  br.s     loc_C9BE
0xc987  ldarg.0
0xc988  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc98d  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::DisposeSerializationManager()
0xc992  ldarg.0
0xc993  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc998  brfalse.s loc_C9BE
0xc99a  ldarg.0
0xc99b  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xc9a0  call     instance void [WindowsBase]System.IO.Packaging.Package::Close()
0xc9a5  ldarg.0
0xc9a6  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc9ab  call     instance void [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager::Commit()
0xc9b0  ldarg.0
0xc9b1  ldnull
0xc9b2  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xc9b7  ldarg.0
0xc9b8  ldnull
0xc9b9  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc9be  ldarg.0
0xc9bf  ldc.i4.2
0xc9c0  stfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xc9c5  leave.s  loc_C9D3
0xc9c7  stloc.1
0xc9c8  ldarg.0
0xc9c9  dup
0xc9ca  ldloc.1
0xc9cb  call     instance bool System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled([hasfieldmarshal] object value, class [mscorlib]System.Exception sender)
0xc9d0  pop
0xc9d1  leave.s  loc_C9D3
0xc9d3  ret
```
