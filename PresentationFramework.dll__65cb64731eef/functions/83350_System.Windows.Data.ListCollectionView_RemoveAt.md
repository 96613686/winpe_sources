# System.Windows.Data.ListCollectionView::RemoveAt

- ea: `0x83350`
- end: `0x83393`
- name: `System.Windows.Data.ListCollectionView::RemoveAt`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x38c70`
- `0x7fb60`
- `0x80450`
- `0x832a0`
- `0x83350`
- `0x833f0`
- `0x83770`

## string_xrefs

- `0x83360`: `MemberNotAllowedDuringAddOrEdit`
- `0x8336d`: `RemoveAt`

## pseudocode

```c

```

## disassembly

```asm
0x83350  ldarg.0
0x83351  call     instance bool System.Windows.Data.ListCollectionView::get_IsEditingItem()
0x83356  brtrue.s loc_83360
0x83358  ldarg.0
0x83359  call     instance bool System.Windows.Data.ListCollectionView::get_IsAddingNew()
0x8335e  brfalse.s loc_8337E
0x83360  ldstr    aMembernotallow// "MemberNotAllowedDuringAddOrEdit"
0x83365  ldc.i4.1
0x83366  newarr   [mscorlib]System.Object
0x8336b  dup
0x8336c  ldc.i4.0
0x8336d  ldstr    aRemoveat// "RemoveAt"
0x83372  stelem.ref
0x83373  call     string System.Windows.SR::Get(string id, object[] args)
0x83378  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8337d  throw
0x8337e  ldarg.0
0x8337f  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x83384  ldarg.0
0x83385  ldarg.0
0x83386  ldarg.1
0x83387  callvirt instance object System.Windows.Data.CollectionView::GetItemAt(int32 index)
0x8338c  ldarg.1
0x8338d  call     instance void System.Windows.Data.ListCollectionView::RemoveImpl(object item, int32 index)
0x83392  ret
```
