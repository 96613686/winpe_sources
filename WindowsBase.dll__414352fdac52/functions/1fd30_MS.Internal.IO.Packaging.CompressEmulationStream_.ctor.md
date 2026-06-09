# MS.Internal.IO.Packaging.CompressEmulationStream::.ctor

- ea: `0x1fd30`
- end: `0x1fdeb`
- name: `MS.Internal.IO.Packaging.CompressEmulationStream::.ctor`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x20480`
- `0x28420`

## callees

- `0x1fab0`
- `0x1fd30`
- `0x2c100`

## string_xrefs

- `0x1fd74`: `ReadNotSupported`
- `0x1fd87`: `tempStream`

## pseudocode

```c

```

## disassembly

```asm
0x1fd30  ldarg.0
0x1fd31  call     instance void [mscorlib]System.IO.Stream::.ctor()
0x1fd36  ldarg.3
0x1fd37  ldc.i4.0
0x1fd38  conv.i8
0x1fd39  bge.s    loc_1FD46
0x1fd3b  ldstr    aPosition// "position"
0x1fd40  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1fd45  throw
0x1fd46  ldarg.1
0x1fd47  brtrue.s loc_1FD54
0x1fd49  ldstr    aBasestream// "baseStream"
0x1fd4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fd53  throw
0x1fd54  ldarg.1
0x1fd55  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x1fd5a  brtrue.s loc_1FD6C
0x1fd5c  ldstr    aSeeknotsupport// "SeekNotSupported"
0x1fd61  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1fd66  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1fd6b  throw
0x1fd6c  ldarg.1
0x1fd6d  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x1fd72  brtrue.s loc_1FD84
0x1fd74  ldstr    aReadnotsupport// "ReadNotSupported"
0x1fd79  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1fd7e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1fd83  throw
0x1fd84  ldarg.2
0x1fd85  brtrue.s loc_1FD92
0x1fd87  ldstr    aTempstream// "tempStream"
0x1fd8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fd91  throw
0x1fd92  ldarg.s  4
0x1fd94  brtrue.s loc_1FDA1
0x1fd96  ldstr    aTransformer// "transformer"
0x1fd9b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fda0  throw
0x1fda1  ldarg.0
0x1fda2  ldarg.1
0x1fda3  stfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompressEmulationStream::_baseStream
0x1fda8  ldarg.0
0x1fda9  ldarg.2
0x1fdaa  stfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompressEmulationStream::_tempStream
0x1fdaf  ldarg.0
0x1fdb0  ldarg.s  4
0x1fdb2  stfld    class MS.Internal.IO.Packaging.IDeflateTransform MS.Internal.IO.Packaging.CompressEmulationStream::_transformer
0x1fdb7  ldarg.0
0x1fdb8  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompressEmulationStream::_baseStream
0x1fdbd  ldc.i4.0
0x1fdbe  conv.i8
0x1fdbf  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x1fdc4  ldarg.0
0x1fdc5  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompressEmulationStream::_tempStream
0x1fdca  ldc.i4.0
0x1fdcb  conv.i8
0x1fdcc  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x1fdd1  ldarg.0
0x1fdd2  ldfld    class MS.Internal.IO.Packaging.IDeflateTransform MS.Internal.IO.Packaging.CompressEmulationStream::_transformer
0x1fdd7  ldarg.1
0x1fdd8  ldarg.2
0x1fdd9  callvirt instance void MS.Internal.IO.Packaging.IDeflateTransform::Decompress(class [mscorlib]System.IO.Stream source, class [mscorlib]System.IO.Stream sink)
0x1fdde  ldarg.0
0x1fddf  ldfld    class [mscorlib]System.IO.Stream MS.Internal.IO.Packaging.CompressEmulationStream::_tempStream
0x1fde4  ldarg.3
0x1fde5  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x1fdea  ret
```
