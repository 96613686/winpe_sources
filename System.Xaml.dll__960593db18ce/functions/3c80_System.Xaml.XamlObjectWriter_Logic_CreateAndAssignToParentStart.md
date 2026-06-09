# System.Xaml.XamlObjectWriter::Logic_CreateAndAssignToParentStart

- ea: `0x3c80`
- end: `0x3e82`
- name: `System.Xaml.XamlObjectWriter::Logic_CreateAndAssignToParentStart`
- size: `514`
- prototype: ``
- caller_count: `3`
- callee_count: `37`
- tags: ``

## callers

- `0x2880`
- `0x2ca0`
- `0x30c0`

## callees

- `0x10`
- `0x2760`
- `0x2870`
- `0x3b70`
- `0x3c80`
- `0x4380`
- `0x44d0`
- `0x4560`
- `0x48f0`
- `0x8590`
- `0x8750`
- `0x8b00`
- `0x8b80`
- `0xd110`
- `0xd130`
- `0xd150`
- `0xd600`
- `0xd8d0`
- `0xef20`
- `0x11f20`
- `0x11f50`
- `0x1d480`
- `0x1d4b0`
- `0x20200`
- `0x20210`
- `0x21200`
- `0x215c0`
- `0x215d0`
- `0x216f0`
- `0x21770`
- `0x217f0`
- `0x21910`
- `0x21930`
- `0x21b70`
- `0x21b90`
- `0x25490`
- `0x25620`

## pseudocode

```c

```

## disassembly

