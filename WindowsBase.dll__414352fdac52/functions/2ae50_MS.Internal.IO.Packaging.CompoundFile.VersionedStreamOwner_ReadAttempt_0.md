# MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::ReadAttempt_0

- ea: `0x2ae50`
- end: `0x2aedb`
- name: `MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::ReadAttempt_0`
- size: `139`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x2a850`
- `0x2a8a0`
- `0x2ab20`
- `0x2ab60`
- `0x2ae40`

## callees

- `0x2aab0`
- `0x2aaf0`
- `0x2ae50`
- `0x2af70`
- `0x2b100`
- `0x2b280`
- `0x2c100`
- `0x2c130`
- `0x44e60`

## string_xrefs

- `0x2aea6`: `ReaderVersionError`

## pseudocode

```c

```

## disassembly

```asm
0x2ae50  ldarg.0
0x2ae51  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStream::CheckDisposed()
0x2ae56  ldarg.0
0x2ae57  ldfld    bool MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_readOccurred
0x2ae5c  brtrue.s loc_2AEDA
0x2ae5e  ldarg.0
0x2ae5f  call     instance void MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::EnsureParsed()
0x2ae64  ldarg.1
0x2ae65  brtrue.s loc_2AE76
0x2ae67  ldarg.0
0x2ae68  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2ae6d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2ae72  ldc.i4.0
0x2ae73  conv.i8
0x2ae74  ble.s    loc_2AED3
0x2ae76  ldarg.0
0x2ae77  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ae7c  brtrue.s loc_2AE8E
0x2ae7e  ldstr    aVersionstreamm// "VersionStreamMissing"
0x2ae83  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2ae88  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x2ae8d  throw
0x2ae8e  ldarg.0
0x2ae8f  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2ae94  ldarg.0
0x2ae95  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2ae9a  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_ReaderVersion()
0x2ae9f  callvirt instance bool MS.Internal.IO.Packaging.CompoundFile.FormatVersion::IsReadableBy(class MS.Internal.IO.Packaging.CompoundFile.VersionPair version)
0x2aea4  brtrue.s loc_2AED3
0x2aea6  ldstr    aReaderversione// "ReaderVersionError"
0x2aeab  ldc.i4.2
0x2aeac  newarr   [mscorlib]System.Object
0x2aeb1  dup
0x2aeb2  ldc.i4.0
0x2aeb3  ldarg.0
0x2aeb4  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2aeb9  callvirt instance class MS.Internal.IO.Packaging.CompoundFile.VersionPair MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_ReaderVersion()
0x2aebe  stelem.ref
0x2aebf  dup
0x2aec0  ldc.i4.1
0x2aec1  ldarg.0
0x2aec2  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2aec7  stelem.ref
0x2aec8  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2aecd  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x2aed2  throw
0x2aed3  ldarg.0
0x2aed4  ldc.i4.1
0x2aed5  stfld    bool MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_readOccurred
0x2aeda  ret
```
