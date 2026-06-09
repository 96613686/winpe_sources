# MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::Validate

- ea: `0x1b8f0`
- end: `0x1b9dc`
- name: `MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::Validate`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1b2e0`

## callees

- `0x18e40`
- `0x1b670`
- `0x1b8f0`
- `0x1e7d0`
- `0x1e850`
- `0x2c100`
- `0x44e60`

## string_xrefs

- `0x1b9cb`: `ZipNotSupportedCompressionMethod`

## pseudocode

```c

```

## disassembly

```asm
0x1b8f0  ldarg.0
0x1b8f1  ldfld    unsigned int32 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_signature
0x1b8f6  ldc.i4   0x2014B50
0x1b8fb  beq.s    loc_1B90D
0x1b8fd  ldstr    aCorrupteddata// "CorruptedData"
0x1b902  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b907  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1b90c  throw
0x1b90d  ldarg.0
0x1b90e  call     instance unsigned int32 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_DiskNumberStart()
0x1b913  brfalse.s loc_1B925
0x1b915  ldstr    aNotsupportedmu// "NotSupportedMultiDisk"
0x1b91a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b91f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1b924  throw
0x1b925  ldarg.0
0x1b926  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_fileNameLength
0x1b92b  ldarg.0
0x1b92c  ldfld    unsigned int8[] MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_fileName
0x1b931  ldlen
0x1b932  conv.i4
0x1b933  beq.s    loc_1B945
0x1b935  ldstr    aCorrupteddata// "CorruptedData"
0x1b93a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b93f  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1b944  throw
0x1b945  ldarg.0
0x1b946  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_extraFieldLength
0x1b94b  ldarg.0
0x1b94c  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_extraField
0x1b951  callvirt instance unsigned int16 MS.Internal.IO.Zip.ZipIOExtraField::get_Size()
0x1b956  beq.s    loc_1B968
0x1b958  ldstr    aCorrupteddata// "CorruptedData"
0x1b95d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b962  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1b967  throw
0x1b968  ldarg.0
0x1b969  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_versionNeededToExtract
0x1b96e  call     void MS.Internal.IO.Zip.ZipArchive::VerifyVersionNeededToExtract(unsigned int16 version)
0x1b973  ldarg.0
0x1b974  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_versionNeededToExtract
0x1b979  ldc.i4.s 0x2D
0x1b97b  bge.s    loc_1B99A
0x1b97d  ldarg.0
0x1b97e  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_extraField
0x1b983  callvirt instance valuetype MS.Internal.IO.Zip.ZipIOZip64ExtraFieldUsage MS.Internal.IO.Zip.ZipIOExtraField::get_Zip64ExtraFieldUsage()
0x1b988  brfalse.s loc_1B99A
0x1b98a  ldstr    aCorrupteddata// "CorruptedData"
0x1b98f  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b994  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1b999  throw
0x1b99a  ldarg.0
0x1b99b  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_fileCommentLength
0x1b9a0  ldarg.0
0x1b9a1  ldfld    unsigned int8[] MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_fileComment
0x1b9a6  ldlen
0x1b9a7  conv.i4
0x1b9a8  beq.s    loc_1B9BA
0x1b9aa  ldstr    aCorrupteddata// "CorruptedData"
0x1b9af  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b9b4  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1b9b9  throw
0x1b9ba  ldarg.0
0x1b9bb  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_compressionMethod
0x1b9c0  brfalse.s loc_1B9DB
0x1b9c2  ldarg.0
0x1b9c3  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::_compressionMethod
0x1b9c8  ldc.i4.8
0x1b9c9  beq.s    loc_1B9DB
0x1b9cb  ldstr    aZipnotsupporte// "ZipNotSupportedCompressionMethod"
0x1b9d0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1b9d5  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1b9da  throw
0x1b9db  ret
```
