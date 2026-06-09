# System.Windows.Markup.RestrictiveXamlXmlReader::.cctor

- ea: `0xadee0`
- end: `0xae02d`
- name: `System.Windows.Markup.RestrictiveXamlXmlReader::.cctor`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0xadee0`
- `0xae160`
- `0x264cd0`
- `0x264cf0`
- `0x264d10`
- `0x264d40`

## string_xrefs

- `0xadf38`: `System.Configuration.Install.AssemblyInstaller`
- `0xadf3d`: `System.Configuration.Install, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`
- `0xadf52`: `System.Activities.Presentation, Version = 4.0.0.0, Culture = neutral, PublicKeyToken = 31bf3856ad364e35`
- `0xadf67`: `System.Windows.Forms, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`

## pseudocode

```c

```

## disassembly

```asm
0xadee0  call     class [mscorlib]System.Collections.Generic.IList`1<string> [System.Xaml]System.Xaml.XamlLanguage::get_XamlNamespaces()
0xadee5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xadeea  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Windows.Markup.RestrictiveXamlXmlReader::AllXamlNamespaces
0xadeef  ldtoken  [WindowsBase]System.Windows.DependencyObject
0xadef4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xadef9  stsfld   class [mscorlib]System.Type System.Windows.Markup.RestrictiveXamlXmlReader::DependencyObjectType
0xadefe  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0xadf03  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Windows.Markup.RestrictiveXamlXmlReader::SafeTypesFromRegistry
0xadf08  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::.ctor()
0xadf0d  dup
0xadf0e  ldstr    aSystemWindowsD// "System.Windows.Data.ObjectDataProvider"
0xadf13  ldstr    asc_28A0A2// ""
0xadf18  newobj   instance void RestrictedType::.ctor(string typeName, string assemblyName)
0xadf1d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadf22  dup
0xadf23  ldstr    aSystemWindowsR// "System.Windows.ResourceDictionary"
0xadf28  ldstr    asc_28A0A2// ""
0xadf2d  newobj   instance void RestrictedType::.ctor(string typeName, string assemblyName)
0xadf32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadf37  dup
0xadf38  ldstr    aSystemConfigur// "System.Configuration.Install.AssemblyIn"...
0xadf3d  ldstr    aSystemConfigur_0// "System.Configuration.Install, Version=4"...
0xadf42  newobj   instance void RestrictedType::.ctor(string typeName, string assemblyName)
0xadf47  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadf4c  dup
0xadf4d  ldstr    aSystemActiviti// "System.Activities.Presentation.Workflow"...
0xadf52  ldstr    aSystemActiviti_0// "System.Activities.Presentation, Version"...
0xadf57  newobj   instance void RestrictedType::.ctor(string typeName, string assemblyName)
0xadf5c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadf61  dup
0xadf62  ldstr    aSystemWindowsF// "System.Windows.Forms.BindingSource"
0xadf67  ldstr    aSystemWindowsF_0// "System.Windows.Forms, Version=4.0.0.0, "...
0xadf6c  newobj   instance void RestrictedType::.ctor(string typeName, string assemblyName)
0xadf71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadf76  stsfld   class [mscorlib]System.Collections.Generic.List`1<class RestrictedType> System.Windows.Markup.RestrictiveXamlXmlReader::_restrictedTypes
0xadf7b  ldnull
0xadf7c  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>> System.Windows.Markup.RestrictiveXamlXmlReader::_unloadedTypes
0xadf81  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>>::.ctor()
0xadf86  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>> System.Windows.Markup.RestrictiveXamlXmlReader::_unloadedTypes
0xadf8b  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class RestrictedType> System.Windows.Markup.RestrictiveXamlXmlReader::_restrictedTypes
0xadf90  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::GetEnumerator()
0xadf95  stloc.0
0xadf96  br.s     loc_AE009
0xadf98  ldloca.s 0
0xadf9a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RestrictedType>::get_Current()
0xadf9f  stloc.1
0xadfa0  ldloc.1
0xadfa1  callvirt instance string RestrictedType::get_AssemblyName()
0xadfa6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xadfab  brtrue.s loc_ADFEC
0xadfad  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>> System.Windows.Markup.RestrictiveXamlXmlReader::_unloadedTypes
0xadfb2  ldloc.1
0xadfb3  callvirt instance string RestrictedType::get_AssemblyName()
0xadfb8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>>::ContainsKey(var<u1>)
0xadfbd  brtrue.s loc_ADFD4
0xadfbf  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>> System.Windows.Markup.RestrictiveXamlXmlReader::_unloadedTypes
0xadfc4  ldloc.1
0xadfc5  callvirt instance string RestrictedType::get_AssemblyName()
0xadfca  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::.ctor()
0xadfcf  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>>::set_Item(var<u1>, !!T0)
0xadfd4  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>> System.Windows.Markup.RestrictiveXamlXmlReader::_unloadedTypes
0xadfd9  ldloc.1
0xadfda  callvirt instance string RestrictedType::get_AssemblyName()
0xadfdf  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>>::get_Item(void)
0xadfe4  ldloc.1
0xadfe5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class RestrictedType>::Add(var<u1>)
0xadfea  br.s     loc_AE009
0xadfec  ldloc.1
0xadfed  callvirt instance string RestrictedType::get_TypeName()
0xadff2  ldc.i4.0
0xadff3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0xadff8  stloc.2
0xadff9  ldloc.2
0xadffa  ldnull
0xadffb  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xae000  brfalse.s loc_AE009
0xae002  ldloc.1
0xae003  ldloc.2
0xae004  callvirt instance void RestrictedType::set_TypeReference(class [mscorlib]System.Type value)
0xae009  ldloca.s 0
0xae00b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RestrictedType>::MoveNext()
0xae010  brtrue.s loc_ADF98
0xae012  leave.s  loc_AE022
0xae014  ldloca.s 0
0xae016  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class RestrictedType>
0xae01c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xae021  endfinally
0xae022  call     class [System.Core]System.Collections.Generic.HashSet`1<string> System.Windows.Markup.RestrictiveXamlXmlReader::ReadAllowedTypesForRestrictedXamlContexts()
0xae027  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> System.Windows.Markup.RestrictiveXamlXmlReader::SafeTypesFromRegistry
0xae02c  ret
```
