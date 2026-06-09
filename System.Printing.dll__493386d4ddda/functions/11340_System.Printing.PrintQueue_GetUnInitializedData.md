# System.Printing.PrintQueue::GetUnInitializedData

- ea: `0x11340`
- end: `0x11410`
- name: `System.Printing.PrintQueue::GetUnInitializedData`
- size: `208`
- prototype: ``
- caller_count: `54`
- callee_count: `10`
- tags: ``

## callers

- `0xe5e0`
- `0xe760`
- `0xe7c0`
- `0xe820`
- `0xe880`
- `0xe8a0`
- `0xe910`
- `0xe9f0`
- `0xea60`
- `0xead0`
- `0xeb40`
- `0xeba0`
- `0xed00`
- `0xee60`
- `0xeef0`
- `0xef80`
- `0xf010`
- `0xf090`
- `0xf0b0`
- `0xf0d0`
- `0xf0f0`
- `0xf110`
- `0xf130`
- `0xf150`
- `0xf170`
- `0xf190`
- `0xf1b0`
- `0xf1d0`
- `0xf1f0`
- `0xf210`
- `0xf230`
- `0xf250`
- `0xf270`
- `0xf290`
- `0xf2b0`
- `0xf2d0`
- `0xf2f0`
- `0xf310`
- `0xf340`
- `0xf360`
- `0xf380`
- `0xf3a0`
- `0xf3c0`
- `0xf3e0`
- `0xf400`
- `0xf420`
- `0xf440`
- `0xf460`
- `0xf480`
- `0xf4a0`

## callees

- `0xa6f0`
- `0xf850`
- `0x102b0`
- `0x11340`
- `0x11a70`
- `0x14570`
- `0x17110`
- `0x172a0`
- `0x1ae80`
- `0x1aed0`

## pseudocode

```c

```

## disassembly

```asm
0x11340  ldnull
0x11341  stloc.1
0x11342  ldarg.0
0x11343  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x11348  ldarg.1
0x11349  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x1134e  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsInitialized()
0x11353  brtrue   loc_113ED
0x11358  ldarg.0
0x11359  ldarg.2
0x1135a  callvirt instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintQueue::get_InternalPropertiesCollection(string attributeName)
0x1135f  ldarg.2
0x11360  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x11365  call     instance bool System.Printing.IndexedProperties.PrintProperty::get_IsInitialized()
0x1136a  brtrue   loc_113ED
0x1136f  ldarg.0
0x11370  ldfld    bool System.Printing.PrintQueue::isBrowsable
0x11375  brfalse.s loc_11384
0x11377  ldarg.0
0x11378  call     instance void System.Printing.PrintQueue::ActivateBrowsableQueue()
0x1137d  ldarg.0
0x1137e  ldc.i4.0
0x1137f  stfld    bool System.Printing.PrintQueue::isBrowsable
0x11384  ldarg.0
0x11385  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1138a  newobj   instance void MS.Internal.PrintWin32Thunk.GetDataThunkObject::.ctor(class [mscorlib]System.Type printingType)
0x1138f  stloc.1
0x11390  ldc.i4.1
0x11391  newarr   [mscorlib]System.String
0x11396  stloc.s  4
0x11398  ldloc.s  4
0x1139a  ldc.i4.0
0x1139b  ldarg.2
0x1139c  stelem.ref
0x1139d  ldloc.1
0x1139e  ldarg.0
0x1139f  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::printerThunkHandler
0x113a4  ldarg.0
0x113a5  ldloc.s  4
0x113a7  call     instance bool MS.Internal.PrintWin32Thunk.GetDataThunkObject::PopulatePrintSystemObject([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, class System.Printing.PrintSystemObject printingHandler, string[] printObject)
0x113ac  pop
0x113ad  ldarg.0
0x113ae  ldfld    string[] System.Printing.PrintQueue::refreshPropertiesFilter
0x113b3  ldlen
0x113b4  ldc.i4.1
0x113b5  add
0x113b6  newarr   [mscorlib]System.String
0x113bb  stloc.2
0x113bc  ldc.i4.0
0x113bd  stloc.0
0x113be  ldc.i4.0
0x113bf  stloc.0
0x113c0  ldarg.0
0x113c1  ldfld    string[] System.Printing.PrintQueue::refreshPropertiesFilter
0x113c6  stloc.3
0x113c7  ldloc.0
0x113c8  ldloc.3
0x113c9  ldlen
0x113ca  bge.s    loc_113D8
0x113cc  ldloc.2
0x113cd  ldloc.0
0x113ce  ldloc.3
0x113cf  ldloc.0
0x113d0  ldelem.ref
0x113d1  stelem.ref
0x113d2  ldloc.0
0x113d3  ldc.i4.1
0x113d4  add
0x113d5  stloc.0
0x113d6  br.s     loc_113C0
0x113d8  ldloc.2
0x113d9  ldloc.0
0x113da  ldarg.2
0x113db  call     instance char[] [mscorlib]System.String::ToCharArray()
0x113e0  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x113e5  stelem.ref
0x113e6  ldarg.0
0x113e7  ldloc.2
0x113e8  stfld    string[] System.Printing.PrintQueue::refreshPropertiesFilter
0x113ed  leave.s  loc_11403
0x113ef  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x113f4  ldstr    aPrintsystemexc_8// "PrintSystemException.PrintQueue.GetUnin"...
0x113f9  call     class [mscorlib]System.Exception System.Printing.PrintQueue::CreatePrintSystemException(int32 hresult, string messageId)
0x113fe  throw
0x113ff  leave.s  loc_11403
0x11401  leave.s  loc_1140F
0x11403  leave.s  loc_1140F
0x11405  ldloc.1
0x11406  brfalse.s loc_1140E
0x11408  ldloc.1
0x11409  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1140e  endfinally
0x1140f  ret
```
