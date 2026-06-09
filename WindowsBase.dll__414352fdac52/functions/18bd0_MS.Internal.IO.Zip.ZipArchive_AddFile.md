# MS.Internal.IO.Zip.ZipArchive::AddFile

- ea: `0x18bd0`
- end: `0x18c68`
- name: `MS.Internal.IO.Zip.ZipArchive::AddFile`
- size: `152`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x23b50`
- `0x4af50`
- `0x56f80`
- `0x5ace0`

## callees

- `0x18bd0`
- `0x18d00`
- `0x19100`
- `0x19120`
- `0x191a0`
- `0x19270`
- `0x19510`
- `0x19820`
- `0x2c100`

## string_xrefs

- `0x18bdf`: `CanNotWriteInReadOnlyMode`
- `0x18bfe`: `compressionMethod`
- `0x18c2d`: `AttemptedToCreateDuplicateFileName`

## pseudocode

```c

```

## disassembly

```asm
0x18bd0  ldarg.0
0x18bd1  call     instance void MS.Internal.IO.Zip.ZipArchive::CheckDisposed()
0x18bd6  ldarg.0
0x18bd7  ldfld    valuetype [mscorlib]System.IO.FileAccess MS.Internal.IO.Zip.ZipArchive::_openAccess
0x18bdc  ldc.i4.1
0x18bdd  bne.un.s loc_18BEF
0x18bdf  ldstr    aCannotwriteinr// "CanNotWriteInReadOnlyMode"
0x18be4  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x18be9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18bee  throw
0x18bef  ldarg.1
0x18bf0  call     string MS.Internal.IO.Zip.ZipIOBlockManager::ValidateNormalizeFileName(string zipFileName)
0x18bf5  starg.s  1
0x18bf7  ldarg.2
0x18bf8  brfalse.s loc_18C09
0x18bfa  ldarg.2
0x18bfb  ldc.i4.8
0x18bfc  beq.s    loc_18C09
0x18bfe  ldstr    aCompressionmet// "compressionMethod"
0x18c03  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x18c08  throw
0x18c09  ldarg.3
0x18c0a  ldc.i4.0
0x18c0b  blt.s    loc_18C19
0x18c0d  ldarg.3
0x18c0e  ldc.i4.6
0x18c0f  ble.s    loc_18C24
0x18c11  ldarg.3
0x18c12  ldc.i4   0xFF
0x18c17  beq.s    loc_18C24
0x18c19  ldstr    aDeflateoption// "deflateOption"
0x18c1e  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x18c23  throw
0x18c24  ldarg.0
0x18c25  ldarg.1
0x18c26  call     instance bool MS.Internal.IO.Zip.ZipArchive::FileExists(string zipFileName)
0x18c2b  brfalse.s loc_18C3D
0x18c2d  ldstr    aAttemptedtocre// "AttemptedToCreateDuplicateFileName"
0x18c32  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x18c37  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18c3c  throw
0x18c3d  ldarg.0
0x18c3e  ldfld    class MS.Internal.IO.Zip.ZipIOBlockManager MS.Internal.IO.Zip.ZipArchive::_blockManager
0x18c43  ldarg.1
0x18c44  ldarg.2
0x18c45  ldarg.3
0x18c46  callvirt instance class MS.Internal.IO.Zip.ZipIOLocalFileBlock MS.Internal.IO.Zip.ZipIOBlockManager::CreateLocalFileBlock(string zipFileName, valuetype MS.Internal.IO.Zip.CompressionMethodEnum compressionMethod, valuetype MS.Internal.IO.Zip.DeflateOptionEnum deflateOption)
0x18c4b  stloc.0
0x18c4c  ldarg.0
0x18c4d  ldloc.0
0x18c4e  newobj   instance void MS.Internal.IO.Zip.ZipFileInfo::.ctor(class MS.Internal.IO.Zip.ZipArchive zipArchive, class MS.Internal.IO.Zip.ZipIOLocalFileBlock fileBlock)
0x18c53  stloc.1
0x18c54  ldarg.0
0x18c55  call     instance class [mscorlib]System.Collections.IDictionary MS.Internal.IO.Zip.ZipArchive::get_ZipFileInfoDictionary()
0x18c5a  ldloc.1
0x18c5b  callvirt instance string MS.Internal.IO.Zip.ZipFileInfo::get_Name()
0x18c60  ldloc.1
0x18c61  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x18c66  ldloc.1
0x18c67  ret
```
