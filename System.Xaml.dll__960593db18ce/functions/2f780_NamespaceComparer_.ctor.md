# NamespaceComparer::.ctor

- ea: `0x2f780`
- end: `0x2f82c`
- name: `NamespaceComparer::.ctor`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x130c0`

## callees

- `0x87c0`
- `0x11f50`
- `0x12e70`
- `0x2f780`
- `0x2f940`
- `0x2f960`

## string_xrefs

- `0x2f7d5`: `XmlnsCompatCycle`

## pseudocode

```c

```

## disassembly

```asm
0x2f780  ldarg.0
0x2f781  call     instance void [mscorlib]System.Object::.ctor()
0x2f786  ldarg.0
0x2f787  ldarg.1
0x2f788  stfld    class System.Xaml.MS.Impl.XmlNsInfo NamespaceComparer::_nsInfo
0x2f78d  ldarg.0
0x2f78e  ldarg.1
0x2f78f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.MS.Impl.XmlNsInfo::get_OldToNewNs()
0x2f794  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x2f799  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2f79e  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, int32> NamespaceComparer::_subsumeCount
0x2f7a3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2f7a8  stloc.0
0x2f7a9  ldarg.1
0x2f7aa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.MS.Impl.XmlNsInfo::get_OldToNewNs()
0x2f7af  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x2f7b4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, string>::GetEnumerator()
0x2f7b9  stloc.1
0x2f7ba  br.s     loc_2F812
0x2f7bc  ldloca.s 1
0x2f7be  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, string>::get_Current()
0x2f7c3  stloc.2
0x2f7c4  ldloc.0
0x2f7c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Clear()
0x2f7ca  ldloc.2
0x2f7cb  stloc.3
0x2f7cc  ldloc.0
0x2f7cd  ldloc.3
0x2f7ce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2f7d3  brfalse.s loc_2F7F8
0x2f7d5  ldstr    aXmlnscompatcyc// "XmlnsCompatCycle"
0x2f7da  ldc.i4.2
0x2f7db  newarr   [mscorlib]System.Object
0x2f7e0  dup
0x2f7e1  ldc.i4.0
0x2f7e2  ldarg.2
0x2f7e3  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x2f7e8  stelem.ref
0x2f7e9  dup
0x2f7ea  ldc.i4.1
0x2f7eb  ldloc.3
0x2f7ec  stelem.ref
0x2f7ed  call     string System.Xaml.SR::Get(string id, object[] args)
0x2f7f2  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0x2f7f7  throw
0x2f7f8  ldloc.0
0x2f7f9  ldloc.3
0x2f7fa  ldnull
0x2f7fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2f800  ldarg.0
0x2f801  ldloc.3
0x2f802  call     instance void NamespaceComparer::IncrementSubsumeCount(string ns)
0x2f807  ldarg.0
0x2f808  ldloc.3
0x2f809  call     instance string NamespaceComparer::GetNewNs(string oldNs)
0x2f80e  stloc.3
0x2f80f  ldloc.3
0x2f810  brtrue.s loc_2F7CC
0x2f812  ldloca.s 1
0x2f814  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, string>::MoveNext()
0x2f819  brtrue.s loc_2F7BC
0x2f81b  leave.s  loc_2F82B
0x2f81d  ldloca.s 1
0x2f81f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, string>
0x2f825  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f82a  endfinally
0x2f82b  ret
```
