# MS.Internal.IO.Zip.ZipIOModeEnforcingStream::Write

- ea: `0x1e3f0`
- end: `0x1e44c`
- name: `MS.Internal.IO.Zip.ZipIOModeEnforcingStream::Write`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1e3f0`
- `0x1e510`
- `0x2c100`

## string_xrefs

- `0x1e3fe`: `WriteNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x1e3f0  ldarg.0
0x1e3f1  call     instance void MS.Internal.IO.Zip.ZipIOModeEnforcingStream::CheckDisposed()
0x1e3f6  ldarg.0
0x1e3f7  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x1e3fc  brtrue.s loc_1E40E
0x1e3fe  ldstr    aWritenotsuppor// "WriteNotSupported"
0x1e403  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1e408  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1e40d  throw
0x1e40e  ldarg.0
0x1e40f  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_baseStream
0x1e414  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x1e419  brfalse.s loc_1E42E
0x1e41b  ldarg.0
0x1e41c  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_baseStream
0x1e421  ldarg.0
0x1e422  ldfld    int64 MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_currentStreamPosition
0x1e427  ldc.i4.0
0x1e428  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1e42d  pop
0x1e42e  ldarg.0
0x1e42f  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_baseStream
0x1e434  ldarg.1
0x1e435  ldarg.2
0x1e436  ldarg.3
0x1e437  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x1e43c  ldarg.0
0x1e43d  ldarg.0
0x1e43e  ldfld    int64 MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_currentStreamPosition
0x1e443  ldarg.3
0x1e444  conv.i8
0x1e445  add.ovf
0x1e446  stfld    int64 MS.Internal.IO.Zip.ZipIOModeEnforcingStream::_currentStreamPosition
0x1e44b  ret
```
