# System.Windows.Xps.XpsDocumentWriter::CloneSourcePrintTicket

- ea: `0xc230`
- end: `0xc34a`
- name: `System.Windows.Xps.XpsDocumentWriter::CloneSourcePrintTicket`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xc6e0`

## callees

- `0xc230`

## pseudocode

```c

```

## disassembly

```asm
0xc230  ldnull
0xc231  stloc.0
0xc232  ldarg.2
0xc233  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc238  stloc.1
0xc239  ldloca.s 1
0xc23b  ldind.i4
0xc23c  ldc.i4.1
0xc23d  beq      loc_C2E3
0xc242  ldloca.s 1
0xc244  ldind.i4
0xc245  ldc.i4.2
0xc246  beq.s    loc_C2A0
0xc248  ldloca.s 1
0xc24a  ldind.i4
0xc24b  ldc.i4.3
0xc24c  bne.un   loc_C313
0xc251  ldarg.0
0xc252  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xc257  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader> [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader::get_FixedDocuments()
0xc25c  ldarg.0
0xc25d  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc262  ldc.i4.2
0xc263  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc268  unbox    [mscorlib]System.Int32
0xc26d  ldind.i4
0xc26e  ldc.i4.2
0xc26f  sub
0xc270  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader>::get_Item(!!T0)
0xc275  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedPageReader> [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader::get_FixedPages()
0xc27a  ldarg.0
0xc27b  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc280  ldarg.2
0xc281  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc286  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc28b  unbox    [mscorlib]System.Int32
0xc290  ldind.i4
0xc291  ldc.i4.1
0xc292  sub
0xc293  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedPageReader>::get_Item(!!T0)
0xc298  callvirt instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedPageReader::get_PrintTicket()
0xc29d  stloc.0
0xc29e  br.s     loc_C313
0xc2a0  ldarg.0
0xc2a1  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc2a6  ldc.i4.3
0xc2a7  ldc.i4.1
0xc2a8  box      [mscorlib]System.Int32
0xc2ad  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc2b2  ldarg.0
0xc2b3  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xc2b8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader> [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader::get_FixedDocuments()
0xc2bd  ldarg.0
0xc2be  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc2c3  ldarg.2
0xc2c4  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc2c9  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc2ce  unbox    [mscorlib]System.Int32
0xc2d3  ldind.i4
0xc2d4  ldc.i4.1
0xc2d5  sub
0xc2d6  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader>::get_Item(!!T0)
0xc2db  callvirt instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentReader::get_PrintTicket()
0xc2e0  stloc.0
0xc2e1  br.s     loc_C313
0xc2e3  ldarg.0
0xc2e4  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc2e9  ldc.i4.2
0xc2ea  ldc.i4.1
0xc2eb  box      [mscorlib]System.Int32
0xc2f0  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc2f5  ldarg.0
0xc2f6  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc2fb  ldc.i4.3
0xc2fc  ldc.i4.1
0xc2fd  box      [mscorlib]System.Int32
0xc302  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc307  ldarg.0
0xc308  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader System.Windows.Xps.XpsDocumentWriter::_sourceXpsFixedDocumentSequenceReader
0xc30d  callvirt instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceReader::get_PrintTicket()
0xc312  stloc.0
0xc313  ldarg.0
0xc314  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc319  ldarg.2
0xc31a  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc31f  ldarg.0
0xc320  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc325  ldarg.2
0xc326  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc32b  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc330  unbox    [mscorlib]System.Int32
0xc335  ldind.i4
0xc336  ldc.i4.1
0xc337  add
0xc338  box      [mscorlib]System.Int32
0xc33d  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc342  ldarg.2
0xc343  ldloc.0
0xc344  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::set_PrintTicket(class [ReachFramework]System.Printing.PrintTicket)
0xc349  ret
```
