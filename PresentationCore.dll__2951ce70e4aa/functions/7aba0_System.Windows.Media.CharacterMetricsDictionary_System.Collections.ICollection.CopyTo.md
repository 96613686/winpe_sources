# System.Windows.Media.CharacterMetricsDictionary::System.Collections.ICollection.CopyTo

- ea: `0x7aba0`
- end: `0x7ad26`
- name: `System.Windows.Media.CharacterMetricsDictionary::System.Collections.ICollection.CopyTo`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x7a9c0`
- `0x7aa00`
- `0x7aba0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x7abc6`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x7abfc`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`
- `0x7ac82`: `Collection_CopyTo_ArrayCannotBeMultidimensional`

## pseudocode

```c

```

## disassembly

```asm
0x7aba0  ldarg.1
0x7aba1  brtrue.s loc_7ABAE
0x7aba3  ldstr    aArray// "array"
0x7aba8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7abad  throw
0x7abae  ldarg.2
0x7abaf  ldc.i4.0
0x7abb0  bge.s    loc_7ABBD
0x7abb2  ldstr    aIndex// "index"
0x7abb7  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x7abbc  throw
0x7abbd  ldarg.2
0x7abbe  ldarg.1
0x7abbf  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x7abc4  blt.s    loc_7ABEC
0x7abc6  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x7abcb  ldc.i4.2
0x7abcc  newarr   [mscorlib]System.Object
0x7abd1  dup
0x7abd2  ldc.i4.0
0x7abd3  ldstr    aIndex// "index"
0x7abd8  stelem.ref
0x7abd9  dup
0x7abda  ldc.i4.1
0x7abdb  ldstr    aArray// "array"
0x7abe0  stelem.ref
0x7abe1  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7abe6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7abeb  throw
0x7abec  ldarg.0
0x7abed  call     instance int32 System.Windows.Media.CharacterMetricsDictionary::get_Count()
0x7abf2  ldarg.1
0x7abf3  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x7abf8  ldarg.2
0x7abf9  sub
0x7abfa  ble.s    loc_7AC23
0x7abfc  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x7ac01  ldc.i4.2
0x7ac02  newarr   [mscorlib]System.Object
0x7ac07  dup
0x7ac08  ldc.i4.0
0x7ac09  ldarg.2
0x7ac0a  box      [mscorlib]System.Int32
0x7ac0f  stelem.ref
0x7ac10  dup
0x7ac11  ldc.i4.1
0x7ac12  ldstr    aArray// "array"
0x7ac17  stelem.ref
0x7ac18  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7ac1d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7ac22  throw
0x7ac23  ldarg.1
0x7ac24  isinst   valuetype [mscorlib]System.Collections.DictionaryEntry[]
0x7ac29  stloc.3
0x7ac2a  ldloc.3
0x7ac2b  brfalse.s loc_7AC79
0x7ac2d  ldarg.0
0x7ac2e  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>> System.Windows.Media.CharacterMetricsDictionary::GetEnumerator()
0x7ac33  stloc.1
0x7ac34  br.s     loc_7AC62
0x7ac36  ldloc.1
0x7ac37  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>>::get_Current()
0x7ac3c  stloc.s  5
0x7ac3e  ldloc.3
0x7ac3f  ldarg.2
0x7ac40  dup
0x7ac41  ldc.i4.1
0x7ac42  add
0x7ac43  starg.s  2
0x7ac45  ldloca.s 5
0x7ac47  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>::get_Key()
0x7ac4c  box      [mscorlib]System.Int32
0x7ac51  ldloca.s 5
0x7ac53  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>::get_Value()
0x7ac58  newobj   instance void [mscorlib]System.Collections.DictionaryEntry::.ctor(object, object)
0x7ac5d  stelem   [mscorlib]System.Collections.DictionaryEntry
0x7ac62  ldloc.1
0x7ac63  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7ac68  brtrue.s loc_7AC36
0x7ac6a  leave    loc_7AD25
0x7ac6f  ldloc.1
0x7ac70  brfalse.s loc_7AC78
0x7ac72  ldloc.1
0x7ac73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ac78  endfinally
0x7ac79  ldarg.1
0x7ac7a  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x7ac7f  ldc.i4.1
0x7ac80  beq.s    loc_7AC92
0x7ac82  ldstr    aCollectionCopy_1// "Collection_CopyTo_ArrayCannotBeMultidim"...
0x7ac87  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x7ac8c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7ac91  throw
0x7ac92  ldarg.1
0x7ac93  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7ac98  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x7ac9d  stloc.2
0x7ac9e  ldloc.2
0x7ac9f  ldtoken  [mscorlib]System.Collections.DictionaryEntry
0x7aca4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7aca9  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x7acae  brtrue.s loc_7ACD7
0x7acb0  ldstr    aCannotconvertt// "CannotConvertType"
0x7acb5  ldc.i4.2
0x7acb6  newarr   [mscorlib]System.Object
0x7acbb  dup
0x7acbc  ldc.i4.0
0x7acbd  ldtoken  [mscorlib]System.Collections.DictionaryEntry
0x7acc2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7acc7  stelem.ref
0x7acc8  dup
0x7acc9  ldc.i4.1
0x7acca  ldloc.2
0x7accb  stelem.ref
0x7accc  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7acd1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7acd6  throw
0x7acd7  ldarg.0
0x7acd8  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>> System.Windows.Media.CharacterMetricsDictionary::GetEnumerator()
0x7acdd  stloc.0
0x7acde  br.s     loc_7AD11
0x7ace0  ldloc.0
0x7ace1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>>::get_Current()
0x7ace6  stloc.s  4
0x7ace8  ldarg.1
0x7ace9  ldloca.s 4
0x7aceb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>::get_Key()
0x7acf0  box      [mscorlib]System.Int32
0x7acf5  ldloca.s 4
0x7acf7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>::get_Value()
0x7acfc  newobj   instance void [mscorlib]System.Collections.DictionaryEntry::.ctor(object, object)
0x7ad01  box      [mscorlib]System.Collections.DictionaryEntry
0x7ad06  ldarg.2
0x7ad07  dup
0x7ad08  ldc.i4.1
0x7ad09  add
0x7ad0a  starg.s  2
0x7ad0c  callvirt instance void [mscorlib]System.Array::SetValue(object, int32)
0x7ad11  ldloc.0
0x7ad12  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7ad17  brtrue.s loc_7ACE0
0x7ad19  leave.s  loc_7AD25
0x7ad1b  ldloc.0
0x7ad1c  brfalse.s loc_7AD24
0x7ad1e  ldloc.0
0x7ad1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7ad24  endfinally
0x7ad25  ret
```
