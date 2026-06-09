# System.Windows.Media.LanguageSpecificStringDictionary::CopyTo

- ea: `0x79b90`
- end: `0x79c20`
- name: `System.Windows.Media.LanguageSpecificStringDictionary::CopyTo`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x79b90`
- `0x146e70`

## string_xrefs

- `0x79bb3`: `Collection_CopyTo_IndexGreaterThanOrEqualToArrayLength`
- `0x79beb`: `Collection_CopyTo_NumberOfElementsExceedsArrayLength`

## pseudocode

```c

```

## disassembly

```asm
0x79b90  ldarg.1
0x79b91  brtrue.s loc_79B9E
0x79b93  ldstr    aArray// "array"
0x79b98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x79b9d  throw
0x79b9e  ldarg.2
0x79b9f  ldc.i4.0
0x79ba0  bge.s    loc_79BAD
0x79ba2  ldstr    aIndex// "index"
0x79ba7  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x79bac  throw
0x79bad  ldarg.2
0x79bae  ldarg.1
0x79baf  ldlen
0x79bb0  conv.i4
0x79bb1  blt.s    loc_79BD9
0x79bb3  ldstr    aCollectionCopy// "Collection_CopyTo_IndexGreaterThanOrEqu"...
0x79bb8  ldc.i4.2
0x79bb9  newarr   [mscorlib]System.Object
0x79bbe  dup
0x79bbf  ldc.i4.0
0x79bc0  ldstr    aIndex// "index"
0x79bc5  stelem.ref
0x79bc6  dup
0x79bc7  ldc.i4.1
0x79bc8  ldstr    aArray// "array"
0x79bcd  stelem.ref
0x79bce  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x79bd3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79bd8  throw
0x79bd9  ldarg.0
0x79bda  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.XmlLanguage, string> System.Windows.Media.LanguageSpecificStringDictionary::_innerDictionary
0x79bdf  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::get_Count()
0x79be4  ldarg.1
0x79be5  ldlen
0x79be6  conv.i4
0x79be7  ldarg.2
0x79be8  sub
0x79be9  ble.s    loc_79C12
0x79beb  ldstr    aCollectionCopy_0// "Collection_CopyTo_NumberOfElementsExcee"...
0x79bf0  ldc.i4.2
0x79bf1  newarr   [mscorlib]System.Object
0x79bf6  dup
0x79bf7  ldc.i4.0
0x79bf8  ldarg.2
0x79bf9  box      [mscorlib]System.Int32
0x79bfe  stelem.ref
0x79bff  dup
0x79c00  ldc.i4.1
0x79c01  ldstr    aArray// "array"
0x79c06  stelem.ref
0x79c07  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x79c0c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79c11  throw
0x79c12  ldarg.0
0x79c13  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class System.Windows.Markup.XmlLanguage, string> System.Windows.Media.LanguageSpecificStringDictionary::_innerDictionary
0x79c18  ldarg.1
0x79c19  ldarg.2
0x79c1a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class System.Windows.Markup.XmlLanguage, string>>::CopyTo(var<u1>[], !!T0)
0x79c1f  ret
```
