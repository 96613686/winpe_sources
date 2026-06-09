# System.Xaml.DeferringWriter::WriteNamespace

- ea: `0x1d90`
- end: `0x1e21`
- name: `System.Xaml.DeferringWriter::WriteNamespace`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1d90`
- `0x1f20`
- `0x8750`
- `0xf3a0`
- `0x11f50`

## string_xrefs

- `0x1db0`: `TemplateNotCollected`
- `0x1dbd`: `WriteNamespace`
- `0x1e10`: `WriteNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldarg.0
0x1d91  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1d96  stloc.0
0x1d97  ldloc.0
0x1d98  switch   loc_1DAF, loc_1DCE, loc_1DDB, loc_1DB0
0x1dad  br.s     loc_1DEF
0x1daf  ret
0x1db0  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1db5  ldc.i4.1
0x1db6  newarr   [mscorlib]System.Object
0x1dbb  dup
0x1dbc  ldc.i4.0
0x1dbd  ldstr    aWritenamespace// "WriteNamespace"
0x1dc2  stelem.ref
0x1dc3  call     string System.Xaml.SR::Get(string id, object[] args)
0x1dc8  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1dcd  throw
0x1dce  ldarg.0
0x1dcf  call     instance void System.Xaml.DeferringWriter::StartDeferredList()
0x1dd4  ldarg.0
0x1dd5  ldc.i4.2
0x1dd6  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1ddb  ldarg.0
0x1ddc  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1de1  ldarg.1
0x1de2  callvirt instance void System.Xaml.XamlWriter::WriteNamespace(class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0x1de7  ldarg.0
0x1de8  ldc.i4.1
0x1de9  stfld    bool System.Xaml.DeferringWriter::_handled
0x1dee  ret
0x1def  ldstr    aMissingcase// "MissingCase"
0x1df4  ldc.i4.2
0x1df5  newarr   [mscorlib]System.Object
0x1dfa  dup
0x1dfb  ldc.i4.0
0x1dfc  ldarg.0
0x1dfd  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1e02  constrained. System.Xaml.DeferringMode
0x1e08  callvirt instance string [mscorlib]System.Object::ToString()
0x1e0d  stelem.ref
0x1e0e  dup
0x1e0f  ldc.i4.1
0x1e10  ldstr    aWritenamespace// "WriteNamespace"
0x1e15  stelem.ref
0x1e16  call     string System.Xaml.SR::Get(string id, object[] args)
0x1e1b  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1e20  throw
```
