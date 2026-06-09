# System.Xaml.DeferringWriter::WriteStartMember

- ea: `0x1b90`
- end: `0x1c31`
- name: `System.Xaml.DeferringWriter::WriteStartMember`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1b90`
- `0x8750`
- `0xa630`
- `0xf370`
- `0x11f50`

## string_xrefs

- `0x1bcc`: `TemplateNotCollected`
- `0x1bd9`: `WriteMember`
- `0x1c1f`: `WriteMember`

## pseudocode

```c

```

## disassembly

```asm
0x1b90  ldarg.0
0x1b91  ldc.i4.0
0x1b92  stfld    bool System.Xaml.DeferringWriter::_handled
0x1b97  ldarg.0
0x1b98  ldfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1b9d  stloc.0
0x1b9e  ldloc.0
0x1b9f  switch   loc_1BB6, loc_1BFE, loc_1BEA, loc_1BCC
0x1bb4  br.s     loc_1BFE
0x1bb6  ldarg.1
0x1bb7  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class System.Xaml.XamlDeferringLoader> System.Xaml.XamlMember::get_DeferringLoader()
0x1bbc  ldnull
0x1bbd  call     bool class System.Xaml.Schema.XamlValueConverter`1<class System.Xaml.XamlDeferringLoader>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x1bc2  brfalse.s loc_1C30
0x1bc4  ldarg.0
0x1bc5  ldc.i4.1
0x1bc6  stfld    valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1bcb  ret
0x1bcc  ldstr    aTemplatenotcol// "TemplateNotCollected"
0x1bd1  ldc.i4.1
0x1bd2  newarr   [mscorlib]System.Object
0x1bd7  dup
0x1bd8  ldc.i4.0
0x1bd9  ldstr    aWritemember// "WriteMember"
0x1bde  stelem.ref
0x1bdf  call     string System.Xaml.SR::Get(string id, object[] args)
0x1be4  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1be9  throw
0x1bea  ldarg.0
0x1beb  ldfld    class System.Xaml.XamlWriter System.Xaml.DeferringWriter::_deferredWriter
0x1bf0  ldarg.1
0x1bf1  callvirt instance void System.Xaml.XamlWriter::WriteStartMember(class System.Xaml.XamlMember xamlMember)
0x1bf6  ldarg.0
0x1bf7  ldc.i4.1
0x1bf8  stfld    bool System.Xaml.DeferringWriter::_handled
0x1bfd  ret
0x1bfe  ldstr    aMissingcase// "MissingCase"
0x1c03  ldc.i4.2
0x1c04  newarr   [mscorlib]System.Object
0x1c09  dup
0x1c0a  ldc.i4.0
0x1c0b  ldarg.0
0x1c0c  ldflda   valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::_mode
0x1c11  constrained. System.Xaml.DeferringMode
0x1c17  callvirt instance string [mscorlib]System.Object::ToString()
0x1c1c  stelem.ref
0x1c1d  dup
0x1c1e  ldc.i4.1
0x1c1f  ldstr    aWritemember// "WriteMember"
0x1c24  stelem.ref
0x1c25  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c2a  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x1c2f  throw
0x1c30  ret
```
