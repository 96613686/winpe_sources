# System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue

- ea: `0x48b0`
- end: `0x48e1`
- name: `System.Xaml.XamlObjectWriter::Logic_PendCurrentFixupToken_SetValue`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x4b10`
- `0x4c50`
- `0x4ee0`
- `0x5170`

## callees

- `0x27f0`
- `0x2870`
- `0x20480`
- `0x20c40`
- `0x20c60`
- `0x20ca0`
- `0x21a50`
- `0x21a70`

## pseudocode

```c

```

## disassembly

```asm
0x48b0  ldarg.2
0x48b1  ldarg.1
0x48b2  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LineNumber()
0x48b7  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_LineNumber(int32 value)
0x48bc  ldarg.2
0x48bd  ldarg.1
0x48be  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LinePosition()
0x48c3  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_LinePosition(int32 value)
0x48c8  ldarg.2
0x48c9  ldarg.0
0x48ca  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x48cf  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_Runtime(class MS.Internal.Xaml.Runtime.XamlRuntime value)
0x48d4  ldarg.0
0x48d5  call     instance class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::get_NameFixupGraph()
0x48da  ldarg.2
0x48db  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::AddDependency(class MS.Internal.Xaml.Context.NameFixupToken fixupToken)
0x48e0  ret
```