```asm
0x3c80  ldarg.1
0x3c81  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x3c86  stloc.2
0x3c87  ldarg.1
0x3c88  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentIsObjectFromMember()
0x3c8d  brfalse.s loc_3CA5
0x3c8f  ldarg.1
0x3c90  ldstr    aConstructimpli// "ConstructImplicitType"
0x3c95  call     string System.Xaml.SR::Get(string id)
0x3c9a  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x3c9f  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3ca4  throw
0x3ca5  ldloc.2
0x3ca6  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x3cab  brfalse.s loc_3CF0
0x3cad  ldarg.1
0x3cae  callvirt instance object[] MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCtorArgs()
0x3cb3  brfalse.s loc_3CF0
0x3cb5  ldarg.1
0x3cb6  callvirt instance object[] MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCtorArgs()
0x3cbb  stloc.3
0x3cbc  ldc.i4.0
0x3cbd  stloc.s  4
0x3cbf  br.s     loc_3CE9
0x3cc1  ldloc.3
0x3cc2  ldloc.s  4
0x3cc4  ldelem.ref
0x3cc5  isinst   System.Windows.Markup.MarkupExtension
0x3cca  stloc.s  5
0x3ccc  ldloc.s  5
0x3cce  brfalse.s loc_3CE3
0x3cd0  ldloc.3
0x3cd1  ldloc.s  4
0x3cd3  ldarg.0
0x3cd4  ldarg.1
0x3cd5  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x3cda  ldloc.s  5
0x3cdc  ldc.i4.0
0x3cdd  call     instance object System.Xaml.XamlObjectWriter::Logic_PushAndPopAProvideValueStackFrame(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlMember prop, class System.Windows.Markup.MarkupExtension me, bool useIRME)
0x3ce2  stelem.ref
0x3ce3  ldloc.s  4
0x3ce5  ldc.i4.1
0x3ce6  add
0x3ce7  stloc.s  4
0x3ce9  ldloc.s  4
0x3ceb  ldloc.3
0x3cec  ldlen
0x3ced  conv.i4
0x3cee  blt.s    loc_3CC1
0x3cf0  ldarg.1
0x3cf1  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentHasPreconstructionPropertyValuesDictionary()
0x3cf6  brfalse.s loc_3D0C
0x3cf8  ldarg.1
0x3cf9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xaml.XamlMember, object> MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentPreconstructionPropertyValues()
0x3cfe  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_FactoryMethod()
0x3d03  ldloca.s 1
0x3d05  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class System.Xaml.XamlMember, object>::TryGetValue(var<u1>, !!T0)
0x3d0a  brtrue.s loc_3D24
0x3d0c  ldarg.0
0x3d0d  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x3d12  ldloc.2
0x3d13  ldarg.1
0x3d14  callvirt instance object[] MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCtorArgs()
0x3d19  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CreateInstance(class System.Xaml.XamlType xamlType, object[] args)
0x3d1e  stloc.0
0x3d1f  br       loc_3E26
0x3d24  ldloc.1
0x3d25  castclass [mscorlib]System.String
0x3d2a  call     class MS.Internal.Xaml.Parser.XamlPropertyName MS.Internal.Xaml.Parser.XamlPropertyName::Parse(string longName)
0x3d2f  stloc.s  6
0x3d31  ldloc.s  6
0x3d33  brtrue.s loc_3D63
0x3d35  call     class [mscorlib]System.Globalization.CultureInfo System.Xaml.TypeConverterHelper::get_InvariantEnglishUS()
0x3d3a  ldstr    aInvalidexpress// "InvalidExpression"
0x3d3f  call     string System.Xaml.SR::Get(string id)
0x3d44  ldc.i4.1
0x3d45  newarr   [mscorlib]System.Object
0x3d4a  dup
0x3d4b  ldc.i4.0
0x3d4c  ldloc.1
0x3d4d  stelem.ref
0x3d4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d53  stloc.s  9
0x3d55  ldarg.1
0x3d56  ldloc.s  9
0x3d58  newobj   instance void System.Xaml.XamlInternalException::.ctor(string message)
0x3d5d  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3d62  throw
0x3d63  ldloc.s  6
0x3d65  ldfld    class MS.Internal.Xaml.Parser.XamlName MS.Internal.Xaml.Parser.XamlPropertyName::Owner
0x3d6a  brtrue.s loc_3D71
0x3d6c  ldloc.2
0x3d6d  stloc.s  7
0x3d6f  br.s     loc_3DC4
0x3d71  ldarg.1
0x3d72  ldloc.s  6
0x3d74  ldfld    class MS.Internal.Xaml.Parser.XamlName MS.Internal.Xaml.Parser.XamlPropertyName::Owner
0x3d79  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.XamlContext::GetXamlType(class MS.Internal.Xaml.Parser.XamlName typeName)
0x3d7e  stloc.s  7
0x3d80  ldloc.s  7
0x3d82  ldnull
0x3d83  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3d88  brfalse.s loc_3DC4
0x3d8a  ldarg.1
0x3d8b  ldloc.s  6
0x3d8d  ldfld    class MS.Internal.Xaml.Parser.XamlName MS.Internal.Xaml.Parser.XamlPropertyName::Owner
0x3d92  callvirt instance class System.Xaml.Schema.XamlTypeName MS.Internal.Xaml.XamlContext::GetXamlTypeName(class MS.Internal.Xaml.Parser.XamlName typeName)
0x3d97  stloc.s  0xA
0x3d99  ldarg.1
0x3d9a  ldstr    aCannotresolvet// "CannotResolveTypeForFactoryMethod"
0x3d9f  ldc.i4.2
0x3da0  newarr   [mscorlib]System.Object
0x3da5  dup
0x3da6  ldc.i4.0
0x3da7  ldloc.s  0xA
0x3da9  stelem.ref
0x3daa  dup
0x3dab  ldc.i4.1
0x3dac  ldloc.s  6
0x3dae  callvirt instance string MS.Internal.Xaml.Parser.XamlName::get_Name()
0x3db3  stelem.ref
0x3db4  call     string System.Xaml.SR::Get(string id, object[] args)
0x3db9  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3dbe  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3dc3  throw
0x3dc4  ldarg.0
0x3dc5  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x3dca  ldloc.s  7
0x3dcc  ldloc.s  6
0x3dce  callvirt instance string MS.Internal.Xaml.Parser.XamlName::get_Name()
0x3dd3  ldarg.1
0x3dd4  callvirt instance object[] MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentCtorArgs()
0x3dd9  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CreateWithFactoryMethod(class System.Xaml.XamlType xamlType, string methodName, object[] args)
0x3dde  stloc.0
0x3ddf  ldarg.0
0x3de0  ldloc.0
0x3de1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3de6  call     instance class System.Xaml.XamlType System.Xaml.XamlObjectWriter::GetXamlType(class [mscorlib]System.Type clrType)
0x3deb  stloc.s  8
0x3ded  ldloc.s  8
0x3def  ldloc.2
0x3df0  callvirt instance bool System.Xaml.XamlType::CanAssignTo(class System.Xaml.XamlType xamlType)
0x3df5  brtrue.s loc_3E26
0x3df7  ldarg.1
0x3df8  ldstr    aNotassignablef// "NotAssignableFrom"
0x3dfd  ldc.i4.2
0x3dfe  newarr   [mscorlib]System.Object
0x3e03  dup
0x3e04  ldc.i4.0
0x3e05  ldloc.2
0x3e06  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x3e0b  stelem.ref
0x3e0c  dup
0x3e0d  ldc.i4.1
0x3e0e  ldloc.s  8
0x3e10  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x3e15  stelem.ref
0x3e16  call     string System.Xaml.SR::Get(string id, object[] args)
0x3e1b  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3e20  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x3e25  throw
0x3e26  ldarg.1
0x3e27  ldnull
0x3e28  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCtorArgs(object[] value)
0x3e2d  ldarg.1
0x3e2e  ldloc.0
0x3e2f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x3e34  ldloc.2
0x3e35  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x3e3a  brtrue.s loc_3E44
0x3e3c  ldloc.2
0x3e3d  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x3e42  brfalse.s loc_3E4B
0x3e44  ldarg.1
0x3e45  ldloc.0
0x3e46  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x3e4b  ldarg.0
0x3e4c  ldarg.1
0x3e4d  call     instance void System.Xaml.XamlObjectWriter::Logic_BeginInit(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3e52  ldarg.1
0x3e53  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x3e58  ldc.i4.1
0x3e59  ble.s    loc_3E73
0x3e5b  ldloc.0
0x3e5c  isinst   System.Windows.Markup.MarkupExtension
0x3e61  brtrue.s loc_3E73
0x3e63  ldarg.1
0x3e64  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x3e69  ldc.i4.1
0x3e6a  ble.s    loc_3E73
0x3e6c  ldarg.0
0x3e6d  ldarg.1
0x3e6e  call     instance void System.Xaml.XamlObjectWriter::Logic_CheckAssignmentToParentStart(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3e73  ldarg.0
0x3e74  ldloc.0
0x3e75  callvirt instance void System.Xaml.XamlObjectWriter::OnBeforeProperties(object value)
0x3e7a  ldarg.0
0x3e7b  ldarg.1
0x3e7c  call     instance void System.Xaml.XamlObjectWriter::Logic_ApplyCurrentPreconstructionPropertyValues(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x3e81  ret
```
