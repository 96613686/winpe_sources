# System.Xaml.XamlObjectWriter::ProcessNameFixup_Reparse

- ea: `0x5790`
- end: `0x5946`
- name: `System.Xaml.XamlObjectWriter::ProcessNameFixup_Reparse`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `reparse_path`

## callers

- `0x56d0`

## callees

- `0x2870`
- `0x3fe0`
- `0x40c0`
- `0x4770`
- `0x4c50`
- `0x4f50`
- `0x5790`
- `0x5950`
- `0x59c0`
- `0x8b20`
- `0x8b40`
- `0xa4c0`
- `0xa5d0`
- `0xb280`
- `0xb2f0`
- `0x20370`
- `0x20480`
- `0x20a20`
- `0x20c10`
- `0x20c30`
- `0x20c40`
- `0x20c50`
- `0x20c60`
- `0x20c70`
- `0x20c80`
- `0x20cb0`
- `0x20fe0`
- `0x21000`
- `0x21220`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x219b0`

## pseudocode

```c

```

## disassembly

```asm
0x5790  ldnull
0x5791  stloc.0
0x5792  ldarg.1
0x5793  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5798  stloc.1
0x5799  ldloc.1
0x579a  ldarg.2
0x579b  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_NameResolutionComplete(bool value)
0x57a0  ldloc.1
0x57a1  ldarg.0
0x57a2  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_IsInitializedCallback(class MS.Internal.Xaml.Context.ICheckIfInitialized value)
0x57a7  ldarg.1
0x57a8  callvirt instance valuetype MS.Internal.Xaml.Context.FixupType MS.Internal.Xaml.Context.NameFixupToken::get_FixupType()
0x57ad  stloc.s  4
0x57af  ldloc.s  4
0x57b1  switch   loc_57CB, loc_57DA, loc_5800, loc_5839
0x57c6  br       loc_5864
0x57cb  ldarg.0
0x57cc  ldloc.1
0x57cd  call     instance bool System.Xaml.XamlObjectWriter::Logic_ProvideValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x57d2  stloc.3
0x57d3  ldloc.3
0x57d4  brfalse  loc_5864
0x57d9  ret
0x57da  ldarg.0
0x57db  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x57e0  ldloc.1
0x57e1  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x57e6  castclass System.Windows.Markup.MarkupExtension
0x57eb  ldloc.1
0x57ec  callvirt instance class MS.Internal.Xaml.ServiceProviderContext MS.Internal.Xaml.Context.ObjectWriterContext::get_ServiceProviderContext()
0x57f1  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::CallProvideValue(class System.Windows.Markup.MarkupExtension me, class [mscorlib]System.IServiceProvider serviceProvider)
0x57f6  stloc.0
0x57f7  ldloc.1
0x57f8  ldloc.0
0x57f9  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x57fe  br.s     loc_5864
0x5800  ldarg.0
0x5801  ldloc.1
0x5802  ldloc.1
0x5803  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x5808  callvirt instance class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> System.Xaml.XamlMember::get_TypeConverter()
0x580d  ldloc.1
0x580e  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x5813  ldloc.1
0x5814  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x5819  ldloc.1
0x581a  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x581f  callvirt instance string System.Xaml.XamlMember::get_Name()
0x5824  ldarg.1
0x5825  call     instance object System.Xaml.XamlObjectWriter::Logic_CreateFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.Schema.XamlValueConverter`1<class [System]System.ComponentModel.TypeConverter> typeConverter, object value, class System.Xaml.XamlMember property, string targetName, class MS.Internal.Xaml.Runtime.IAddLineInfo lineInfo)
0x582a  stloc.0
0x582b  ldarg.1
0x582c  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5831  ldloc.0
0x5832  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x5837  br.s     loc_5864
0x5839  ldarg.0
0x583a  ldloc.1
0x583b  call     instance void System.Xaml.XamlObjectWriter::Logic_CreateFromInitializationValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x5840  ldarg.1
0x5841  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5846  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x584b  brfalse.s loc_5864
0x584d  ldarg.0
0x584e  ldarg.1
0x584f  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x5854  ldarg.1
0x5855  callvirt instance class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.Context.NameFixupToken::get_TargetContext()
0x585a  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x585f  call     instance void System.Xaml.XamlObjectWriter::Logic_RegisterName_OnCurrent(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, string name)
0x5864  ldarg.1
0x5865  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x586a  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.FixupTarget::get_Property()
0x586f  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x5874  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x5879  brfalse.s loc_588A
0x587b  ldarg.0
0x587c  ldarg.1
0x587d  ldloc.1
0x587e  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x5883  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup_UpdatePendingAddKey(class MS.Internal.Xaml.Context.NameFixupToken token, object key)
0x5888  br.s     loc_58D8
0x588a  ldarg.1
0x588b  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5890  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.FixupTarget::get_Property()
0x5895  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x589a  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x589f  brfalse.s loc_58B0
0x58a1  ldarg.0
0x58a2  ldarg.1
0x58a3  ldloc.1
0x58a4  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x58a9  call     instance void System.Xaml.XamlObjectWriter::ProcessNameFixup_UpdatePendingAddItem(class MS.Internal.Xaml.Context.NameFixupToken token, object item)
0x58ae  br.s     loc_58D8
0x58b0  ldarg.1
0x58b1  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x58b6  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.FixupTarget::get_Property()
0x58bb  ldnull
0x58bc  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x58c1  brfalse.s loc_58CC
0x58c3  ldarg.0
0x58c4  ldloc.1
0x58c5  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentProperty(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x58ca  br.s     loc_58D8
0x58cc  ldarg.0
0x58cd  ldloc.1
0x58ce  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x58d3  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x58d8  ldloc.1
0x58d9  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x58de  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x58e3  stloc.2
0x58e4  ldloc.2
0x58e5  brfalse.s loc_5945
0x58e7  ldloc.2
0x58e8  ldarg.1
0x58e9  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x58ee  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_Target(class MS.Internal.Xaml.Context.FixupTarget value)
0x58f3  ldloc.2
0x58f4  ldarg.1
0x58f5  callvirt instance int32 MS.Internal.Xaml.Context.NameFixupToken::get_LineNumber()
0x58fa  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_LineNumber(int32 value)
0x58ff  ldloc.2
0x5900  ldarg.1
0x5901  callvirt instance int32 MS.Internal.Xaml.Context.NameFixupToken::get_LinePosition()
0x5906  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_LinePosition(int32 value)
0x590b  ldarg.1
0x590c  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5911  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.FixupTarget::get_Property()
0x5916  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x591b  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x5920  brtrue.s loc_5939
0x5922  ldarg.1
0x5923  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x5928  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.FixupTarget::get_Property()
0x592d  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x5932  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x5937  brfalse.s loc_5945
0x5939  ldarg.0
0x593a  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x593f  ldloc.2
0x5940  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::AddDependency(class MS.Internal.Xaml.Context.NameFixupToken fixupToken)
0x5945  ret
```
