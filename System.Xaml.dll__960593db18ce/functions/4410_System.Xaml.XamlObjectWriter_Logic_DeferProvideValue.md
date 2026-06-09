# System.Xaml.XamlObjectWriter::Logic_DeferProvideValue

- ea: `0x4410`
- end: `0x4465`
- name: `System.Xaml.XamlObjectWriter::Logic_DeferProvideValue`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x2ca0`

## callees

- `0x4410`
- `0x4ee0`
- `0x5170`
- `0x5240`
- `0x8b40`
- `0xb280`
- `0xd130`
- `0x215c0`
- `0x21630`
- `0x21690`
- `0x216d0`
- `0x22010`

## pseudocode

```c

```

## disassembly

```asm
0x4410  ldarg.1
0x4411  ldc.i4.2
0x4412  callvirt instance class System.Xaml.XamlSavedContext MS.Internal.Xaml.Context.ObjectWriterContext::GetSavedContext(valuetype System.Xaml.SavedContextType savedContextType)
0x4417  stloc.0
0x4418  ldarg.1
0x4419  callvirt instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_LiveDepth()
0x441e  ldc.i4.2
0x441f  ble.s    loc_445C
0x4421  ldarg.1
0x4422  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x4427  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x442c  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x4431  brfalse.s loc_445C
0x4433  ldarg.1
0x4434  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentType()
0x4439  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x443e  brfalse.s loc_445C
0x4440  ldarg.0
0x4441  ldarg.1
0x4442  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4447  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x444c  ldloc.0
0x444d  call     instance class MS.Internal.Xaml.Context.NameFixupToken System.Xaml.XamlObjectWriter::GetTokenForUnresolvedChildren(object childThatHasUnresolvedChildren, class System.Xaml.XamlMember property, class System.Xaml.XamlSavedContext deferredMarkupExtensionContext)
0x4452  stloc.1
0x4453  ldarg.0
0x4454  ldarg.1
0x4455  ldloc.1
0x4456  call     instance void System.Xaml.XamlObjectWriter::Logic_PendKeyFixupToken(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class MS.Internal.Xaml.Context.NameFixupToken token)
0x445b  ret
0x445c  ldarg.0
0x445d  ldarg.1
0x445e  ldloc.0
0x445f  call     instance void System.Xaml.XamlObjectWriter::Logic_AddDependencyForUnresolvedChildren(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, class System.Xaml.XamlSavedContext deferredMarkupExtensionContext)
0x4464  ret
```
