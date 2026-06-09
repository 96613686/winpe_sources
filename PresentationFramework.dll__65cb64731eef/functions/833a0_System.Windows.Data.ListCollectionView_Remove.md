# System.Windows.Data.ListCollectionView::Remove

- ea: `0x833a0`
- end: `0x833e9`
- name: `System.Windows.Data.ListCollectionView::Remove`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x38c70`
- `0x80450`
- `0x832a0`
- `0x833a0`
- `0x833f0`
- `0x83770`
- `0x84370`

## string_xrefs

- `0x833b0`: `MemberNotAllowedDuringAddOrEdit`
- `0x833bd`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x833a0  ldarg.0
0x833a1  call     instance bool System.Windows.Data.ListCollectionView::get_IsEditingItem()
0x833a6  brtrue.s loc_833B0
0x833a8  ldarg.0
0x833a9  call     instance bool System.Windows.Data.ListCollectionView::get_IsAddingNew()
0x833ae  brfalse.s loc_833CE
0x833b0  ldstr    aMembernotallow// "MemberNotAllowedDuringAddOrEdit"
0x833b5  ldc.i4.1
0x833b6  newarr   [mscorlib]System.Object
0x833bb  dup
0x833bc  ldc.i4.0
0x833bd  ldstr    aRemove// "Remove"
0x833c2  stelem.ref
0x833c3  call     string System.Windows.SR::Get(string id, object[] args)
0x833c8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x833cd  throw
0x833ce  ldarg.0
0x833cf  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x833d4  ldarg.0
0x833d5  ldarg.1
0x833d6  call     instance int32 System.Windows.Data.ListCollectionView::InternalIndexOf(object item)
0x833db  stloc.0
0x833dc  ldloc.0
0x833dd  ldc.i4.0
0x833de  blt.s    loc_833E8
0x833e0  ldarg.0
0x833e1  ldarg.1
0x833e2  ldloc.0
0x833e3  call     instance void System.Windows.Data.ListCollectionView::RemoveImpl(object item, int32 index)
0x833e8  ret
```
