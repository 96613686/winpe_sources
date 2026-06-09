# System.Windows.Xps.XpsDocumentWriter::BeginWrite

- ea: `0xc6e0`
- end: `0xc966`
- name: `System.Windows.Xps.XpsDocumentWriter::BeginWrite`
- size: `646`
- prototype: ``
- caller_count: `21`
- callee_count: `15`
- tags: ``

## callers

- `0xb470`
- `0xb4e0`
- `0xb510`
- `0xb530`
- `0xb560`
- `0xb580`
- `0xb5b0`
- `0xb5d0`
- `0xb600`
- `0xb620`
- `0xb650`
- `0xb780`
- `0xb7c0`
- `0xb830`
- `0xb870`
- `0xb8e0`
- `0xb920`
- `0xb990`
- `0xb9d0`
- `0xba40`
- `0xba80`

## callees

- `0xbf70`
- `0xc050`
- `0xc230`
- `0xc360`
- `0xc450`
- `0xc4f0`
- `0xc660`
- `0xc6e0`
- `0xca20`
- `0xca50`
- `0xca70`
- `0xd700`
- `0xdea0`
- `0x10410`
- `0x10550`

## string_xrefs

- `0xc714`: `XPSWriter.BatchMode`
- `0xc705`: `XPSWriter.DoneWriting`

## pseudocode

```c

```

## disassembly

