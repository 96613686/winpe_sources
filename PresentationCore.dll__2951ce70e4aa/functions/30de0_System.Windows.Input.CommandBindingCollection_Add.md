# System.Windows.Input.CommandBindingCollection::Add

- ea: `0x30de0`
- end: `0x30e15`
- name: `System.Windows.Input.CommandBindingCollection::Add`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x30d40`
- `0x312c0`

## callees

- `0x30de0`
- `0x146e40`

## string_xrefs

- `0x30e05`: `CollectionOnlyAcceptsCommandBindings`

## pseudocode

```c

```

## disassembly

```asm
0x30de0  ldarg.1
0x30de1  brfalse.s loc_30E05
0x30de3  ldarg.0
0x30de4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30de9  brtrue.s loc_30DF7
0x30deb  ldarg.0
0x30dec  ldc.i4.1
0x30ded  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding>::.ctor(int32)
0x30df2  stfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30df7  ldarg.0
0x30df8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30dfd  ldarg.1
0x30dfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding>::Add(var<u1>)
0x30e03  ldc.i4.0
0x30e04  ret
0x30e05  ldstr    aCollectiononly// "CollectionOnlyAcceptsCommandBindings"
0x30e0a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x30e0f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x30e14  throw
```
