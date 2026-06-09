# System.Xaml.DeferringWriter::WriteObject

- ea: `0x1a20`
- end: `0x1ace`
- name: `System.Xaml.DeferringWriter::WriteObject`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1a00`
- `0x1a10`

## callees

- `0x1a20`
- `0x1f20`
- `0x8750`
- `0xf340`
- `0xf350`
- `0x11f50`

## string_xrefs

- `0x1a46`: `TemplateNotCollected`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  ldc.i4.0
0x1a22  stfld    bool System.Xaml.DeferringWriter::_handled
0x1a27  ldarg.0
0x1a28  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1a2d  stloc.0
0x1a2e  ldloc.0
0x1a2f  switch   loc_1ACD, loc_1A60, loc_1A6D, loc_1A46
0x1a44  br.s     loc_1A9F
0x1a46  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1a4b  ldc.i4.1
0x1a4c  newarr   [mscorlib]System.Object
0x1a51  dup
0x1a52  ldc.i4.0
0x1a53  ldarg.3
0x1a54  stelem.ref
0x1a55  call     string System.Xaml.SR::Get(string id, object[] args)
0x1a5a  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1a5f  throw
0x1a60  ldarg.0
0x1a61  call     instance void System.Xaml.DeferringWriter::StartDeferredList()
0x1a66  ldarg.0
0x1a67  ldc.i4.2
0x1a68  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1a6d  ldarg.2
0x1a6e  brfalse.s loc_1A7D
0x1a70  ldarg.0
0x1a71  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1a76  callvirt instance void System.Xaml.XamlWriter::WriteGetObject()
0x1a7b  br.s     loc_1A89
0x1a7d  ldarg.0
0x1a7e  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1a83  ldarg.1
0x1a84  callvirt instance void System.Xaml.XamlWriter::WriteStartObject(class System.Xaml.XamlType type)
0x1a89  ldarg.0
0x1a8a  ldarg.0
0x1a8b  ldfld    int32 System.Xaml.DeferringWriter::_deferredTreeDepth
0x1a90  ldc.i4.1
0x1a91  add
0x1a92  stfld    int32 System.Xaml.DeferringWriter::_deferredTreeDepth
0x1a97  ldarg.0
0x1a98  ldc.i4.1
0x1a99  stfld    bool System.Xaml.DeferringWriter::_handled
0x1a9e  ret
0x1a9f  ldstr    aMissingcase// "MissingCase"
0x1aa4  ldc.i4.2
0x1aa5  newarr   [mscorlib]System.Object
0x1aaa  dup
0x1aab  ldc.i4.0
0x1aac  ldarg.0
0x1aad  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1ab2  constrained. System.Xaml.DeferringMode
0x1ab8  callvirt instance string [mscorlib]System.Object::ToString()
0x1abd  stelem.ref
0x1abe  dup
0x1abf  ldc.i4.1
0x1ac0  ldarg.3
0x1ac1  stelem.ref
0x1ac2  call     string System.Xaml.SR::Get(string id, object[] args)
0x1ac7  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1acc  throw
0x1acd  ret
```
