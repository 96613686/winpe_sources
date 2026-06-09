# System.Windows.Input.CommandBindingCollection::Insert

- ea: `0x30e90`
- end: `0x30eba`
- name: `System.Windows.Input.CommandBindingCollection::Insert`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x30d30`

## callees

- `0x30e90`
- `0x146e40`

## string_xrefs

- `0x30ea9`: `CollectionOnlyAcceptsCommandBindings`

## pseudocode

```c

```

## disassembly

```asm
0x30e90  ldarg.2
0x30e91  brfalse.s loc_30EA9
0x30e93  ldarg.0
0x30e94  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30e99  brfalse.s loc_30EB9
0x30e9b  ldarg.0
0x30e9c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding> System.Windows.Input.CommandBindingCollection::_innerCBList
0x30ea1  ldarg.1
0x30ea2  ldarg.2
0x30ea3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.CommandBinding>::Insert(int32, var<u1>)
0x30ea8  ret
0x30ea9  ldstr    aCollectiononly// "CollectionOnlyAcceptsCommandBindings"
0x30eae  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x30eb3  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x30eb8  throw
0x30eb9  ret
```
