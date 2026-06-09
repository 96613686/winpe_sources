# System.Windows.Media.LanguageSpecificStringDictionary::System.Collections.ICollection.CopyTo

- ea: `0x79c50`
- end: `0x79ddb`
- name: `System.Windows.Media.LanguageSpecificStringDictionary::System.Collections.ICollection.CopyTo`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x79c50`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x79c76`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x79cb1`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`
- `0x79d37`: `Collection_CopyTo_ArrayCannotBeMultidimensional`

## pseudocode

```c

```

## disassembly

```asm
0x79c50  ldarg.1
0x79c51  brtrue.s loc_79C5E
0x79c53  ldstr    aArray// "array"
0x79c58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x79c5d  throw
0x79c5e  ldarg.2
0x79c5f  ldc.i4.0
0x79c60  bge.s    loc_79C6D
0x79c62  ldstr    aIndex// "index"
0x79c67  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x79c6c  throw
0x79c6d  ldarg.2
0x79c6e  ldarg.1
0x79c6f  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x79c74  blt.s    loc_79C9C
0x79c76  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x79c7b  ldc.i4.2
0x79c7c  newarr   [mscorlib]System.Object
0x79c81  dup
0x79c82  ldc.i4.0
0x79c83  ldstr    aIndex// "index"
0x79c88  stelem.ref
0x79c89  dup
0x79c8a  ldc.i4.1
0x79c8b  ldstr    aArray// "array"
0x79c90  stelem.ref
0x79c91  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x79c96  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79c9b  throw
0x79c9c  ldarg.0
0x79c9d  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.XmlLanguage, string> System.Windows.Media.LanguageSpecificStringDictionary::_innerDictionary
0x79ca2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::get_Count()
0x79ca7  ldarg.1
0x79ca8  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x79cad  ldarg.2
0x79cae  sub
0x79caf  ble.s    loc_79CD8
0x79cb1  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x79cb6  ldc.i4.2
0x79cb7  newarr   [mscorlib]System.Object
0x79cbc  dup
0x79cbd  ldc.i4.0
0x79cbe  ldarg.2
0x79cbf  box      [mscorlib]System.Int32
0x79cc4  stelem.ref
0x79cc5  dup
0x79cc6  ldc.i4.1
0x79cc7  ldstr    aArray// "array"
0x79ccc  stelem.ref
0x79ccd  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x79cd2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79cd7  throw
0x79cd8  ldarg.1
0x79cd9  isinst   valuetype [mscorlib]System.Collections.DictionaryEntry[]
0x79cde  stloc.3
0x79cdf  ldloc.3
0x79ce0  brfalse.s loc_79D2E
0x79ce2  ldarg.0
0x79ce3  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.XmlLanguage, string> System.Windows.Media.LanguageSpecificStringDictionary::_innerDictionary
0x79ce8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::GetEnumerator()
0x79ced  stloc.1
0x79cee  br.s     loc_79D17
0x79cf0  ldloc.1
0x79cf1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::get_Current()
0x79cf6  stloc.s  5
0x79cf8  ldloc.3
0x79cf9  ldarg.2
0x79cfa  dup
0x79cfb  ldc.i4.1
0x79cfc  add
0x79cfd  starg.s  2
0x79cff  ldloca.s 5
0x79d01  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>::get_Key()
0x79d06  ldloca.s 5
0x79d08  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>::get_Value()
0x79d0d  newobj   instance void [mscorlib]System.Collections.DictionaryEntry::.ctor(object, object)
0x79d12  stelem   [mscorlib]System.Collections.DictionaryEntry
0x79d17  ldloc.1
0x79d18  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x79d1d  brtrue.s loc_79CF0
0x79d1f  leave    loc_79DDA
0x79d24  ldloc.1
0x79d25  brfalse.s loc_79D2D
0x79d27  ldloc.1
0x79d28  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79d2d  endfinally
0x79d2e  ldarg.1
0x79d2f  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x79d34  ldc.i4.1
0x79d35  beq.s    loc_79D47
0x79d37  ldstr    aCollectionCopy_1// "Collection_CopyTo_ArrayCannotBeMultidim"...
0x79d3c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x79d41  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79d46  throw
0x79d47  ldarg.1
0x79d48  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x79d4d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x79d52  stloc.2
0x79d53  ldloc.2
0x79d54  ldtoken  [mscorlib]System.Collections.DictionaryEntry
0x79d59  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x79d5e  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x79d63  brtrue.s loc_79D8C
0x79d65  ldstr    aCannotconvertt// "CannotConvertType"
0x79d6a  ldc.i4.2
0x79d6b  newarr   [mscorlib]System.Object
0x79d70  dup
0x79d71  ldc.i4.0
0x79d72  ldtoken  [mscorlib]System.Collections.DictionaryEntry
0x79d77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x79d7c  stelem.ref
0x79d7d  dup
0x79d7e  ldc.i4.1
0x79d7f  ldloc.2
0x79d80  stelem.ref
0x79d81  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x79d86  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79d8b  throw
0x79d8c  ldarg.0
0x79d8d  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.XmlLanguage, string> System.Windows.Media.LanguageSpecificStringDictionary::_innerDictionary
0x79d92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::GetEnumerator()
0x79d97  stloc.0
0x79d98  br.s     loc_79DC6
0x79d9a  ldloc.0
0x79d9b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::get_Current()
0x79da0  stloc.s  4
0x79da2  ldarg.1
0x79da3  ldloca.s 4
0x79da5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>::get_Key()
0x79daa  ldloca.s 4
0x79dac  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>::get_Value()
0x79db1  newobj   instance void [mscorlib]System.Collections.DictionaryEntry::.ctor(object, object)
0x79db6  box      [mscorlib]System.Collections.DictionaryEntry
0x79dbb  ldarg.2
0x79dbc  dup
0x79dbd  ldc.i4.1
0x79dbe  add
0x79dbf  starg.s  2
0x79dc1  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x79dc6  ldloc.0
0x79dc7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x79dcc  brtrue.s loc_79D9A
0x79dce  leave.s  loc_79DDA
0x79dd0  ldloc.0
0x79dd1  brfalse.s loc_79DD9
0x79dd3  ldloc.0
0x79dd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79dd9  endfinally
0x79dda  ret
```
