# System.Windows.Data.CollectionView::ValidateCollectionChangedEventArgs

- ea: `0x80ac0`
- end: `0x80bc9`
- name: `System.Windows.Data.CollectionView::ValidateCollectionChangedEventArgs`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x800a0`

## callees

- `0x38c40`
- `0x38c70`
- `0x80ac0`

## string_xrefs

- `0x80b94`: `CannotMoveToUnknownPosition`
- `0x80b31`: `RemovedItemNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x80ac0  ldarg.1
0x80ac1  callvirt instance valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_Action()
0x80ac6  stloc.0
0x80ac7  ldloc.0
0x80ac8  switch   loc_80AE6, loc_80B07, loc_80B41, loc_80B6D, loc_80BC8
0x80ae1  br       loc_80BA4
0x80ae6  ldarg.1
0x80ae7  callvirt instance class [mscorlib]System.Collections.IList [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_NewItems()
0x80aec  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x80af1  ldc.i4.1
0x80af2  beq      loc_80BC8
0x80af7  ldstr    aRangeactionsno// "RangeActionsNotSupported"
0x80afc  call     string System.Windows.SR::Get(string id)
0x80b01  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x80b06  throw
0x80b07  ldarg.1
0x80b08  callvirt instance class [mscorlib]System.Collections.IList [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_OldItems()
0x80b0d  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x80b12  ldc.i4.1
0x80b13  beq.s    loc_80B25
0x80b15  ldstr    aRangeactionsno// "RangeActionsNotSupported"
0x80b1a  call     string System.Windows.SR::Get(string id)
0x80b1f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x80b24  throw
0x80b25  ldarg.1
0x80b26  callvirt instance int32 [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_OldStartingIndex()
0x80b2b  ldc.i4.0
0x80b2c  bge      loc_80BC8
0x80b31  ldstr    aRemoveditemnot// "RemovedItemNotFound"
0x80b36  call     string System.Windows.SR::Get(string id)
0x80b3b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80b40  throw
0x80b41  ldarg.1
0x80b42  callvirt instance class [mscorlib]System.Collections.IList [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_NewItems()
0x80b47  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x80b4c  ldc.i4.1
0x80b4d  bne.un.s loc_80B5D
0x80b4f  ldarg.1
0x80b50  callvirt instance class [mscorlib]System.Collections.IList [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_OldItems()
0x80b55  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x80b5a  ldc.i4.1
0x80b5b  beq.s    loc_80BC8
0x80b5d  ldstr    aRangeactionsno// "RangeActionsNotSupported"
0x80b62  call     string System.Windows.SR::Get(string id)
0x80b67  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x80b6c  throw
0x80b6d  ldarg.1
0x80b6e  callvirt instance class [mscorlib]System.Collections.IList [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_NewItems()
0x80b73  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x80b78  ldc.i4.1
0x80b79  beq.s    loc_80B8B
0x80b7b  ldstr    aRangeactionsno// "RangeActionsNotSupported"
0x80b80  call     string System.Windows.SR::Get(string id)
0x80b85  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x80b8a  throw
0x80b8b  ldarg.1
0x80b8c  callvirt instance int32 [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_NewStartingIndex()
0x80b91  ldc.i4.0
0x80b92  bge.s    loc_80BC8
0x80b94  ldstr    aCannotmovetoun// "CannotMoveToUnknownPosition"
0x80b99  call     string System.Windows.SR::Get(string id)
0x80b9e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80ba3  throw
0x80ba4  ldstr    aUnexpectedcoll// "UnexpectedCollectionChangeAction"
0x80ba9  ldc.i4.1
0x80baa  newarr   [mscorlib]System.Object
0x80baf  dup
0x80bb0  ldc.i4.0
0x80bb1  ldarg.1
0x80bb2  callvirt instance valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::get_Action()
0x80bb7  box      [System]System.Collections.Specialized.NotifyCollectionChangedAction
0x80bbc  stelem.ref
0x80bbd  call     string System.Windows.SR::Get(string id, object[] args)
0x80bc2  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x80bc7  throw
0x80bc8  ret
```
