# System.Windows.Media.FamilyTypefaceCollection::CopyItems

- ea: `0x808e0`
- end: `0x809d5`
- name: `System.Windows.Media.FamilyTypefaceCollection::CopyItems`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x80460`
- `0x80470`

## callees

- `0x806f0`
- `0x808e0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x80955`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x8098b`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`
- `0x808f7`: `Collection_CopyTo_ArrayCannotBeMultidimensional`

## pseudocode

```c

```

## disassembly

```asm
0x808e0  ldarg.1
0x808e1  brtrue.s loc_808EE
0x808e3  ldstr    aArray// "array"
0x808e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x808ed  throw
0x808ee  ldarg.1
0x808ef  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x808f4  ldc.i4.1
0x808f5  beq.s    loc_80907
0x808f7  ldstr    aCollectionCopy_1// "Collection_CopyTo_ArrayCannotBeMultidim"...
0x808fc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x80901  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x80906  throw
0x80907  ldarg.1
0x80908  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8090d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x80912  stloc.0
0x80913  ldloc.0
0x80914  ldtoken  System.Windows.Media.FamilyTypeface
0x80919  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8091e  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x80923  brtrue.s loc_8094C
0x80925  ldstr    aCannotconvertt// "CannotConvertType"
0x8092a  ldc.i4.2
0x8092b  newarr   [mscorlib]System.Object
0x80930  dup
0x80931  ldc.i4.0
0x80932  ldtoken  class System.Windows.Media.FamilyTypeface[]
0x80937  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8093c  stelem.ref
0x8093d  dup
0x8093e  ldc.i4.1
0x8093f  ldloc.0
0x80940  stelem.ref
0x80941  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x80946  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x8094b  throw
0x8094c  ldarg.2
0x8094d  ldarg.1
0x8094e  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x80953  blt.s    loc_8097B
0x80955  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x8095a  ldc.i4.2
0x8095b  newarr   [mscorlib]System.Object
0x80960  dup
0x80961  ldc.i4.0
0x80962  ldstr    aIndex// "index"
0x80967  stelem.ref
0x80968  dup
0x80969  ldc.i4.1
0x8096a  ldstr    aArray// "array"
0x8096f  stelem.ref
0x80970  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x80975  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x8097a  throw
0x8097b  ldarg.0
0x8097c  ldfld    int32 System.Windows.Media.FamilyTypefaceCollection::_count
0x80981  ldarg.1
0x80982  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x80987  ldarg.2
0x80988  sub
0x80989  ble.s    loc_809B2
0x8098b  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x80990  ldc.i4.2
0x80991  newarr   [mscorlib]System.Object
0x80996  dup
0x80997  ldc.i4.0
0x80998  ldarg.2
0x80999  box      [mscorlib]System.Int32
0x8099e  stelem.ref
0x8099f  dup
0x809a0  ldc.i4.1
0x809a1  ldstr    aArray// "array"
0x809a6  stelem.ref
0x809a7  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x809ac  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x809b1  throw
0x809b2  ldarg.0
0x809b3  ldfld    int32 System.Windows.Media.FamilyTypefaceCollection::_count
0x809b8  brfalse.s loc_809D4
0x809ba  ldarg.0
0x809bb  call     instance void System.Windows.Media.FamilyTypefaceCollection::InitializeItemsFromInnerList()
0x809c0  ldarg.0
0x809c1  ldfld    class System.Windows.Media.FamilyTypeface[] System.Windows.Media.FamilyTypefaceCollection::_items
0x809c6  ldc.i4.0
0x809c7  ldarg.1
0x809c8  ldarg.2
0x809c9  ldarg.0
0x809ca  ldfld    int32 System.Windows.Media.FamilyTypefaceCollection::_count
0x809cf  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x809d4  ret
```
