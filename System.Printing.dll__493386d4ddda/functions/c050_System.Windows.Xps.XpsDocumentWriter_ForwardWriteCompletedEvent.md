# System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent

- ea: `0xc050`
- end: `0xc132`
- name: `System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xc6e0`

## callees

- `0xbd80`
- `0xc050`
- `0x10730`

## pseudocode

```c

```

## disassembly

```asm
0xc050  ldarg.2
0xc051  call     instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0xc056  stloc.0
0xc057  ldloc.0
0xc058  brtrue.s loc_C084
0xc05a  ldarg.2
0xc05b  call     instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xc060  brfalse.s loc_C084
0xc062  ldtoken  [ReachFramework]System.Printing.PrintingCanceledException
0xc067  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc06c  ldarg.2
0xc06d  call     instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xc072  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xc077  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc07c  ldc.i4.0
0xc07d  bne.un.s loc_C082
0xc07f  ldloc.0
0xc080  br.s     loc_C083
0xc082  ldc.i4.1
0xc083  stloc.0
0xc084  ldarg.2
0xc085  call     instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xc08a  stloc.1
0xc08b  ldarg.0
0xc08c  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc091  brfalse.s loc_C0C4
0xc093  ldloc.0
0xc094  brtrue.s loc_C0AC
0xc096  ldarg.2
0xc097  call     instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0xc09c  brtrue.s loc_C0AC
0xc09e  ldarg.0
0xc09f  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc0a4  ldc.i4.0
0xc0a5  call     instance void System.Printing.PrintQueue::DisposeSerializationManager([hasfieldmarshal] bool abort)
0xc0aa  br.s     loc_C0B8
0xc0ac  ldarg.0
0xc0ad  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc0b2  ldc.i4.1
0xc0b3  call     instance void System.Printing.PrintQueue::DisposeSerializationManager([hasfieldmarshal] bool abort)
0xc0b8  leave.s  loc_C0CF
0xc0ba  ldc.i4.1
0xc0bb  stloc.0
0xc0bc  stloc.1
0xc0bd  leave.s  loc_C0CF
0xc0bf  ldc.i4.0
0xc0c0  stloc.0
0xc0c1  stloc.1
0xc0c2  leave.s  loc_C0CF
0xc0c4  ldarg.0
0xc0c5  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc0ca  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::DisposeSerializationManager()
0xc0cf  ldarg.0
0xc0d0  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc0d5  brtrue.s loc_C103
0xc0d7  ldarg.0
0xc0d8  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc0dd  brfalse.s loc_C103
0xc0df  ldarg.0
0xc0e0  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xc0e5  call     instance void [WindowsBase]System.IO.Packaging.Package::Close()
0xc0ea  ldarg.0
0xc0eb  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc0f0  call     instance void [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager::Commit()
0xc0f5  ldarg.0
0xc0f6  ldnull
0xc0f7  stfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.XpsDocumentWriter::_mxdwPackage
0xc0fc  ldarg.0
0xc0fd  ldnull
0xc0fe  stfld    class [ReachFramework]System.Windows.Xps.Serialization.MXDWSerializationManager System.Windows.Xps.XpsDocumentWriter::_mxdwManager
0xc103  ldarg.0
0xc104  ldfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xc109  brfalse.s loc_C11B
0xc10b  ldarg.0
0xc10c  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::_sourceXpsDocument
0xc111  stloc.2
0xc112  ldloc.2
0xc113  brfalse.s loc_C11B
0xc115  ldloc.2
0xc116  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::Close()
0xc11b  ldloc.0
0xc11c  ldarg.0
0xc11d  ldfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xc122  ldloc.1
0xc123  newobj   instance void [PresentationFramework]System.Windows.Documents.Serialization.WritingCompletedEventArgs::.ctor(bool, object, class [mscorlib]System.Exception)
0xc128  stloc.3
0xc129  ldarg.0
0xc12a  dup
0xc12b  ldloc.3
0xc12c  callvirt instance void System.Windows.Xps.XpsDocumentWriter::raise_WritingCompleted(object sender, class [PresentationFramework]System.Windows.Documents.Serialization.WritingCompletedEventArgs e)
0xc131  ret
```
