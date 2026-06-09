# MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::EnsureParsed

- ea: `0x2af70`
- end: `0x2b03f`
- name: `MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::EnsureParsed`
- size: `207`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x2ad20`
- `0x2ad50`
- `0x2ad80`
- `0x2ae50`

## callees

- `0x2aab0`
- `0x2af70`
- `0x2b190`
- `0x2b1a0`
- `0x2c100`
- `0x2c130`
- `0x44e60`

## string_xrefs

- `0x2af9a`: `ReadNotSupported`
- `0x2affb`: `InvalidTransformFeatureName`

## pseudocode

```c

```

## disassembly

```asm
0x2af70  ldarg.0
0x2af71  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2af76  brtrue   loc_2B03E
0x2af7b  ldarg.0
0x2af7c  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af81  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2af86  ldc.i4.0
0x2af87  conv.i8
0x2af88  ble      loc_2B03E
0x2af8d  ldarg.0
0x2af8e  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2af93  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x2af98  brtrue.s loc_2AFAA
0x2af9a  ldstr    aReadnotsupport// "ReadNotSupported"
0x2af9f  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2afa4  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2afa9  throw
0x2afaa  ldarg.0
0x2afab  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2afb0  ldc.i4.0
0x2afb1  conv.i8
0x2afb2  ldc.i4.0
0x2afb3  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2afb8  pop
0x2afb9  ldarg.0
0x2afba  ldarg.0
0x2afbb  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2afc0  call     class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.FormatVersion::LoadFromStream(class [mscorlib]System.IO.Stream stream)
0x2afc5  stfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2afca  ldarg.0
0x2afcb  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2afd0  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x2afd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2afda  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x2afdf  ldarg.0
0x2afe0  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2afe5  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x2afea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2afef  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x2aff4  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2aff9  brfalse.s loc_2B02D
0x2affb  ldstr    aInvalidtransfo// "InvalidTransformFeatureName"
0x2b000  ldc.i4.2
0x2b001  newarr   [mscorlib]System.Object
0x2b006  dup
0x2b007  ldc.i4.0
0x2b008  ldarg.0
0x2b009  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_fileVersion
0x2b00e  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x2b013  stelem.ref
0x2b014  dup
0x2b015  ldc.i4.1
0x2b016  ldarg.0
0x2b017  ldfld    class MS.Internal.IO.Packaging.CompoundFile.FormatVersion MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_codeVersion
0x2b01c  callvirt instance string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::get_FeatureIdentifier()
0x2b021  stelem.ref
0x2b022  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2b027  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x2b02c  throw
0x2b02d  ldarg.0
0x2b02e  ldarg.0
0x2b02f  call     instance class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompoundFile.VersionedStream::get_BaseStream()
0x2b034  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x2b039  stfld    int64 MS.Internal.IO.Packaging.CompoundFile.VersionedStreamOwner::_dataOffset
0x2b03e  ret
```
