# MS.Internal.IO.Zip.ZipIOLocalFileBlock::ParseRecord

- ea: `0x1ccd0`
- end: `0x1ce09`
- name: `MS.Internal.IO.Zip.ZipIOLocalFileBlock::ParseRecord`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1c830`

## callees

- `0x19400`
- `0x19480`
- `0x1a2e0`
- `0x1b600`
- `0x1b630`
- `0x1b660`
- `0x1ca90`
- `0x1cb30`
- `0x1ccd0`
- `0x1ce10`
- `0x1d0d0`
- `0x1d270`
- `0x1d290`
- `0x1d350`
- `0x1d370`
- `0x1d5e0`
- `0x1dee0`
- `0x20290`
- `0x2c100`

## string_xrefs

- `0x1cded`: `ZipNotSupportedCompressionMethod`

## pseudocode

```c

```

## disassembly

```asm
0x1ccd0  ldarg.0
0x1ccd1  call     instance void MS.Internal.IO.Zip.ZipIOLocalFileBlock::CheckDisposed()
0x1ccd6  ldarg.0
0x1ccd7  ldarg.1
0x1ccd8  ldarg.0
0x1ccd9  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipIOLocalFileBlock::_blockManager
0x1ccde  callvirt instance class [mscorlib]System.Text.Encoding MS.Internal.IO.Zip.ZipIOBlockManager::get_Encoding()
0x1cce3  call     class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileHeader::ParseRecord(class [mscorlib]System.IO.BinaryReader reader, class [mscorlib]System.Text.Encoding encoding)
0x1cce8  stfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1cced  ldarg.0
0x1ccee  ldfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1ccf3  callvirt instance bool MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_StreamingCreationFlag()
0x1ccf8  brfalse.s loc_1CD41
0x1ccfa  ldarg.0
0x1ccfb  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipIOLocalFileBlock::_blockManager
0x1cd00  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOBlockManager::get_Stream()
0x1cd05  ldarg.s  5
0x1cd07  callvirt instance int64 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_CompressedSize()
0x1cd0c  ldc.i4.1
0x1cd0d  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1cd12  pop
0x1cd13  ldarg.0
0x1cd14  ldarg.1
0x1cd15  ldarg.s  5
0x1cd17  callvirt instance int64 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_CompressedSize()
0x1cd1c  ldarg.s  5
0x1cd1e  callvirt instance int64 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_UncompressedSize()
0x1cd23  ldarg.s  5
0x1cd25  callvirt instance unsigned int32 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_Crc32()
0x1cd2a  ldarg.0
0x1cd2b  ldfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1cd30  callvirt instance unsigned int16 MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_VersionNeededToExtract()
0x1cd35  call     class MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor::ParseRecord(class [mscorlib]System.IO.BinaryReader reader, int64 compressedSizeFromCentralDir, int64 uncompressedSizeFromCentralDir, unsigned int32 crc32FromCentralDir, unsigned int16 versionNeededToExtract)
0x1cd3a  stfld    class MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileDataDescriptor
0x1cd3f  br.s     loc_1CD48
0x1cd41  ldarg.0
0x1cd42  ldnull
0x1cd43  stfld    class MS.Internal.IO.Zip.ZipIOLocalFileDataDescriptor MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileDataDescriptor
0x1cd48  ldarg.0
0x1cd49  ldarg.3
0x1cd4a  stfld    int64 MS.Internal.IO.Zip.ZipIOLocalFileBlock::_offset
0x1cd4f  ldarg.0
0x1cd50  ldc.i4.0
0x1cd51  stfld    bool MS.Internal.IO.Zip.ZipIOLocalFileBlock::_dirtyFlag
0x1cd56  ldarg.0
0x1cd57  ldarg.0
0x1cd58  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipIOLocalFileBlock::_blockManager
0x1cd5d  ldarg.0
0x1cd5e  ldarg.3
0x1cd5f  ldarg.0
0x1cd60  ldfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1cd65  callvirt instance int64 MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_Size()
0x1cd6a  add.ovf
0x1cd6b  ldarg.s  5
0x1cd6d  callvirt instance int64 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_CompressedSize()
0x1cd72  newobj   instance void MS.Internal.IO.Zip.ZipIOFileItemStream::.ctor(class MS.Internal.IO.Zip.ZipIOBlockManager blockManager, class MS.Internal.IO.Zip.ZipIOLocalFileBlock block, int64 persistedOffset, int64 persistedSize)
0x1cd77  stfld    class MS.Internal.IO.Zip.ZipIOFileItemStream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_fileItemStream
0x1cd7c  ldarg.0
0x1cd7d  ldfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1cd82  callvirt instance valuetype MS.Internal.IO.Zip.CompressionMethodEnum MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_CompressionMethod()
0x1cd87  ldc.i4.8
0x1cd88  bne.un.s loc_1CDC1
0x1cd8a  ldarg.0
0x1cd8b  ldarg.0
0x1cd8c  ldfld    class MS.Internal.IO.Zip.ZipIOFileItemStream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_fileItemStream
0x1cd91  ldarg.s  5
0x1cd93  callvirt instance int64 MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader::get_UncompressedSize()
0x1cd98  newobj   instance void MS.Internal.IO.Packaging.CompressStream::.ctor(class [mscorlib]System.IO.Stream baseStream, int64 length)
0x1cd9d  stfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_deflateStream
0x1cda2  ldarg.0
0x1cda3  ldarg.0
0x1cda4  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipIOLocalFileBlock::_blockManager
0x1cda9  ldarg.0
0x1cdaa  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_deflateStream
0x1cdaf  ldarg.0
0x1cdb0  call     instance unsigned int32 MS.Internal.IO.Zip.ZipIOLocalFileBlock::get_Crc32()
0x1cdb5  newobj   instance void MS.Internal.IO.Zip.ProgressiveCrcCalculatingStream::.ctor(class MS.Internal.IO.Zip.ZipIOBlockManager blockManager, class [mscorlib]System.IO.Stream underlyingStream, unsigned int32 expectedCrc)
0x1cdba  stfld    class MS.Internal.IO.Zip.ProgressiveCrcCalculatingStream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_crcCalculatingStream
0x1cdbf  br.s     loc_1CDFD
0x1cdc1  ldarg.0
0x1cdc2  ldfld    class MS.Internal.IO.Zip.ZipIOLocalFileHeader MS.Internal.IO.Zip.ZipIOLocalFileBlock::_localFileHeader
0x1cdc7  callvirt instance valuetype MS.Internal.IO.Zip.CompressionMethodEnum MS.Internal.IO.Zip.ZipIOLocalFileHeader::get_CompressionMethod()
0x1cdcc  brtrue.s loc_1CDED
0x1cdce  ldarg.0
0x1cdcf  ldarg.0
0x1cdd0  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipIOLocalFileBlock::_blockManager
0x1cdd5  ldarg.0
0x1cdd6  ldfld    class MS.Internal.IO.Zip.ZipIOFileItemStream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_fileItemStream
0x1cddb  ldarg.0
0x1cddc  call     instance unsigned int32 MS.Internal.IO.Zip.ZipIOLocalFileBlock::get_Crc32()
0x1cde1  newobj   instance void MS.Internal.IO.Zip.ProgressiveCrcCalculatingStream::.ctor(class MS.Internal.IO.Zip.ZipIOBlockManager blockManager, class [mscorlib]System.IO.Stream underlyingStream, unsigned int32 expectedCrc)
0x1cde6  stfld    class MS.Internal.IO.Zip.ProgressiveCrcCalculatingStream MS.Internal.IO.Zip.ZipIOLocalFileBlock::_crcCalculatingStream
0x1cdeb  br.s     loc_1CDFD
0x1cded  ldstr    aZipnotsupporte// "ZipNotSupportedCompressionMethod"
0x1cdf2  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1cdf7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1cdfc  throw
0x1cdfd  ldarg.0
0x1cdfe  ldarg.2
0x1cdff  ldarg.s  4
0x1ce01  ldarg.s  5
0x1ce03  call     instance void MS.Internal.IO.Zip.ZipIOLocalFileBlock::Validate(string fileName, class MS.Internal.IO.Zip.ZipIOCentralDirectoryBlock centralDir, class MS.Internal.IO.Zip.ZipIOCentralDirectoryFileHeader centralDirFileHeader)
0x1ce08  ret
```
