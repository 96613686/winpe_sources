# System.Printing.PrintSystemJobInfo::Restart

- ea: `0x178c0`
- end: `0x17931`
- name: `System.Printing.PrintSystemJobInfo::Restart`
- size: `113`
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
- `0x178c0`
- `0x17fd0`
- `0x18120`
- `0x18950`
- `0x18980`
- `0x18990`

## string_xrefs

- `0x17925`: `PrintSystemException.PrintSystemJobInfo.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x178c0  ldarg.0
0x178c1  call     instance void System.Printing.PrintSystemJobInfo::VerifyAccess()
0x178c6  ldarg.0
0x178c7  ldfld    bool System.Printing.PrintSystemJobInfo::isDeleted
0x178cc  brtrue.s loc_17925
0x178ce  ldarg.0
0x178cf  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x178d4  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::get_PrinterThunkHandler()
0x178d9  ldarg.0
0x178da  ldfld    int32 System.Printing.PrintSystemJobInfo::jobIdentifier
0x178df  ldc.i4.4
0x178e0  call     instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetJob([hasfieldmarshal] unsigned int32 value, unsigned int32 jobID)
0x178e5  pop
0x178e6  ldstr    aStatus// "Status"
0x178eb  stloc.0
0x178ec  ldarg.0
0x178ed  ldloc.0
0x178ee  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemJobInfo::get_InternalPropertiesCollection(string attributeName)
0x178f3  ldloc.0
0x178f4  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x178f9  ldc.i4.1
0x178fa  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInternallyInitialized([hasfieldmarshal] bool A_0)
0x178ff  ldarg.0
0x17900  dup
0x17901  ldfld    valuetype System.Printing.PrintJobStatus System.Printing.PrintSystemJobInfo::jobStatus
0x17906  ldc.i4   0x800
0x1790b  or
0x1790c  call     instance void System.Printing.PrintSystemJobInfo::set_JobStatusSecondary(int32 status)
0x17911  leave.s  loc_17930
0x17913  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x17918  ldstr    aPrintsystemexc_22// "PrintSystemException.PrintSystemJobInfo"...
0x1791d  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x17922  throw
0x17923  leave.s  loc_17930
0x17925  ldstr    aPrintsystemexc_23// "PrintSystemException.PrintSystemJobInfo"...
0x1792a  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId)
0x1792f  throw
0x17930  ret
```
