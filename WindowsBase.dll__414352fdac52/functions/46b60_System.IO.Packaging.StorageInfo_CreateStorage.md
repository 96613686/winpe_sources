# System.IO.Packaging.StorageInfo::CreateStorage

- ea: `0x46b60`
- end: `0x46c3f`
- name: `System.IO.Packaging.StorageInfo::CreateStorage`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x46980`
- `0x46b10`

## callees

- `0xd690`
- `0x28b60`
- `0x2c100`
- `0x2c130`
- `0x46630`
- `0x46b60`
- `0x46f60`
- `0x47060`
- `0x47150`

## string_xrefs

- `0x46bc9`: `CanNotCreateAccessDenied`
- `0x46be0`: `IStorage.CreateStorage`
- `0x46c0e`: `IStorage.CreateStorage`
- `0x46bf7`: `UnableToCreateStorage`
- `0x46c2d`: `StorageAlreadyExist`

## pseudocode

```c

```

## disassembly

```asm
0x46b60  ldarg.0
0x46b61  ldarg.1
0x46b62  newobj   instance void System.IO.Packaging.StorageInfo::.ctor(class System.IO.Packaging.StorageInfo parent, string fileName)
0x46b67  stloc.0
0x46b68  ldloc.0
0x46b69  ldarg.1
0x46b6a  callvirt instance bool System.IO.Packaging.StorageInfo::InternalExists(string name)
0x46b6f  brtrue   loc_46C2D
0x46b74  ldarg.0
0x46b75  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46b7a  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x46b7f  ldarg.1
0x46b80  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x46b85  isinst   System.IO.Packaging.StorageInfoCore
0x46b8a  stloc.1
0x46b8b  ldloc.1
0x46b8c  ldnull
0x46b8d  cgt.un
0x46b8f  call     void MS.Internal.Invariant::Assert(bool condition)
0x46b94  ldarg.0
0x46b95  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46b9a  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46b9f  ldarg.1
0x46ba0  ldarg.0
0x46ba1  call     instance valuetype [mscorlib]System.Runtime.InteropServices.ComTypes.STATSTG System.IO.Packaging.StorageInfo::GetStat()
0x46ba6  ldfld    int32 [mscorlib]System.Runtime.InteropServices.ComTypes.STATSTG::grfMode
0x46bab  ldc.i4.3
0x46bac  and
0x46bad  ldc.i4.s 0x10
0x46baf  or
0x46bb0  ldc.i4.0
0x46bb1  ldc.i4.0
0x46bb2  ldloc.1
0x46bb3  ldflda   class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46bb8  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.IStorage::CreateStorage(string pwcsName, int32 grfMode, int32 reserved1, int32 reserved2, [out] class MS.Internal.IO.Packaging.CompoundFile.IStorage& ppstg)
0x46bbd  stloc.2
0x46bbe  ldloc.2
0x46bbf  brfalse.s loc_46C25
0x46bc1  ldloc.2
0x46bc2  ldc.i4   0x80030005
0x46bc7  bne.un.s loc_46BF7
0x46bc9  ldstr    aCannotcreateac// "CanNotCreateAccessDenied"
0x46bce  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46bd3  ldstr    aNamedapifailur// "NamedAPIFailure"
0x46bd8  ldc.i4.1
0x46bd9  newarr   [mscorlib]System.Object
0x46bde  dup
0x46bdf  ldc.i4.0
0x46be0  ldstr    aIstorageCreate// "IStorage.CreateStorage"
0x46be5  stelem.ref
0x46be6  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x46beb  ldloc.2
0x46bec  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x46bf1  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string, class [mscorlib]System.Exception)
0x46bf6  throw
0x46bf7  ldstr    aUnabletocreate// "UnableToCreateStorage"
0x46bfc  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46c01  ldstr    aNamedapifailur// "NamedAPIFailure"
0x46c06  ldc.i4.1
0x46c07  newarr   [mscorlib]System.Object
0x46c0c  dup
0x46c0d  ldc.i4.0
0x46c0e  ldstr    aIstorageCreate// "IStorage.CreateStorage"
0x46c13  stelem.ref
0x46c14  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x46c19  ldloc.2
0x46c1a  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x46c1f  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x46c24  throw
0x46c25  ldarg.0
0x46c26  call     instance void System.IO.Packaging.StorageInfo::InvalidateEnumerators()
0x46c2b  br.s     loc_46C3D
0x46c2d  ldstr    aStoragealready// "StorageAlreadyExist"
0x46c32  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46c37  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x46c3c  throw
0x46c3d  ldloc.0
0x46c3e  ret
```
