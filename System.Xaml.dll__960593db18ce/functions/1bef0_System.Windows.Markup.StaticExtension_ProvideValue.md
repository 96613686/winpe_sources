# System.Windows.Markup.StaticExtension::ProvideValue

- ea: `0x1bef0`
- end: `0x1c099`
- name: `System.Windows.Markup.StaticExtension::ProvideValue`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x11f20`
- `0x11f50`
- `0x1b610`
- `0x1bef0`
- `0x1c0a0`
- `0x1c140`

## string_xrefs

- `0x1bef8`: `MarkupExtensionStaticMember`
- `0x1bf5a`: `MarkupExtensionBadStatic`
- `0x1bf97`: `MarkupExtensionBadStatic`
- `0x1c042`: `MarkupExtensionBadStatic`
- `0x1c07f`: `MarkupExtensionBadStatic`
- `0x1bfb9`: `serviceProvider`
- `0x1bfdf`: `MarkupExtensionNoContext`

## pseudocode

```c

```

## disassembly

```asm
0x1bef0  ldarg.0
0x1bef1  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bef6  brtrue.s loc_1BF08
0x1bef8  ldstr    aMarkupextensio_2// "MarkupExtensionStaticMember"
0x1befd  call     string System.Xaml.SR::Get(string id)
0x1bf02  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1bf07  throw
0x1bf08  ldarg.0
0x1bf09  call     instance class [mscorlib]System.Type System.Windows.Markup.StaticExtension::get_MemberType()
0x1bf0e  stloc.1
0x1bf0f  ldnull
0x1bf10  stloc.2
0x1bf11  ldnull
0x1bf12  stloc.3
0x1bf13  ldloc.1
0x1bf14  ldnull
0x1bf15  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bf1a  brfalse.s loc_1BF3F
0x1bf1c  ldarg.0
0x1bf1d  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf22  stloc.2
0x1bf23  ldloc.1
0x1bf24  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1bf29  ldstr    asc_37256// "."
0x1bf2e  ldarg.0
0x1bf2f  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf34  call     string [mscorlib]System.String::Concat(string, string, string)
0x1bf39  stloc.3
0x1bf3a  br       loc_1C061
0x1bf3f  ldarg.0
0x1bf40  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf45  stloc.3
0x1bf46  ldarg.0
0x1bf47  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf4c  ldc.i4.s 0x2E
0x1bf4e  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1bf53  stloc.s  4
0x1bf55  ldloc.s  4
0x1bf57  ldc.i4.0
0x1bf58  bge.s    loc_1BF79
0x1bf5a  ldstr    aMarkupextensio_3// "MarkupExtensionBadStatic"
0x1bf5f  ldc.i4.1
0x1bf60  newarr   [mscorlib]System.Object
0x1bf65  dup
0x1bf66  ldc.i4.0
0x1bf67  ldarg.0
0x1bf68  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf6d  stelem.ref
0x1bf6e  call     string System.Xaml.SR::Get(string id, object[] args)
0x1bf73  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1bf78  throw
0x1bf79  ldarg.0
0x1bf7a  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bf7f  ldc.i4.0
0x1bf80  ldloc.s  4
0x1bf82  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1bf87  stloc.s  5
0x1bf89  ldloc.s  5
0x1bf8b  ldsfld   string [mscorlib]System.String::Empty
0x1bf90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bf95  brfalse.s loc_1BFB6
0x1bf97  ldstr    aMarkupextensio_3// "MarkupExtensionBadStatic"
0x1bf9c  ldc.i4.1
0x1bf9d  newarr   [mscorlib]System.Object
0x1bfa2  dup
0x1bfa3  ldc.i4.0
0x1bfa4  ldarg.0
0x1bfa5  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1bfaa  stelem.ref
0x1bfab  call     string System.Xaml.SR::Get(string id, object[] args)
0x1bfb0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1bfb5  throw
0x1bfb6  ldarg.1
0x1bfb7  brtrue.s loc_1BFC4
0x1bfb9  ldstr    aServiceprovide// "serviceProvider"
0x1bfbe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1bfc3  throw
0x1bfc4  ldarg.1
0x1bfc5  ldtoken  System.Windows.Markup.IXamlTypeResolver
0x1bfca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bfcf  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1bfd4  isinst   System.Windows.Markup.IXamlTypeResolver
0x1bfd9  stloc.s  6
0x1bfdb  ldloc.s  6
0x1bfdd  brtrue.s loc_1C00B
0x1bfdf  ldstr    aMarkupextensio_4// "MarkupExtensionNoContext"
0x1bfe4  ldc.i4.2
0x1bfe5  newarr   [mscorlib]System.Object
0x1bfea  dup
0x1bfeb  ldc.i4.0
0x1bfec  ldarg.0
0x1bfed  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1bff2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1bff7  stelem.ref
0x1bff8  dup
0x1bff9  ldc.i4.1
0x1bffa  ldstr    aIxamltyperesol// "IXamlTypeResolver"
0x1bfff  stelem.ref
0x1c000  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c005  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1c00a  throw
0x1c00b  ldloc.s  6
0x1c00d  ldloc.s  5
0x1c00f  callvirt instance class [mscorlib]System.Type System.Windows.Markup.IXamlTypeResolver::Resolve(string qualifiedTypeName)
0x1c014  stloc.1
0x1c015  ldarg.0
0x1c016  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1c01b  ldloc.s  4
0x1c01d  ldc.i4.1
0x1c01e  add
0x1c01f  ldarg.0
0x1c020  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1c025  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1c02a  ldloc.s  4
0x1c02c  sub
0x1c02d  ldc.i4.1
0x1c02e  sub
0x1c02f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1c034  stloc.2
0x1c035  ldloc.2
0x1c036  ldsfld   string [mscorlib]System.String::Empty
0x1c03b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c040  brfalse.s loc_1C061
0x1c042  ldstr    aMarkupextensio_3// "MarkupExtensionBadStatic"
0x1c047  ldc.i4.1
0x1c048  newarr   [mscorlib]System.Object
0x1c04d  dup
0x1c04e  ldc.i4.0
0x1c04f  ldarg.0
0x1c050  ldfld    string System.Windows.Markup.StaticExtension::_member
0x1c055  stelem.ref
0x1c056  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c05b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1c060  throw
0x1c061  ldloc.1
0x1c062  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x1c067  brfalse.s loc_1C071
0x1c069  ldloc.1
0x1c06a  ldloc.2
0x1c06b  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x1c070  ret
0x1c071  ldarg.0
0x1c072  ldloc.1
0x1c073  ldloc.2
0x1c074  ldloca.s 0
0x1c076  call     instance bool System.Windows.Markup.StaticExtension::GetFieldOrPropertyValue(class [mscorlib]System.Type type, string name, [out] object& value)
0x1c07b  brfalse.s loc_1C07F
0x1c07d  ldloc.0
0x1c07e  ret
0x1c07f  ldstr    aMarkupextensio_3// "MarkupExtensionBadStatic"
0x1c084  ldc.i4.1
0x1c085  newarr   [mscorlib]System.Object
0x1c08a  dup
0x1c08b  ldc.i4.0
0x1c08c  ldloc.3
0x1c08d  stelem.ref
0x1c08e  call     string System.Xaml.SR::Get(string id, object[] args)
0x1c093  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1c098  throw
```
