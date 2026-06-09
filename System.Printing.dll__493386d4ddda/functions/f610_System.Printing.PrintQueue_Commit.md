# System.Printing.PrintQueue::Commit

- ea: `0xf610`
- end: `0xf70e`
- name: `System.Printing.PrintQueue::Commit`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0xdef0`

## callees

- `0xa6f0`
- `0xe640`
- `0xf610`
- `0xf850`
- `0xfd70`
- `0x102b0`
- `0x110d0`
- `0x11410`
- `0x12800`
- `0x145f0`
- `0x17110`
- `0x1b4a0`
- `0x1b4c0`

## string_xrefs

- `0xf6e0`: `PrintSystemException.PrintQueue.Commit`

## pseudocode

```c

```

## disassembly

```asm
0xf610  ldarg.0
0xf611  call     instance void System.Printing.PrintQueue::VerifyAccess()
0xf616  ldnull
0xf617  stloc.2
0xf618  ldarg.0
0xf619  ldfld    bool System.Printing.PrintQueue::isBrowsable
0xf61e  brfalse.s loc_F62D
0xf620  ldarg.0
0xf621  call     instance void System.Printing.PrintQueue::ActivateBrowsableQueue()
0xf626  ldarg.0
0xf627  ldc.i4.0
0xf628  stfld    bool System.Printing.PrintQueue::isBrowsable
0xf62d  ldarg.0
0xf62e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf633  newobj   instance void MS.Internal.PrintWin32Thunk.SetDataThunkObject::.ctor(class [mscorlib]System.Type printingType)
0xf638  stloc.2
0xf639  ldnull
0xf63a  stloc.0
0xf63b  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xf640  stloc.s  5
0xf642  ldarg.0
0xf643  ldloc.s  5
0xf645  call     instance string[] System.Printing.PrintQueue::GetAlteredPropertiesFilter(class [System]System.Collections.Specialized.StringCollection collection)
0xf64a  stloc.0
0xf64b  ldloc.2
0xf64c  ldarg.0
0xf64d  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::printerThunkHandler
0xf652  ldarg.0
0xf653  ldloc.0
0xf654  call     instance bool MS.Internal.PrintWin32Thunk.SetDataThunkObject::CommitDataFromPrintSystemObject([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, class System.Printing.PrintSystemObject printingHandler, string[] printObject)
0xf659  pop
0xf65a  ldloc.0
0xf65b  brfalse.s loc_F6BA
0xf65d  ldc.i4.0
0xf65e  stloc.1
0xf65f  ldloc.1
0xf660  ldloc.0
0xf661  ldlen
0xf662  bge.s    loc_F6BA
0xf664  ldnull
0xf665  stloc.s  4
0xf667  ldarg.0
0xf668  ldloc.0
0xf669  ldloc.1
0xf66a  ldelem.ref
0xf66b  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintQueue::get_InternalPropertiesCollection(string attributeName)
0xf670  stloc.s  4
0xf672  ldloc.s  4
0xf674  ldloc.0
0xf675  ldloc.1
0xf676  ldelem.ref
0xf677  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xf67c  ldc.i4.0
0xf67d  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0xf682  ldloc.s  4
0xf684  ldarg.0
0xf685  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xf68a  beq.s    loc_F6B4
0xf68c  ldnull
0xf68d  stloc.s  6
0xf68f  ldloc.s  5
0xf691  ldc.i4.0
0xf692  call     instance string [System]System.Collections.Specialized.StringCollection::get_Item(int32)
0xf697  stloc.s  6
0xf699  ldarg.0
0xf69a  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xf69f  ldloc.s  6
0xf6a1  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xf6a6  ldc.i4.0
0xf6a7  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0xf6ac  ldloc.s  5
0xf6ae  ldc.i4.0
0xf6af  callvirt instance void [System]System.Collections.Specialized.StringCollection::RemoveAt(int32)
0xf6b4  ldloc.1
0xf6b5  ldc.i4.1
0xf6b6  add
0xf6b7  stloc.1
0xf6b8  br.s     loc_F65F
0xf6ba  ldarg.0
0xf6bb  dup
0xf6bc  ldarg.0
0xf6bd  ldfld    class System.Printing.PrintServer System.Printing.PrintQueue::hostingPrintServer
0xf6c2  callvirt instance string System.Printing.PrintServer::get_Name()
0xf6c7  ldarg.0
0xf6c8  callvirt instance string System.Printing.PrintQueue::get_Name()
0xf6cd  call     instance string System.Printing.PrintQueue::PrepareNameForDownLevelConnectivity(string serverName, string printerName)
0xf6d2  stfld    string System.Printing.PrintQueue::fullQueueName
0xf6d7  leave.s  loc_F701
0xf6d9  stloc.3
0xf6da  ldloc.3
0xf6db  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0xf6e0  ldstr    aPrintsystemexc_6// "PrintSystemException.PrintQueue.Commit"
0xf6e5  ldloc.3
0xf6e6  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [ReachFramework]System.Printing.PrintCommitAttributesException::get_CommittedAttributesCollection()
0xf6eb  ldloc.3
0xf6ec  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [ReachFramework]System.Printing.PrintCommitAttributesException::get_FailedAttributesCollection()
0xf6f1  ldarg.0
0xf6f2  callvirt instance string System.Printing.PrintQueue::get_Name()
0xf6f7  newobj   instance void [ReachFramework]System.Printing.PrintCommitAttributesException::.ctor(int32, string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>, string)
0xf6fc  throw
0xf6fd  leave.s  loc_F701
0xf6ff  leave.s  loc_F70D
0xf701  leave.s  loc_F70D
0xf703  ldloc.2
0xf704  brfalse.s loc_F70C
0xf706  ldloc.2
0xf707  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf70c  endfinally
0xf70d  ret
```
