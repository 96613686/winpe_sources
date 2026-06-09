# System.Xaml.XamlXmlReader::ThrowIfDisposed

- ea: `0x6560`
- end: `0x6574`
- name: `System.Xaml.XamlXmlReader::ThrowIfDisposed`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x6430`

## callees

- `0x6560`
- `0xb3f0`

## string_xrefs

- `0x6568`: `XamlXmlReader`

## pseudocode

```c

```

## disassembly

```asm
0x6560  ldarg.0
0x6561  call     instance bool System.Xaml.XamlReader::get_IsDisposed()
0x6566  brfalse.s loc_6573
0x6568  ldstr    aXamlxmlreader// "XamlXmlReader"
0x656d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x6572  throw
0x6573  ret
```
