# System.Xaml.XamlObjectWriter::WriteEndObject

- ea: `0x2ca0`
- end: `0x30b9`
- name: `System.Xaml.XamlObjectWriter::WriteEndObject`
- size: `1049`
- prototype: ``
- caller_count: `0`
- callee_count: `50`
- tags: ``

## callees

- `0x1630`
- `0x19c0`
- `0x19d0`
- `0x19e0`
- `0x2780`
- `0x2810`
- `0x2ca0`
- `0x3a60`
- `0x3c80`
- `0x43e0`
- `0x4410`
- `0x4740`
- `0x4c50`
- `0x5170`
- `0x5280`
- `0x5500`
- `0x5a20`
- `0x7580`
- `0x8590`
- `0x8620`
- `0xb2f0`
- `0xd150`
- `0xef20`
- `0xf360`
- `0x11f20`
- `0x11f50`
- `0x20720`
- `0x20bf0`
- `0x20c10`
- `0x20ce0`
- `0x21200`
- `0x21540`
- `0x21590`
- `0x215c0`
- `0x215d0`
- `0x21610`
- `0x21650`
- `0x21690`
- `0x216d0`
- `0x216f0`
- `0x217b0`
- `0x217f0`
- `0x21890`
- `0x219b0`
- `0x219d0`
- `0x21a50`
- `0x21a70`
- `0x21b50`
- `0x221d0`
- `0x225c0`

## string_xrefs

- `0x2d61`: `OpenPropertyInCurrentFrame_EO`

## pseudocode

```c

```

## disassembly

