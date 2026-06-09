# MS.Internal.IO.Packaging.InterleavedZipPartStream::SetLength

- ea: `0x20af0`
- end: `0x20b8d`
- name: `MS.Internal.IO.Packaging.InterleavedZipPartStream::SetLength`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x20af0`
- `0x20d90`
- `0x2c100`
- `0x56d30`
- `0x56db0`
- `0x56dc0`
- `0x56de0`

## string_xrefs

- `0x20b0e`: `StreamDoesNotSupportWrite`

## pseudocode

```c

```

## disassembly

```asm
0x20af0  ldarg.0
0x20af1  call     instance void MS.Internal.IO.Packaging.InterleavedZipPartStream::CheckClosed()
0x20af6  ldarg.1
0x20af7  ldc.i4.0
0x20af8  conv.i8
0x20af9  bge.s    loc_20B06
0x20afb  ldstr    aNewlength// "newLength"
0x20b00  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x20b05  throw
0x20b06  ldarg.0
0x20b07  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x20b0c  brtrue.s loc_20B1E
0x20b0e  ldstr    aStreamdoesnots// "StreamDoesNotSupportWrite"
0x20b13  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x20b18  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x20b1d  throw
0x20b1e  ldarg.0
0x20b1f  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x20b24  brtrue.s loc_20B36
0x20b26  ldstr    aSeeknotsupport// "SeekNotSupported"
0x20b2b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x20b30  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x20b35  throw
0x20b36  ldarg.1
0x20b37  brtrue.s loc_20B3D
0x20b39  ldc.i4.0
0x20b3a  stloc.0
0x20b3b  br.s     loc_20B4D
0x20b3d  ldarg.0
0x20b3e  ldfld    class PieceDirectory MS.Internal.IO.Packaging.InterleavedZipPartStream::_dir
0x20b43  ldarg.1
0x20b44  ldc.i4.1
0x20b45  conv.i8
0x20b46  sub
0x20b47  callvirt instance int32 PieceDirectory::GetPieceNumberFromOffset(int64 offset)
0x20b4c  stloc.0
0x20b4d  ldarg.0
0x20b4e  ldfld    class PieceDirectory MS.Internal.IO.Packaging.InterleavedZipPartStream::_dir
0x20b53  ldloc.0
0x20b54  callvirt instance void PieceDirectory::SetLogicalLastPiece(int32 pieceNumber)
0x20b59  ldarg.0
0x20b5a  ldfld    class PieceDirectory MS.Internal.IO.Packaging.InterleavedZipPartStream::_dir
0x20b5f  ldloc.0
0x20b60  callvirt instance class [mscorlib]System.IO.Stream PieceDirectory::GetStream(int32 pieceNumber)
0x20b65  stloc.1
0x20b66  ldarg.1
0x20b67  ldarg.0
0x20b68  ldfld    class PieceDirectory MS.Internal.IO.Packaging.InterleavedZipPartStream::_dir
0x20b6d  ldloc.0
0x20b6e  callvirt instance int64 PieceDirectory::GetStartOffset(int32 pieceNumber)
0x20b73  sub
0x20b74  stloc.2
0x20b75  ldloc.1
0x20b76  ldloc.2
0x20b77  callvirt instance void [mscorlib]System.IO.Stream::SetLength(int64)
0x20b7c  ldarg.0
0x20b7d  ldfld    int64 MS.Internal.IO.Packaging.InterleavedZipPartStream::_currentOffset
0x20b82  ldarg.1
0x20b83  ble.s    loc_20B8C
0x20b85  ldarg.0
0x20b86  ldarg.1
0x20b87  stfld    int64 MS.Internal.IO.Packaging.InterleavedZipPartStream::_currentOffset
0x20b8c  ret
```
