# System.IO.Packaging.StreamInfo::GetStream_1

- ea: `0x47a20`
- end: `0x47c7b`
- name: `System.IO.Packaging.StreamInfo::GetStream_1`
- size: `603`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: ``

## callers

- `0x29dc0`
- `0x29e40`
- `0x2a7f0`
- `0x479e0`
- `0x47a00`
- `0x48920`

## callees

- `0x28950`
- `0x28b40`
- `0x2c100`
- `0x2c130`
- `0x46ae0`
- `0x46b00`
- `0x46b10`
- `0x46f60`
- `0x47020`
- `0x47440`
- `0x47a20`
- `0x47ed0`
- `0x47f10`
- `0x47f50`
- `0x47fe0`
- `0x48100`
- `0x48140`
- `0x48180`

## string_xrefs

- `0x47bd7`: `UnableToCreateStream`
- `0x47bee`: `IStorage.CreateStream`

## pseudocode

```c

```

## disassembly

```asm
0x47a20  ldarg.0
0x47a21  call     instance void System.IO.Packaging.StreamInfo::CheckDisposedStatus()
0x47a26  ldc.i4.0
0x47a27  stloc.0
0x47a28  ldnull
0x47a29  stloc.1
0x47a2a  ldarg.0
0x47a2b  ldarg.2
0x47a2c  stfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47a31  ldarg.0
0x47a32  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47a37  callvirt instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x47a3c  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x47a41  ldc.i4.3
0x47a42  bne.un.s loc_47A47
0x47a44  ldc.i4.3
0x47a45  starg.s  2
0x47a47  ldarg.2
0x47a48  ldloca.s 0
0x47a4a  call     void MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::UpdateModeFlagFromFileAccess(valuetype [mscorlib]System.IO.FileAccess access, int32& grfMode)
0x47a4f  ldloc.0
0x47a50  ldc.i4.s 0x10
0x47a52  or
0x47a53  stloc.0
0x47a54  ldarg.0
0x47a55  ldloc.0
0x47a56  call     instance void System.IO.Packaging.StreamInfo::CheckAccessMode(int32 grfMode)
0x47a5b  ldarg.1
0x47a5c  ldc.i4.1
0x47a5d  sub
0x47a5e  switch   loc_47B18, loc_47A90, loc_47B28, loc_47B5A, loc_47C28, loc_47A80
0x47a7b  br       loc_47C38
0x47a80  ldstr    aFilemodeunsupp// "FileModeUnsupported"
0x47a85  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47a8a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47a8f  throw
0x47a90  ldarg.0
0x47a91  ldarg.0
0x47a92  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47a97  call     instance void System.IO.Packaging.StreamInfo::CreateTimeReadOnlyCheck(valuetype [mscorlib]System.IO.FileAccess access)
0x47a9c  ldarg.0
0x47a9d  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47aa2  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47aa7  brfalse.s loc_47ABE
0x47aa9  ldarg.0
0x47aaa  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47aaf  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47ab4  castclass [mscorlib]System.IO.Stream
0x47ab9  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x47abe  ldarg.0
0x47abf  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47ac4  ldnull
0x47ac5  stfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47aca  ldarg.0
0x47acb  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47ad0  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47ad5  brfalse.s loc_47AF8
0x47ad7  ldarg.0
0x47ad8  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47add  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47ae2  castclass [mscorlib]System.IDisposable
0x47ae7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47aec  ldarg.0
0x47aed  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47af2  ldnull
0x47af3  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47af8  ldloc.0
0x47af9  ldc.i4   0x1000
0x47afe  or
0x47aff  stloc.0
0x47b00  ldarg.0
0x47b01  ldarg.0
0x47b02  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47b07  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47b0c  ldloc.0
0x47b0d  call     instance class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfo::CreateStreamOnParentIStorage(string name, int32 mode)
0x47b12  stloc.1
0x47b13  br       loc_47C48
0x47b18  ldstr    aFilemodeunsupp// "FileModeUnsupported"
0x47b1d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47b22  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47b27  throw
0x47b28  ldarg.0
0x47b29  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47b2e  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47b33  brfalse.s loc_47B42
0x47b35  ldarg.0
0x47b36  ldarg.0
0x47b37  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47b3c  call     instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::CFStreamOfClone(valuetype [mscorlib]System.IO.FileAccess access)
0x47b41  ret
0x47b42  ldarg.0
0x47b43  ldarg.0
0x47b44  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47b49  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47b4e  ldloc.0
0x47b4f  call     instance class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfo::OpenStreamOnParentIStorage(string name, int32 mode)
0x47b54  stloc.1
0x47b55  br       loc_47C48
0x47b5a  ldarg.0
0x47b5b  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47b60  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47b65  brfalse.s loc_47B74
0x47b67  ldarg.0
0x47b68  ldarg.0
0x47b69  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47b6e  call     instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::CFStreamOfClone(valuetype [mscorlib]System.IO.FileAccess access)
0x47b73  ret
0x47b74  ldc.i4.1
0x47b75  ldarg.0
0x47b76  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47b7b  callvirt instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x47b80  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x47b85  beq      loc_47C10
0x47b8a  ldc.i4.1
0x47b8b  ldarg.0
0x47b8c  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47b91  beq.s    loc_47C10
0x47b93  ldarg.0
0x47b94  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47b99  callvirt instance bool System.IO.Packaging.StorageInfo::get_Exists()
0x47b9e  brtrue.s loc_47BAB
0x47ba0  ldarg.0
0x47ba1  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47ba6  callvirt instance void System.IO.Packaging.StorageInfo::Create()
0x47bab  ldarg.0
0x47bac  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47bb1  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfo::get_SafeIStorage()
0x47bb6  ldarg.0
0x47bb7  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47bbc  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47bc1  ldloc.0
0x47bc2  ldc.i4.0
0x47bc3  ldc.i4.0
0x47bc4  ldloca.s 1
0x47bc6  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.IStorage::CreateStream(string pwcsName, int32 grfMode, int32 reserved1, int32 reserved2, [out] class MS.Internal.IO.Packaging.CompoundFile.IStream& ppstm)
0x47bcb  stloc.3
0x47bcc  ldloc.3
0x47bcd  brfalse.s loc_47C05
0x47bcf  ldc.i4   0x80030050
0x47bd4  ldloc.3
0x47bd5  beq.s    loc_47C05
0x47bd7  ldstr    aUnabletocreate_1// "UnableToCreateStream"
0x47bdc  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47be1  ldstr    aNamedapifailur// "NamedAPIFailure"
0x47be6  ldc.i4.1
0x47be7  newarr   [mscorlib]System.Object
0x47bec  dup
0x47bed  ldc.i4.0
0x47bee  ldstr    aIstorageCreate_0// "IStorage.CreateStream"
0x47bf3  stelem.ref
0x47bf4  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x47bf9  ldloc.3
0x47bfa  newobj   instance void [mscorlib]System.Runtime.InteropServices.COMException::.ctor(string, int32)
0x47bff  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x47c04  throw
0x47c05  ldarg.0
0x47c06  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47c0b  callvirt instance void System.IO.Packaging.StorageInfo::InvalidateEnumerators()
0x47c10  ldloc.1
0x47c11  brtrue.s loc_47C48
0x47c13  ldarg.0
0x47c14  ldarg.0
0x47c15  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47c1a  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47c1f  ldloc.0
0x47c20  call     instance class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfo::OpenStreamOnParentIStorage(string name, int32 mode)
0x47c25  stloc.1
0x47c26  br.s     loc_47C48
0x47c28  ldstr    aFilemodeunsupp// "FileModeUnsupported"
0x47c2d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47c32  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47c37  throw
0x47c38  ldstr    aFilemodeinvali// "FileModeInvalid"
0x47c3d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47c42  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47c47  throw
0x47c48  ldarg.0
0x47c49  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47c4e  ldloc.1
0x47c4f  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47c54  ldarg.0
0x47c55  ldarg.0
0x47c56  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47c5b  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47c60  ldarg.0
0x47c61  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47c66  ldarg.0
0x47c67  call     instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::BuildStreamOnUnderlyingIStream(class MS.Internal.IO.Packaging.CompoundFile.IStream underlyingIStream, valuetype [mscorlib]System.IO.FileAccess access, class System.IO.Packaging.StreamInfo parent)
0x47c6c  stloc.2
0x47c6d  ldarg.0
0x47c6e  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47c73  ldloc.2
0x47c74  stfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47c79  ldloc.2
0x47c7a  ret
```
