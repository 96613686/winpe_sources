# System.Xaml.XamlObjectWriter::WriteNamespace

- ea: `0x3820`
- end: `0x3947`
- name: `System.Xaml.XamlObjectWriter::WriteNamespace`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x19c0`
- `0x3820`
- `0x3a60`
- `0x6970`
- `0x6980`
- `0x8590`
- `0xb280`
- `0xefa0`
- `0xf3a0`
- `0x11f20`
- `0x11f50`
- `0x1d440`
- `0x21200`
- `0x21540`
- `0x215d0`
- `0x21650`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.0
0x3821  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x3826  ldarg.1
0x3827  brtrue.s loc_3834
0x3829  ldstr    aNamespacedecla// "namespaceDeclaration"
0x382e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3833  throw
0x3834  ldarg.1
0x3835  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0x383a  brtrue.s loc_384C
0x383c  ldstr    aNamespacedecla_0// "NamespaceDeclarationPrefixCannotBeNull"
0x3841  call     string System.Xaml.SR::Get(string id)
0x3846  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x384b  throw
0x384c  ldarg.1
0x384d  callvirt instance string System.Xaml.NamespaceDeclaration::get_Namespace()
0x3852  brtrue.s loc_3864
0x3854  ldstr    aNamespacedecla_1// "NamespaceDeclarationNamespaceCannotBeNu"...
0x3859  call     string System.Xaml.SR::Get(string id)
0x385e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3863  throw
0x3864  ldarg.0
0x3865  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x386a  ldarg.1
0x386b  callvirt instance void System.Xaml.XamlWriter::WriteNamespace(class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0x3870  ldarg.0
0x3871  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x3876  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x387b  brfalse.s loc_387E
0x387d  ret
0x387e  ldarg.0
0x387f  ldfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x3884  brfalse.s loc_38A3
0x3886  ldstr    aValuemustbefol// "ValueMustBeFollowedByEndMember"
0x388b  call     string System.Xaml.SR::Get(string id)
0x3890  stloc.0
0x3891  ldarg.0
0x3892  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3897  ldloc.0
0x3898  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x389d  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x38a2  throw
0x38a3  ldarg.0
0x38a4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x38a9  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x38ae  ldnull
0x38af  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x38b4  brfalse.s loc_3911
0x38b6  ldarg.0
0x38b7  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x38bc  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x38c1  ldnull
0x38c2  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x38c7  brfalse.s loc_3911
0x38c9  ldstr    aNopropertyincu_6// "NoPropertyInCurrentFrame_NS"
0x38ce  ldc.i4.3
0x38cf  newarr   [mscorlib]System.Object
0x38d4  dup
0x38d5  ldc.i4.0
0x38d6  ldarg.1
0x38d7  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0x38dc  stelem.ref
0x38dd  dup
0x38de  ldc.i4.1
0x38df  ldarg.1
0x38e0  callvirt instance string System.Xaml.NamespaceDeclaration::get_Namespace()
0x38e5  stelem.ref
0x38e6  dup
0x38e7  ldc.i4.2
0x38e8  ldarg.0
0x38e9  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x38ee  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x38f3  callvirt instance string [mscorlib]System.Object::ToString()
0x38f8  stelem.ref
0x38f9  call     string System.Xaml.SR::Get(string id, object[] args)
0x38fe  stloc.1
0x38ff  ldarg.0
0x3900  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3905  ldloc.1
0x3906  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x390b  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3910  throw
0x3911  ldarg.0
0x3912  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3917  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x391c  ldnull
0x391d  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3922  brfalse.s loc_392F
0x3924  ldarg.0
0x3925  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x392a  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x392f  ldarg.0
0x3930  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3935  ldarg.1
0x3936  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0x393b  ldarg.1
0x393c  callvirt instance string System.Xaml.NamespaceDeclaration::get_Namespace()
0x3941  callvirt instance void MS.Internal.Xaml.XamlContext::AddNamespacePrefix(string prefix, string xamlNamespace)
0x3946  ret
```
