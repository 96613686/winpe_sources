# System.Printing.PrintQueue::CreateAsyncSerializationManager

- ea: `0x10550`
- end: `0x1066b`
- name: `System.Printing.PrintQueue::CreateAsyncSerializationManager`
- size: `283`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0xc6e0`
- `0xd330`
- `0x10670`

## callees

- `0xb130`
- `0xddf0`
- `0xdea0`
- `0xe550`
- `0xf540`
- `0x10550`
- `0x10680`
- `0x18b80`
- `0x18d90`

## pseudocode

```c

```

## disassembly

```asm
0x10550  ldarg.0
0x10551  ldc.i4.0
0x10552  stfld    bool System.Printing.PrintQueue::printingIsCancelled
0x10557  ldarg.0
0x10558  call     instance bool System.Printing.PrintQueue::get_IsXpsDevice()
0x1055d  brtrue.s loc_1056C
0x1055f  ldarg.0
0x10560  call     instance bool System.Printing.PrintQueue::IsXpsDeviceSimulationSupported()
0x10565  brtrue.s loc_1056C
0x10567  ldc.i4.0
0x10568  stloc.s  6
0x1056a  br.s     loc_1056F
0x1056c  ldc.i4.1
0x1056d  stloc.s  6
0x1056f  ldloc.s  6
0x10571  conv.u1
0x10572  stloc.s  7
0x10574  ldarg.0
0x10575  call     instance bool System.Printing.PrintQueue::IsXpsOMPrintingSupported()
0x1057a  brfalse.s loc_1058C
0x1057c  ldarg.0
0x1057d  ldarg.1
0x1057e  ldc.i4.1
0x1057f  ldarg.3
0x10580  ldarg.2
0x10581  call     instance class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Printing.PrintQueue::CreateXpsOMSerializationManager([hasfieldmarshal] bool isBatchMode, [hasfieldmarshal] bool isAsync, class [ReachFramework]System.Printing.PrintTicket printTicket, [hasfieldmarshal] bool mustSetPrintJobIdentifier)
0x10586  stloc.2
0x10587  br       loc_10669
0x1058c  ldloc.s  7
0x1058e  brtrue.s loc_105A6
0x10590  ldarg.2
0x10591  brfalse.s loc_10599
0x10593  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x10598  throw
0x10599  ldarg.0
0x1059a  ldarg.1
0x1059b  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::.ctor(class [System.Printing]System.Printing.PrintQueue, bool)
0x105a0  stloc.2
0x105a1  br       loc_10669
0x105a6  ldarg.0
0x105a7  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x105ac  call     instance string System.Printing.PrintJobSettings::get_Description()
0x105b1  stloc.s  5
0x105b3  ldarg.0
0x105b4  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x105b9  call     instance string System.Printing.PrintJobSettings::get_Description()
0x105be  ldnull
0x105bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x105c4  brfalse.s loc_105CD
0x105c6  ldsfld   string System.Printing.PrintQueue::defaultXpsJobName
0x105cb  stloc.s  5
0x105cd  ldarg.0
0x105ce  ldloc.s  5
0x105d0  newobj   instance void System.Printing.PrintQueueStream::.ctor(class System.Printing.PrintQueue printQueue, string printJobName)
0x105d5  stloc.1
0x105d6  ldloc.1
0x105d7  call     class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::CreateXpsDocument(class [mscorlib]System.IO.Stream)
0x105dc  stloc.s  4
0x105de  ldloc.s  4
0x105e0  ldc.i4.1
0x105e1  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsPackagingPolicy::.ctor(class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument, valuetype [ReachFramework]System.Windows.Xps.Packaging.PackageInterleavingOrder)
0x105e6  stloc.3
0x105e7  ldloc.3
0x105e8  ldloc.1
0x105e9  ldftn    instance void System.Printing.PrintQueueStream::HandlePackagingProgressEvent(object sender, class [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventArgs e)
0x105ef  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventHandler::.ctor(object, native int)
0x105f4  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsPackagingPolicy::add_PackagingProgressEvent(class [ReachFramework]System.Windows.Xps.Packaging.PackagingProgressEventHandler)
0x105f9  ldloc.3
0x105fa  ldarg.1
0x105fb  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync::.ctor(class [ReachFramework]System.Windows.Xps.Serialization.BasePackagingPolicy, bool)
0x10600  stloc.0
0x10601  ldloc.0
0x10602  ldc.i4.1
0x10603  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::SetFontSubsettingPolicy(valuetype [ReachFramework]System.Windows.Xps.Serialization.FontSubsetterCommitPolicies)
0x10608  ldloc.0
0x10609  ldc.i4.4
0x1060a  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::SetFontSubsettingCountPolicy(int32)
0x1060f  ldloc.0
0x10610  stloc.2
0x10611  ldloc.0
0x10612  brfalse.s loc_10669
0x10614  ldloc.0
0x10615  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0x1061a  ldarg.0
0x1061b  ldftn    instance void System.Printing.PrintQueue::ForwardXpsDriverDocEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventArgs args)
0x10621  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventHandler::.ctor(object, native int)
0x10626  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationXpsDriverDocEvent(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationXpsDriverDocEventHandler)
0x1062b  ldarg.0
0x1062c  ldfld    object System.Printing.PrintQueue::_lockObject
0x10631  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x10636  ldarg.0
0x10637  ldc.i4.1
0x10638  stfld    bool System.Printing.PrintQueue::isWriterAttached
0x1063d  ldarg.0
0x1063e  ldloc.1
0x1063f  stfld    class System.Printing.PrintQueueStream System.Printing.PrintQueue::writerStream
0x10644  ldarg.0
0x10645  ldloc.s  4
0x10647  stfld    class [ReachFramework]System.Windows.Xps.Packaging.XpsDocument System.Printing.PrintQueue::xpsDocument
0x1064c  ldarg.2
0x1064d  brfalse.s loc_1065B
0x1064f  ldloc.0
0x10650  ldloc.1
0x10651  call     instance int32 System.Printing.PrintQueueStream::get_JobIdentifier()
0x10656  call     instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::set_JobIdentifier(int32)
0x1065b  leave.s  loc_10669
0x1065d  ldarg.0
0x1065e  ldfld    object System.Printing.PrintQueue::_lockObject
0x10663  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x10668  endfinally
0x10669  ldloc.2
0x1066a  ret
```
