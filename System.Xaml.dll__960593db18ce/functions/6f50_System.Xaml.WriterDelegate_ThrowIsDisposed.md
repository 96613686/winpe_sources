# System.Xaml.WriterDelegate::ThrowIsDisposed

- ea: `0x6f50`
- end: `0x6f64`
- name: `System.Xaml.WriterDelegate::ThrowIsDisposed`
- size: `20`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x6db0`
- `0x6dd0`
- `0x6df0`
- `0x6e10`
- `0x6e30`
- `0x6e50`
- `0x6e70`
- `0x6f00`
- `0x6f20`

## callees

- `0x6f50`
- `0xf460`

## string_xrefs

- `0x6f58`: `XamlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  ldarg.0
0x6f51  call     instance bool System.Xaml.XamlWriter::get_IsDisposed()
0x6f56  brfalse.s loc_6F63
0x6f58  ldstr    aXamlwriter// "XamlWriter"
0x6f5d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x6f62  throw
0x6f63  ret
```
