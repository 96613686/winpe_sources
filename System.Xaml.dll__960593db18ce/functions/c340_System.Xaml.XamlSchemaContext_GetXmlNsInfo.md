# System.Xaml.XamlSchemaContext::GetXmlNsInfo

- ea: `0xc340`
- end: `0xc450`
- name: `System.Xaml.XamlSchemaContext::GetXmlNsInfo`
- size: `272`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0xc010`
- `0xc260`
- `0xc450`
- `0xc5f0`

## callees

- `0xc80`
- `0xbf30`
- `0xbf50`
- `0xbf80`
- `0xbfe0`
- `0xc1e0`
- `0xc340`
- `0x12ee0`

## pseudocode

```c

```

## disassembly

```asm
0xc340  ldarg.0
0xc341  call     instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::get_XmlnsInfo()
0xc346  ldarg.1
0xc347  ldloca.s 0
0xc349  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo>::TryGetValue(var<u1>, !!T0)
0xc34e  brtrue.s loc_C38D
0xc350  ldarg.0
0xc351  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class System.Xaml.WeakRefKey, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::_xmlnsInfoForDynamicAssemblies
0xc356  brfalse.s loc_C375
0xc358  ldarg.1
0xc359  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_IsDynamic()
0xc35e  brfalse.s loc_C375
0xc360  ldarg.0
0xc361  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class System.Xaml.WeakRefKey, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::_xmlnsInfoForDynamicAssemblies
0xc366  ldarg.1
0xc367  newobj   instance void System.Xaml.WeakRefKey::.ctor(object target)
0xc36c  ldloca.s 0
0xc36e  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class System.Xaml.WeakRefKey, class System.Xaml.MS.Impl.XmlNsInfo>::TryGetValue(var<u1>, !!T0)
0xc373  brtrue.s loc_C38D
0xc375  ldarg.0
0xc376  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::_xmlnsInfoForUnreferencedAssemblies
0xc37b  brfalse.s loc_C38F
0xc37d  ldarg.0
0xc37e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::_xmlnsInfoForUnreferencedAssemblies
0xc383  ldarg.1
0xc384  ldloca.s 0
0xc386  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo>::TryGetValue(var<u1>, !!T0)
0xc38b  brfalse.s loc_C38F
0xc38d  ldloc.0
0xc38e  ret
0xc38f  ldc.i4.0
0xc390  stloc.1
0xc391  ldarg.0
0xc392  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Reflection.Assembly> System.Xaml.XamlSchemaContext::_referenceAssemblies
0xc397  brfalse.s loc_C3CA
0xc399  ldarg.0
0xc39a  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Reflection.Assembly> System.Xaml.XamlSchemaContext::_referenceAssemblies
0xc39f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Reflection.Assembly>::GetEnumerator()
0xc3a4  stloc.2
0xc3a5  br.s     loc_C3B6
0xc3a7  ldloc.2
0xc3a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Reflection.Assembly>::get_Current()
0xc3ad  stloc.3
0xc3ae  ldloc.3
0xc3af  ldarg.1
0xc3b0  bne.un.s loc_C3B6
0xc3b2  ldc.i4.1
0xc3b3  stloc.1
0xc3b4  leave.s  loc_C3F5
0xc3b6  ldloc.2
0xc3b7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc3bc  brtrue.s loc_C3A7
0xc3be  leave.s  loc_C3F5
0xc3c0  ldloc.2
0xc3c1  brfalse.s loc_C3C9
0xc3c3  ldloc.2
0xc3c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3c9  endfinally
0xc3ca  ldarg.1
0xc3cb  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_ReflectionOnly()
0xc3d0  brtrue.s loc_C3F3
0xc3d2  ldtoken  [mscorlib]System.Object
0xc3d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc3dc  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xc3e1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc3e6  ldarg.1
0xc3e7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc3ec  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0xc3f1  br.s     loc_C3F4
0xc3f3  ldc.i4.0
0xc3f4  stloc.1
0xc3f5  ldarg.1
0xc3f6  ldarg.0
0xc3f7  call     instance bool System.Xaml.XamlSchemaContext::get_FullyQualifyAssemblyNamesInClrNamespaces()
0xc3fc  newobj   instance void System.Xaml.MS.Impl.XmlNsInfo::.ctor(class [mscorlib]System.Reflection.Assembly assembly, bool fullyQualifyAssemblyName)
0xc401  stloc.0
0xc402  ldloc.1
0xc403  brfalse.s loc_C440
0xc405  ldarg.1
0xc406  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_IsDynamic()
0xc40b  brfalse.s loc_C430
0xc40d  ldarg.0
0xc40e  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Reflection.Assembly> System.Xaml.XamlSchemaContext::_referenceAssemblies
0xc413  brtrue.s loc_C430
0xc415  ldarg.0
0xc416  call     instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class System.Xaml.WeakRefKey, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::get_XmlnsInfoForDynamicAssemblies()
0xc41b  ldarg.1
0xc41c  newobj   instance void System.Xaml.WeakRefKey::.ctor(object target)
0xc421  ldloc.0
0xc422  call     T0x2B000022
0xc427  stloc.0
0xc428  ldarg.0
0xc429  call     instance void System.Xaml.XamlSchemaContext::RegisterAssemblyCleanup()
0xc42e  br.s     loc_C44E
0xc430  ldarg.0
0xc431  call     instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::get_XmlnsInfo()
0xc436  ldarg.1
0xc437  ldloc.0
0xc438  call     T0x2B000023
0xc43d  stloc.0
0xc43e  br.s     loc_C44E
0xc440  ldarg.0
0xc441  call     instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Reflection.Assembly, class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::get_XmlnsInfoForUnreferencedAssemblies()
0xc446  ldarg.1
0xc447  ldloc.0
0xc448  call     T0x2B000023
0xc44d  stloc.0
0xc44e  ldloc.0
0xc44f  ret
```
