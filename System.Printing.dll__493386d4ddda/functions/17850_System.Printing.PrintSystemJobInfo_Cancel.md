# System.Printing.PrintSystemJobInfo::Cancel

- ea: `0x17850`
- end: `0x178ba`
- name: `System.Printing.PrintSystemJobInfo::Cancel`
- size: `106`
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
- `0x17850`
- `0x17fd0`
- `0x18120`
- `0x18950`
- `0x18980`
- `0x18990`

## string_xrefs

- `0x178ae`: `PrintSystemException.PrintSystemJobInfo.Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x17850  ldarg.0
0x17851  call     instance void System.Printing.PrintSystemJobInfo::VerifyAccess()
0x17856  ldarg.0
0x17857  ldfld    bool System.Printing.PrintSystemJobInfo::isDeleted
0x1785c  brtrue.s loc_178AE
0x1785e  ldarg.0
0x1785f  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17864  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::get_PrinterThunkHandler()
0x17869  ldarg.0
0x1786a  ldfld    int32 System.Printing.PrintSystemJobInfo::jobIdentifier
0x1786f  ldc.i4.5
0x17870  call     instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetJob([hasfieldmarshal] unsigned int32 value, unsigned int32 jobID)
0x17875  pop
0x17876  ldstr    aStatus// "Status"
0x1787b  stloc.0
0x1787c  ldarg.0
0x1787d  ldloc.0
0x1787e  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemJobInfo::get_InternalPropertiesCollection(string attributeName)
0x17883  ldloc.0
0x17884  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x17889  ldc.i4.1
0x1788a  call     instance void System.Printing.IndexedProperties.PrintProperty::set_IsInternallyInitialized([hasfieldmarshal] bool A_0)
0x1788f  ldarg.0
0x17890  ldc.i4   0x100
0x17895  call     instance void System.Printing.PrintSystemJobInfo::set_JobStatusSecondary(int32 status)
0x1789a  leave.s  loc_178B9
0x1789c  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x178a1  ldstr    aPrintsystemexc_22// "PrintSystemException.PrintSystemJobInfo"...
0x178a6  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x178ab  throw
0x178ac  leave.s  loc_178B9
0x178ae  ldstr    aPrintsystemexc_23// "PrintSystemException.PrintSystemJobInfo"...
0x178b3  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId)
0x178b8  throw
0x178b9  ret
```
