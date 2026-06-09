# System.Windows.Markup.Localizer.BamlLocalizationDictionary::CopyTo

- ea: `0xb7ca0`
- end: `0xb7d75`
- name: `System.Windows.Markup.Localizer.BamlLocalizationDictionary::CopyTo`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0xb7e30`

## callees

- `0x38c40`
- `0x38c70`
- `0xb7c90`
- `0xb7ca0`
- `0xb7f40`

## string_xrefs

- `0xb7d03`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`
- `0xb7ccb`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`

## pseudocode

```c

```

## disassembly

```asm
0xb7ca0  ldarg.0
0xb7ca1  ldarg.1
0xb7ca2  ldstr    aArray// "array"
0xb7ca7  call     instance void System.Windows.Markup.Localizer.BamlLocalizationDictionary::CheckNonNullParam(object param, string paramName)
0xb7cac  ldarg.2
0xb7cad  ldc.i4.0
0xb7cae  bge.s    loc_B7CC5
0xb7cb0  ldstr    aArrayindex// "arrayIndex"
0xb7cb5  ldstr    aParametercanno// "ParameterCannotBeNegative"
0xb7cba  call     string System.Windows.SR::Get(string id)
0xb7cbf  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xb7cc4  throw
0xb7cc5  ldarg.2
0xb7cc6  ldarg.1
0xb7cc7  ldlen
0xb7cc8  conv.i4
0xb7cc9  blt.s    loc_B7CF6
0xb7ccb  ldstr    aCollectionCopy_0// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0xb7cd0  ldc.i4.2
0xb7cd1  newarr   [mscorlib]System.Object
0xb7cd6  dup
0xb7cd7  ldc.i4.0
0xb7cd8  ldstr    aArrayindex// "arrayIndex"
0xb7cdd  stelem.ref
0xb7cde  dup
0xb7cdf  ldc.i4.1
0xb7ce0  ldstr    aArray// "array"
0xb7ce5  stelem.ref
0xb7ce6  call     string System.Windows.SR::Get(string id, object[] args)
0xb7ceb  ldstr    aArrayindex// "arrayIndex"
0xb7cf0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb7cf5  throw
0xb7cf6  ldarg.0
0xb7cf7  call     instance int32 System.Windows.Markup.Localizer.BamlLocalizationDictionary::get_Count()
0xb7cfc  ldarg.1
0xb7cfd  ldlen
0xb7cfe  conv.i4
0xb7cff  ldarg.2
0xb7d00  sub
0xb7d01  ble.s    loc_B7D29
0xb7d03  ldstr    aCollectionCopy// "Collection_CopyTo_NumberOfElementsExcee"...
0xb7d08  ldc.i4.2
0xb7d09  newarr   [mscorlib]System.Object
0xb7d0e  dup
0xb7d0f  ldc.i4.0
0xb7d10  ldstr    aArrayindex// "arrayIndex"
0xb7d15  stelem.ref
0xb7d16  dup
0xb7d17  ldc.i4.1
0xb7d18  ldstr    aArray// "array"
0xb7d1d  stelem.ref
0xb7d1e  call     string System.Windows.SR::Get(string id, object[] args)
0xb7d23  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb7d28  throw
0xb7d29  ldarg.0
0xb7d2a  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.Localizer.BamlLocalizableResourceKey, class System.Windows.Markup.Localizer.BamlLocalizableResource> System.Windows.Markup.Localizer.BamlLocalizationDictionary::_dictionary
0xb7d2f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.Localizer.BamlLocalizableResourceKey, class System.Windows.Markup.Localizer.BamlLocalizableResource>>::GetEnumerator()
0xb7d34  stloc.0
0xb7d35  br.s     loc_B7D60
0xb7d37  ldloc.0
0xb7d38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.Localizer.BamlLocalizableResourceKey, class System.Windows.Markup.Localizer.BamlLocalizableResource>>::get_Current()
0xb7d3d  stloc.1
0xb7d3e  ldloca.s 2
0xb7d40  ldloca.s 1
0xb7d42  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.Localizer.BamlLocalizableResourceKey, class System.Windows.Markup.Localizer.BamlLocalizableResource>::get_Key()
0xb7d47  ldloca.s 1
0xb7d49  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.Localizer.BamlLocalizableResourceKey, class System.Windows.Markup.Localizer.BamlLocalizableResource>::get_Value()
0xb7d4e  call     instance void [mscorlib]System.Collections.DictionaryEntry::.ctor(object, object)
0xb7d53  ldarg.1
0xb7d54  ldarg.2
0xb7d55  dup
0xb7d56  ldc.i4.1
0xb7d57  add
0xb7d58  starg.s  2
0xb7d5a  ldloc.2
0xb7d5b  stelem   [mscorlib]System.Collections.DictionaryEntry
0xb7d60  ldloc.0
0xb7d61  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb7d66  brtrue.s loc_B7D37
0xb7d68  leave.s  loc_B7D74
0xb7d6a  ldloc.0
0xb7d6b  brfalse.s loc_B7D73
0xb7d6d  ldloc.0
0xb7d6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb7d73  endfinally
0xb7d74  ret
```
