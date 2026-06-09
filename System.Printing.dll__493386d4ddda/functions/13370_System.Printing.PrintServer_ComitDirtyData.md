# System.Printing.PrintServer::ComitDirtyData

- ea: `0x13370`
- end: `0x13452`
- name: `System.Printing.PrintServer::ComitDirtyData`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x12140`

## callees

- `0xa6f0`
- `0x128c0`
- `0x12a50`
- `0x13370`
- `0x13550`
- `0x14540`
- `0x14550`
- `0x145f0`
- `0x17110`
- `0x172a0`

## string_xrefs

- `0x13441`: `PrintSystemException.PrintServer.Commit`

## pseudocode

```c

```

## disassembly

```asm
0x13370  ldnull
0x13371  stloc.s  7
0x13373  ldnull
0x13374  stloc.s  6
0x13376  ldnull
0x13377  stloc.s  5
0x13379  ldc.i4.0
0x1337a  stloc.1
0x1337b  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x13380  stloc.s  4
0x13382  ldarg.1
0x13383  brfalse  loc_13418
0x13388  ldc.i4.0
0x13389  stloc.2
0x1338a  ldloc.2
0x1338b  ldarg.1
0x1338c  ldlen
0x1338d  bge      loc_13418
0x13392  ldarg.0
0x13393  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x13398  ldarg.1
0x13399  ldloc.2
0x1339a  ldelem.ref
0x1339b  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x133a0  stloc.0
0x133a1  ldsfld   class [mscorlib]System.Collections.Hashtable System.Printing.PrintServer::internalAttributeNameMapping
0x133a6  ldloc.0
0x133a7  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0x133ac  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x133b1  castclass [mscorlib]System.String
0x133b6  stloc.s  7
0x133b8  ldsfld   class [mscorlib]System.Collections.Hashtable System.Printing.PrintServer::setAttributeInteropMap
0x133bd  ldloc.0
0x133be  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x133c3  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x133c8  castclass ThunkSetPrinterData
0x133cd  stloc.s  6
0x133cf  ldloc.s  6
0x133d1  ldarg.0
0x133d2  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintServer::serverThunkHandler
0x133d7  ldloc.s  7
0x133d9  ldloc.0
0x133da  callvirt instance object System.Printing.IndexedProperties.PrintProperty::get_Value()
0x133df  callvirt instance bool ThunkSetPrinterData::Invoke([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string printerHandle, object valueName)
0x133e4  pop
0x133e5  ldloc.s  4
0x133e7  ldloc.0
0x133e8  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0x133ed  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x133f2  ldarg.0
0x133f3  ldloc.0
0x133f4  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0x133f9  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintServer::get_InternalPropertiesCollection(string attributeName)
0x133fe  ldloc.0
0x133ff  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0x13404  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x13409  ldc.i4.0
0x1340a  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsDirty([hasfieldmarshal] bool setDirty)
0x1340f  ldloc.2
0x13410  ldc.i4.1
0x13411  add
0x13412  stloc.2
0x13413  br       loc_1338A
0x13418  leave.s  loc_13451
0x1341a  stloc.s  5
0x1341c  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x13421  stloc.3
0x13422  ldloc.1
0x13423  ldarg.1
0x13424  ldlen
0x13425  bge.s    loc_13439
0x13427  ldloc.3
0x13428  ldarg.1
0x13429  ldloc.1
0x1342a  ldelem.ref
0x1342b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x13430  ldloc.1
0x13431  ldc.i4.1
0x13432  add
0x13433  stloc.1
0x13434  ldloc.1
0x13435  ldarg.1
0x13436  ldlen
0x13437  blt.s    loc_13427
0x13439  ldarg.0
0x1343a  ldloc.s  5
0x1343c  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x13441  ldstr    aPrintsystemexc_12// "PrintSystemException.PrintServer.Commit"
0x13446  ldloc.s  4
0x13448  ldloc.3
0x13449  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintCommitAttributesException(int32 hresult, string messageId, class [mscorlib]System.Collections.ObjectModel.Collection`1<string> commitedAttributes, class [mscorlib]System.Collections.ObjectModel.Collection`1<string> failedAttributes)
0x1344e  throw
0x1344f  leave.s  loc_13451
0x13451  ret
```
