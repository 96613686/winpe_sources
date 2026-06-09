# System.Windows.Input.CommandBindingCollection::AddRange

- ea: `0x30e20`
- end: `0x30e8f`
- name: `System.Windows.Input.CommandBindingCollection::AddRange`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x30cc0`

## callees

- `0x30e20`
- `0x146e40`

## string_xrefs

- `0x30e76`: `CollectionOnlyAcceptsCommandBindings`

## pseudocode

```c

```

## disassembly

```asm
0x30e20  ldarg.1
0x30e21  brtrue.s loc_30E2E
0x30e23  ldstr    aCollection// "collection"
0x30e28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30e2d  throw
0x30e2e  ldarg.1
0x30e2f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x30e34  ldc.i4.0
0x30e35  ble.s    loc_30E8E
0x30e37  ldarg.0
0x30e38  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30e3d  brtrue.s loc_30E50
0x30e3f  ldarg.0
0x30e40  ldarg.1
0x30e41  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x30e46  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding>::.ctor(int32)
0x30e4b  stfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30e50  ldarg.1
0x30e51  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x30e56  stloc.1
0x30e57  br.s     loc_30E86
0x30e59  ldloc.1
0x30e5a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x30e5f  isinst   System.Windows.Input.CommandBinding
0x30e64  stloc.0
0x30e65  ldloc.0
0x30e66  brfalse.s loc_30E76
0x30e68  ldarg.0
0x30e69  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30e6e  ldloc.0
0x30e6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding>::Add(var<u1>)
0x30e74  br.s     loc_30E86
0x30e76  ldstr    aCollectiononly// "CollectionOnlyAcceptsCommandBindings"
0x30e7b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x30e80  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x30e85  throw
0x30e86  ldloc.1
0x30e87  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30e8c  brtrue.s loc_30E59
0x30e8e  ret
```
