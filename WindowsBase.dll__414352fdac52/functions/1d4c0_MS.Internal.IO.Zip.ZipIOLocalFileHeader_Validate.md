# MS.Internal.IO.Zip.ZipIOLocalFileHeader::Validate

- ea: `0x1d4c0`
- end: `0x1d5b7`
- name: `MS.Internal.IO.Zip.ZipIOLocalFileHeader::Validate`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1d0d0`

## callees

- `0x18e40`
- `0x1d290`
- `0x1d410`
- `0x1d4c0`
- `0x1e7d0`
- `0x1e850`
- `0x2c100`
- `0x44e60`

## string_xrefs

- `0x1d5a6`: `ZipNotSupportedCompressionMethod`

## pseudocode

```c

```

## disassembly

```asm
0x1d4c0  ldarg.0
0x1d4c1  ldfld    unsigned int32 MS.Internal.IO.Zip.ZipIOLocalFileHeader::_signature
0x1d4c6  ldc.i4   0x4034B50
0x1d4cb  beq.s    loc_1D4DD
0x1d4cd  ldstr    aCorrupteddata// "CorruptedData"
0x1d4d2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d4d7  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1d4dc  throw
0x1d4dd  ldarg.0
0x1d4de  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOLocalFileHeader::_fileNameLength
0x1d4e3  ldarg.0
0x1d4e4  ldfld    unsigned int8[] MS.Internal.IO.Zip.ZipIOLocalFileHeader::_fileName
0x1d4e9  ldlen
0x1d4ea  conv.i4
0x1d4eb  beq.s    loc_1D4FD
0x1d4ed  ldstr    aCorrupteddata// "CorruptedData"
0x1d4f2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d4f7  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1d4fc  throw
0x1d4fd  ldarg.0
0x1d4fe  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOLocalFileHeader::_versionNeededToExtract
0x1d503  call     void MS.Internal.IO.Zip.ZipArchive::VerifyVersionNeededToExtract(unsigned int16 version)
0x1d508  ldarg.0
0x1d509  call     instance bool MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_EncryptedFlag()
0x1d50e  brfalse.s loc_1D520
0x1d510  ldstr    aZipnotsupporte_1// "ZipNotSupportedEncryptedArchive"
0x1d515  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d51a  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1d51f  throw
0x1d520  ldarg.0
0x1d521  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOLocalFileHeader::_versionNeededToExtract
0x1d526  ldc.i4.s 0x2D
0x1d528  bge.s    loc_1D547
0x1d52a  ldarg.0
0x1d52b  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOLocalFileHeader::_extraField
0x1d530  callvirt instance valuetype MS.Internal.IO.Zip.ZipIOZip64ExtraFieldUsage MS.Internal.IO.Zip.ZipIOExtraField::get_Zip64ExtraFieldUsage()
0x1d535  brfalse.s loc_1D547
0x1d537  ldstr    aCorrupteddata// "CorruptedData"
0x1d53c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d541  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1d546  throw
0x1d547  ldarg.0
0x1d548  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOLocalFileHeader::_extraField
0x1d54d  callvirt instance valuetype MS.Internal.IO.Zip.ZipIOZip64ExtraFieldUsage MS.Internal.IO.Zip.ZipIOExtraField::get_Zip64ExtraFieldUsage()
0x1d552  brfalse.s loc_1D572
0x1d554  ldarg.0
0x1d555  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOLocalFileHeader::_extraField
0x1d55a  callvirt instance valuetype MS.Internal.IO.Zip.ZipIOZip64ExtraFieldUsage MS.Internal.IO.Zip.ZipIOExtraField::get_Zip64ExtraFieldUsage()
0x1d55f  ldc.i4.3
0x1d560  beq.s    loc_1D572
0x1d562  ldstr    aCorrupteddata// "CorruptedData"
0x1d567  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d56c  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1d571  throw
0x1d572  ldarg.0
0x1d573  ldfld    unsigned int16 MS.Internal.IO.Zip.ZipIOLocalFileHeader::_extraFieldLength
0x1d578  ldarg.0
0x1d579  ldfld    class MS.Internal.IO.Zip.ZipIOExtraField MS.Internal.IO.Zip.ZipIOLocalFileHeader::_extraField
0x1d57e  callvirt instance unsigned int16 MS.Internal.IO.Zip.ZipIOExtraField::get_Size()
0x1d583  beq.s    loc_1D595
0x1d585  ldstr    aCorrupteddata// "CorruptedData"
0x1d58a  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d58f  newobj   instance void System.IO.FileFormatException::.ctor(string message)
0x1d594  throw
0x1d595  ldarg.0
0x1d596  call     instance valuetype MS.Internal.IO.Zip.CompressionMethodEnum MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_CompressionMethod()
0x1d59b  brfalse.s loc_1D5B6
0x1d59d  ldarg.0
0x1d59e  call     instance valuetype MS.Internal.IO.Zip.CompressionMethodEnum MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_CompressionMethod()
0x1d5a3  ldc.i4.8
0x1d5a4  beq.s    loc_1D5B6
0x1d5a6  ldstr    aZipnotsupporte// "ZipNotSupportedCompressionMethod"
0x1d5ab  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1d5b0  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1d5b5  throw
0x1d5b6  ret
```
