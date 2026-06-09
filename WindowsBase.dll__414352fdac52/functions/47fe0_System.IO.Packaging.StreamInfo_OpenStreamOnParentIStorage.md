# System.IO.Packaging.StreamInfo::OpenStreamOnParentIStorage

- ea: `0x47fe0`
- end: `0x4802e`
- name: `System.IO.Packaging.StreamInfo::OpenStreamOnParentIStorage`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x47a20`

## callees

- `0x28b50`
- `0x2c100`
- `0x2c130`
- `0x47020`
- `0x47fe0`

## string_xrefs

- `0x47ffe`: `UnableToOpenStream`
- `0x48015`: `IStorage.OpenStream`

## pseudocode

```c

```

## disassembly

```asm
0x47fe0  ldnull
0x47fe1  stloc.0
0x47fe2  ldc.i4.0
0x47fe3  stloc.1
0x47fe4  ldarg.0
0x47fe5  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47fea  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfo::get_SafeIStorage()
0x47fef  ldarg.1
0x47ff0  ldc.i4.0
0x47ff1  ldarg.2
0x47ff2  ldc.i4.0
0x47ff3  ldloca.s 0
0x47ff5  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.IStorage::OpenStream(string pwcsName, int32 reserved1, int32 grfMode, int32 reserved2, [out] class MS.Internal.IO.Packaging.CompoundFile.IStream& ppstm)
0x47ffa  stloc.1
0x47ffb  ldloc.1
0x47ffc  brfalse.s loc_4802C
0x47ffe  ldstr    aUnabletoopenst// "UnableToOpenStream"
0x48003  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x48008  ldstr    aNamedapifailur// "NamedAPIFailure"
0x4800d  ldc.i4.1
0x4800e  newarr   [mscorlib]System.Object
0x48013  dup
0x48014  ldc.i4.0
0x48015  ldstr    aIstorageOpenst_0// "IStorage.OpenStream"
0x4801a  stelem.ref
0x4801b  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x48020  ldloc.1
0x48021  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x48026  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x4802b  throw
0x4802c  ldloc.0
0x4802d  ret
```
