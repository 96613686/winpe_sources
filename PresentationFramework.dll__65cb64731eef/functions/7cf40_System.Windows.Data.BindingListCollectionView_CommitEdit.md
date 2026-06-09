# System.Windows.Data.BindingListCollectionView::CommitEdit

- ea: `0x7cf40`
- end: `0x7cfe1`
- name: `System.Windows.Data.BindingListCollectionView::CommitEdit`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x7c9c0`
- `0x7cee0`

## callees

- `0x38c70`
- `0x7cd40`
- `0x7cf40`
- `0x7d0b0`
- `0x7e260`
- `0x7e650`
- `0x7e6d0`
- `0x7ec70`
- `0x80450`
- `0x263400`

## string_xrefs

- `0x7cf55`: `MemberNotAllowedDuringTransaction`
- `0x7cf62`: `CommitEdit`

## pseudocode

```c

```

## disassembly

```asm
0x7cf40  newobj   instance void <>c__DisplayClass62_0::.ctor()
0x7cf45  stloc.0
0x7cf46  ldloc.0
0x7cf47  ldarg.0
0x7cf48  stfld    class System.Windows.Data.BindingListCollectionView <>c__DisplayClass62_0::<>4__this
0x7cf4d  ldarg.0
0x7cf4e  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsAddingNew()
0x7cf53  brfalse.s loc_7CF7B
0x7cf55  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x7cf5a  ldc.i4.2
0x7cf5b  newarr   [mscorlib]System.Object
0x7cf60  dup
0x7cf61  ldc.i4.0
0x7cf62  ldstr    aCommitedit// "CommitEdit"
0x7cf67  stelem.ref
0x7cf68  dup
0x7cf69  ldc.i4.1
0x7cf6a  ldstr    aAddnew// "AddNew"
0x7cf6f  stelem.ref
0x7cf70  call     string System.Windows.SR::Get(string id, object[] args)
0x7cf75  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7cf7a  throw
0x7cf7b  ldarg.0
0x7cf7c  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x7cf81  ldarg.0
0x7cf82  ldfld    object System.Windows.Data.BindingListCollectionView::_editItem
0x7cf87  brtrue.s loc_7CF8A
0x7cf89  ret
0x7cf8a  ldloc.0
0x7cf8b  ldarg.0
0x7cf8c  ldfld    object System.Windows.Data.BindingListCollectionView::_editItem
0x7cf91  isinst   [System]System.ComponentModel.IEditableObject
0x7cf96  stfld    class [System]System.ComponentModel.IEditableObject <>c__DisplayClass62_0::ieo
0x7cf9b  ldarg.0
0x7cf9c  ldfld    object System.Windows.Data.BindingListCollectionView::_editItem
0x7cfa1  stloc.1
0x7cfa2  ldarg.0
0x7cfa3  ldnull
0x7cfa4  call     instance void System.Windows.Data.BindingListCollectionView::SetEditItem(object item)
0x7cfa9  ldloc.0
0x7cfaa  ldfld    class [System]System.ComponentModel.IEditableObject <>c__DisplayClass62_0::ieo
0x7cfaf  brfalse.s loc_7CFC9
0x7cfb1  ldarg.0
0x7cfb2  call     instance class [System]System.ComponentModel.IBindingList System.Windows.Data.BindingListCollectionView::get_InternalList()
0x7cfb7  ldloc.0
0x7cfb8  ldftn    instance void <>c__DisplayClass62_0::<CommitEdit>b__0()
0x7cfbe  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7cfc3  ldc.i4.1
0x7cfc4  call     void System.Windows.Data.BindingOperations::AccessCollection(class [mscorlib]System.Collections.IEnumerable collection, class [mscorlib]System.Action accessMethod, bool writeAccess)
0x7cfc9  ldarg.0
0x7cfca  ldfld    bool System.Windows.Data.BindingListCollectionView::_isGrouping
0x7cfcf  brfalse.s loc_7CFE0
0x7cfd1  ldarg.0
0x7cfd2  ldloc.1
0x7cfd3  call     instance void System.Windows.Data.BindingListCollectionView::RemoveItemFromGroups(object item)
0x7cfd8  ldarg.0
0x7cfd9  ldloc.1
0x7cfda  call     instance void System.Windows.Data.BindingListCollectionView::AddItemToGroups(object item)
0x7cfdf  ret
0x7cfe0  ret
```
