# System.Xaml.XamlObjectWriter::Logic_CreatePropertyValueFromValue

- ea: `0x4110`
- end: `0x429a`
- name: `System.Xaml.XamlObjectWriter::Logic_CreatePropertyValueFromValue`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: ``

## callers

- `0x33d0`
- `0x4a40`

## callees

- `0x10`
- `0x2870`
- `0x40b0`
- `0x4110`
- `0x8b40`
- `0xa3f0`
- `0xa440`
- `0xa4c0`
- `0xa590`
- `0xa5d0`
- `0xa630`
- `0xa6c0`
- `0xa6e0`
- `0xb280`
- `0xb2f0`
- `0xd130`
- `0xd1e0`
- `0xd310`
- `0xd800`
- `0xefa0`
- `0x15ca0`
- `0x1baf0`
- `0x1bba0`
- `0x1bc70`
- `0x20280`
- `0x21220`
- `0x21610`
- `0x21630`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x21710`

## pseudocode

```c

```

## disassembly

```asm
0x4110  ldarg.1
0x4111  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x4116  stloc.0
0x4117  ldloc.0
0x4118  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x411d  stloc.1
0x411e  ldarg.1
0x411f  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4124  stloc.2
0x4125  ldloc.2
0x4126  isinst   System.Xaml.XamlReader
0x412b  stloc.3
0x412c  ldloc.3
0x412d  brfalse.s loc_415D
0x412f  ldloc.0
0x4130  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class System.Xaml.XamlDeferringLoader> System.Xaml.XamlMember::get_DeferringLoader()
0x4135  stloc.s  7
0x4137  ldloc.s  7
0x4139  ldnull
0x413a  call     bool class System.Xaml.Schema.XamlValueConverter`1<class System.Xaml.XamlDeferringLoader>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x413f  brfalse.s loc_415D
0x4141  ldarg.1
0x4142  ldarg.0
0x4143  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4148  ldarg.1
0x4149  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x414e  ldloc.s  7
0x4150  ldloc.3
0x4151  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::DeferredLoad(class MS.Internal.Xaml.ServiceProviderContext serviceContext, class System.Xaml.Schema.XamlValueConverter`1<class System.Xaml.XamlDeferringLoader> deferringLoader, class System.Xaml.XamlReader deferredContent)
0x4156  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x415b  ldc.i4.1
0x415c  ret
0x415d  ldloc.0
0x415e  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlMember::get_TypeConverter()
0x4163  stloc.s  4
0x4165  ldnull
0x4166  stloc.s  5
0x4168  ldnull
0x4169  stloc.s  6
0x416b  ldloc.0
0x416c  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x4171  brfalse.s loc_417D
0x4173  ldloc.0
0x4174  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x4179  stloc.s  6
0x417b  br.s     loc_4185
0x417d  ldarg.1
0x417e  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4183  stloc.s  6
0x4185  ldloc.0
0x4186  ldnull
0x4187  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x418c  brfalse  loc_426E
0x4191  ldloc.0
0x4192  callvirt instance bool System.Xaml.XamlMember::get_IsUnknown()
0x4197  brtrue   loc_426E
0x419c  ldloc.s  6
0x419e  ldnull
0x419f  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x41a4  brfalse  loc_426E
0x41a9  ldarg.1
0x41aa  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentType()
0x41af  stloc.s  8
0x41b1  ldloc.0
0x41b2  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x41b7  brfalse.s loc_41E7
0x41b9  ldloc.0
0x41ba  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x41bf  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x41c4  brfalse.s loc_41E7
0x41c6  ldloc.s  8
0x41c8  ldnull
0x41c9  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x41ce  brfalse.s loc_41E7
0x41d0  ldloc.s  8
0x41d2  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x41d7  brfalse.s loc_41E7
0x41d9  ldloc.s  8
0x41db  callvirt instance class System.Xaml.XamlType System.Xaml.XamlType::get_KeyType()
0x41e0  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlType::get_TypeConverter()
0x41e5  stloc.s  4
0x41e7  ldloc.s  4
0x41e9  ldnull
0x41ea  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x41ef  brfalse.s loc_426E
0x41f1  ldloc.s  4
0x41f3  callvirt instance class [mscorlib]System.Type class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::get_ConverterType()
0x41f8  ldnull
0x41f9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x41fe  brfalse.s loc_426E
0x4200  ldloc.s  4
0x4202  call     class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.Schema.BuiltInValueConverter::get_String()
0x4207  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x420c  brfalse.s loc_426E
0x420e  ldarg.0
0x420f  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4214  ldloc.s  4
0x4216  callvirt T0x2B000003
0x421b  stloc.s  9
0x421d  ldloc.s  9
0x421f  brfalse.s loc_426E
0x4221  ldloc.s  6
0x4223  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetTypeConverterEventArgs> System.Xaml.XamlType::get_SetTypeConverterHandler()
0x4228  brfalse.s loc_426E
0x422a  ldloc.0
0x422b  ldloc.s  9
0x422d  ldloc.2
0x422e  ldarg.1
0x422f  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x4234  call     class [mscorlib]System.Globalization.CultureInfo System.Xaml.TypeConverterHelper::get_InvariantEnglishUS()
0x4239  ldarg.1
0x423a  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x423f  newobj   instance void System.Windows.Markup.XamlSetTypeConverterEventArgs::.ctor(class System.Xaml.XamlMember member, class [System]System.ComponentModel.TypeConverter typeConverter, object value, class [System]System.ComponentModel.ITypeDescriptorContext serviceProvider, class [mscorlib]System.Globalization.CultureInfo cultureInfo, object targetObject)
0x4244  stloc.s  0xA
0x4246  ldloc.s  0xA
0x4248  ldloc.s  6
0x424a  callvirt instance void System.Windows.Markup.XamlSetTypeConverterEventArgs::set_CurrentType(class System.Xaml.XamlType value)
0x424f  ldloc.s  6
0x4251  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetTypeConverterEventArgs> System.Xaml.XamlType::get_SetTypeConverterHandler()
0x4256  ldarg.1
0x4257  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x425c  ldloc.s  0xA
0x425e  callvirt instance void class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetTypeConverterEventArgs>::Invoke(object, var<u1>)
0x4263  ldloc.s  0xA
0x4265  callvirt instance bool System.Windows.Markup.XamlSetValueEventArgs::get_Handled()
0x426a  brfalse.s loc_426E
0x426c  ldc.i4.0
0x426d  ret
0x426e  ldloc.s  4
0x4270  ldnull
0x4271  call     bool class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter>::op_Inequality(class System.Xaml.Schema.XamlValueConverter`1<var<u1>>, !!T0)
0x4276  brfalse.s loc_428D
0x4278  ldarg.0
0x4279  ldarg.1
0x427a  ldloc.s  4
0x427c  ldloc.2
0x427d  ldloc.0
0x427e  ldloc.0
0x427f  callvirt instance string System.Xaml.XamlMember::get_Name()
0x4284  call     instance object System.Xaml.XamlObjectWriter::Logic_CreateFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> typeConverter, object value, class System.Xaml.XamlMember property, string targetName)
0x4289  stloc.s  5
0x428b  br.s     loc_4290
0x428d  ldloc.2
0x428e  stloc.s  5
0x4290  ldarg.1
0x4291  ldloc.s  5
0x4293  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x4298  ldc.i4.1
0x4299  ret
```
