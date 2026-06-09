# MS.Internal.IO.Packaging.PackagingUtilities::VerifyStreamReadArgs

- ea: `0x1f1f0`
- end: `0x1f266`
- name: `MS.Internal.IO.Packaging.PackagingUtilities::VerifyStreamReadArgs`
- size: `118`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1dcc0`
- `0x1fae0`
- `0x1fe70`
- `0x209b0`
- `0x26630`
- `0x27840`
- `0x290e0`

## callees

- `0x1f1f0`
- `0x2c100`

## string_xrefs

- `0x1f1f8`: `ReadNotSupported`
- `0x1f238`: `ReadCountNegative`
- `0x1f250`: `ReadBufferTooSmall`

## pseudocode

```c

```

## disassembly

```asm
0x1f1f0  ldarg.0
0x1f1f1  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x1f1f6  brtrue.s loc_1F208
0x1f1f8  ldstr    aReadnotsupport// "ReadNotSupported"
0x1f1fd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1f202  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1f207  throw
0x1f208  ldarg.1
0x1f209  brtrue.s loc_1F216
0x1f20b  ldstr    aBuffer// "buffer"
0x1f210  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f215  throw
0x1f216  ldarg.2
0x1f217  ldc.i4.0
0x1f218  bge.s    loc_1F22F
0x1f21a  ldstr    aOffset// "offset"
0x1f21f  ldstr    aOffsetnegative// "OffsetNegative"
0x1f224  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1f229  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1f22e  throw
0x1f22f  ldarg.3
0x1f230  ldc.i4.0
0x1f231  bge.s    loc_1F248
0x1f233  ldstr    aCount// "count"
0x1f238  ldstr    aReadcountnegat// "ReadCountNegative"
0x1f23d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1f242  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1f247  throw
0x1f248  ldarg.2
0x1f249  ldarg.3
0x1f24a  add.ovf
0x1f24b  ldarg.1
0x1f24c  ldlen
0x1f24d  conv.i4
0x1f24e  ble.s    loc_1F265
0x1f250  ldstr    aReadbuffertoos// "ReadBufferTooSmall"
0x1f255  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1f25a  ldstr    aBuffer// "buffer"
0x1f25f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1f264  throw
0x1f265  ret
```
