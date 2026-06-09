# System.Xaml.XamlObjectWriter::Logic_ApplyPropertyValue

- ea: `0x45b0`
- end: `0x470a`
- name: `System.Xaml.XamlObjectWriter::Logic_ApplyPropertyValue`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: ``

## callers

- `0x44e0`
- `0x4c50`

## callees

- `0x2870`
- `0x40b0`
- `0x4470`
- `0x45b0`
- `0x4710`
- `0x4f50`
- `0x4f90`
- `0x5030`
- `0x5050`
- `0x8af0`
- `0x8b40`
- `0x8b70`
- `0x8bf0`
- `0xa4c0`
- `0xa590`
- `0xa5d0`
- `0xa6e0`
- `0xb280`
- `0xb2f0`
- `0xd1b0`
- `0xd500`
- `0x1ca30`
- `0x202d0`
- `0x202e0`
- `0x215d0`
- `0x21610`
- `0x216d0`
- `0x21710`
- `0x21a30`
- `0x21a40`

## pseudocode

```c

```

## disassembly

```asm
0x45b0  ldarg.s  4
0x45b2  brtrue.s loc_45BC
0x45b4  ldarg.1
0x45b5  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x45ba  br.s     loc_45C2
0x45bc  ldarg.1
0x45bd  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x45c2  stloc.0
0x45c3  ldarg.3
0x45c4  isinst   System.Windows.Markup.XData
0x45c9  brfalse.s loc_45F6
0x45cb  ldarg.3
0x45cc  isinst   System.Windows.Markup.XData
0x45d1  stloc.1
0x45d2  ldarg.2
0x45d3  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x45d8  callvirt instance bool System.Xaml.XamlType::get_IsXData()
0x45dd  brfalse.s loc_45EE
0x45df  ldarg.0
0x45e0  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x45e5  ldloc.0
0x45e6  ldarg.2
0x45e7  ldloc.1
0x45e8  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::SetXmlInstance(object inst, class System.Xaml.XamlMember property, class System.Windows.Markup.XData xData)
0x45ed  ret
0x45ee  ldloc.1
0x45ef  callvirt instance string System.Windows.Markup.XData::get_Text()
0x45f4  starg.s  3
0x45f6  ldarg.0
0x45f7  ldloc.0
0x45f8  ldarg.2
0x45f9  ldarg.3
0x45fa  call     instance void System.Xaml.XamlObjectWriter::SetValue(object inst, class System.Xaml.XamlMember property, object value)
0x45ff  ldarg.2
0x4600  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x4605  brfalse  loc_4709
0x460a  ldarg.s  4
0x460c  brtrue.s loc_4616
0x460e  ldarg.1
0x460f  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x4614  br.s     loc_461C
0x4616  ldarg.1
0x4617  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x461c  stloc.2
0x461d  ldloc.2
0x461e  ldarg.2
0x461f  isinst   System.Xaml.XamlDirective
0x4624  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetAliasedProperty(class System.Xaml.XamlDirective directive)
0x4629  stloc.3
0x462a  ldarg.2
0x462b  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4630  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4635  brfalse.s loc_466B
0x4637  ldloc.3
0x4638  ldnull
0x4639  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x463e  brfalse.s loc_466B
0x4640  ldarg.0
0x4641  ldarg.1
0x4642  ldloc.3
0x4643  ldarg.s  4
0x4645  call     instance void System.Xaml.XamlObjectWriter::Logic_DuplicatePropertyCheck(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlMember property, bool onParent)
0x464a  ldarg.0
0x464b  ldarg.1
0x464c  ldloc.3
0x464d  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlMember::get_TypeConverter()
0x4652  ldarg.3
0x4653  ldloc.3
0x4654  ldloc.3
0x4655  callvirt instance string System.Xaml.XamlMember::get_Name()
0x465a  call     instance object System.Xaml.XamlObjectWriter::Logic_CreateFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> typeConverter, object value, class System.Xaml.XamlMember property, string targetName)
0x465f  stloc.s  4
0x4661  ldarg.0
0x4662  ldloc.0
0x4663  ldloc.3
0x4664  ldloc.s  4
0x4666  call     instance void System.Xaml.XamlObjectWriter::SetValue(object inst, class System.Xaml.XamlMember property, object value)
0x466b  ldarg.2
0x466c  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Name()
0x4671  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4676  brfalse.s loc_469D
0x4678  ldloc.0
0x4679  ldarg.1
0x467a  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x467f  bne.un.s loc_468F
0x4681  ldarg.0
0x4682  ldarg.1
0x4683  ldarg.3
0x4684  castclass [mscorlib]System.String
0x4689  call     instance void System.Xaml.XamlObjectWriter::Logic_RegisterName_OnCurrent(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string name)
0x468e  ret
0x468f  ldarg.0
0x4690  ldarg.1
0x4691  ldarg.3
0x4692  castclass [mscorlib]System.String
0x4697  call     instance void System.Xaml.XamlObjectWriter::Logic_RegisterName_OnParent(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string name)
0x469c  ret
0x469d  ldarg.2
0x469e  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_ConnectionId()
0x46a3  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x46a8  brfalse.s loc_46B9
0x46aa  ldarg.0
0x46ab  ldarg.1
0x46ac  ldarg.3
0x46ad  unbox.any [mscorlib]System.Int32
0x46b2  ldloc.0
0x46b3  call     instance void System.Xaml.XamlObjectWriter::Logic_SetConnectionId(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, int32 connectionId, object instance)
0x46b8  ret
0x46b9  ldarg.2
0x46ba  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Base()
0x46bf  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x46c4  brfalse.s loc_4709
0x46c6  ldarg.0
0x46c7  ldarg.1
0x46c8  ldarg.3
0x46c9  castclass [mscorlib]System.String
0x46ce  call     instance void System.Xaml.XamlObjectWriter::Logic_CheckBaseUri(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string value)
0x46d3  ldarg.1
0x46d4  ldarg.3
0x46d5  castclass [mscorlib]System.String
0x46da  newobj   instance void [System]System.Uri::.ctor(string)
0x46df  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_BaseUri(class [System]System.Uri value)
0x46e4  ldarg.1
0x46e5  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x46ea  brfalse.s loc_4709
0x46ec  ldarg.0
0x46ed  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x46f2  ldarg.1
0x46f3  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x46f8  ldarg.1
0x46f9  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x46fe  ldarg.1
0x46ff  callvirt instance class [System]System.Uri MS.Internal.Xaml.Context.ObjectWriterContext::get_BaseUri()
0x4704  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::SetUriBase(class System.Xaml.XamlType xamlType, object obj, class [System]System.Uri baseUri)
0x4709  ret
```
