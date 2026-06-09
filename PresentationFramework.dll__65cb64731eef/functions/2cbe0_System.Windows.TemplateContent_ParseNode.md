# System.Windows.TemplateContent::ParseNode

- ea: `0x2cbe0`
- end: `0x2d67b`
- name: `System.Windows.TemplateContent::ParseNode`
- size: `2715`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: ``

## callers

- `0x2cb30`

## callees

- `0x16de0`
- `0x170d0`
- `0x17260`
- `0x1c370`
- `0x1c3f0`
- `0x1c720`
- `0x2ca90`
- `0x2cbe0`
- `0x2d680`
- `0x2d6f0`
- `0x2de50`
- `0x2dea0`
- `0x2e060`
- `0x2e110`
- `0x2e120`
- `0x2e150`
- `0x2e1f0`
- `0x2e290`
- `0x2e2d0`
- `0x2e2e0`
- `0x2e310`
- `0x2e330`
- `0x93ba0`
- `0x252660`
- `0x252680`
- `0x252690`
- `0x2526a0`
- `0x2526b0`
- `0x2526c0`
- `0x2526d0`
- `0x2526e0`
- `0x252700`
- `0x252740`
- `0x252750`
- `0x252760`
- `0x252770`
- `0x252780`
- `0x252790`
- `0x2527a0`
- `0x2527b0`
- `0x2527c0`
- `0x2527d0`
- `0x2527e0`
- `0x2527f0`
- `0x252800`
- `0x252810`
- `0x252990`
- `0x252aa0`
- `0x252ba0`

## string_xrefs

