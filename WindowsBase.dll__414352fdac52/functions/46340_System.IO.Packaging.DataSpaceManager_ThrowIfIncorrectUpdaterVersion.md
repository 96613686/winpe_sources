# System.IO.Packaging.DataSpaceManager::ThrowIfIncorrectUpdaterVersion

- ea: `0x46340`
- end: `0x46385`
- name: `System.IO.Packaging.DataSpaceManager::ThrowIfIncorrectUpdaterVersion`
- size: `69`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x45950`
- `0x45c10`
- `0x45f40`

## callees

- `0x2b160`
- `0x2b2b0`
- `0x2c130`
- `0x44e60`
- `0x462c0`
- `0x46340`

## string_xrefs

- `0x46358`: `UpdaterVersionError`

## pseudocode

```c

```

## disassembly

```asm
0x46340  ldarg.0
0x46341  call     instance void System.IO.Packaging.DataSpaceManager::EnsureDataSpaceVersionInformation()
0x46346  ldarg.0
0x46347  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x4634c  ldsfld   class MS.Internal.IO.Packaging.CompoundFile.VersionPair System.IO.Packaging.DataSpaceManager::DataSpaceCurrentUpdaterVersion
0x46351  callvirt instance bool MS.Internal.IO.Packaging.CompoundFile.FormatVersion::IsUpdatableBy(class MS.Internal.IO.Packaging.CompoundFile.VersionPair version)
0x46356  brtrue.s loc_46384
0x46358  ldstr    aUpdaterversion// "UpdaterVersionError"
0x4635d  ldc.i4.2
0x4635e  newarr   [mscorlib]System.Object
0x46363  dup
0x46364  ldc.i4.0
0x46365  ldarg.0
0x46366  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x4636b  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_UpdaterVersion()
0x46370  stelem.ref
0x46371  dup
0x46372  ldc.i4.1
0x46373  ldsfld   class MS.Internal.IO.Packaging.CompoundFile.VersionPair System.IO.Packaging.DataSpaceManager::DataSpaceCurrentUpdaterVersion
0x46378  stelem.ref
0x46379  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4637e  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x46383  throw
0x46384  ret
```
