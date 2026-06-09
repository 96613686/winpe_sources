# System.Printing.PrintQueue::Install

- ea: `0xdef0`
- end: `0xe0a9`
- name: `System.Printing.PrintQueue::Install`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x11fe0`

## callees

- `0x3a10`
- `0x3ad0`
- `0x6b50`
- `0xa6f0`
- `0xdbd0`
- `0xdef0`
- `0xf610`
- `0x100f0`
- `0x10120`
- `0x10220`
- `0x12800`
- `0x12a40`
- `0x14540`
- `0x14550`
- `0x14560`
- `0x17110`
- `0x172a0`

## pseudocode

```c

```

## disassembly

```asm
0xdef0  ldnull
0xdef1  stloc.1
0xdef2  ldnull
0xdef3  stloc.3
0xdef4  ldarg.1
0xdef5  brfalse  loc_E065
0xdefa  ldarg.2
0xdefb  brfalse  loc_E065
0xdf00  ldarg.3
0xdf01  brfalse  loc_E065
0xdf06  newobj   instance void MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::.ctor()
0xdf0b  stloc.2
0xdf0c  ldarg.s  5
0xdf0e  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0xdf13  stloc.s  7
0xdf15  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xdf1a  stloc.s  6
0xdf1c  ldloc.s  7
0xdf1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdf23  brfalse  loc_DFBC
0xdf28  ldloc.s  7
0xdf2a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdf2f  castclass [mscorlib]System.Collections.DictionaryEntry
0xdf34  unbox    [mscorlib]System.Collections.DictionaryEntry
0xdf39  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xdf3e  castclass System.Printing.IndexedProperties.PrintProperty
0xdf43  stloc.0
0xdf44  ldloc.0
0xdf45  callvirt instance object System.Printing.IndexedProperties.PrintProperty::get_Value()
0xdf4a  brfalse.s loc_DFB7
0xdf4c  ldloc.0
0xdf4d  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xdf52  ldstr    aHostingprintse_0// "HostingPrintServer"
0xdf57  callvirt instance bool [mscorlib]System.String::Equals(string)
0xdf5c  brtrue.s loc_DFB7
0xdf5e  ldloc.0
0xdf5f  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xdf64  ldstr    aName// "Name"
0xdf69  callvirt instance bool [mscorlib]System.String::Equals(string)
0xdf6e  brtrue.s loc_DFB7
0xdf70  ldloc.0
0xdf71  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xdf76  ldstr    aUserprintticke// "UserPrintTicket"
0xdf7b  callvirt instance bool [mscorlib]System.String::Equals(string)
0xdf80  brtrue.s loc_DFA9
0xdf82  ldloc.0
0xdf83  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xdf88  ldstr    aDefaultprintti// "DefaultPrintTicket"
0xdf8d  callvirt instance bool [mscorlib]System.String::Equals(string)
0xdf92  brtrue.s loc_DFA9
0xdf94  ldloc.2
0xdf95  ldloc.0
0xdf96  call     string System.Printing.PrintQueue::GetAttributeNamePerPrintQueueObject(class System.Printing.IndexedProperties.PrintProperty attributeValue)
0xdf9b  ldloc.0
0xdf9c  call     object System.Printing.PrintQueue::GetAttributeValuePerPrintQueueObject(class System.Printing.IndexedProperties.PrintProperty attributeValue)
0xdfa1  callvirt instance bool MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::SetValueFromName([hasfieldmarshal] string value, object valueName)
0xdfa6  pop
0xdfa7  br.s     loc_DFB7
0xdfa9  ldloc.s  6
0xdfab  ldloc.0
0xdfac  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xdfb1  ldloc.0
0xdfb2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xdfb7  br       loc_DF1C
0xdfbc  ldloc.2
0xdfbd  ldstr    aName// "Name"
0xdfc2  ldarg.1
0xdfc3  callvirt instance bool MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::SetValueFromName([hasfieldmarshal] string value, object valueName)
0xdfc8  pop
0xdfc9  ldloc.2
0xdfca  ldstr    aQueuedrivernam// "QueueDriverName"
0xdfcf  ldarg.2
0xdfd0  callvirt instance bool MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::SetValueFromName([hasfieldmarshal] string value, object valueName)
0xdfd5  pop
0xdfd6  ldloc.2
0xdfd7  ldstr    aQueueportname// "QueuePortName"
0xdfdc  ldarg.3
0xdfdd  call     string System.Printing.PrintQueue::BuildPortNamesString(string[] portNames)
0xdfe2  callvirt instance bool MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::SetValueFromName([hasfieldmarshal] string value, object valueName)
0xdfe7  pop
0xdfe8  ldloc.2
0xdfe9  ldstr    aQueueprintproc// "QueuePrintProcessorName"
0xdfee  ldarg.s  4
0xdff0  callvirt instance bool MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter::SetValueFromName([hasfieldmarshal] string value, object valueName)
0xdff5  pop
0xdff6  ldarg.0
0xdff7  callvirt instance string System.Printing.PrintServer::get_Name()
0xdffc  ldloc.2
0xdffd  call     class MS.Internal.PrintWin32Thunk.PrinterThunkHandler MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkAddPrinter(string serverName, class MS.Internal.PrintWin32Thunk.DirectInteropForPrintQueue.PrinterInfoTwoSetter printInfoTwoLeveThunk)
0xe002  stloc.1
0xe003  ldarg.0
0xe004  ldarg.1
0xe005  ldc.i4   0xF000C
0xe00a  newobj   instance void System.Printing.PrintQueue::.ctor(class System.Printing.PrintServer printServer, string printQueueName, valuetype System.Printing.PrintSystemDesiredAccess desiredAccess)
0xe00f  stloc.3
0xe010  ldloc.s  6
0xe012  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0xe017  stloc.s  5
0xe019  ldloc.s  5
0xe01b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe020  brfalse.s loc_E05F
0xe022  ldloc.s  5
0xe024  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe029  castclass [mscorlib]System.Collections.DictionaryEntry
0xe02e  unbox    [mscorlib]System.Collections.DictionaryEntry
0xe033  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xe038  castclass System.Printing.IndexedProperties.PrintProperty
0xe03d  stloc.s  4
0xe03f  ldloc.3
0xe040  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0xe045  ldloc.s  4
0xe047  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0xe04c  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0xe051  ldloc.s  4
0xe053  callvirt instance object System.Printing.IndexedProperties.PrintProperty::get_Value()
0xe058  callvirt instance void System.Printing.IndexedProperties.PrintProperty::set_Value(object objValue)
0xe05d  br.s     loc_E019
0xe05f  ldloc.3
0xe060  callvirt instance void System.Printing.PrintQueue::Commit()
0xe065  leave.s  loc_E09B
0xe067  ldloc.1
0xe068  brfalse.s loc_E073
0xe06a  ldloc.1
0xe06b  stloc.s  0xA
0xe06d  ldloc.1
0xe06e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe073  throw
0xe074  leave.s  loc_E09B
0xe076  stloc.s  8
0xe078  ldloc.1
0xe079  brfalse.s loc_E084
0xe07b  ldloc.1
0xe07c  stloc.s  9
0xe07e  ldloc.1
0xe07f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe084  ldarg.0
0xe085  ldloc.s  8
0xe087  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0xe08c  ldstr    aPrintsystemexc_1// "PrintSystemException.PrintServer.AddPri"...
0xe091  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0xe096  throw
0xe097  leave.s  loc_E09B
0xe099  leave.s  loc_E0A7
0xe09b  leave.s  loc_E0A7
0xe09d  ldloc.1
0xe09e  brfalse.s loc_E0A6
0xe0a0  ldloc.1
0xe0a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0a6  endfinally
0xe0a7  ldloc.3
0xe0a8  ret
```
