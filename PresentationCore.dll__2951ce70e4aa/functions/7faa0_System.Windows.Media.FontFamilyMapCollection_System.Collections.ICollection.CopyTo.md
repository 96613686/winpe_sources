# System.Windows.Media.FontFamilyMapCollection::System.Collections.ICollection.CopyTo

- ea: `0x7faa0`
- end: `0x7fb8f`
- name: `System.Windows.Media.FontFamilyMapCollection::System.Collections.ICollection.CopyTo`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x7faa0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x7fb15`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x7fb4b`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`
- `0x7fab7`: `Collection_CopyTo_ArrayCannotBeMultidimensional`

## pseudocode

```c

```

## disassembly

```asm
0x7faa0  ldarg.1
0x7faa1  brtrue.s loc_7FAAE
0x7faa3  ldstr    aArray// "array"
0x7faa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7faad  throw
0x7faae  ldarg.1
0x7faaf  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x7fab4  ldc.i4.1
0x7fab5  beq.s    loc_7FAC7
0x7fab7  ldstr    aCollectionCopy_1// "Collection_CopyTo_ArrayCannotBeMultidim"...
0x7fabc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x7fac1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fac6  throw
0x7fac7  ldarg.1
0x7fac8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7facd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x7fad2  stloc.0
0x7fad3  ldloc.0
0x7fad4  ldtoken  System.Windows.Media.FamilyTypeface
0x7fad9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7fade  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x7fae3  brtrue.s loc_7FB0C
0x7fae5  ldstr    aCannotconvertt// "CannotConvertType"
0x7faea  ldc.i4.2
0x7faeb  newarr   [mscorlib]System.Object
0x7faf0  dup
0x7faf1  ldc.i4.0
0x7faf2  ldtoken  System.Windows.Media.FamilyTypeface
0x7faf7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7fafc  stelem.ref
0x7fafd  dup
0x7fafe  ldc.i4.1
0x7faff  ldloc.0
0x7fb00  stelem.ref
0x7fb01  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7fb06  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fb0b  throw
0x7fb0c  ldarg.2
0x7fb0d  ldarg.1
0x7fb0e  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x7fb13  blt.s    loc_7FB3B
0x7fb15  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x7fb1a  ldc.i4.2
0x7fb1b  newarr   [mscorlib]System.Object
0x7fb20  dup
0x7fb21  ldc.i4.0
0x7fb22  ldstr    aIndex// "index"
0x7fb27  stelem.ref
0x7fb28  dup
0x7fb29  ldc.i4.1
0x7fb2a  ldstr    aArray// "array"
0x7fb2f  stelem.ref
0x7fb30  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7fb35  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fb3a  throw
0x7fb3b  ldarg.0
0x7fb3c  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fb41  ldarg.1
0x7fb42  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x7fb47  ldarg.2
0x7fb48  sub
0x7fb49  ble.s    loc_7FB72
0x7fb4b  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x7fb50  ldc.i4.2
0x7fb51  newarr   [mscorlib]System.Object
0x7fb56  dup
0x7fb57  ldc.i4.0
0x7fb58  ldarg.2
0x7fb59  box      [mscorlib]System.Int32
0x7fb5e  stelem.ref
0x7fb5f  dup
0x7fb60  ldc.i4.1
0x7fb61  ldstr    aArray// "array"
0x7fb66  stelem.ref
0x7fb67  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7fb6c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fb71  throw
0x7fb72  ldarg.0
0x7fb73  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fb78  brfalse.s loc_7FB8E
0x7fb7a  ldarg.0
0x7fb7b  ldfld    class System.Windows.Media.FontFamilyMap[] System.Windows.Media.FontFamilyMapCollection::_items
0x7fb80  ldc.i4.0
0x7fb81  ldarg.1
0x7fb82  ldarg.2
0x7fb83  ldarg.0
0x7fb84  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fb89  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x7fb8e  ret
```
