# System.Xaml.XamlObjectWriter::Logic_CreateFromInitializationValue

- ea: `0x3fe0`
- end: `0x40a3`
- name: `System.Xaml.XamlObjectWriter::Logic_CreateFromInitializationValue`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x33d0`
- `0x5790`

## callees

- `0x3fe0`
- `0x40b0`
- `0x44e0`
- `0x8590`
- `0xd050`
- `0xd070`
- `0xd110`
- `0xd130`
- `0xd310`
- `0xd8d0`
- `0x11f50`
- `0x21200`
- `0x21590`
- `0x21610`
- `0x216d0`
- `0x216f0`
- `0x21770`
- `0x218f0`

## string_xrefs

- `0x3fff`: `CantCreateUnknownType`

## pseudocode

```c

```

## disassembly

```asm
0x3fe0  ldarg.1
0x3fe1  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x3fe6  stloc.0
0x3fe7  ldloc.0
0x3fe8  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x3fed  stloc.1
0x3fee  ldarg.1
0x3fef  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x3ff4  stloc.2
0x3ff5  ldnull
0x3ff6  stloc.3
0x3ff7  ldloc.0
0x3ff8  callvirt instance bool System.Xaml.XamlType::get_IsUnknown()
0x3ffd  brfalse.s loc_4028
0x3fff  ldstr    aCantcreateunkn// "CantCreateUnknownType"
0x4004  ldc.i4.1
0x4005  newarr   [mscorlib]System.Object
0x400a  dup
0x400b  ldc.i4.0
0x400c  ldloc.0
0x400d  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x4012  stelem.ref
0x4013  call     string System.Xaml.SR::Get(string id, object[] args)
0x4018  stloc.s  4
0x401a  ldarg.1
0x401b  ldloc.s  4
0x401d  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4022  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4027  throw
0x4028  ldloc.1
0x4029  ldnull
0x402a  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Equality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x402f  brfalse.s loc_4056
0x4031  ldarg.1
0x4032  ldstr    aInitialization// "InitializationSyntaxWithoutTypeConverte"...
0x4037  ldc.i4.1
0x4038  newarr   [mscorlib]System.Object
0x403d  dup
0x403e  ldc.i4.0
0x403f  ldloc.0
0x4040  callvirt instance string System.Xaml.XamlType::GetQualifiedName()
0x4045  stelem.ref
0x4046  call     string System.Xaml.SR::Get(string id, object[] args)
0x404b  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x4050  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x4055  throw
0x4056  ldarg.0
0x4057  ldarg.1
0x4058  ldloc.1
0x4059  ldloc.2
0x405a  ldnull
0x405b  ldloc.0
0x405c  callvirt instance string System.Xaml.XamlType::get_Name()
0x4061  call     instance object System.Xaml.XamlObjectWriter::Logic_CreateFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> typeConverter, object value, class System.Xaml.XamlMember property, string targetName)
0x4066  stloc.3
0x4067  ldarg.1
0x4068  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x406d  ldarg.1
0x406e  ldloc.3
0x406f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x4074  ldarg.1
0x4075  ldc.i4.1
0x4076  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentIsTypeConvertedObject(bool value)
0x407b  ldloc.3
0x407c  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x4081  brtrue.s loc_40A2
0x4083  ldloc.0
0x4084  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x4089  brtrue.s loc_4093
0x408b  ldloc.0
0x408c  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x4091  brfalse.s loc_409A
0x4093  ldarg.1
0x4094  ldloc.3
0x4095  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentCollection(object value)
0x409a  ldarg.0
0x409b  ldarg.1
0x409c  ldc.i4.1
0x409d  call     instance void System.Xaml.XamlObjectWriter::Logic_ApplyCurrentPreconstructionPropertyValues(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, bool skipDirectives)
0x40a2  ret
```
