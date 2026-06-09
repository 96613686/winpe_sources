# System.IO.Packaging.StreamInfo::CreateStreamOnParentIStorage

- ea: `0x47f50`
- end: `0x47fd9`
- name: `System.IO.Packaging.StreamInfo::CreateStreamOnParentIStorage`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x47a20`
- `0x47cf0`

## callees

- `0x28b40`
- `0x2c100`
- `0x2c130`
- `0x46b00`
- `0x46b10`
- `0x46f60`
- `0x47020`
- `0x47f50`

## string_xrefs

- `0x47f9e`: `UnableToCreateStream`
- `0x47fb5`: `IStorage.CreateStream`

## pseudocode

```c

```

## disassembly

```asm
0x47f50  ldnull
0x47f51  stloc.0
0x47f52  ldc.i4.0
0x47f53  stloc.1
0x47f54  ldarg.0
0x47f55  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47f5a  callvirt instance bool System.IO.Packaging.StorageInfo::get_Exists()
0x47f5f  brtrue.s loc_47F6C
0x47f61  ldarg.0
0x47f62  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47f67  callvirt instance void System.IO.Packaging.StorageInfo::Create()
0x47f6c  ldarg.0
0x47f6d  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47f72  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfo::get_SafeIStorage()
0x47f77  ldarg.1
0x47f78  ldarg.2
0x47f79  ldc.i4.0
0x47f7a  ldc.i4.0
0x47f7b  ldloca.s 0
0x47f7d  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.IStorage::CreateStream(string pwcsName, int32 grfMode, int32 reserved1, int32 reserved2, [out] class MS.Internal.IO.Packaging.CompoundFile.IStream& ppstm)
0x47f82  stloc.1
0x47f83  ldc.i4   0x800300FF
0x47f88  ldloc.1
0x47f89  bne.un.s loc_47F9B
0x47f8b  ldstr    aStorageflagsun// "StorageFlagsUnsupported"
0x47f90  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47f95  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47f9a  throw
0x47f9b  ldloc.1
0x47f9c  brfalse.s loc_47FCC
0x47f9e  ldstr    aUnabletocreate_1// "UnableToCreateStream"
0x47fa3  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47fa8  ldstr    aNamedapifailur// "NamedAPIFailure"
0x47fad  ldc.i4.1
0x47fae  newarr   [mscorlib]System.Object
0x47fb3  dup
0x47fb4  ldc.i4.0
0x47fb5  ldstr    aIstorageCreate_0// "IStorage.CreateStream"
0x47fba  stelem.ref
0x47fbb  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x47fc0  ldloc.1
0x47fc1  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x47fc6  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x47fcb  throw
0x47fcc  ldarg.0
0x47fcd  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47fd2  callvirt instance void System.IO.Packaging.StorageInfo::InvalidateEnumerators()
0x47fd7  ldloc.0
0x47fd8  ret
```
