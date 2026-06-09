# System.Windows.Xps.XpsDocumentWriter::ForwardUserPrintTicket

- ea: `0xbf70`
- end: `0xc041`
- name: `System.Windows.Xps.XpsDocumentWriter::ForwardUserPrintTicket`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xc6e0`

## callees

- `0xbd20`
- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0xbf70  ldarg.0
0xbf71  ldfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xbf76  ldarg.2
0xbf77  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xbf7c  bne.un.s loc_BF8F
0xbf7e  ldarg.2
0xbf7f  ldarg.0
0xbf80  ldfld    class [ReachFramework]System.Printing.PrintTicket System.Windows.Xps.XpsDocumentWriter::currentUserPrintTicket
0xbf85  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::set_PrintTicket(class [ReachFramework]System.Printing.PrintTicket)
0xbf8a  br       loc_C040
0xbf8f  ldarg.2
0xbf90  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xbf95  ldarg.0
0xbf96  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xbf9b  ldarg.2
0xbf9c  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xbfa1  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xbfa6  unbox    [mscorlib]System.Int32
0xbfab  ldind.i4
0xbfac  newobj   instance void [PresentationFramework]System.Windows.Documents.Serialization.WritingPrintTicketRequiredEventArgs::.ctor(valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel, int32)
0xbfb1  stloc.0
0xbfb2  ldarg.2
0xbfb3  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xbfb8  stloc.1
0xbfb9  ldloca.s 1
0xbfbb  ldind.i4
0xbfbc  ldc.i4.1
0xbfbd  beq.s    loc_BFD9
0xbfbf  ldloca.s 1
0xbfc1  ldind.i4
0xbfc2  ldc.i4.2
0xbfc3  bne.un.s loc_BFFD
0xbfc5  ldarg.0
0xbfc6  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xbfcb  ldc.i4.3
0xbfcc  ldc.i4.1
0xbfcd  box      [mscorlib]System.Int32
0xbfd2  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xbfd7  br.s     loc_BFFD
0xbfd9  ldarg.0
0xbfda  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xbfdf  ldc.i4.2
0xbfe0  ldc.i4.1
0xbfe1  box      [mscorlib]System.Int32
0xbfe6  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xbfeb  ldarg.0
0xbfec  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xbff1  ldc.i4.3
0xbff2  ldc.i4.1
0xbff3  box      [mscorlib]System.Int32
0xbff8  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xbffd  ldarg.0
0xbffe  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc003  ldarg.2
0xc004  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc009  ldarg.0
0xc00a  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Xps.XpsDocumentWriter::_printTicketSequences
0xc00f  ldarg.2
0xc010  call     instance valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicketLevel()
0xc015  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xc01a  unbox    [mscorlib]System.Int32
0xc01f  ldind.i4
0xc020  ldc.i4.1
0xc021  add
0xc022  box      [mscorlib]System.Int32
0xc027  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xc02c  ldarg.0
0xc02d  dup
0xc02e  ldloc.0
0xc02f  callvirt instance void System.Windows.Xps.XpsDocumentWriter::raise_WritingPrintTicketRequired(object sender, class [PresentationFramework]System.Windows.Documents.Serialization.WritingPrintTicketRequiredEventArgs e)
0xc034  ldarg.2
0xc035  ldloc.0
0xc036  call     instance class [ReachFramework]System.Printing.PrintTicket [PresentationFramework]System.Windows.Documents.Serialization.WritingPrintTicketRequiredEventArgs::get_CurrentPrintTicket()
0xc03b  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::set_PrintTicket(class [ReachFramework]System.Printing.PrintTicket)
0xc040  ret
```