- `0x2d1d7`: `ContentTemplate`
- `0x2d1fc`: `ContentTemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x2cbe0  ldarg.s  5
0x2cbe2  ldsfld   object [WindowsBase]System.Windows.DependencyProperty::UnsetValue
0x2cbe7  stind.ref
0x2cbe8  ldarg.1
0x2cbe9  callvirt instance valuetype [System.Xaml]System.Xaml.XamlNodeType [System.Xaml]System.Xaml.XamlReader::get_NodeType()
0x2cbee  stloc.2
0x2cbef  ldloc.2
0x2cbf0  switch   loc_2D679, loc_2CC1A, loc_2CD74, loc_2CE8F, loc_2D0EB, loc_2D392, loc_2D3A3, loc_2D588
0x2cc15  br       loc_2D679
0x2cc1a  ldarg.1
0x2cc1b  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlReader::get_Type()
0x2cc20  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2cc25  ldtoken  System.Windows.StaticResourceExtension
0x2cc2a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cc2f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2cc34  brfalse.s loc_2CC63
0x2cc36  ldarg.0
0x2cc37  call     instance class System.Windows.TemplateLoadData System.Windows.TemplateContent::get_TemplateLoadData()
0x2cc3c  callvirt instance class [System.Xaml]System.Xaml.XamlObjectWriter System.Windows.TemplateLoadData::get_ObjectWriter()
0x2cc41  stloc.3
0x2cc42  ldloc.3
0x2cc43  callvirt instance void [System.Xaml]System.Xaml.XamlObjectWriter::Clear()
0x2cc48  ldarg.0
0x2cc49  ldloc.3
0x2cc4a  ldarg.2
0x2cc4b  callvirt instance class [WindowsBase]MS.Utility.FrugalObjectList`1<class [System.Xaml]System.Xaml.NamespaceDeclaration> StackOfFrames::get_InScopeNamespaces()
0x2cc50  ldnull
0x2cc51  call     instance void System.Windows.TemplateContent::WriteNamespaces(class [System.Xaml]System.Xaml.XamlWriter writer, class [WindowsBase]MS.Utility.FrugalObjectList`1<class [System.Xaml]System.Xaml.NamespaceDeclaration> previousNamespaces, class [WindowsBase]MS.Utility.FrugalObjectList`1<class [System.Xaml]System.Xaml.NamespaceDeclaration> localNamespaces)
0x2cc56  ldarg.s  5
0x2cc58  ldarg.0
0x2cc59  ldarg.1
0x2cc5a  ldloc.3
0x2cc5b  call     instance class System.Windows.StaticResourceExtension System.Windows.TemplateContent::LoadTimeBindUnshareableStaticResource(class [System.Xaml]System.Xaml.XamlReader xamlReader, class [System.Xaml]System.Xaml.XamlObjectWriter writer)
0x2cc60  stind.ref
0x2cc61  ldc.i4.1
0x2cc62  ret
0x2cc63  ldarg.2
0x2cc64  callvirt instance int32 class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_Depth()
0x2cc69  ldc.i4.0
0x2cc6a  ble      loc_2CD48
0x2cc6f  ldarg.2
0x2cc70  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cc75  callvirt instance bool Frame::get_NameSet()
0x2cc7a  brtrue   loc_2CD48
0x2cc7f  ldarg.2
0x2cc80  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cc85  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cc8a  ldnull
0x2cc8b  call     bool [System.Xaml]System.Xaml.XamlType::op_Inequality(class [System.Xaml]System.Xaml.XamlType, class [System.Xaml]System.Xaml.XamlType)
0x2cc90  brfalse  loc_2CD48
0x2cc95  ldarg.2
0x2cc96  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cc9b  callvirt instance bool Frame::get_IsInNameScope()
0x2cca0  brtrue   loc_2CD48
0x2cca5  ldarg.2
0x2cca6  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ccab  callvirt instance bool Frame::get_IsInStyleOrTemplate()
0x2ccb0  brtrue   loc_2CD48
0x2ccb5  ldtoken  System.Windows.FrameworkElement
0x2ccba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ccbf  ldarg.2
0x2ccc0  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ccc5  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2ccca  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2cccf  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2ccd4  brtrue.s loc_2CCF7
0x2ccd6  ldtoken  System.Windows.FrameworkContentElement
0x2ccdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cce0  ldarg.2
0x2cce1  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cce6  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cceb  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2ccf0  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2ccf5  brfalse.s loc_2CD3C
0x2ccf7  ldarg.s  4
0x2ccf9  ldarg.s  4
0x2ccfb  ldind.i4
0x2ccfc  stloc.s  5
0x2ccfe  ldloc.s  5
0x2cd00  ldc.i4.1
0x2cd01  add
0x2cd02  stind.i4
0x2cd03  ldloca.s 5
0x2cd05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2cd0a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2cd0f  ldstr    aT// "_T"
0x2cd14  call     string [mscorlib]System.String::Concat(string, string)
0x2cd19  stloc.s  4
0x2cd1b  ldarg.0
0x2cd1c  ldloc.s  4
0x2cd1e  ldarg.3
0x2cd1f  ldarg.2
0x2cd20  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cd25  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cd2a  call     instance void System.Windows.TemplateContent::UpdateSharedPropertyNames(string name, class [mscorlib]System.Collections.Generic.List`1<valuetype System.Windows.PropertyValue> sharedProperties, class [System.Xaml]System.Xaml.XamlType type)
0x2cd2f  ldarg.2
0x2cd30  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cd35  ldloc.s  4
0x2cd37  callvirt instance void Frame::set_Name(string value)
0x2cd3c  ldarg.2
0x2cd3d  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cd42  ldc.i4.1
0x2cd43  callvirt instance void Frame::set_NameSet(bool value)
0x2cd48  ldarg.0
0x2cd49  call     instance class [System.Xaml]System.Xaml.XamlType System.Windows.TemplateContent::get_RootType()
0x2cd4e  ldnull
0x2cd4f  call     bool [System.Xaml]System.Xaml.XamlType::op_Equality(class [System.Xaml]System.Xaml.XamlType, class [System.Xaml]System.Xaml.XamlType)
0x2cd54  brfalse.s loc_2CD62
0x2cd56  ldarg.0
0x2cd57  ldarg.1
0x2cd58  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlReader::get_Type()
0x2cd5d  call     instance void System.Windows.TemplateContent::set_RootType(class [System.Xaml]System.Xaml.XamlType value)
0x2cd62  ldarg.2
0x2cd63  ldarg.1
0x2cd64  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlReader::get_Type()
0x2cd69  ldnull
0x2cd6a  callvirt instance void StackOfFrames::Push(class [System.Xaml]System.Xaml.XamlType xamlType, string name)
0x2cd6f  br       loc_2D679
0x2cd74  ldarg.2
0x2cd75  callvirt instance int32 class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_Depth()
0x2cd7a  ldc.i4.0
0x2cd7b  ble      loc_2CE59
0x2cd80  ldarg.2
0x2cd81  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cd86  callvirt instance bool Frame::get_NameSet()
0x2cd8b  brtrue   loc_2CE59
0x2cd90  ldarg.2
0x2cd91  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cd96  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cd9b  ldnull
0x2cd9c  call     bool [System.Xaml]System.Xaml.XamlType::op_Inequality(class [System.Xaml]System.Xaml.XamlType, class [System.Xaml]System.Xaml.XamlType)
0x2cda1  brfalse  loc_2CE59
0x2cda6  ldarg.2
0x2cda7  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cdac  callvirt instance bool Frame::get_IsInNameScope()
0x2cdb1  brtrue   loc_2CE59
0x2cdb6  ldarg.2
0x2cdb7  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cdbc  callvirt instance bool Frame::get_IsInStyleOrTemplate()
0x2cdc1  brtrue   loc_2CE59
0x2cdc6  ldtoken  System.Windows.FrameworkElement
0x2cdcb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cdd0  ldarg.2
0x2cdd1  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cdd6  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cddb  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2cde0  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2cde5  brtrue.s loc_2CE08
0x2cde7  ldtoken  System.Windows.FrameworkContentElement
0x2cdec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cdf1  ldarg.2
0x2cdf2  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cdf7  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cdfc  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2ce01  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2ce06  brfalse.s loc_2CE4D
0x2ce08  ldarg.s  4
0x2ce0a  ldarg.s  4
0x2ce0c  ldind.i4
0x2ce0d  stloc.s  5
0x2ce0f  ldloc.s  5
0x2ce11  ldc.i4.1
0x2ce12  add
0x2ce13  stind.i4
0x2ce14  ldloca.s 5
0x2ce16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ce1b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2ce20  ldstr    aT// "_T"
0x2ce25  call     string [mscorlib]System.String::Concat(string, string)
0x2ce2a  stloc.s  7
0x2ce2c  ldarg.0
0x2ce2d  ldloc.s  7
0x2ce2f  ldarg.3
0x2ce30  ldarg.2
0x2ce31  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ce36  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2ce3b  call     instance void System.Windows.TemplateContent::UpdateSharedPropertyNames(string name, class [mscorlib]System.Collections.Generic.List`1<valuetype System.Windows.PropertyValue> sharedProperties, class [System.Xaml]System.Xaml.XamlType type)
0x2ce40  ldarg.2
0x2ce41  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ce46  ldloc.s  7
0x2ce48  callvirt instance void Frame::set_Name(string value)
0x2ce4d  ldarg.2
0x2ce4e  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ce53  ldc.i4.1
0x2ce54  callvirt instance void Frame::set_NameSet(bool value)
0x2ce59  ldarg.2
0x2ce5a  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ce5f  callvirt instance class [System.Xaml]System.Xaml.XamlMember Frame::get_Property()
0x2ce64  callvirt instance class [System.Xaml]System.Xaml.XamlType [System.Xaml]System.Xaml.XamlMember::get_Type()
0x2ce69  stloc.s  6
0x2ce6b  ldarg.0
0x2ce6c  call     instance class [System.Xaml]System.Xaml.XamlType System.Windows.TemplateContent::get_RootType()
0x2ce71  ldnull
0x2ce72  call     bool [System.Xaml]System.Xaml.XamlType::op_Equality(class [System.Xaml]System.Xaml.XamlType, class [System.Xaml]System.Xaml.XamlType)
0x2ce77  brfalse.s loc_2CE81
0x2ce79  ldarg.0
0x2ce7a  ldloc.s  6
0x2ce7c  call     instance void System.Windows.TemplateContent::set_RootType(class [System.Xaml]System.Xaml.XamlType value)
0x2ce81  ldarg.2
0x2ce82  ldloc.s  6
0x2ce84  ldnull
0x2ce85  callvirt instance void StackOfFrames::Push(class [System.Xaml]System.Xaml.XamlType xamlType, string name)
0x2ce8a  br       loc_2D679
0x2ce8f  ldarg.2
0x2ce90  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ce95  callvirt instance bool Frame::get_IsInStyleOrTemplate()
0x2ce9a  brtrue   loc_2D0E0
0x2ce9f  ldarg.2
0x2cea0  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cea5  callvirt instance bool Frame::get_NameSet()
0x2ceaa  brtrue   loc_2CF52
0x2ceaf  ldarg.2
0x2ceb0  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2ceb5  callvirt instance bool Frame::get_IsInNameScope()
0x2ceba  brtrue   loc_2CF52
0x2cebf  ldtoken  System.Windows.FrameworkElement
0x2cec4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cec9  ldarg.2
0x2ceca  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cecf  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2ced4  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2ced9  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2cede  brtrue.s loc_2CF01
0x2cee0  ldtoken  System.Windows.FrameworkContentElement
0x2cee5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ceea  ldarg.2
0x2ceeb  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cef0  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cef5  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2cefa  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2ceff  brfalse.s loc_2CF46
0x2cf01  ldarg.s  4
0x2cf03  ldarg.s  4
0x2cf05  ldind.i4
0x2cf06  stloc.s  5
0x2cf08  ldloc.s  5
0x2cf0a  ldc.i4.1
0x2cf0b  add
0x2cf0c  stind.i4
0x2cf0d  ldloca.s 5
0x2cf0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2cf14  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2cf19  ldstr    aT// "_T"
0x2cf1e  call     string [mscorlib]System.String::Concat(string, string)
0x2cf23  stloc.s  8
0x2cf25  ldarg.0
0x2cf26  ldloc.s  8
0x2cf28  ldarg.3
0x2cf29  ldarg.2
0x2cf2a  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cf2f  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cf34  call     instance void System.Windows.TemplateContent::UpdateSharedPropertyNames(string name, class [mscorlib]System.Collections.Generic.List`1<valuetype System.Windows.PropertyValue> sharedProperties, class [System.Xaml]System.Xaml.XamlType type)
0x2cf39  ldarg.2
0x2cf3a  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cf3f  ldloc.s  8
0x2cf41  callvirt instance void Frame::set_Name(string value)
0x2cf46  ldarg.2
0x2cf47  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cf4c  ldc.i4.1
0x2cf4d  callvirt instance void Frame::set_NameSet(bool value)
0x2cf52  ldarg.0
0x2cf53  call     instance class System.Windows.TemplateLoadData System.Windows.TemplateContent::get_TemplateLoadData()
0x2cf58  callvirt instance string System.Windows.TemplateLoadData::get_RootName()
0x2cf5d  brtrue.s loc_2CF7E
0x2cf5f  ldarg.2
0x2cf60  callvirt instance int32 class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_Depth()
0x2cf65  ldc.i4.1
0x2cf66  bne.un.s loc_2CF7E
0x2cf68  ldarg.0
0x2cf69  call     instance class System.Windows.TemplateLoadData System.Windows.TemplateContent::get_TemplateLoadData()
0x2cf6e  ldarg.2
0x2cf6f  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cf74  callvirt instance string Frame::get_Name()
0x2cf79  callvirt instance void System.Windows.TemplateLoadData::set_RootName(string value)
0x2cf7e  ldtoken  System.Windows.Controls.ContentPresenter
0x2cf83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cf88  ldarg.2
0x2cf89  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cf8e  callvirt instance class [System.Xaml]System.Xaml.XamlType Frame::get_Type()
0x2cf93  callvirt instance class [mscorlib]System.Type [System.Xaml]System.Xaml.XamlType::get_UnderlyingType()
0x2cf98  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2cf9d  brfalse  loc_2D041
0x2cfa2  ldarg.0
0x2cfa3  call     instance class System.Windows.FrameworkTemplate System.Windows.TemplateContent::get_OwnerTemplate()
0x2cfa8  callvirt instance class [mscorlib]System.Type System.Windows.FrameworkTemplate::get_TargetTypeInternal()
0x2cfad  ldarg.2
0x2cfae  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cfb3  callvirt instance string Frame::get_ContentSource()
0x2cfb8  ldarg.2
0x2cfb9  callvirt instance var<u1> class MS.Internal.Xaml.Context.XamlContextStack`1<class Frame>::get_CurrentFrame()
0x2cfbe  callvirt instance string Frame::get_Name()
0x2cfc3  ldarg.0
0x2cfc4  call     instance class System.Windows.FrameworkTemplate System.Windows.TemplateContent::get_OwnerTemplate()
0x2cfc9  ldflda   valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord> System.Windows.FrameworkTemplate::ChildRecordFromChildIndex
0x2cfce  ldarg.0
0x2cfcf  call     instance class System.Windows.FrameworkTemplate System.Windows.TemplateContent::get_OwnerTemplate()
0x2cfd4  ldflda   valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>> System.Windows.FrameworkTemplate::TriggerSourceRecordFromChildIndex
0x2cfd9  ldarg.0
0x2cfda  call     instance class System.Windows.FrameworkTemplate System.Windows.TemplateContent::get_OwnerTemplate()
0x2cfdf  ldflda   valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent> System.Windows.FrameworkTemplate::ResourceDependents
  ... truncated ...
```
