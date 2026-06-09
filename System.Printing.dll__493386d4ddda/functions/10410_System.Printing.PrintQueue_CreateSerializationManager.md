# System.Printing.PrintQueue::CreateSerializationManager

- ea: `0x10410`
- end: `0x10524`
- name: `System.Printing.PrintQueue::CreateSerializationManager`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0xc6e0`
- `0xd330`
- `0x10530`

## callees

- `0xb130`
- `0xddf0`
- `0xdea0`
- `0xe550`
- `0xf540`
- `0x10410`
- `0x10680`
- `0x18c60`
- `0x18d90`

## pseudocode

```c

```

## disassembly

```asm
0x10410  ldarg.0
0x10411  ldc.i4.0
0x10412  stfld    bool System.Printing.PrintQueue::printingIsCancelled
0x10417  ldarg.0
0x10418  call     instance bool System.Printing.PrintQueue::get_IsXpsDevice()
0x1041d  brtrue.s loc_1042C
0x1041f  ldarg.0
0x10420  call     instance bool System.Printing.PrintQueue::IsXpsDeviceSimulationSupported()
0x10425  brtrue.s loc_1042C
0x10427  ldc.i4.0
0x10428  stloc.s  6
0x1042a  br.s     loc_1042F
0x1042c  ldc.i4.1
0x1042d  stloc.s  6
0x1042f  ldloc.s  6
0x10431  conv.u1
0x10432  stloc.s  7
0x10434  ldarg.0
0x10435  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0x1043a  brfalse.s loc_1044C
0x1043c  ldarg.0
0x1043d  ldarg.1
0x1043e  ldc.i4.0
0x1043f  ldarg.3
0x10440  ldarg.2
0x10441  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateXpsOMSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool isAsync, class [ReachFramework]System.Printing.PrintTicket printTicket, [hasfieldmarshal] bool mustSetPrintJobIdentifier)
0x10446  stloc.2
0x10447  br       loc_10522
0x1044c  ldloc.s  7
0x1044e  brtrue.s loc_1045D
0x10450  ldarg.0
0x10451  ldarg.1
0x10452  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager::.ctor(class [System.Printing]System.Printing.PrintQueue, bool)
0x10457  stloc.2
0x10458  br       loc_10522
0x1045d  ldarg.0
0x1045e  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x10463  call     instance string System.Printing.PrintJobSettings::get_Description()
0x10468  stloc.s  5
0x1046a  ldarg.0
0x1046b  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x10470  call     instance string System.Printing.PrintJobSettings::get_Description()
0x10475  ldnull
0x10476  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1047b  brfalse.s loc_10484
0x1047d  ldsfld   string System.Printing.PrintQueue::defaultXpsJobName
0x10482  stloc.s  5
0x10484  ldarg.0
0x10485  ldloc.s  5
0x10487  ldc.i4.0
0x10488  ldarg.3
0x10489  newobj   instance void System.Printing.PrintQueueStream::.ctor(class System.Printing.PrintQueue printQueue, string printJobName, [hasfieldmarshal] bool commitDataOnClose, class [ReachFramework]System.Printing.PrintTicket printTicket)
0x1048e  stloc.1
0x1048f  ldloc.1
0x10490  call     class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateXpsDocument(class [mscorlib]System.IO.Stream)
0x10495  stloc.s  4
0x10497  ldloc.s  4
0x10499  ldc.i4.1
0x1049a  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsPackagingPolicy::.ctor(class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument, valuetype [ReachFramework]System.Windows.Xps.Packaging.PackageInterleavingOrder)
0x1049f  stloc.3
0x104a0  ldloc.3
0x104a1  ldloc.1
0x104a2  ldftn    instance void System.Printing.PrintQueueStream::HandlePackagingProgressEvent(object sender, class [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventArgs e)
0x104a8  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventHandler::.ctor(object, native int)
0x104ad  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsPackagingPolicy::add_PackagingProgressEvent(class [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventHandler)
0x104b2  ldloc.3
0x104b3  ldarg.1
0x104b4  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::.ctor(class [ReachFramework]System.Windows.Xps.Serialization.BasePackagingPolicy, bool)
0x104b9  stloc.0
0x104ba  ldloc.0
0x104bb  ldc.i4.1
0x104bc  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::SetFontSubsettingPolicy(valuetype [ReachFramework]System.Windows.Xps.Serialization.FontSubsetterCommitPolicies)
0x104c1  ldloc.0
0x104c2  ldc.i4.4
0x104c3  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::SetFontSubsettingCountPolicy(int32)
0x104c8  ldloc.0
0x104c9  stloc.2
0x104ca  ldloc.0
0x104cb  brfalse.s loc_10522
0x104cd  ldloc.0
0x104ce  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0x104d3  ldarg.0
0x104d4  ldftn    instance void System.Printing.PrintQueue::ForwardXpsDriverDocEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventArgs args)
0x104da  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventHandler::.ctor(object, native int)
0x104df  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationXpsDriverDocEvent(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventHandler)
0x104e4  ldarg.0
0x104e5  ldfld    object System.Printing.PrintQueue::_lockObject
0x104ea  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x104ef  ldarg.0
0x104f0  ldc.i4.1
0x104f1  stfld    bool System.Printing.PrintQueue::isWriterAttached
0x104f6  ldarg.0
0x104f7  ldloc.1
0x104f8  stfld    class System.Printing.PrintQueueStream System.Printing.PrintQueue::writerStream
0x104fd  ldarg.0
0x104fe  ldloc.s  4
0x10500  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Printing.PrintQueue::xpsDocument
0x10505  ldarg.2
0x10506  brfalse.s loc_10514
0x10508  ldloc.0
0x10509  ldloc.1
0x1050a  call     instance int32 System.Printing.PrintQueueStream::get_JobIdentifier()
0x1050f  call     instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::set_JobIdentifier(int32)
0x10514  leave.s  loc_10522
0x10516  ldarg.0
0x10517  ldfld    object System.Printing.PrintQueue::_lockObject
0x1051c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x10521  endfinally
0x10522  ldloc.2
0x10523  ret
```
