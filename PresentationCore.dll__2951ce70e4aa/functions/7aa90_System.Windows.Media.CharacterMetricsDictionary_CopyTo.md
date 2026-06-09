# System.Windows.Media.CharacterMetricsDictionary::CopyTo

- ea: `0x7aa90`
- end: `0x7ab5d`
- name: `System.Windows.Media.CharacterMetricsDictionary::CopyTo`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x7aa90`
- `0x146e70`

## string_xrefs

- `0x7aab3`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x7ab09`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`

## pseudocode

```c

```

## disassembly

```asm
0x7aa90  ldarg.1
0x7aa91  brtrue.s loc_7AA9E
0x7aa93  ldstr    aArray// "array"
0x7aa98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7aa9d  throw
0x7aa9e  ldarg.2
0x7aa9f  ldc.i4.0
0x7aaa0  bge.s    loc_7AAAD
0x7aaa2  ldstr    aIndex// "index"
0x7aaa7  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x7aaac  throw
0x7aaad  ldarg.2
0x7aaae  ldarg.1
0x7aaaf  ldlen
0x7aab0  conv.i4
0x7aab1  blt.s    loc_7AAD9
0x7aab3  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x7aab8  ldc.i4.2
0x7aab9  newarr   [mscorlib]System.Object
0x7aabe  dup
0x7aabf  ldc.i4.0
0x7aac0  ldstr    aIndex// "index"
0x7aac5  stelem.ref
0x7aac6  dup
0x7aac7  ldc.i4.1
0x7aac8  ldstr    aArray// "array"
0x7aacd  stelem.ref
0x7aace  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7aad3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7aad8  throw
0x7aad9  ldarg.0
0x7aada  ldfld    class System.Windows.Media.CharacterMetrics[][] System.Windows.Media.CharacterMetricsDictionary::_pageTable
0x7aadf  stloc.s  4
0x7aae1  ldloc.s  4
0x7aae3  brfalse  loc_7AB5C
0x7aae8  ldarg.2
0x7aae9  stloc.3
0x7aaea  ldc.i4.0
0x7aaeb  stloc.1
0x7aaec  br.s     loc_7AB55
0x7aaee  ldloc.s  4
0x7aaf0  ldloc.1
0x7aaf1  ldelem.ref
0x7aaf2  stloc.2
0x7aaf3  ldloc.2
0x7aaf4  brfalse.s loc_7AB51
0x7aaf6  ldc.i4.0
0x7aaf7  stloc.0
0x7aaf8  br.s     loc_7AB4B
0x7aafa  ldloc.2
0x7aafb  ldloc.0
0x7aafc  ldelem.ref
0x7aafd  stloc.s  5
0x7aaff  ldloc.s  5
0x7ab01  brfalse.s loc_7AB47
0x7ab03  ldloc.3
0x7ab04  ldarg.1
0x7ab05  ldlen
0x7ab06  conv.i4
0x7ab07  blt.s    loc_7AB30
0x7ab09  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x7ab0e  ldc.i4.2
0x7ab0f  newarr   [mscorlib]System.Object
0x7ab14  dup
0x7ab15  ldc.i4.0
0x7ab16  ldarg.2
0x7ab17  box      [mscorlib]System.Int32
0x7ab1c  stelem.ref
0x7ab1d  dup
0x7ab1e  ldc.i4.1
0x7ab1f  ldstr    aArray// "array"
0x7ab24  stelem.ref
0x7ab25  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x7ab2a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7ab2f  throw
0x7ab30  ldarg.1
0x7ab31  ldloc.3
0x7ab32  dup
0x7ab33  ldc.i4.1
0x7ab34  add
0x7ab35  stloc.3
0x7ab36  ldloc.1
0x7ab37  ldc.i4.8
0x7ab38  shl
0x7ab39  ldloc.0
0x7ab3a  or
0x7ab3b  ldloc.s  5
0x7ab3d  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>::.ctor(var<u1>, !!T0)
0x7ab42  stelem   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class System.Windows.Media.CharacterMetrics>
0x7ab47  ldloc.0
0x7ab48  ldc.i4.1
0x7ab49  add
0x7ab4a  stloc.0
0x7ab4b  ldloc.0
0x7ab4c  ldloc.2
0x7ab4d  ldlen
0x7ab4e  conv.i4
0x7ab4f  blt.s    loc_7AAFA
0x7ab51  ldloc.1
0x7ab52  ldc.i4.1
0x7ab53  add
0x7ab54  stloc.1
0x7ab55  ldloc.1
0x7ab56  ldloc.s  4
0x7ab58  ldlen
0x7ab59  conv.i4
0x7ab5a  blt.s    loc_7AAEE
0x7ab5c  ret
```
