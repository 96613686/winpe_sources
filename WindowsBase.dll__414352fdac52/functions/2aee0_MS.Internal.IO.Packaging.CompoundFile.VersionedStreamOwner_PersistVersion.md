# MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::PersistVersion

- ea: `0x2aee0`
- end: `0x2af70`
- name: `MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::PersistVersion`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ad80`

## callees

- `0x2aab0`
- `0x2aee0`
- `0x2b1b0`
- `0x2c100`
- `0x44e60`

## string_xrefs

- `0x2aeed`: `WriteNotSupported`
- `0x2af45`: `VersionUpdateFailure`

## pseudocode

```c

```

## disassembly

```asm
0x2aee0  ldarg.0
0x2aee1  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2aee6  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x2aeeb  brtrue.s loc_2AEFD
0x2aeed  ldstr    aWritenotsuppor// "WriteNotSupported"
0x2aef2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2aef7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2aefc  throw
0x2aefd  ldarg.0
0x2aefe  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af03  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x2af08  ldarg.0
0x2af09  ldfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2af0e  sub.ovf
0x2af0f  stloc.0
0x2af10  ldarg.0
0x2af11  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af16  ldc.i4.0
0x2af17  conv.i8
0x2af18  ldc.i4.0
0x2af19  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2af1e  pop
0x2af1f  ldarg.1
0x2af20  ldarg.0
0x2af21  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af26  callvirt instance int32 MS.Internal.IO.Packaging.CompoundFile.FormatVersion::SaveToStream(class [mscorlib]System.IO.Stream stream)
0x2af2b  conv.i8
0x2af2c  stloc.1
0x2af2d  ldarg.0
0x2af2e  ldarg.1
0x2af2f  stfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2af34  ldarg.0
0x2af35  ldfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2af3a  brfalse.s loc_2AF55
0x2af3c  ldloc.1
0x2af3d  ldarg.0
0x2af3e  ldfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2af43  beq.s    loc_2AF55
0x2af45  ldstr    aVersionupdatef// "VersionUpdateFailure"
0x2af4a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2af4f  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x2af54  throw
0x2af55  ldarg.0
0x2af56  ldloc.1
0x2af57  stfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2af5c  ldarg.0
0x2af5d  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af62  ldloc.0
0x2af63  ldarg.0
0x2af64  ldfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2af69  add.ovf
0x2af6a  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x2af6f  ret
```
