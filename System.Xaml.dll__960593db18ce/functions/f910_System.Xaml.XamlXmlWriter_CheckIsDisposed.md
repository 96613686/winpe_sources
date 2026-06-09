# System.Xaml.XamlXmlWriter::CheckIsDisposed

- ea: `0xf910`
- end: `0xf924`
- name: `System.Xaml.XamlXmlWriter::CheckIsDisposed`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0xf6c0`
- `0xf700`
- `0xf770`
- `0xf790`
- `0xf7f0`
- `0xf810`
- `0xf860`

## callees

- `0xf460`
- `0xf910`

## string_xrefs

- `0xf918`: `XamlXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0xf910  ldarg.0
0xf911  call     instance bool System.Xaml.XamlWriter::get_IsDisposed()
0xf916  brfalse.s loc_F923
0xf918  ldstr    aXamlxmlwriter// "XamlXmlWriter"
0xf91d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0xf922  throw
0xf923  ret
```
