# RestrictedStream::Read

- ea: `0x5a640`
- end: `0x5a66d`
- name: `RestrictedStream::Read`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x2c100`
- `0x5a640`
- `0x5a6f0`

## string_xrefs

- `0x5a65d`: `WriteOnlyStream`

## pseudocode

```c

```

## disassembly

```asm
0x5a640  ldarg.0
0x5a641  call     instance void RestrictedStream::ThrowIfStreamDisposed()
0x5a646  ldarg.0
0x5a647  ldfld    bool RestrictedStream::_canRead
0x5a64c  brfalse.s loc_5A65D
0x5a64e  ldarg.0
0x5a64f  ldfld    class [mscorlib]System.IO.Stream RestrictedStream::_stream
0x5a654  ldarg.1
0x5a655  ldarg.2
0x5a656  ldarg.3
0x5a657  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x5a65c  ret
0x5a65d  ldstr    aWriteonlystrea// "WriteOnlyStream"
0x5a662  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5a667  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x5a66c  throw
```
