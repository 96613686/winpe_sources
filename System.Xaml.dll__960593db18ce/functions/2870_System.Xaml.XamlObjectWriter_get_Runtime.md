# System.Xaml.XamlObjectWriter::get_Runtime

- ea: `0x2870`
- end: `0x287c`
- name: `System.Xaml.XamlObjectWriter::get_Runtime`
- size: `12`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x28b0`
- `0x30c0`
- `0x3b20`
- `0x3c80`
- `0x40c0`
- `0x4110`
- `0x4380`
- `0x43e0`
- `0x4560`
- `0x45b0`
- `0x4770`
- `0x48b0`
- `0x4940`
- `0x4a40`
- `0x4b10`
- `0x5030`
- `0x5050`
- `0x5660`
- `0x56d0`
- `0x5790`
- `0x5a20`

## callees

- `0x21010`

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.0
0x2871  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2876  callvirt instance class MS.Internal.Xaml.Runtime.XamlRuntime MS.Internal.Xaml.Context.ObjectWriterContext::get_Runtime()
0x287b  ret
```
