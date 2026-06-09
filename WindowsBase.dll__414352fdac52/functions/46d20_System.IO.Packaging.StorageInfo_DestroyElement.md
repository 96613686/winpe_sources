# System.IO.Packaging.StorageInfo::DestroyElement

- ea: `0x46d20`
- end: `0x46eaa`
- name: `System.IO.Packaging.StorageInfo::DestroyElement`
- size: `394`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x469e0`
- `0x46c40`
- `0x48030`

## callees

- `0xfea0`
- `0x27bc0`
- `0x28bd0`
- `0x2c100`
- `0x45270`
- `0x46630`
- `0x46ac0`
- `0x46ae0`
- `0x46ca0`
- `0x46d20`
- `0x46f60`
- `0x47440`
- `0x477c0`

## string_xrefs

- `0x46d40`: `CanNotDeleteInReadOnly`
- `0x46dc2`: `CanNotDeleteAccessDenied`
- `0x46dd4`: `CanNotDelete`

## pseudocode

```c

```

## disassembly

```asm
0x46d20  ldarg.0
0x46d21  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46d26  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x46d2b  ldarg.1
0x46d2c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x46d31  stloc.0
0x46d32  ldc.i4.1
0x46d33  ldarg.0
0x46d34  call     instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x46d39  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x46d3e  bne.un.s loc_46D50
0x46d40  ldstr    aCannotdeletein// "CanNotDeleteInReadOnly"
0x46d45  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46d4a  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x46d4f  throw
0x46d50  ldarg.0
0x46d51  call     instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x46d56  callvirt instance class System.IO.Packaging.DataSpaceManager System.IO.Packaging.StorageRoot::GetDataSpaceManager()
0x46d5b  stloc.1
0x46d5c  ldloc.1
0x46d5d  brfalse.s loc_46D9E
0x46d5f  ldloc.0
0x46d60  isinst   System.IO.Packaging.StorageInfoCore
0x46d65  brfalse.s loc_46D84
0x46d67  ldloc.0
0x46d68  castclass System.IO.Packaging.StorageInfoCore
0x46d6d  ldfld    string System.IO.Packaging.StorageInfoCore::storageName
0x46d72  stloc.2
0x46d73  ldarg.0
0x46d74  ldloc.2
0x46d75  newobj   instance void System.IO.Packaging.StorageInfo::.ctor(class System.IO.Packaging.StorageInfo parent, string fileName)
0x46d7a  stloc.3
0x46d7b  ldarg.0
0x46d7c  ldloc.3
0x46d7d  call     instance void System.IO.Packaging.StorageInfo::RemoveSubStorageEntryFromDataSpaceMap(class System.IO.Packaging.StorageInfo storageInfo)
0x46d82  br.s     loc_46D9E
0x46d84  ldloc.0
0x46d85  isinst   System.IO.Packaging.StreamInfoCore
0x46d8a  brfalse.s loc_46D9E
0x46d8c  ldloc.1
0x46d8d  ldarg.0
0x46d8e  call     instance string System.IO.Packaging.StorageInfo::get_FullNameInternal()
0x46d93  ldarg.1
0x46d94  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.CompoundFileStreamReference::.ctor(string storageName, string streamName)
0x46d99  callvirt instance void System.IO.Packaging.DataSpaceManager::RemoveContainerFromDataSpaceMap(class MS.Internal.IO.Packaging.CompoundFile.CompoundFileReference target)
0x46d9e  nop
0x46d9f  ldarg.0
0x46da0  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46da5  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46daa  ldarg.1
0x46dab  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.IStorage::DestroyElement(string pwcsName)
0x46db0  leave.s  loc_46DE6
0x46db2  stloc.s  4
0x46db4  ldloc.s  4
0x46db6  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x46dbb  ldc.i4   0x80030005
0x46dc0  bne.un.s loc_46DD4
0x46dc2  ldstr    aCannotdeleteac// "CanNotDeleteAccessDenied"
0x46dc7  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46dcc  ldloc.s  4
0x46dce  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string, class [mscorlib]System.Exception)
0x46dd3  throw
0x46dd4  ldstr    aCannotdelete// "CanNotDelete"
0x46dd9  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46dde  ldloc.s  4
0x46de0  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0x46de5  throw
0x46de6  ldarg.0
0x46de7  call     instance void System.IO.Packaging.StorageInfo::InvalidateEnumerators()
0x46dec  ldloc.0
0x46ded  isinst   System.IO.Packaging.StorageInfoCore
0x46df2  brfalse.s loc_46E2B
0x46df4  ldloc.0
0x46df5  castclass System.IO.Packaging.StorageInfoCore
0x46dfa  stloc.s  5
0x46dfc  ldloc.s  5
0x46dfe  ldnull
0x46dff  stfld    string System.IO.Packaging.StorageInfoCore::storageName
0x46e04  ldloc.s  5
0x46e06  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46e0b  brfalse  loc_46E98
0x46e10  ldloc.s  5
0x46e12  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46e17  castclass [mscorlib]System.IDisposable
0x46e1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46e21  ldloc.s  5
0x46e23  ldnull
0x46e24  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStorage System.IO.Packaging.StorageInfoCore::safeIStorage
0x46e29  br.s     loc_46E98
0x46e2b  ldloc.0
0x46e2c  isinst   System.IO.Packaging.StreamInfoCore
0x46e31  brfalse.s loc_46E98
0x46e33  ldloc.0
0x46e34  castclass System.IO.Packaging.StreamInfoCore
0x46e39  stloc.s  6
0x46e3b  ldloc.s  6
0x46e3d  ldnull
0x46e3e  stfld    string System.IO.Packaging.StreamInfoCore::streamName
0x46e43  ldloc.s  6
0x46e45  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x46e4a  brfalse.s loc_46E5D
0x46e4c  ldloc.s  6
0x46e4e  ldfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x46e53  castclass [mscorlib]System.IO.Stream
0x46e58  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x46e5d  leave.s  loc_46E6E
0x46e5f  stloc.s  7
0x46e61  ldloc.s  7
0x46e63  call     bool MS.Internal.CriticalExceptions::IsCriticalException(class [mscorlib]System.Exception ex)
0x46e68  brfalse.s loc_46E6C
0x46e6a  rethrow
0x46e6c  leave.s  loc_46E6E
0x46e6e  ldloc.s  6
0x46e70  ldnull
0x46e71  stfld    object System.IO.Packaging.StreamInfoCore::exposedStream
0x46e76  ldloc.s  6
0x46e78  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x46e7d  brfalse.s loc_46E98
0x46e7f  ldloc.s  6
0x46e81  ldfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x46e86  castclass [mscorlib]System.IDisposable
0x46e8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46e90  ldloc.s  6
0x46e92  ldnull
0x46e93  stfld    class MS.Internal.IO.Packaging.CompoundFile.IStream System.IO.Packaging.StreamInfoCore::safeIStream
0x46e98  ldarg.0
0x46e99  ldfld    class System.IO.Packaging.StorageInfoCore System.IO.Packaging.StorageInfo::core
0x46e9e  ldfld    class [mscorlib]System.Collections.Hashtable System.IO.Packaging.StorageInfoCore::elementInfoCores
0x46ea3  ldarg.1
0x46ea4  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x46ea9  ret
```
