# System.Xaml.MS.Impl.XmlNsInfo::LoadClrToXmlNs

- ea: `0x130c0`
- end: `0x131c5`
- name: `System.Xaml.MS.Impl.XmlNsInfo::LoadClrToXmlNs`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x12e30`

## callees

- `0xc790`
- `0x12df0`
- `0x12e10`
- `0x130c0`
- `0x136d0`
- `0x16470`
- `0x2f780`
- `0x2f9a0`
- `0x2f9c0`

## pseudocode

```c

```

## disassembly

```asm
0x130c0  call     T0x2B00002C
0x130c5  stloc.0
0x130c6  ldarg.0
0x130c7  call     instance class [mscorlib]System.Reflection.Assembly System.Xaml.MS.Impl.XmlNsInfo::get_Assembly()
0x130cc  stloc.1
0x130cd  ldloc.1
0x130ce  ldnull
0x130cf  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x130d4  brfalse.s loc_130D8
0x130d6  ldloc.0
0x130d7  ret
0x130d8  ldarg.0
0x130d9  call     instance class [mscorlib]System.Collections.Generic.IList`1<class XmlNsDefinition> System.Xaml.MS.Impl.XmlNsInfo::get_NsDefs()
0x130de  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class XmlNsDefinition>::GetEnumerator()
0x130e3  stloc.3
0x130e4  br.s     loc_13124
0x130e6  ldloc.3
0x130e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class XmlNsDefinition>::get_Current()
0x130ec  stloc.s  4
0x130ee  ldloc.0
0x130ef  ldloc.s  4
0x130f1  callvirt instance string XmlNsDefinition::get_ClrNamespace()
0x130f6  ldloca.s 5
0x130f8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::TryGetValue(var<u1>, !!T0)
0x130fd  brtrue.s loc_13116
0x130ff  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x13104  stloc.s  5
0x13106  ldloc.0
0x13107  ldloc.s  4
0x13109  callvirt instance string XmlNsDefinition::get_ClrNamespace()
0x1310e  ldloc.s  5
0x13110  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::TryAdd(var<u1>, !!T0)
0x13115  pop
0x13116  ldloc.s  5
0x13118  ldloc.s  4
0x1311a  callvirt instance string XmlNsDefinition::get_XmlNamespace()
0x1311f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x13124  ldloc.3
0x13125  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1312a  brtrue.s loc_130E6
0x1312c  leave.s  loc_13138
0x1312e  ldloc.3
0x1312f  brfalse.s loc_13137
0x13131  ldloc.3
0x13132  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13137  endfinally
0x13138  ldarg.0
0x13139  ldfld    bool System.Xaml.MS.Impl.XmlNsInfo::_fullyQualifyAssemblyName
0x1313e  brtrue.s loc_13148
0x13140  ldloc.1
0x13141  call     string System.Xaml.XamlSchemaContext::GetAssemblyShortName(class [mscorlib]System.Reflection.Assembly assembly)
0x13146  br.s     loc_1314E
0x13148  ldloc.1
0x13149  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1314e  stloc.2
0x1314f  ldloc.0
0x13150  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::GetEnumerator()
0x13155  stloc.s  6
0x13157  br.s     loc_131A5
0x13159  ldloc.s  6
0x1315b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>>::get_Current()
0x13160  stloc.s  7
0x13162  ldloca.s 7
0x13164  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::get_Value()
0x13169  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0x1316e  stloc.s  8
0x13170  ldarg.0
0x13171  ldloc.1
0x13172  newobj   instance void NamespaceComparer::.ctor(class System.Xaml.MS.Impl.XmlNsInfo nsInfo, class [mscorlib]System.Reflection.Assembly assembly)
0x13177  stloc.s  9
0x13179  ldloc.s  8
0x1317b  ldloc.s  9
0x1317d  ldftn    instance int32 NamespaceComparer::CompareNamespacesByPreference(string ns1, string ns2)
0x13183  newobj   instance void class [mscorlib]System.Comparison`1<string>::.ctor(object, native int)
0x13188  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x1318d  ldloca.s 7
0x1318f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::get_Key()
0x13194  ldloc.2
0x13195  call     string System.Xaml.Schema.ClrNamespaceUriParser::GetUri(string clrNs, string assemblyName)
0x1319a  stloc.s  0xA
0x1319c  ldloc.s  8
0x1319e  ldloc.s  0xA
0x131a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x131a5  ldloc.s  6
0x131a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x131ac  brtrue.s loc_13159
0x131ae  leave.s  loc_131BC
0x131b0  ldloc.s  6
0x131b2  brfalse.s loc_131BB
0x131b4  ldloc.s  6
0x131b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x131bb  endfinally
0x131bc  ldarg.0
0x131bd  ldloc.0
0x131be  call     instance void System.Xaml.MS.Impl.XmlNsInfo::MakeListsImmutable(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> dict)
0x131c3  ldloc.0
0x131c4  ret
```