```asm
0x2ca0  ldarg.0
0x2ca1  call     instance void System.Xaml.XamlObjectWriter::ThrowIfDisposed()
0x2ca6  ldarg.0
0x2ca7  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2cac  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0x2cb1  ldarg.0
0x2cb2  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2cb7  callvirt instance bool System.Xaml.DeferringWriter::get_Handled()
0x2cbc  brfalse.s loc_2CF5
0x2cbe  ldarg.0
0x2cbf  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2cc4  callvirt instance valuetype System.Xaml.DeferringMode System.Xaml.DeferringWriter::get_Mode()
0x2cc9  ldc.i4.3
0x2cca  bne.un.s loc_2CF4
0x2ccc  ldarg.0
0x2ccd  ldfld    class System.Xaml.DeferringWriter System.Xaml.XamlObjectWriter::_deferringWriter
0x2cd2  callvirt instance class System.Xaml.XamlNodeList System.Xaml.DeferringWriter::CollectTemplateList()
0x2cd7  stloc.3
0x2cd8  ldarg.0
0x2cd9  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2cde  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x2ce3  ldarg.0
0x2ce4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ce9  ldloc.3
0x2cea  callvirt instance class System.Xaml.XamlReader System.Xaml.XamlNodeList::GetReader()
0x2cef  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x2cf4  ret
0x2cf5  ldarg.0
0x2cf6  ldfld    bool System.Xaml.XamlObjectWriter::_nextNodeMustBeEndMember
0x2cfb  brfalse.s loc_2D1C
0x2cfd  ldstr    aValuemustbefol// "ValueMustBeFollowedByEndMember"
0x2d02  call     string System.Xaml.SR::Get(string id)
0x2d07  stloc.s  4
0x2d09  ldarg.0
0x2d0a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d0f  ldloc.s  4
0x2d11  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2d16  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2d1b  throw
0x2d1c  ldarg.0
0x2d1d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d22  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2d27  ldnull
0x2d28  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d2d  brfalse.s loc_2D4E
0x2d2f  ldstr    aNotypeincurren// "NoTypeInCurrentFrame_EO"
0x2d34  call     string System.Xaml.SR::Get(string id)
0x2d39  stloc.s  5
0x2d3b  ldarg.0
0x2d3c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d41  ldloc.s  5
0x2d43  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2d48  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2d4d  throw
0x2d4e  ldarg.0
0x2d4f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d54  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x2d59  ldnull
0x2d5a  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d5f  brfalse.s loc_2DAC
0x2d61  ldstr    aOpenpropertyin// "OpenPropertyInCurrentFrame_EO"
0x2d66  ldc.i4.2
0x2d67  newarr   [mscorlib]System.Object
0x2d6c  dup
0x2d6d  ldc.i4.0
0x2d6e  ldarg.0
0x2d6f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d74  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2d79  callvirt instance string [mscorlib]System.Object::ToString()
0x2d7e  stelem.ref
0x2d7f  dup
0x2d80  ldc.i4.1
0x2d81  ldarg.0
0x2d82  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d87  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentProperty()
0x2d8c  callvirt instance string [mscorlib]System.Object::ToString()
0x2d91  stelem.ref
0x2d92  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d97  stloc.s  6
0x2d99  ldarg.0
0x2d9a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2d9f  ldloc.s  6
0x2da1  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x2da6  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2dab  throw
0x2dac  ldarg.0
0x2dad  ldarg.0
0x2dae  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2db3  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2db8  call     instance bool System.Xaml.XamlObjectWriter::HasUnresolvedChildren(object parent)
0x2dbd  stloc.0
0x2dbe  ldarg.0
0x2dbf  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2dc4  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2dc9  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x2dce  ldnull
0x2dcf  cgt.un
0x2dd1  stloc.1
0x2dd2  ldarg.0
0x2dd3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2dd8  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentIsObjectFromMember()
0x2ddd  brtrue   loc_2F64
0x2de2  ldarg.0
0x2de3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2de8  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2ded  brtrue.s loc_2DFB
0x2def  ldarg.0
0x2df0  ldarg.0
0x2df1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2df6  call     instance void System.Xaml.XamlObjectWriter::Logic_CreateAndAssignToParentStart(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2dfb  ldarg.0
0x2dfc  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e01  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2e06  stloc.s  7
0x2e08  ldarg.0
0x2e09  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e0e  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2e13  stloc.s  8
0x2e15  ldarg.0
0x2e16  ldloc.s  8
0x2e18  callvirt instance void System.Xaml.XamlObjectWriter::OnAfterProperties(object value)
0x2e1d  ldarg.0
0x2e1e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e23  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2e28  callvirt instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0x2e2d  brfalse  loc_2EE7
0x2e32  ldloc.0
0x2e33  brfalse.s loc_2E46
0x2e35  ldarg.0
0x2e36  ldarg.0
0x2e37  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e3c  call     instance void System.Xaml.XamlObjectWriter::Logic_DeferProvideValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2e41  br       loc_2FC6
0x2e46  ldarg.0
0x2e47  ldarg.0
0x2e48  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e4d  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2e52  ldarg.0
0x2e53  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e58  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2e5d  call     instance void System.Xaml.XamlObjectWriter::ExecutePendingAdds(class System.Xaml.XamlType instanceType, object instance)
0x2e62  ldarg.0
0x2e63  ldarg.0
0x2e64  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e69  call     instance void System.Xaml.XamlObjectWriter::Logic_EndInit(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2e6e  ldarg.0
0x2e6f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e74  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2e79  stloc.s  8
0x2e7b  ldarg.0
0x2e7c  ldarg.0
0x2e7d  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e82  call     instance void System.Xaml.XamlObjectWriter::Logic_AssignProvidedValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2e87  ldarg.0
0x2e88  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2e8d  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x2e92  brfalse.s loc_2EBB
0x2e94  ldarg.0
0x2e95  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x2e9a  brfalse.s loc_2EAF
0x2e9c  ldarg.0
0x2e9d  ldloc.s  8
0x2e9f  ldarg.0
0x2ea0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ea5  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x2eaa  call     instance void System.Xaml.XamlObjectWriter::TriggerNameResolution(object instance, string name)
0x2eaf  ldarg.0
0x2eb0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2eb5  ldnull
0x2eb6  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstanceRegisteredName(string value)
0x2ebb  ldarg.0
0x2ebc  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ec1  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2ec6  stloc.s  8
0x2ec8  ldloc.s  8
0x2eca  isinst   MS.Internal.Xaml.Context.NameFixupToken
0x2ecf  ldnull
0x2ed0  cgt.un
0x2ed2  stloc.1
0x2ed3  ldloc.1
0x2ed4  brtrue.s loc_2EE0
0x2ed6  ldarg.0
0x2ed7  ldloc.s  8
0x2ed9  call     instance bool System.Xaml.XamlObjectWriter::HasUnresolvedChildren(object parent)
0x2ede  br.s     loc_2EE1
0x2ee0  ldc.i4.0
0x2ee1  stloc.0
0x2ee2  br       loc_2FC6
0x2ee7  ldarg.0
0x2ee8  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2eed  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x2ef2  ldc.i4.1
0x2ef3  ble.s    loc_2F0E
0x2ef5  ldarg.0
0x2ef6  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2efb  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentWasAssignedAtCreation()
0x2f00  brtrue.s loc_2F0E
0x2f02  ldarg.0
0x2f03  ldarg.0
0x2f04  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f09  call     instance void System.Xaml.XamlObjectWriter::Logic_DoAssignmentToParentProperty(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2f0e  ldloc.0
0x2f0f  brfalse.s loc_2F34
0x2f11  ldarg.0
0x2f12  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f17  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x2f1c  ldc.i4.1
0x2f1d  ble      loc_2FC6
0x2f22  ldarg.0
0x2f23  ldarg.0
0x2f24  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f29  ldnull
0x2f2a  call     instance void System.Xaml.XamlObjectWriter::Logic_AddDependencyForUnresolvedChildren(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlSavedContext deferredMarkupExtensionContext)
0x2f2f  br       loc_2FC6
0x2f34  ldloc.1
0x2f35  brtrue   loc_2FC6
0x2f3a  ldarg.0
0x2f3b  ldarg.0
0x2f3c  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f41  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2f46  ldarg.0
0x2f47  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f4c  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2f51  call     instance void System.Xaml.XamlObjectWriter::ExecutePendingAdds(class System.Xaml.XamlType instanceType, object instance)
0x2f56  ldarg.0
0x2f57  ldarg.0
0x2f58  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f5d  call     instance void System.Xaml.XamlObjectWriter::Logic_EndInit(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x2f62  br.s     loc_2FC6
0x2f64  ldloc.0
0x2f65  brfalse.s loc_2F76
0x2f67  ldarg.0
0x2f68  ldarg.0
0x2f69  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f6e  ldnull
0x2f6f  call     instance void System.Xaml.XamlObjectWriter::Logic_AddDependencyForUnresolvedChildren(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlSavedContext deferredMarkupExtensionContext)
0x2f74  br.s     loc_2F92
0x2f76  ldarg.0
0x2f77  ldarg.0
0x2f78  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f7d  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x2f82  ldarg.0
0x2f83  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f88  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2f8d  call     instance void System.Xaml.XamlObjectWriter::ExecutePendingAdds(class System.Xaml.XamlType instanceType, object instance)
0x2f92  ldarg.0
0x2f93  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2f98  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentIsPropertyValueSet()
0x2f9d  brfalse.s loc_2FC6
0x2f9f  ldarg.0
0x2fa0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fa5  ldarg.0
0x2fa6  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fab  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x2fb0  ldarg.0
0x2fb1  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fb6  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x2fbb  newobj   instance void System.Xaml.XamlDuplicateMemberException::.ctor(class System.Xaml.XamlMember member, class System.Xaml.XamlType type)
0x2fc0  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Context.ObjectWriterContext::WithLineInfo(class System.Xaml.XamlException ex)
0x2fc5  throw
0x2fc6  ldarg.0
0x2fc7  ldarg.0
0x2fc8  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fcd  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x2fd2  stfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x2fd7  ldarg.0
0x2fd8  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fdd  callvirt instance string MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstanceRegisteredName()
0x2fe2  stloc.2
0x2fe3  ldarg.0
0x2fe4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2fe9  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x2fee  ldc.i4.1
0x2fef  bne.un.s loc_3002
0x2ff1  ldarg.0
0x2ff2  ldarg.0
0x2ff3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x2ff8  callvirt instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterContext::get_RootNameScope()
0x2ffd  stfld    class System.Windows.Markup.INameScope System.Xaml.XamlObjectWriter::_rootNamescope
0x3002  ldarg.0
0x3003  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3008  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x300d  ldloc.0
0x300e  brfalse.s loc_303A
0x3010  ldarg.0
0x3011  ldfld    class MS.Internal.Xaml.Context.NameFixupGraph System.Xaml.XamlObjectWriter::_nameFixupGraph
0x3016  ldarg.0
0x3017  ldfld    object System.Xaml.XamlObjectWriter::_lastInstance
0x301c  ldloc.2
0x301d  ldarg.0
0x301e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x3023  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LineNumber()
0x3028  ldarg.0
0x3029  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext System.Xaml.XamlObjectWriter::_context
0x302e  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LinePosition()
0x3033  callvirt instance void MS.Internal.Xaml.Context.NameFixupGraph::IsOffTheStack(object instance, string name, int32 lineNumber, int32 linePosition)
0x3038  br.s     loc_3092
0x303a  ldloc.1
0x303b  brfalse.s loc_307D
0x303d  ldloc.2
  ... truncated ...
```
