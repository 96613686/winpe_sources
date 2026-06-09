# System.Windows.Media.FontFamilyMapCollection::CopyTo

- ea: `0x7fa10`
- end: `0x7fa9b`
- name: `System.Windows.Media.FontFamilyMapCollection::CopyTo`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x7fa10`
- `0x146e70`

## string_xrefs

- `0x7fa24`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x7fa57`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`

## pseudocode

```c

```

## disassembly

```asm
0x7fa10  ldarg.1
0x7fa11  brtrue.s loc_7FA1E
0x7fa13  ldstr    aArray// "array"
0x7fa18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fa1d  throw
0x7fa1e  ldarg.2
0x7fa1f  ldarg.1
0x7fa20  ldlen
0x7fa21  conv.i4
0x7fa22  blt.s    loc_7FA4A
0x7fa24  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x7fa29  ldc.i4.2
0x7fa2a  newarr   [mscorlib]System.Object
0x7fa2f  dup
0x7fa30  ldc.i4.0
0x7fa31  ldstr    aIndex// "index"
0x7fa36  stelem.ref
0x7fa37  dup
0x7fa38  ldc.i4.1
0x7fa39  ldstr    aArray// "array"
0x7fa3e  stelem.ref
0x7fa3f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7fa44  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fa49  throw
0x7fa4a  ldarg.0
0x7fa4b  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fa50  ldarg.1
0x7fa51  ldlen
0x7fa52  conv.i4
0x7fa53  ldarg.2
0x7fa54  sub
0x7fa55  ble.s    loc_7FA7E
0x7fa57  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x7fa5c  ldc.i4.2
0x7fa5d  newarr   [mscorlib]System.Object
0x7fa62  dup
0x7fa63  ldc.i4.0
0x7fa64  ldarg.2
0x7fa65  box      [mscorlib]System.Int32
0x7fa6a  stelem.ref
0x7fa6b  dup
0x7fa6c  ldc.i4.1
0x7fa6d  ldstr    aArray// "array"
0x7fa72  stelem.ref
0x7fa73  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7fa78  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7fa7d  throw
0x7fa7e  ldarg.0
0x7fa7f  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fa84  brfalse.s loc_7FA9A
0x7fa86  ldarg.0
0x7fa87  ldfld    class System.Windows.Media.FontFamilyMap[] System.Windows.Media.FontFamilyMapCollection::_items
0x7fa8c  ldc.i4.0
0x7fa8d  ldarg.1
0x7fa8e  ldarg.2
0x7fa8f  ldarg.0
0x7fa90  ldfld    int32 System.Windows.Media.FontFamilyMapCollection::_count
0x7fa95  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x7fa9a  ret
```
