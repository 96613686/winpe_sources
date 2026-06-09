# System.Printing.PrintSystemJobInfo::Resume

- ea: `0x177e0`
- end: `0x1784e`
- name: `System.Printing.PrintSystemJobInfo::Resume`
- size: `110`
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
- `0x177e0`
- `0x17fd0`
- `0x18120`
- `0x18950`
- `0x18980`
- `0x18990`

## string_xrefs

- `0x17842`: `PrintSystemException.PrintSystemJobInfo.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x177e0  ldarg.0
0x177e1  call     instance void System.Printing.PrintSystemJobInfo::VerifyAccess()
0x177e6  ldarg.0
0x177e7  ldfld    bool System.Printing.PrintSystemJobInfo::isDeleted
0x177ec  brtrue.s loc_17842
0x177ee  ldarg.0
0x177ef  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x177f4  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::get_PrinterThunkHandler()
0x177f9  ldarg.0
0x177fa  ldfld    int32 System.Printing.PrintSystemJobInfo::jobIdentifier
0x177ff  ldc.i4.2
0x17800  call     instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetJob([hasfieldmarshal] unsigned int32 value, unsigned int32 jobID)
0x17805  pop
0x17806  ldstr    aStatus// "Status"
0x1780b  stloc.0
0x1780c  ldarg.0
0x1780d  ldloc.0
0x1780e  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemJobInfo::get_InternalPropertiesCollection(string attributeName)
0x17813  ldloc.0
0x17814  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x17819  ldc.i4.1
0x1781a  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInternallyInitialized([hasfieldmarshal] bool A_0)
0x1781f  ldarg.0
0x17820  dup
0x17821  ldfld    valuetype System.Printing.PrintJobStatus System.Printing.PrintSystemJobInfo::jobStatus
0x17826  ldc.i4.s 0xFE
0x17828  and
0x17829  call     instance void System.Printing.PrintSystemJobInfo::set_JobStatusSecondary(int32 status)
0x1782e  leave.s  loc_1784D
0x17830  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x17835  ldstr    aPrintsystemexc_22// "PrintSystemException.PrintSystemJobInfo"...
0x1783a  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x1783f  throw
0x17840  leave.s  loc_1784D
0x17842  ldstr    aPrintsystemexc_23// "PrintSystemException.PrintSystemJobInfo"...
0x17847  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId)
0x1784c  throw
0x1784d  ret
```
