# System.IO.Packaging.StreamInfo::Create_3

- ea: `0x47cf0`
- end: `0x47ece`
- name: `System.IO.Packaging.StreamInfo::Create_3`
- size: `478`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: ``

## callers

- `0x47c80`
- `0x47ca0`
- `0x47cc0`
- `0x47ce0`
- `0x48a20`

## callees

- `0x27bc0`
- `0x28950`
- `0x2c100`
- `0x45370`
- `0x460e0`
- `0x46ac0`
- `0x46ae0`
- `0x47440`
- `0x477c0`
- `0x47cf0`
- `0x47ed0`
- `0x47f10`
- `0x47f50`
- `0x48140`
- `0x48180`

## string_xrefs

- `0x47e24`: `StreamAlreadyExist`

## pseudocode

```c

```

## disassembly

```asm
0x47cf0  ldarg.0
0x47cf1  call     instance void System.IO.Packaging.StreamInfo::CheckDisposedStatus()
0x47cf6  ldc.i4.0
0x47cf7  stloc.0
0x47cf8  ldnull
0x47cf9  stloc.1
0x47cfa  ldnull
0x47cfb  stloc.2
0x47cfc  ldarg.0
0x47cfd  ldarg.2
0x47cfe  call     instance void System.IO.Packaging.StreamInfo::CreateTimeReadOnlyCheck(valuetype [mscorlib]System.IO.FileAccess access)
0x47d03  ldarg.3
0x47d04  brfalse.s loc_47D48
0x47d06  ldarg.3
0x47d07  callvirt instance int32 [mscorlib]System.String::get_Length()
0x47d0c  brtrue.s loc_47D1E
0x47d0e  ldstr    aDataspacelabel_1// "DataSpaceLabelInvalidEmpty"
0x47d13  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47d18  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47d1d  throw
0x47d1e  ldarg.0
0x47d1f  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47d24  callvirt instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x47d29  callvirt instance class System.IO.Packaging.DataSpaceManager System.IO.Packaging.StorageRoot::GetDataSpaceManager()
0x47d2e  stloc.2
0x47d2f  ldloc.2
0x47d30  ldarg.3
0x47d31  callvirt instance bool System.IO.Packaging.DataSpaceManager::DataSpaceIsDefined(string dataSpaceLabel)
0x47d36  brtrue.s loc_47D48
0x47d38  ldstr    aDataspacelabel_2// "DataSpaceLabelUndefined"
0x47d3d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47d42  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47d47  throw
0x47d48  ldarg.0
0x47d49  ldarg.2
0x47d4a  stfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47d4f  ldarg.0
0x47d50  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47d55  callvirt instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x47d5a  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x47d5f  ldc.i4.3
0x47d60  bne.un.s loc_47D65
0x47d62  ldc.i4.3
0x47d63  starg.s  2
0x47d65  ldarg.2
0x47d66  ldloca.s 0
0x47d68  call     void MS.Internal.IO.Packaging.CompoundFile.SafeNativeCompoundFileMethods::UpdateModeFlagFromFileAccess(valuetype [mscorlib]System.IO.FileAccess access, int32& grfMode)
0x47d6d  ldloc.0
0x47d6e  ldc.i4.s 0x10
0x47d70  or
0x47d71  stloc.0
0x47d72  ldarg.0
0x47d73  ldloc.0
0x47d74  call     instance void System.IO.Packaging.StreamInfo::CheckAccessMode(int32 grfMode)
0x47d79  ldarg.1
0x47d7a  ldc.i4.1
0x47d7b  sub
0x47d7c  switch   loc_47E17, loc_47D9E, loc_47E49, loc_47E49, loc_47E49, loc_47E49
0x47d99  br       loc_47E49
0x47d9e  ldarg.0
0x47d9f  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47da4  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47da9  brfalse.s loc_47DC0
0x47dab  ldarg.0
0x47dac  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47db1  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47db6  castclass [mscorlib]System.IO.Stream
0x47dbb  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x47dc0  ldarg.0
0x47dc1  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47dc6  ldnull
0x47dc7  stfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47dcc  ldarg.0
0x47dcd  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47dd2  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47dd7  brfalse.s loc_47DFA
0x47dd9  ldarg.0
0x47dda  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47ddf  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47de4  castclass [mscorlib]System.IDisposable
0x47de9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47dee  ldarg.0
0x47def  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47df4  ldnull
0x47df5  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47dfa  ldloc.0
0x47dfb  ldc.i4   0x1000
0x47e00  or
0x47e01  stloc.0
0x47e02  ldarg.0
0x47e03  ldarg.0
0x47e04  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e09  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47e0e  ldloc.0
0x47e0f  call     instance class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfo::CreateStreamOnParentIStorage(string name, int32 mode)
0x47e14  stloc.1
0x47e15  br.s     loc_47E59
0x47e17  ldarg.0
0x47e18  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e1d  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47e22  brfalse.s loc_47E34
0x47e24  ldstr    aStreamalreadye// "StreamAlreadyExist"
0x47e29  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47e2e  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x47e33  throw
0x47e34  ldarg.0
0x47e35  ldarg.0
0x47e36  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e3b  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47e40  ldloc.0
0x47e41  call     instance class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfo::CreateStreamOnParentIStorage(string name, int32 mode)
0x47e46  stloc.1
0x47e47  br.s     loc_47E59
0x47e49  ldstr    aFilemodeinvali// "FileModeInvalid"
0x47e4e  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47e53  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47e58  throw
0x47e59  ldarg.0
0x47e5a  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e5f  ldloc.1
0x47e60  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47e65  ldarg.0
0x47e66  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e6b  ldarg.3
0x47e6c  stfld    string System.IO.Packaging.StreamInfoCore::dataSpaceLabel
0x47e71  ldarg.3
0x47e72  brfalse.s loc_47EA0
0x47e74  ldloc.2
0x47e75  ldarg.0
0x47e76  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47e7b  callvirt instance string System.IO.Packaging.StorageInfo::get_FullNameInternal()
0x47e80  ldarg.0
0x47e81  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e86  ldfld    string System.IO.Packaging.StreamInfoCore::streamName
0x47e8b  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::.ctor(string storageName, string streamName)
0x47e90  ldarg.0
0x47e91  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47e96  ldfld    string System.IO.Packaging.StreamInfoCore::dataSpaceLabel
0x47e9b  callvirt instance void System.IO.Packaging.DataSpaceManager::CreateDataSpaceMapping(class MS.Internal.IO.Packaging.CompoundFile.CompoundFileReference containerReference, string label)
0x47ea0  ldarg.0
0x47ea1  ldarg.0
0x47ea2  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47ea7  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x47eac  ldarg.0
0x47ead  ldfld    valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StreamInfo::openFileAccess
0x47eb2  ldarg.0
0x47eb3  call     instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::BuildStreamOnUnderlyingIStream(class MS.Internal.IO.Packaging.CompoundFile.IStream underlyingIStream, valuetype [mscorlib]System.IO.FileAccess access, class System.IO.Packaging.StreamInfo parent)
0x47eb8  stloc.3
0x47eb9  ldarg.0
0x47eba  ldc.i4.0
0x47ebb  stfld    bool System.IO.Packaging.StreamInfo::_needToGetTransformInfo
0x47ec0  ldarg.0
0x47ec1  ldfld    class System.IO.Packaging.StreamInfoCore System.IO.Packaging.StreamInfo::core
0x47ec6  ldloc.3
0x47ec7  stfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x47ecc  ldloc.3
0x47ecd  ret
```
