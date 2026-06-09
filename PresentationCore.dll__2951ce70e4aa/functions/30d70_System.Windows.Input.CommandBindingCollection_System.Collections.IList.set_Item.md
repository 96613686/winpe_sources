# System.Windows.Input.CommandBindingCollection::System.Collections.IList.set_Item

- ea: `0x30d70`
- end: `0x30d93`
- name: `System.Windows.Input.CommandBindingCollection::System.Collections.IList.set_Item`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x30d70`
- `0x30dc0`
- `0x146e40`

## string_xrefs

- `0x30d7a`: `CollectionOnlyAcceptsCommandBindings`

## pseudocode

```c

```

## disassembly

```asm
0x30d70  ldarg.2
0x30d71  isinst   System.Windows.Input.CommandBinding
0x30d76  stloc.0
0x30d77  ldloc.0
0x30d78  brtrue.s loc_30D8A
0x30d7a  ldstr    aCollectiononly// "CollectionOnlyAcceptsCommandBindings"
0x30d7f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x30d84  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x30d89  throw
0x30d8a  ldarg.0
0x30d8b  ldarg.1
0x30d8c  ldloc.0
0x30d8d  call     instance void System.Windows.Input.CommandBindingCollection::set_Item(int32 index, class System.Windows.Input.CommandBinding value)
0x30d92  ret
```
