# System.Windows.Markup.EventSetterHandlerConverter::ConvertFrom

- ea: `0x89940`
- end: `0x89a2e`
- name: `System.Windows.Markup.EventSetterHandlerConverter::ConvertFrom`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0xb100`
- `0x38c40`
- `0x89940`

## string_xrefs

- `0x89943`: `typeDescriptorContext`
- `0x899a5`: `typeDescriptorContext`
- `0x8997a`: `MS.Internal.Xaml.ServiceProviderContext`

## pseudocode

```c

```

## disassembly

```asm
0x89940  ldarg.1
0x89941  brtrue.s loc_8994E
0x89943  ldstr    aTypedescriptor// "typeDescriptorContext"
0x89948  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8994d  throw
0x8994e  ldarg.3
0x8994f  brtrue.s loc_8995C
0x89951  ldstr    aSource// "source"
0x89956  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8995b  throw
0x8995c  ldsfld   class [mscorlib]System.Type System.Windows.Markup.EventSetterHandlerConverter::s_ServiceProviderContextType
0x89961  ldnull
0x89962  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x89967  brfalse.s loc_89989
0x89969  ldtoken  [System.Xaml]System.Xaml.IRootObjectProvider
0x8996e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89973  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x89978  stloc.1
0x89979  ldloc.1
0x8997a  ldstr    aMsInternalXaml// "MS.Internal.Xaml.ServiceProviderContext"
0x8997f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x89984  stsfld   class [mscorlib]System.Type System.Windows.Markup.EventSetterHandlerConverter::s_ServiceProviderContextType
0x89989  ldarg.1
0x8998a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8998f  ldsfld   class [mscorlib]System.Type System.Windows.Markup.EventSetterHandlerConverter::s_ServiceProviderContextType
0x89994  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x89999  brfalse.s loc_899B0
0x8999b  ldstr    aTextrangeInval// "TextRange_InvalidParameterValue"
0x899a0  call     string System.Windows.SR::Get(string id)
0x899a5  ldstr    aTypedescriptor// "typeDescriptorContext"
0x899aa  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x899af  throw
0x899b0  ldarg.1
0x899b1  ldtoken  [System.Xaml]System.Xaml.IRootObjectProvider
0x899b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x899bb  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x899c0  isinst   [System.Xaml]System.Xaml.IRootObjectProvider
0x899c5  stloc.0
0x899c6  ldloc.0
0x899c7  brfalse.s loc_89A26
0x899c9  ldarg.3
0x899ca  isinst   [mscorlib]System.String
0x899cf  brfalse.s loc_89A26
0x899d1  ldarg.1
0x899d2  ldtoken  [System.Xaml]System.Windows.Markup.IProvideValueTarget
0x899d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x899dc  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x899e1  isinst   [System.Xaml]System.Windows.Markup.IProvideValueTarget
0x899e6  stloc.2
0x899e7  ldloc.2
0x899e8  brfalse.s loc_89A26
0x899ea  ldloc.2
0x899eb  callvirt instance object [System.Xaml]System.Windows.Markup.IProvideValueTarget::get_TargetObject()
0x899f0  isinst   System.Windows.EventSetter
0x899f5  stloc.3
0x899f6  ldloc.3
0x899f7  brfalse.s loc_89A26
0x899f9  ldarg.3
0x899fa  isinst   [mscorlib]System.String
0x899ff  dup
0x89a00  stloc.s  4
0x89a02  brfalse.s loc_89A26
0x89a04  ldloc.s  4
0x89a06  callvirt instance string [mscorlib]System.String::Trim()
0x89a0b  stloc.s  4
0x89a0d  ldloc.3
0x89a0e  callvirt instance class [PresentationCore]System.Windows.RoutedEvent System.Windows.EventSetter::get_Event()
0x89a13  callvirt instance class [mscorlib]System.Type [PresentationCore]System.Windows.RoutedEvent::get_HandlerType()
0x89a18  ldloc.0
0x89a19  callvirt instance object [System.Xaml]System.Xaml.IRootObjectProvider::get_RootObject()
0x89a1e  ldloc.s  4
0x89a20  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::CreateDelegate(class [mscorlib]System.Type, object, string)
0x89a25  ret
0x89a26  ldarg.0
0x89a27  ldarg.3
0x89a28  call     instance class [mscorlib]System.Exception [System]System.ComponentModel.TypeConverter::GetConvertFromException(object)
0x89a2d  throw
```