```asm
0xc6e0  ldc.i4.0
0xc6e1  stloc.s  4
0xc6e3  ldarg.0
0xc6e4  ldfld    valuetype DocumentWriterState System.Windows.Xps.XpsDocumentWriter::currentState
0xc6e9  stloc.s  0xC
0xc6eb  ldloca.s 0xC
0xc6ed  ldind.i4
0xc6ee  brfalse.s loc_C723
0xc6f0  ldloca.s 0xC
0xc6f2  ldind.i4
0xc6f3  ldc.i4.1
0xc6f4  beq.s    loc_C714
0xc6f6  ldloca.s 0xC
0xc6f8  ldind.i4
0xc6f9  ldc.i4.2
0xc6fa  beq.s    loc_C705
0xc6fc  ldloca.s 0xC
0xc6fe  ldind.i4
0xc6ff  ldc.i4.3
0xc700  bne.un   loc_C963
0xc705  ldstr    aXpswriterDonew// "XPSWriter.DoneWriting"
0xc70a  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xc70f  br       loc_C963
0xc714  ldstr    aXpswriterBatch// "XPSWriter.BatchMode"
0xc719  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xc71e  br       loc_C963
0xc723  nop
0xc724  ldarg.2
0xc725  brtrue   loc_C812
0xc72a  ldarg.0
0xc72b  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc730  stloc.0
0xc731  ldloc.0
0xc732  brfalse  loc_C7FB
0xc737  ldarg.0
0xc738  ldloc.0
0xc739  call     instance bool System.Windows.Xps.XpsDocumentWriter::MxdwConversionRequired([hasfieldmarshal] class System.Printing.PrintQueue value)
0xc73e  brfalse.s loc_C78A
0xc740  ldarg.0
0xc741  dup
0xc742  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc747  call     instance string System.Windows.Xps.XpsDocumentWriter::MxdwInitializeOptimizationConversion(class System.Printing.PrintQueue printQueue)
0xc74c  stloc.s  0xB
0xc74e  ldarg.0
0xc74f  ldloc.s  0xB
0xc751  call     instance void System.Windows.Xps.XpsDocumentWriter::CreateXPSDocument(string documentName)
0xc756  ldarg.0
0xc757  dup
0xc758  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc75d  ldarg.1
0xc75e  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateSerializationManager(bool)
0xc763  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc768  leave    loc_C8FF
0xc76d  stloc.s  0xA
0xc76f  ldc.i4.0
0xc770  ldnull
0xc771  ldloc.s  0xA
0xc773  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs::.ctor(bool, object, class [mscorlib]System.Exception)
0xc778  stloc.s  9
0xc77a  ldarg.0
0xc77b  dup
0xc77c  ldloc.s  9
0xc77e  call     instance void System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs args)
0xc783  leave.s  loc_C785
0xc785  leave    loc_C963
0xc78a  ldarg.3
0xc78b  brfalse.s loc_C7E0
0xc78d  ldarg.0
0xc78e  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc793  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0xc798  brfalse.s loc_C7E0
0xc79a  ldarg.0
0xc79b  ldarg.s  5
0xc79d  stfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xc7a2  ldarg.0
0xc7a3  ldarg.s  4
0xc7a5  stfld    class [ReachFramework]System.Printing.PrintTicket System.Windows.Xps.XpsDocumentWriter::currentUserPrintTicket
0xc7aa  ldc.i4.1
0xc7ab  ldc.i4.0
0xc7ac  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::.ctor(valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel, int32)
0xc7b1  stloc.2
0xc7b2  ldarg.0
0xc7b3  ldfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xc7b8  brfalse.s loc_C7C4
0xc7ba  ldarg.0
0xc7bb  dup
0xc7bc  ldloc.2
0xc7bd  call     instance void System.Windows.Xps.XpsDocumentWriter::CloneSourcePrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc7c2  br.s     loc_C7CC
0xc7c4  ldarg.0
0xc7c5  dup
0xc7c6  ldloc.2
0xc7c7  call     instance void System.Windows.Xps.XpsDocumentWriter::ForwardUserPrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc7cc  ldarg.s  4
0xc7ce  brtrue.s loc_C7E0
0xc7d0  ldloc.2
0xc7d1  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xc7d6  brfalse.s loc_C7E0
0xc7d8  ldloc.2
0xc7d9  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xc7de  starg.s  4
0xc7e0  ldarg.0
0xc7e1  dup
0xc7e2  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc7e7  ldarg.1
0xc7e8  ldarg.s  6
0xc7ea  ldarg.s  4
0xc7ec  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool mustSetJobIdentifier, class [ReachFramework]System.Printing.PrintTicket printTicket)
0xc7f1  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc7f6  br       loc_C8FF
0xc7fb  ldarg.0
0xc7fc  dup
0xc7fd  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc802  ldarg.1
0xc803  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateSerializationManager(bool)
0xc808  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc80d  br       loc_C8FF
0xc812  ldarg.0
0xc813  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc818  stloc.0
0xc819  ldloc.0
0xc81a  brfalse  loc_C8E0
0xc81f  ldarg.0
0xc820  ldloc.0
0xc821  call     instance bool System.Windows.Xps.XpsDocumentWriter::MxdwConversionRequired([hasfieldmarshal] class System.Printing.PrintQueue value)
0xc826  brfalse.s loc_C872
0xc828  ldarg.0
0xc829  dup
0xc82a  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc82f  call     instance string System.Windows.Xps.XpsDocumentWriter::MxdwInitializeOptimizationConversion(class System.Printing.PrintQueue printQueue)
0xc834  stloc.s  8
0xc836  ldarg.0
0xc837  ldloc.s  8
0xc839  call     instance void System.Windows.Xps.XpsDocumentWriter::CreateXPSDocument(string documentName)
0xc83e  ldarg.0
0xc83f  dup
0xc840  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc845  ldarg.1
0xc846  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateAsyncSerializationManager(bool)
0xc84b  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc850  leave    loc_C8F2
0xc855  stloc.s  7
0xc857  ldc.i4.0
0xc858  ldnull
0xc859  ldloc.s  7
0xc85b  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs::.ctor(bool, object, class [mscorlib]System.Exception)
0xc860  stloc.s  6
0xc862  ldarg.0
0xc863  dup
0xc864  ldloc.s  6
0xc866  call     instance void System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs args)
0xc86b  leave.s  loc_C86D
0xc86d  leave    loc_C963
0xc872  ldarg.3
0xc873  brfalse.s loc_C8C8
0xc875  ldarg.0
0xc876  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc87b  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0xc880  brfalse.s loc_C8C8
0xc882  ldarg.0
0xc883  ldarg.s  5
0xc885  stfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xc88a  ldarg.0
0xc88b  ldarg.s  4
0xc88d  stfld    class [ReachFramework]System.Printing.PrintTicket System.Windows.Xps.XpsDocumentWriter::currentUserPrintTicket
0xc892  ldc.i4.1
0xc893  ldc.i4.0
0xc894  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::.ctor(valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel, int32)
0xc899  stloc.1
0xc89a  ldarg.0
0xc89b  ldfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xc8a0  brfalse.s loc_C8AC
0xc8a2  ldarg.0
0xc8a3  dup
0xc8a4  ldloc.1
0xc8a5  call     instance void System.Windows.Xps.XpsDocumentWriter::CloneSourcePrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc8aa  br.s     loc_C8B4
0xc8ac  ldarg.0
0xc8ad  dup
0xc8ae  ldloc.1
0xc8af  call     instance void System.Windows.Xps.XpsDocumentWriter::ForwardUserPrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc8b4  ldarg.s  4
0xc8b6  brtrue.s loc_C8C8
0xc8b8  ldloc.1
0xc8b9  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xc8be  brfalse.s loc_C8C8
0xc8c0  ldloc.1
0xc8c1  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xc8c6  starg.s  4
0xc8c8  ldarg.0
0xc8c9  dup
0xc8ca  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xc8cf  ldarg.1
0xc8d0  ldarg.s  6
0xc8d2  ldarg.s  4
0xc8d4  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateAsyncSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool mustSetJobIdentifier, class [ReachFramework]System.Printing.PrintTicket printTicket)
0xc8d9  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc8de  br.s     loc_C8F2
0xc8e0  ldarg.0
0xc8e1  dup
0xc8e2  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.XpsDocumentWriter::destinationDocument
0xc8e7  ldarg.1
0xc8e8  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateAsyncSerializationManager(bool)
0xc8ed  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc8f2  ldarg.0
0xc8f3  dup
0xc8f4  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc8f9  ldnull
0xc8fa  call     instance void System.Windows.Xps.XpsDocumentWriter::SetCompletionEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager, object userState)
0xc8ff  leave.s  loc_C90F
0xc901  stloc.s  5
0xc903  ldarg.0
0xc904  dup
0xc905  ldloc.s  5
0xc907  call     instance bool System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled([hasfieldmarshal] object value, class [mscorlib]System.Exception sender)
0xc90c  pop
0xc90d  leave.s  loc_C963
0xc90f  ldarg.0
0xc910  ldarg.s  5
0xc912  stfld    valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel System.Windows.Xps.XpsDocumentWriter::currentWriteLevel
0xc917  ldarg.0
0xc918  ldarg.s  4
0xc91a  stfld    class [ReachFramework]System.Printing.PrintTicket System.Windows.Xps.XpsDocumentWriter::currentUserPrintTicket
0xc91f  ldarg.3
0xc920  brfalse.s loc_C953
0xc922  ldarg.0
0xc923  ldfld    bool System.Windows.Xps.XpsDocumentWriter::_isDocumentCloned
0xc928  brfalse.s loc_C939
0xc92a  ldarg.0
0xc92b  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::CloneSourcePrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc931  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler::.ctor(object, native int)
0xc936  stloc.3
0xc937  br.s     loc_C946
0xc939  ldarg.0
0xc93a  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardUserPrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xc940  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler::.ctor(object, native int)
0xc945  stloc.3
0xc946  ldarg.0
0xc947  dup
0xc948  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc94d  ldloc.3
0xc94e  call     instance void System.Windows.Xps.XpsDocumentWriter::SetPrintTicketEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler eventHandler)
0xc953  ldarg.0
0xc954  dup
0xc955  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xc95a  ldnull
0xc95b  call     instance void System.Windows.Xps.XpsDocumentWriter::SetProgressChangedEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager, object userState)
0xc960  ldc.i4.1
0xc961  stloc.s  4
0xc963  ldloc.s  4
0xc965  ret
```
