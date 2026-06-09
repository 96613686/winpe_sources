# System.Windows.Xps.VisualsToXpsDocument::WriteVisual

- ea: `0xd330`
- end: `0xd57c`
- name: `System.Windows.Xps.VisualsToXpsDocument::WriteVisual`
- size: `588`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0xce70`
- `0xce90`
- `0xcef0`
- `0xcf10`

## callees

- `0xc450`
- `0xc4f0`
- `0xc660`
- `0xd0a0`
- `0xd1d0`
- `0xd330`
- `0xd580`
- `0xd5b0`
- `0xd5d0`
- `0xd700`
- `0xdea0`
- `0x10410`
- `0x10550`

## string_xrefs

- `0xd517`: `XPSWriter.BatchDoneWriting`
- `0xd570`: `XPSWriter.BatchSync`
- `0xd538`: `XPSWriter.BatchAsync`

## pseudocode

```c

```

## disassembly

```asm
0xd330  ldc.i4.0
0xd331  stloc.1
0xd332  ldarg.0
0xd333  dup
0xd334  ldfld    int32 System.Windows.Xps.VisualsToXpsDocument::_numberOfVisualsCollated
0xd339  ldc.i4.1
0xd33a  add
0xd33b  stfld    int32 System.Windows.Xps.VisualsToXpsDocument::_numberOfVisualsCollated
0xd340  ldarg.0
0xd341  ldfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd346  brtrue   loc_D4DC
0xd34b  ldarg.1
0xd34c  ldc.i4.1
0xd34d  bne.un   loc_D418
0xd352  ldarg.0
0xd353  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd358  stloc.0
0xd359  ldloc.0
0xd35a  brfalse  loc_D3D4
0xd35f  ldarg.0
0xd360  ldloc.0
0xd361  call     instance bool System.Windows.Xps.VisualsToXpsDocument::MxdwConversionRequired([hasfieldmarshal] class System.Printing.PrintQueue value)
0xd366  brfalse.s loc_D392
0xd368  ldarg.0
0xd369  dup
0xd36a  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd36f  call     instance string System.Windows.Xps.VisualsToXpsDocument::MxdwInitializeOptimizationConversion(class System.Printing.PrintQueue printQueue)
0xd374  stloc.s  8
0xd376  ldarg.0
0xd377  ldloc.s  8
0xd379  call     instance void System.Windows.Xps.VisualsToXpsDocument::CreateXPSDocument(string documentName)
0xd37e  ldarg.0
0xd37f  dup
0xd380  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.VisualsToXpsDocument::destinationDocument
0xd385  ldc.i4.1
0xd386  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateAsyncSerializationManager(bool)
0xd38b  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd390  br.s     loc_D3E6
0xd392  ldnull
0xd393  stloc.s  5
0xd395  ldarg.0
0xd396  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd39b  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0xd3a0  brfalse.s loc_D3BD
0xd3a2  ldc.i4.1
0xd3a3  ldc.i4.0
0xd3a4  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::.ctor(valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel, int32)
0xd3a9  stloc.s  4
0xd3ab  ldarg.0
0xd3ac  dup
0xd3ad  ldloc.s  4
0xd3af  call     instance void System.Windows.Xps.VisualsToXpsDocument::ForwardUserPrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xd3b4  ldloc.s  4
0xd3b6  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xd3bb  stloc.s  5
0xd3bd  ldarg.0
0xd3be  dup
0xd3bf  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd3c4  ldc.i4.1
0xd3c5  ldc.i4.0
0xd3c6  ldloc.s  5
0xd3c8  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateAsyncSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool mustSetJobIdentifier, class [ReachFramework]System.Printing.PrintTicket printTicket)
0xd3cd  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd3d2  br.s     loc_D3E6
0xd3d4  ldarg.0
0xd3d5  dup
0xd3d6  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.VisualsToXpsDocument::destinationDocument
0xd3db  ldc.i4.1
0xd3dc  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateAsyncSerializationManager(bool)
0xd3e1  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd3e6  ldarg.0
0xd3e7  ldfld    bool System.Windows.Xps.VisualsToXpsDocument::isCompletionEventHandlerSet
0xd3ec  brtrue.s loc_D40C
0xd3ee  ldarg.0
0xd3ef  ldfld    class System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.VisualsToXpsDocument::parentWriter
0xd3f4  ldarg.0
0xd3f5  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd3fa  ldarg.0
0xd3fb  ldfld    object System.Windows.Xps.VisualsToXpsDocument::_currentUserState
0xd400  call     instance void System.Windows.Xps.XpsDocumentWriter::SetCompletionEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager, object userState)
0xd405  ldarg.0
0xd406  ldc.i4.1
0xd407  stfld    bool System.Windows.Xps.VisualsToXpsDocument::isCompletionEventHandlerSet
0xd40c  ldarg.0
0xd40d  ldc.i4.2
0xd40e  stfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd413  br       loc_D4AA
0xd418  ldarg.0
0xd419  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd41e  stloc.0
0xd41f  ldloc.0
0xd420  brfalse.s loc_D491
0xd422  ldarg.0
0xd423  ldloc.0
0xd424  call     instance bool System.Windows.Xps.VisualsToXpsDocument::MxdwConversionRequired([hasfieldmarshal] class System.Printing.PrintQueue value)
0xd429  brfalse.s loc_D455
0xd42b  ldarg.0
0xd42c  dup
0xd42d  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd432  call     instance string System.Windows.Xps.VisualsToXpsDocument::MxdwInitializeOptimizationConversion(class System.Printing.PrintQueue printQueue)
0xd437  stloc.s  7
0xd439  ldarg.0
0xd43a  ldloc.s  7
0xd43c  call     instance void System.Windows.Xps.VisualsToXpsDocument::CreateXPSDocument(string documentName)
0xd441  ldarg.0
0xd442  dup
0xd443  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.VisualsToXpsDocument::destinationDocument
0xd448  ldc.i4.1
0xd449  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateSerializationManager(bool)
0xd44e  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd453  br.s     loc_D4A3
0xd455  ldnull
0xd456  stloc.3
0xd457  ldarg.0
0xd458  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd45d  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0xd462  brfalse.s loc_D47B
0xd464  ldc.i4.1
0xd465  ldc.i4.0
0xd466  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::.ctor(valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel, int32)
0xd46b  stloc.2
0xd46c  ldarg.0
0xd46d  dup
0xd46e  ldloc.2
0xd46f  call     instance void System.Windows.Xps.VisualsToXpsDocument::ForwardUserPrintTicket(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs args)
0xd474  ldloc.2
0xd475  call     instance class [ReachFramework]System.Printing.PrintTicket [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventArgs::get_PrintTicket()
0xd47a  stloc.3
0xd47b  ldarg.0
0xd47c  dup
0xd47d  ldfld    class System.Printing.PrintQueue System.Windows.Xps.VisualsToXpsDocument::destinationPrintQueue
0xd482  ldc.i4.1
0xd483  ldc.i4.0
0xd484  ldloc.3
0xd485  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool mustSetJobIdentifier, class [ReachFramework]System.Printing.PrintTicket printTicket)
0xd48a  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd48f  br.s     loc_D4A3
0xd491  ldarg.0
0xd492  dup
0xd493  ldfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Windows.Xps.VisualsToXpsDocument::destinationDocument
0xd498  ldc.i4.1
0xd499  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateSerializationManager(bool)
0xd49e  stfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd4a3  ldarg.0
0xd4a4  ldc.i4.1
0xd4a5  stfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd4aa  ldarg.0
0xd4ab  ldfld    bool System.Windows.Xps.VisualsToXpsDocument::isPrintTicketEventHandlerSet
0xd4b0  brtrue.s loc_D4C5
0xd4b2  ldarg.0
0xd4b3  dup
0xd4b4  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd4b9  call     instance void System.Windows.Xps.VisualsToXpsDocument::SetPrintTicketEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager)
0xd4be  ldarg.0
0xd4bf  ldc.i4.1
0xd4c0  stfld    bool System.Windows.Xps.VisualsToXpsDocument::isPrintTicketEventHandlerSet
0xd4c5  ldarg.0
0xd4c6  ldfld    class System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.VisualsToXpsDocument::parentWriter
0xd4cb  ldarg.0
0xd4cc  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd4d1  ldarg.0
0xd4d2  ldfld    object System.Windows.Xps.VisualsToXpsDocument::_currentUserState
0xd4d7  call     instance void System.Windows.Xps.XpsDocumentWriter::SetProgressChangedEventHandler(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager, object userState)
0xd4dc  ldarg.3
0xd4dd  ldc.i4.3
0xd4de  bne.un.s loc_D4F7
0xd4e0  ldarg.0
0xd4e1  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.VisualsToXpsDocument::_printTicketsTable
0xd4e6  ldarg.0
0xd4e7  ldfld    int32 System.Windows.Xps.VisualsToXpsDocument::_numberOfVisualsCollated
0xd4ec  box      [mscorlib]System.Int32
0xd4f1  ldarg.2
0xd4f2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xd4f7  ldarg.0
0xd4f8  ldfld    valuetype VisualsCollaterState System.Windows.Xps.VisualsToXpsDocument::currentState
0xd4fd  stloc.s  9
0xd4ff  ldloca.s 9
0xd501  ldind.i4
0xd502  ldc.i4.1
0xd503  beq.s    loc_D544
0xd505  ldloca.s 9
0xd507  ldind.i4
0xd508  ldc.i4.2
0xd509  beq.s    loc_D523
0xd50b  ldloca.s 9
0xd50d  ldind.i4
0xd50e  ldc.i4.3
0xd50f  beq.s    loc_D517
0xd511  ldloca.s 9
0xd513  ldind.i4
0xd514  ldc.i4.4
0xd515  bne.un.s loc_D57A
0xd517  ldstr    aXpswriterBatch_0// "XPSWriter.BatchDoneWriting"
0xd51c  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd521  br.s     loc_D57A
0xd523  ldarg.1
0xd524  ldc.i4.1
0xd525  bne.un.s loc_D538
0xd527  ldarg.0
0xd528  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd52d  ldarg.s  4
0xd52f  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xd534  ldc.i4.1
0xd535  stloc.1
0xd536  br.s     loc_D57A
0xd538  ldstr    aXpswriterBatch_2// "XPSWriter.BatchAsync"
0xd53d  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd542  br.s     loc_D57A
0xd544  ldarg.1
0xd545  brtrue.s loc_D570
0xd547  ldarg.0
0xd548  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.VisualsToXpsDocument::_manager
0xd54d  ldarg.s  4
0xd54f  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xd554  leave.s  loc_D56B
0xd556  stloc.s  6
0xd558  ldarg.0
0xd559  ldfld    class System.Windows.Xps.XpsDocumentWriter System.Windows.Xps.VisualsToXpsDocument::parentWriter
0xd55e  ldarg.0
0xd55f  ldloc.s  6
0xd561  call     instance bool System.Windows.Xps.XpsDocumentWriter::OnWritingCanceled([hasfieldmarshal] object value, class [mscorlib]System.Exception sender)
0xd566  pop
0xd567  leave.s  loc_D569
0xd569  leave.s  loc_D57A
0xd56b  leave.s  loc_D57A
0xd56d  ldc.i4.1
0xd56e  stloc.1
0xd56f  endfinally
0xd570  ldstr    aXpswriterBatch_1// "XPSWriter.BatchSync"
0xd575  call     void System.Windows.Xps.XpsWriterException::ThrowException(string message)
0xd57a  ldloc.1
0xd57b  ret
```
