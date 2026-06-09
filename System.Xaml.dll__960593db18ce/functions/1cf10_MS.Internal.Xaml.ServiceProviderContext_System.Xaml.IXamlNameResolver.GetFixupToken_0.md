# MS.Internal.Xaml.ServiceProviderContext::System.Xaml.IXamlNameResolver.GetFixupToken_0

- ea: `0x1cf10`
- end: `0x1d0f4`
- name: `MS.Internal.Xaml.ServiceProviderContext::System.Xaml.IXamlNameResolver.GetFixupToken_0`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `service_task`

## callees

- `0x8b30`
- `0xb280`
- `0xef20`
- `0x11f20`
- `0x1cf10`
- `0x20a30`
- `0x20a50`
- `0x20a90`
- `0x20b50`
- `0x20bb0`
- `0x20bf0`
- `0x20c00`
- `0x20c10`
- `0x20c20`
- `0x20c70`
- `0x20cf0`
- `0x20d00`
- `0x20d10`
- `0x20ff0`
- `0x215d0`
- `0x21610`
- `0x21630`
- `0x21690`
- `0x216b0`
- `0x21710`
- `0x21730`
- `0x21830`
- `0x21850`
- `0x21eb0`
- `0x22010`

## pseudocode

```c

```

## disassembly

