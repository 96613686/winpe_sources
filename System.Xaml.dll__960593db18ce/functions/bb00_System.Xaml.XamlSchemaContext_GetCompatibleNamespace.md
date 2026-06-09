# System.Xaml.XamlSchemaContext::GetCompatibleNamespace

- ea: `0xbb00`
- end: `0xbbe3`
- name: `System.Xaml.XamlSchemaContext::GetCompatibleNamespace`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbaa0`

## callees

- `0x12d0`
- `0x87c0`
- `0xbb00`
- `0xbf40`
- `0xc230`
- `0x11f50`
- `0x12df0`
- `0x12e70`

## string_xrefs

- `0xbb8a`: `DuplicateXmlnsCompatAcrossAssemblies`

## pseudocode

```c

```

## disassembly

```asm
0xbb00  ldnull
0xbb01  stloc.0
0xbb02  ldnull
0xbb03  stloc.1
0xbb04  ldarg.0
0xbb05  ldfld    object System.Xaml.XamlSchemaContext::_syncExaminingAssemblies
0xbb0a  stloc.2
0xbb0b  ldc.i4.0
0xbb0c  stloc.3
0xbb0d  ldloc.2
0xbb0e  ldloca.s 3
0xbb10  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xbb15  ldarg.0
0xbb16  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.MS.Impl.XmlNsInfo> System.Xaml.XamlSchemaContext::EnumerateXmlnsInfos()
0xbb1b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.MS.Impl.XmlNsInfo>::GetEnumerator()
0xbb20  stloc.s  4
0xbb22  br       loc_BBBD
0xbb27  ldloc.s  4
0xbb29  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.MS.Impl.XmlNsInfo>::get_Current()
0xbb2e  stloc.s  5
0xbb30  ldloc.s  5
0xbb32  callvirt instance class [mscorlib]System.Reflection.Assembly System.Xaml.MS.Impl.XmlNsInfo::get_Assembly()
0xbb37  stloc.s  6
0xbb39  ldloc.s  6
0xbb3b  ldnull
0xbb3c  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0xbb41  brtrue.s loc_BBBD
0xbb43  ldnull
0xbb44  stloc.s  7
0xbb46  ldarg.0
0xbb47  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.Reflection.Assembly> System.Xaml.XamlSchemaContext::get_ReferenceAssemblies()
0xbb4c  brtrue.s loc_BB68
0xbb4e  ldloc.s  5
0xbb50  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.MS.Impl.XmlNsInfo::get_OldToNewNs()
0xbb55  stloc.s  7
0xbb57  leave.s  loc_BB71
0xbb59  stloc.s  9
0xbb5b  ldloc.s  9
0xbb5d  call     bool System.Xaml.CriticalExceptions::IsCriticalException(class [mscorlib]System.Exception ex)
0xbb62  brfalse.s loc_BB66
0xbb64  rethrow
0xbb66  leave.s  loc_BBBD
0xbb68  ldloc.s  5
0xbb6a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.MS.Impl.XmlNsInfo::get_OldToNewNs()
0xbb6f  stloc.s  7
0xbb71  ldloc.s  7
0xbb73  ldarg.1
0xbb74  ldloca.s 8
0xbb76  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0xbb7b  brfalse.s loc_BBBD
0xbb7d  ldloc.0
0xbb7e  brfalse.s loc_BBB7
0xbb80  ldloc.0
0xbb81  ldloc.s  8
0xbb83  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbb88  brfalse.s loc_BBB7
0xbb8a  ldstr    aDuplicatexmlns// "DuplicateXmlnsCompatAcrossAssemblies"
0xbb8f  ldc.i4.3
0xbb90  newarr   [mscorlib]System.Object
0xbb95  dup
0xbb96  ldc.i4.0
0xbb97  ldloc.1
0xbb98  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0xbb9d  stelem.ref
0xbb9e  dup
0xbb9f  ldc.i4.1
0xbba0  ldloc.s  6
0xbba2  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0xbba7  stelem.ref
0xbba8  dup
0xbba9  ldc.i4.2
0xbbaa  ldarg.1
0xbbab  stelem.ref
0xbbac  call     string System.Xaml.SR::Get(string id, object[] args)
0xbbb1  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0xbbb6  throw
0xbbb7  ldloc.s  8
0xbbb9  stloc.0
0xbbba  ldloc.s  6
0xbbbc  stloc.1
0xbbbd  ldloc.s  4
0xbbbf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbbc4  brtrue   loc_BB27
0xbbc9  leave.s  loc_BBE1
0xbbcb  ldloc.s  4
0xbbcd  brfalse.s loc_BBD6
0xbbcf  ldloc.s  4
0xbbd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbbd6  endfinally
0xbbd7  ldloc.3
0xbbd8  brfalse.s loc_BBE0
0xbbda  ldloc.2
0xbbdb  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xbbe0  endfinally
0xbbe1  ldloc.0
0xbbe2  ret
```
