# System.Xaml.XamlNodeList::Index

- ea: `0x7680`
- end: `0x76a5`
- name: `System.Xaml.XamlNodeList::Index`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x7680`
- `0x8440`
- `0x11f20`

## string_xrefs

- `0x7688`: `CloseXamlWriterBeforeReading`

## pseudocode

```c

```

## disassembly

```asm
0x7680  ldarg.0
0x7681  ldfld    bool System.Xaml.XamlNodeList::_readMode
0x7686  brtrue.s loc_7698
0x7688  ldstr    aClosexamlwrite// "CloseXamlWriterBeforeReading"
0x768d  call     string System.Xaml.SR::Get(string id)
0x7692  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x7697  throw
0x7698  ldarg.0
0x7699  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> System.Xaml.XamlNodeList::_nodeList
0x769e  ldarg.1
0x769f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::get_Item(!!T0)
0x76a4  ret
```
