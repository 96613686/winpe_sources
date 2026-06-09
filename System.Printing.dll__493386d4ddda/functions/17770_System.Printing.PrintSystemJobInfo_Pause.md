# System.Printing.PrintSystemJobInfo::Pause

- ea: `0x17770`
- end: `0x177dd`
- name: `System.Printing.PrintSystemJobInfo::Pause`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x64b0`
- `0xfc70`
- `0x145d0`
- `0x17110`
- `0x172a0`
- `0x17770`
- `0x17fd0`
- `0x18120`
- `0x18950`
- `0x18980`
- `0x18990`

## string_xrefs

- `0x177d1`: `PrintSystemException.PrintSystemJobInfo.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x17770  ldarg.0
0x17771  call     instance void System.Printing.PrintSystemJobInfo::VerifyAccess()
0x17776  ldarg.0
0x17777  ldfld    bool System.Printing.PrintSystemJobInfo::isDeleted
0x1777c  brtrue.s loc_177D1
0x1777e  ldarg.0
0x1777f  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17784  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::get_PrinterThunkHandler()
0x17789  ldarg.0
0x1778a  ldfld    int32 System.Printing.PrintSystemJobInfo::jobIdentifier
0x1778f  ldc.i4.1
0x17790  call     instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetJob([hasfieldmarshal] unsigned int32 value, unsigned int32 jobID)
0x17795  pop
0x17796  ldstr    aStatus// "Status"
0x1779b  stloc.0
0x1779c  ldarg.0
0x1779d  ldloc.0
0x1779e  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemJobInfo::get_InternalPropertiesCollection(string attributeName)
0x177a3  ldloc.0
0x177a4  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x177a9  ldc.i4.1
0x177aa  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInternallyInitialized([hasfieldmarshal] bool A_0)
0x177af  ldarg.0
0x177b0  dup
0x177b1  ldfld    valuetype System.Printing.PrintJobStatus System.Printing.PrintSystemJobInfo::jobStatus
0x177b6  ldc.i4.1
0x177b7  or
0x177b8  call     instance void System.Printing.PrintSystemJobInfo::set_JobStatusSecondary(int32 status)
0x177bd  leave.s  loc_177DC
0x177bf  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x177c4  ldstr    aPrintsystemexc_22// "PrintSystemException.PrintSystemJobInfo"...
0x177c9  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x177ce  throw
0x177cf  leave.s  loc_177DC
0x177d1  ldstr    aPrintsystemexc_23// "PrintSystemException.PrintSystemJobInfo"...
0x177d6  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId)
0x177db  throw
0x177dc  ret
```
