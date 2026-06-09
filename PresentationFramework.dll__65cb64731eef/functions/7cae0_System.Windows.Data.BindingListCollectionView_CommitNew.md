# System.Windows.Data.BindingListCollectionView::CommitNew

- ea: `0x7cae0`
- end: `0x7cb99`
- name: `System.Windows.Data.BindingListCollectionView::CommitNew`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x7c9c0`
- `0x7cee0`

## callees

- `0x38c70`
- `0x7c770`
- `0x7cae0`
- `0x7cc70`
- `0x7d090`
- `0x7e260`
- `0x7ec70`
- `0x80220`
- `0x80450`
- `0x2631e0`

## string_xrefs

- `0x7caf5`: `MemberNotAllowedDuringTransaction`
- `0x7cb02`: `CommitNew`

## pseudocode

```c

```

## disassembly

```asm
0x7cae0  newobj   instance void <>c__DisplayClass46_0::.ctor()
0x7cae5  stloc.0
0x7cae6  ldloc.0
0x7cae7  ldarg.0
0x7cae8  stfld    class System.Windows.Data.BindingListCollectionView <>c__DisplayClass46_0::<>4__this
0x7caed  ldarg.0
0x7caee  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsEditingItem()
0x7caf3  brfalse.s loc_7CB1B
0x7caf5  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x7cafa  ldc.i4.2
0x7cafb  newarr   [mscorlib]System.Object
0x7cb00  dup
0x7cb01  ldc.i4.0
0x7cb02  ldstr    aCommitnew// "CommitNew"
0x7cb07  stelem.ref
0x7cb08  dup
0x7cb09  ldc.i4.1
0x7cb0a  ldstr    aEdititem// "EditItem"
0x7cb0f  stelem.ref
0x7cb10  call     string System.Windows.SR::Get(string id, object[] args)
0x7cb15  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7cb1a  throw
0x7cb1b  ldarg.0
0x7cb1c  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x7cb21  ldarg.0
0x7cb22  ldfld    object System.Windows.Data.BindingListCollectionView::_newItem
0x7cb27  ldsfld   object System.Windows.Data.CollectionView::NoNewItem
0x7cb2c  bne.un.s loc_7CB2F
0x7cb2e  ret
0x7cb2f  ldloc.0
0x7cb30  ldarg.0
0x7cb31  call     instance class [System]System.ComponentModel.IBindingList System.Windows.Data.BindingListCollectionView::get_InternalList()
0x7cb36  isinst   [System]System.ComponentModel.ICancelAddNew
0x7cb3b  stfld    class [System]System.ComponentModel.ICancelAddNew <>c__DisplayClass46_0::ican
0x7cb40  ldarg.0
0x7cb41  call     instance class [System]System.ComponentModel.IBindingList System.Windows.Data.BindingListCollectionView::get_InternalList()
0x7cb46  ldloc.0
0x7cb47  ldftn    instance void <>c__DisplayClass46_0::<CommitNew>b__0()
0x7cb4d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7cb52  ldc.i4.1
0x7cb53  call     void System.Windows.Data.BindingOperations::AccessCollection(class [mscorlib]System.Collections.IEnumerable collection, class [mscorlib]System.Action accessMethod, bool writeAccess)
0x7cb58  ldarg.0
0x7cb59  ldfld    object System.Windows.Data.BindingListCollectionView::_newItem
0x7cb5e  ldsfld   object System.Windows.Data.CollectionView::NoNewItem
0x7cb63  beq.s    loc_7CB98
0x7cb65  ldarg.0
0x7cb66  call     instance valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::get_NewItemPlaceholderPosition()
0x7cb6b  ldc.i4.1
0x7cb6c  beq.s    loc_7CB71
0x7cb6e  ldc.i4.0
0x7cb6f  br.s     loc_7CB72
0x7cb71  ldc.i4.1
0x7cb72  stloc.1
0x7cb73  ldarg.0
0x7cb74  ldarg.0
0x7cb75  ldfld    int32 System.Windows.Data.BindingListCollectionView::_newItemIndex
0x7cb7a  ldarg.0
0x7cb7b  ldfld    int32 System.Windows.Data.BindingListCollectionView::_newItemIndex
0x7cb80  ldloc.1
0x7cb81  add
0x7cb82  call     instance class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs System.Windows.Data.BindingListCollectionView::ProcessCommitNew(int32 fromIndex, int32 toIndex)
0x7cb87  stloc.2
0x7cb88  ldloc.2
0x7cb89  brfalse.s loc_7CB98
0x7cb8b  ldarg.0
0x7cb8c  ldarg.0
0x7cb8d  call     instance class [System]System.ComponentModel.IBindingList System.Windows.Data.BindingListCollectionView::get_InternalList()
0x7cb92  ldloc.2
0x7cb93  call     instance void System.Windows.Data.CollectionView::OnCollectionChanged(object sender, class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args)
0x7cb98  ret
```
