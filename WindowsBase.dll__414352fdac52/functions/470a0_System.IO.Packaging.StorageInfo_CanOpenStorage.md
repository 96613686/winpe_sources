# System.IO.Packaging.StorageInfo::CanOpenStorage

- ea: `0x470a0`
- end: `0x47129`
- name: `System.IO.Packaging.StorageInfo::CanOpenStorage`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x47060`

## callees

- `0x28b70`
- `0x2c100`
- `0x2c130`
- `0x470a0`
- `0x47150`

## string_xrefs

- `0x470f9`: `CanNotOpenStorage`
- `0x47110`: `IStorage::OpenStorage`

## pseudocode

```c

```

## disassembly

```asm
0x470a0  ldc.i4.0
0x470a1  stloc.0
0x470a2  ldarg.0
0x470a3  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x470a8  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x470ad  ldarg.1
0x470ae  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x470b3  isinst   System.IO.Packaging.StorageInfoCore
0x470b8  stloc.1
0x470b9  ldc.i4.0
0x470ba  stloc.2
0x470bb  ldarg.0
0x470bc  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x470c1  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x470c6  ldarg.1
0x470c7  ldnull
0x470c8  ldarg.0
0x470c9  call     instance valuetype [mscorlib]System.Runtime.InteropServices.ComTypes.STATSTG System.IO.Packaging.StorageInfo::GetStat()
0x470ce  ldfld    int32 [mscorlib]System.Runtime.InteropServices.ComTypes.STATSTG::grfMode
0x470d3  ldc.i4.3
0x470d4  and
0x470d5  ldc.i4.s 0x10
0x470d7  or
0x470d8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x470dd  ldc.i4.0
0x470de  ldloc.1
0x470df  ldflda   class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x470e4  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.IStorage::OpenStorage(string pwcsName, class MS.Internal.IO.Packaging.CompoundFile.IStorage pstgPriority, int32 grfMode, native int snbExclude, int32 reserved, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppstg)
0x470e9  stloc.2
0x470ea  ldloc.2
0x470eb  brtrue.s loc_470F1
0x470ed  ldc.i4.1
0x470ee  stloc.0
0x470ef  br.s     loc_47127
0x470f1  ldc.i4   0x80030002
0x470f6  ldloc.2
0x470f7  beq.s    loc_47127
0x470f9  ldstr    aCannotopenstor// "CanNotOpenStorage"
0x470fe  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47103  ldstr    aNamedapifailur// "NamedAPIFailure"
0x47108  ldc.i4.1
0x47109  newarr   [mscorlib]System.Object
0x4710e  dup
0x4710f  ldc.i4.0
0x47110  ldstr    aIstorageOpenst// "IStorage::OpenStorage"
0x47115  stelem.ref
0x47116  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4711b  ldloc.2
0x4711c  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x47121  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x47126  throw
0x47127  ldloc.0
0x47128  ret
```
