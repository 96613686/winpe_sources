# System.Windows.Markup.TypeExtension::ProvideValue

- ea: `0x1c1e0`
- end: `0x1c2a6`
- name: `System.Windows.Markup.TypeExtension::ProvideValue`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x11f20`
- `0x11f50`
- `0x1b610`
- `0x1c1e0`

## string_xrefs

- `0x1c210`: `serviceProvider`
- `0x1c234`: `MarkupExtensionNoContext`
- `0x1c1fd`: `MarkupExtensionTypeName`
- `0x1c280`: `MarkupExtensionTypeNameBad`

## pseudocode

```c

```

## disassembly

```asm
0x1c1e0  ldarg.0
0x1c1e1  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeExtension::_type
0x1c1e6  ldnull
0x1c1e7  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c1ec  brfalse.s loc_1C1F5
0x1c1ee  ldarg.0
0x1c1ef  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeExtension::_type
0x1c1f4  ret
0x1c1f5  ldarg.0
0x1c1f6  ldfld    string System.Windows.Markup.TypeExtension::_typeName
0x1c1fb  brtrue.s loc_1C20D
0x1c1fd  ldstr    aMarkupextensio_5// "MarkupExtensionTypeName"
0x1c202  call     string System.Xaml.SR::Get(string id)
0x1c207  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c20c  throw
0x1c20d  ldarg.1
0x1c20e  brtrue.s loc_1C21B
0x1c210  ldstr    aServiceprovide// "serviceProvider"
0x1c215  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1c21a  throw
0x1c21b  ldarg.1
0x1c21c  ldtoken  System.Windows.Markup.IXamlTypeResolver
0x1c221  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c226  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1c22b  isinst   System.Windows.Markup.IXamlTypeResolver
0x1c230  stloc.0
0x1c231  ldloc.0
0x1c232  brtrue.s loc_1C260
0x1c234  ldstr    aMarkupextensio_4// "MarkupExtensionNoContext"
0x1c239  ldc.i4.2
0x1c23a  newarr   [mscorlib]System.Object
0x1c23f  dup
0x1c240  ldc.i4.0
0x1c241  ldarg.0
0x1c242  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c247  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1c24c  stelem.ref
0x1c24d  dup
0x1c24e  ldc.i4.1
0x1c24f  ldstr    aIxamltyperesol// "IXamlTypeResolver"
0x1c254  stelem.ref
0x1c255  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c25a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c25f  throw
0x1c260  ldarg.0
0x1c261  ldloc.0
0x1c262  ldarg.0
0x1c263  ldfld    string System.Windows.Markup.TypeExtension::_typeName
0x1c268  callvirt instance class [mscorlib]System.Type System.Windows.Markup.IXamlTypeResolver::Resolve(string qualifiedTypeName)
0x1c26d  stfld    class [mscorlib]System.Type System.Windows.Markup.TypeExtension::_type
0x1c272  ldarg.0
0x1c273  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeExtension::_type
0x1c278  ldnull
0x1c279  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c27e  brfalse.s loc_1C29F
0x1c280  ldstr    aMarkupextensio_6// "MarkupExtensionTypeNameBad"
0x1c285  ldc.i4.1
0x1c286  newarr   [mscorlib]System.Object
0x1c28b  dup
0x1c28c  ldc.i4.0
0x1c28d  ldarg.0
0x1c28e  ldfld    string System.Windows.Markup.TypeExtension::_typeName
0x1c293  stelem.ref
0x1c294  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c299  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1c29e  throw
0x1c29f  ldarg.0
0x1c2a0  ldfld    class [mscorlib]System.Type System.Windows.Markup.TypeExtension::_type
0x1c2a5  ret
```
