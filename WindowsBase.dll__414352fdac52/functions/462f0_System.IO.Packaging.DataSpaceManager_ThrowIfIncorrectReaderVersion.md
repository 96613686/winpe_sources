# System.IO.Packaging.DataSpaceManager::ThrowIfIncorrectReaderVersion

- ea: `0x462f0`
- end: `0x46335`
- name: `System.IO.Packaging.DataSpaceManager::ThrowIfIncorrectReaderVersion`
- size: `69`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x457e0`
- `0x45ad0`
- `0x45d70`

## callees

- `0x2b100`
- `0x2b280`
- `0x2c130`
- `0x44e60`
- `0x462c0`
- `0x462f0`

## string_xrefs

- `0x46308`: `ReaderVersionError`

## pseudocode

```c

```

## disassembly

```asm
0x462f0  ldarg.0
0x462f1  call     instance void System.IO.Packaging.DataSpaceManager::EnsureDataSpaceVersionInformation()
0x462f6  ldarg.0
0x462f7  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x462fc  ldsfld   class MS.Internal.IO.Packaging.CompoundFile.VersionPair System.IO.Packaging.DataSpaceManager::DataSpaceCurrentReaderVersion
0x46301  callvirt instance bool MS.Internal.IO.Packaging.CompoundFile.FormatVersion::IsReadableBy(class MS.Internal.IO.Packaging.CompoundFile.VersionPair version)
0x46306  brtrue.s loc_46334
0x46308  ldstr    aReaderversione// "ReaderVersionError"
0x4630d  ldc.i4.2
0x4630e  newarr   [mscorlib]System.Object
0x46313  dup
0x46314  ldc.i4.0
0x46315  ldarg.0
0x46316  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion System.IO.Packaging.DataSpaceManager::_fileFormatVersion
0x4631b  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_ReaderVersion()
0x46320  stelem.ref
0x46321  dup
0x46322  ldc.i4.1
0x46323  ldsfld   class MS.Internal.IO.Packaging.CompoundFile.VersionPair System.IO.Packaging.DataSpaceManager::DataSpaceCurrentReaderVersion
0x46328  stelem.ref
0x46329  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4632e  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x46333  throw
0x46334  ret
```
