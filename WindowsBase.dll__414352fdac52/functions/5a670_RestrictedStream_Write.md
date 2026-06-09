# RestrictedStream::Write

- ea: `0x5a670`
- end: `0x5a69d`
- name: `RestrictedStream::Write`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x2c100`
- `0x5a670`
- `0x5a6f0`

## string_xrefs

- `0x5a68d`: `ReadOnlyStream`

## pseudocode

```c

```

## disassembly

```asm
0x5a670  ldarg.0
0x5a671  call     instance void RestrictedStream::ThrowIfStreamDisposed()
0x5a676  ldarg.0
0x5a677  ldfld    bool RestrictedStream::_canWrite
0x5a67c  brfalse.s loc_5A68D
0x5a67e  ldarg.0
0x5a67f  ldfld    class [mscorlib]System.IO.Stream RestrictedStream::_stream
0x5a684  ldarg.1
0x5a685  ldarg.2
0x5a686  ldarg.3
0x5a687  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x5a68c  ret
0x5a68d  ldstr    aReadonlystream// "ReadOnlyStream"
0x5a692  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5a697  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x5a69c  throw
```
