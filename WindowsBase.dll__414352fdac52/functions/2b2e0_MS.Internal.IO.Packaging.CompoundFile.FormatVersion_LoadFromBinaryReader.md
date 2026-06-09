# MS.Internal.IO.Packaging.CompoundFile.FormatVersion::LoadFromBinaryReader

- ea: `0x2b2e0`
- end: `0x2b39a`
- name: `MS.Internal.IO.Packaging.CompoundFile.FormatVersion::LoadFromBinaryReader`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x2b3a0`

## callees

- `0x284d0`
- `0x28590`
- `0x2b050`
- `0x2b110`
- `0x2b140`
- `0x2b170`
- `0x2b2e0`
- `0x2b3e0`

## string_xrefs

- `0x2b2e3`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x2b2e0  ldarg.0
0x2b2e1  brtrue.s loc_2B2EE
0x2b2e3  ldstr    aReader// "reader"
0x2b2e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2b2ed  throw
0x2b2ee  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::.ctor()
0x2b2f3  stloc.0
0x2b2f4  ldarg.1
0x2b2f5  ldc.i4.0
0x2b2f6  stind.i4
0x2b2f7  ldloc.0
0x2b2f8  ldarg.0
0x2b2f9  ldloca.s 1
0x2b2fb  call     string MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::ReadByteLengthPrefixedDWordPaddedUnicodeString(class [mscorlib]System.IO.BinaryReader reader, [out] int32& bytesRead)
0x2b300  stfld    string MS.Internal.IO.Packaging.CompoundFile.FormatVersion::_featureIdentifier
0x2b305  ldarg.1
0x2b306  ldarg.1
0x2b307  ldind.i4
0x2b308  ldloc.1
0x2b309  add.ovf
0x2b30a  stind.i4
0x2b30b  ldarg.0
0x2b30c  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b311  stloc.2
0x2b312  ldarg.1
0x2b313  ldarg.1
0x2b314  ldind.i4
0x2b315  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b31a  add.ovf
0x2b31b  stind.i4
0x2b31c  ldarg.0
0x2b31d  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b322  stloc.3
0x2b323  ldarg.1
0x2b324  ldarg.1
0x2b325  ldind.i4
0x2b326  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b32b  add.ovf
0x2b32c  stind.i4
0x2b32d  ldloc.0
0x2b32e  ldloc.2
0x2b32f  ldloc.3
0x2b330  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.VersionPair::.ctor(int16 major, int16 minor)
0x2b335  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::set_ReaderVersion(class MS.Internal.IO.Packaging.CompoundFile.VersionPair value)
0x2b33a  ldarg.0
0x2b33b  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b340  stloc.2
0x2b341  ldarg.1
0x2b342  ldarg.1
0x2b343  ldind.i4
0x2b344  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b349  add.ovf
0x2b34a  stind.i4
0x2b34b  ldarg.0
0x2b34c  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b351  stloc.3
0x2b352  ldarg.1
0x2b353  ldarg.1
0x2b354  ldind.i4
0x2b355  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b35a  add.ovf
0x2b35b  stind.i4
0x2b35c  ldloc.0
0x2b35d  ldloc.2
0x2b35e  ldloc.3
0x2b35f  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.VersionPair::.ctor(int16 major, int16 minor)
0x2b364  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::set_UpdaterVersion(class MS.Internal.IO.Packaging.CompoundFile.VersionPair value)
0x2b369  ldarg.0
0x2b36a  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b36f  stloc.2
0x2b370  ldarg.1
0x2b371  ldarg.1
0x2b372  ldind.i4
0x2b373  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b378  add.ovf
0x2b379  stind.i4
0x2b37a  ldarg.0
0x2b37b  callvirt instance int16 [mscorlib]System.IO.BinaryReader::ReadInt16()
0x2b380  stloc.3
0x2b381  ldarg.1
0x2b382  ldarg.1
0x2b383  ldind.i4
0x2b384  call     int32 MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_Int16Size()
0x2b389  add.ovf
0x2b38a  stind.i4
0x2b38b  ldloc.0
0x2b38c  ldloc.2
0x2b38d  ldloc.3
0x2b38e  newobj   instance void MS.Internal.IO.Packaging.CompoundFile.VersionPair::.ctor(int16 major, int16 minor)
0x2b393  callvirt instance void MS.Internal.IO.Packaging.CompoundFile.FormatVersion::set_WriterVersion(class MS.Internal.IO.Packaging.CompoundFile.VersionPair value)
0x2b398  ldloc.0
0x2b399  ret
```
