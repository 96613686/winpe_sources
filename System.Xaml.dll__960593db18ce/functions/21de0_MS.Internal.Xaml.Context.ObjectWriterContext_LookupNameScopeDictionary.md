# MS.Internal.Xaml.Context.ObjectWriterContext::LookupNameScopeDictionary

- ea: `0x21de0`
- end: `0x21ea6`
- name: `MS.Internal.Xaml.Context.ObjectWriterContext::LookupNameScopeDictionary`
- size: `198`
- prototype: ``
- caller_count: `7`
- callee_count: `14`
- tags: ``

## callers

- `0x21af0`
- `0x21b10`
- `0x21b30`
- `0x21b50`
- `0x21de0`
- `0x22010`
- `0x31560`

## callees

- `0x1230`
- `0x5db0`
- `0x7f90`
- `0xd160`
- `0xefa0`
- `0x215b0`
- `0x21de0`
- `0x21f10`
- `0x22400`
- `0x22540`
- `0x22550`
- `0x22710`
- `0x22c00`
- `0x22c10`

## pseudocode

```c

```

## disassembly

```asm
0x21de0  ldarg.1
0x21de1  callvirt instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterFrame::get_NameScopeDictionary()
0x21de6  brtrue   loc_21E9F
0x21deb  ldarg.1
0x21dec  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlCommonFrame::get_XamlType()
0x21df1  ldnull
0x21df2  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x21df7  brfalse.s loc_21E2B
0x21df9  ldarg.1
0x21dfa  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.XamlCommonFrame::get_XamlType()
0x21dff  callvirt instance bool System.Xaml.XamlType::get_IsNameScope()
0x21e04  brfalse.s loc_21E2B
0x21e06  ldarg.1
0x21e07  ldarg.1
0x21e08  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterFrame::get_Instance()
0x21e0d  isinst   System.Windows.Markup.INameScopeDictionary
0x21e12  dup
0x21e13  brtrue.s loc_21E26
0x21e15  pop
0x21e16  ldarg.1
0x21e17  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterFrame::get_Instance()
0x21e1c  isinst   System.Windows.Markup.INameScope
0x21e21  newobj   instance void System.Xaml.NameScopeDictionary::.ctor(class System.Windows.Markup.INameScope underlyingNameScope)
0x21e26  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterFrame::set_NameScopeDictionary(class System.Windows.Markup.INameScopeDictionary value)
0x21e2b  ldarg.1
0x21e2c  callvirt instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterFrame::get_NameScopeDictionary()
0x21e31  brtrue.s loc_21E9F
0x21e33  ldarg.1
0x21e34  callvirt instance int32 MS.Internal.Xaml.Context.XamlFrame::get_Depth()
0x21e39  ldc.i4.1
0x21e3a  bne.un.s loc_21E4B
0x21e3c  ldarg.1
0x21e3d  ldarg.0
0x21e3e  ldarg.1
0x21e3f  call     instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterContext::HuntAroundForARootNameScope(class MS.Internal.Xaml.Context.ObjectWriterFrame rootFrame)
0x21e44  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterFrame::set_NameScopeDictionary(class System.Windows.Markup.INameScopeDictionary value)
0x21e49  br.s     loc_21E9F
0x21e4b  ldarg.1
0x21e4c  callvirt instance int32 MS.Internal.Xaml.Context.XamlFrame::get_Depth()
0x21e51  ldc.i4.1
0x21e52  ble.s    loc_21E9F
0x21e54  ldarg.1
0x21e55  callvirt instance int32 MS.Internal.Xaml.Context.XamlFrame::get_Depth()
0x21e5a  ldarg.0
0x21e5b  call     instance int32 MS.Internal.Xaml.Context.ObjectWriterContext::get_SavedDepth()
0x21e60  ldc.i4.1
0x21e61  add
0x21e62  bne.un.s loc_21E86
0x21e64  ldarg.0
0x21e65  ldfld    class System.Xaml.XamlObjectWriterSettings MS.Internal.Xaml.Context.ObjectWriterContext::_settings
0x21e6a  brfalse.s loc_21E86
0x21e6c  ldarg.0
0x21e6d  ldfld    class System.Xaml.XamlObjectWriterSettings MS.Internal.Xaml.Context.ObjectWriterContext::_settings
0x21e72  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_RegisterNamesOnExternalNamescope()
0x21e77  brtrue.s loc_21E86
0x21e79  ldarg.1
0x21e7a  newobj   instance void System.Xaml.NameScope::.ctor()
0x21e7f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterFrame::set_NameScopeDictionary(class System.Windows.Markup.INameScopeDictionary value)
0x21e84  br.s     loc_21E9F
0x21e86  ldarg.1
0x21e87  callvirt instance class MS.Internal.Xaml.Context.XamlFrame MS.Internal.Xaml.Context.XamlFrame::get_Previous()
0x21e8c  castclass MS.Internal.Xaml.Context.ObjectWriterFrame
0x21e91  stloc.0
0x21e92  ldarg.1
0x21e93  ldarg.0
0x21e94  ldloc.0
0x21e95  call     instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterContext::LookupNameScopeDictionary(class MS.Internal.Xaml.Context.ObjectWriterFrame frame)
0x21e9a  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterFrame::set_NameScopeDictionary(class System.Windows.Markup.INameScopeDictionary value)
0x21e9f  ldarg.1
0x21ea0  callvirt instance class System.Windows.Markup.INameScopeDictionary MS.Internal.Xaml.Context.ObjectWriterFrame::get_NameScopeDictionary()
0x21ea5  ret
```