```asm
0x1cf10  ldarg.0
0x1cf11  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cf16  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_NameResolutionComplete()
0x1cf1b  brfalse.s loc_1CF1F
0x1cf1d  ldnull
0x1cf1e  ret
0x1cf1f  newobj   instance void MS.Internal.Xaml.Context.NameFixupToken::.ctor()
0x1cf24  stloc.0
0x1cf25  ldloc.0
0x1cf26  ldarg.2
0x1cf27  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_CanAssignDirectly(bool value)
0x1cf2c  ldloc.0
0x1cf2d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x1cf32  ldarg.1
0x1cf33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1cf38  ldloc.0
0x1cf39  callvirt instance bool MS.Internal.Xaml.Context.NameFixupToken::get_CanAssignDirectly()
0x1cf3e  brfalse.s loc_1CF63
0x1cf40  ldloc.0
0x1cf41  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> MS.Internal.Xaml.Context.NameFixupToken::get_NeededNames()
0x1cf46  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1cf4b  ldc.i4.1
0x1cf4c  beq.s    loc_1CF63
0x1cf4e  ldstr    aSimplefixupsmu// "SimpleFixupsMustHaveOneName"
0x1cf53  call     string System.Xaml.SR::Get(string id)
0x1cf58  ldstr    aNames// "names"
0x1cf5d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1cf62  throw
0x1cf63  ldarg.0
0x1cf64  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cf69  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x1cf6e  ldnull
0x1cf6f  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x1cf74  brfalse  loc_1D055
0x1cf79  ldarg.0
0x1cf7a  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cf7f  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x1cf84  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Initialization()
0x1cf89  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x1cf8e  brfalse.s loc_1CFF4
0x1cf90  ldloc.0
0x1cf91  ldc.i4.3
0x1cf92  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_FixupType(valuetype MS.Internal.Xaml.Context.FixupType value)
0x1cf97  ldloc.0
0x1cf98  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1cf9d  ldarg.0
0x1cf9e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cfa3  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentInstance()
0x1cfa8  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Instance(object value)
0x1cfad  ldloc.0
0x1cfae  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1cfb3  ldarg.0
0x1cfb4  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cfb9  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentIsObjectFromMember()
0x1cfbe  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceWasGotten(bool value)
0x1cfc3  ldloc.0
0x1cfc4  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1cfc9  ldarg.0
0x1cfca  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cfcf  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentType()
0x1cfd4  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceType(class System.Xaml.XamlType value)
0x1cfd9  ldloc.0
0x1cfda  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1cfdf  ldarg.0
0x1cfe0  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1cfe5  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_GrandParentProperty()
0x1cfea  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Property(class System.Xaml.XamlMember value)
0x1cfef  br       loc_1D0B4
0x1cff4  ldloc.0
0x1cff5  ldc.i4.2
0x1cff6  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_FixupType(valuetype MS.Internal.Xaml.Context.FixupType value)
0x1cffb  ldloc.0
0x1cffc  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d001  ldarg.0
0x1d002  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d007  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x1d00c  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Instance(object value)
0x1d011  ldloc.0
0x1d012  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d017  ldarg.0
0x1d018  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d01d  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentIsObjectFromMember()
0x1d022  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceWasGotten(bool value)
0x1d027  ldloc.0
0x1d028  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d02d  ldarg.0
0x1d02e  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d033  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x1d038  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceType(class System.Xaml.XamlType value)
0x1d03d  ldloc.0
0x1d03e  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d043  ldarg.0
0x1d044  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d049  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x1d04e  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Property(class System.Xaml.XamlMember value)
0x1d053  br.s     loc_1D0B4
0x1d055  ldloc.0
0x1d056  ldc.i4.1
0x1d057  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_FixupType(valuetype MS.Internal.Xaml.Context.FixupType value)
0x1d05c  ldloc.0
0x1d05d  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d062  ldarg.0
0x1d063  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d068  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentInstance()
0x1d06d  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Instance(object value)
0x1d072  ldloc.0
0x1d073  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d078  ldarg.0
0x1d079  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d07e  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentIsObjectFromMember()
0x1d083  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceWasGotten(bool value)
0x1d088  ldloc.0
0x1d089  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d08e  ldarg.0
0x1d08f  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d094  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x1d099  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_InstanceType(class System.Xaml.XamlType value)
0x1d09e  ldloc.0
0x1d09f  callvirt instance class MS.Internal.Xaml.Context.FixupTarget MS.Internal.Xaml.Context.NameFixupToken::get_Target()
0x1d0a4  ldarg.0
0x1d0a5  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d0aa  callvirt instance class System.Xaml.XamlMember MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentProperty()
0x1d0af  callvirt instance void MS.Internal.Xaml.Context.FixupTarget::set_Property(class System.Xaml.XamlMember value)
0x1d0b4  ldloc.0
0x1d0b5  callvirt instance bool MS.Internal.Xaml.Context.NameFixupToken::get_CanAssignDirectly()
0x1d0ba  brfalse.s loc_1D0D4
0x1d0bc  ldloc.0
0x1d0bd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.INameScopeDictionary> MS.Internal.Xaml.Context.NameFixupToken::get_NameScopeDictionaryList()
0x1d0c2  ldarg.0
0x1d0c3  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d0c8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Windows.Markup.INameScopeDictionary> MS.Internal.Xaml.Context.ObjectWriterContext::get_StackWalkOfNameScopes()
0x1d0cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.INameScopeDictionary>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1d0d2  br.s     loc_1D0F2
0x1d0d4  ldloc.0
0x1d0d5  ldarg.0
0x1d0d6  ldfld    class MS.Internal.Xaml.Context.ObjectWriterContext MS.Internal.Xaml.ServiceProviderContext::_xamlContext
0x1d0db  ldloc.0
0x1d0dc  callvirt instance valuetype MS.Internal.Xaml.Context.FixupType MS.Internal.Xaml.Context.NameFixupToken::get_FixupType()
0x1d0e1  ldc.i4.1
0x1d0e2  beq.s    loc_1D0E7
0x1d0e4  ldc.i4.1
0x1d0e5  br.s     loc_1D0E8
0x1d0e7  ldc.i4.2
0x1d0e8  callvirt instance class System.Xaml.XamlSavedContext MS.Internal.Xaml.Context.ObjectWriterContext::GetSavedContext(valuetype System.Xaml.SavedContextType savedContextType)
0x1d0ed  callvirt instance void MS.Internal.Xaml.Context.NameFixupToken::set_SavedContext(class System.Xaml.XamlSavedContext value)
0x1d0f2  ldloc.0
0x1d0f3  ret
```
