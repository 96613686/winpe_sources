# System.Xaml.XamlObjectWriter::ThrowIfDisposed

- ea: `0x3a60`
- end: `0x3a74`
- name: `System.Xaml.XamlObjectWriter::ThrowIfDisposed`
- size: `20`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x28b0`
- `0x2a90`
- `0x2ca0`
- `0x30c0`
- `0x33d0`
- `0x3690`
- `0x3820`
- `0x3950`
- `0x3ab0`
- `0x3ad0`
- `0x3b00`

## callees

- `0x3a60`
- `0xf460`

## string_xrefs

- `0x3a68`: `XamlObjectWriter`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldarg.0
0x3a61  call     instance bool System.Xaml.XamlWriter::get_IsDisposed()
0x3a66  brfalse.s loc_3A73
0x3a68  ldstr    aXamlobjectwrit// "XamlObjectWriter"
0x3a6d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x3a72  throw
0x3a73  ret
```
