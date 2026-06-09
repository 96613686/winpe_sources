# System.Windows.Data.BindingListCollectionView::set_NewItemPlaceholderPosition

- ea: `0x7c780`
- end: `0x7c999`
- name: `System.Windows.Data.BindingListCollectionView::set_NewItemPlaceholderPosition`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x263160`

## callees

- `0x38c70`
- `0x7c780`
- `0x7cd40`
- `0x7d9b0`
- `0x7e900`
- `0x7e910`
- `0x7fc50`
- `0x80220`
- `0x80450`
- `0x80d70`
- `0x22a8f0`
- `0x22a920`
- `0x263150`

## string_xrefs

- `0x7c7b0`: `MemberNotAllowedDuringTransaction`
- `0x7c7bd`: `NewItemPlaceholderPosition`
- `0x7c98e`: `NewItemPlaceholderPosition`

## pseudocode

```c

```

## disassembly

```asm
0x7c780  newobj   instance void <>c__DisplayClass41_0::.ctor()
0x7c785  stloc.0
0x7c786  ldloc.0
0x7c787  ldarg.0
0x7c788  stfld    class System.Windows.Data.BindingListCollectionView <>c__DisplayClass41_0::<>4__this
0x7c78d  ldloc.0
0x7c78e  ldarg.1
0x7c78f  stfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass41_0::value
0x7c794  ldarg.0
0x7c795  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x7c79a  ldloc.0
0x7c79b  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass41_0::value
0x7c7a0  ldarg.0
0x7c7a1  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c7a6  beq.s    loc_7C7D6
0x7c7a8  ldarg.0
0x7c7a9  call     instance bool System.Windows.Data.BindingListCollectionView::get_IsAddingNew()
0x7c7ae  brfalse.s loc_7C7D6
0x7c7b0  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x7c7b5  ldc.i4.2
0x7c7b6  newarr   [mscorlib]System.Object
0x7c7bb  dup
0x7c7bc  ldc.i4.0
0x7c7bd  ldstr    aNewitemplaceho// "NewItemPlaceholderPosition"
0x7c7c2  stelem.ref
0x7c7c3  dup
0x7c7c4  ldc.i4.1
0x7c7c5  ldstr    aAddnew// "AddNew"
0x7c7ca  stelem.ref
0x7c7cb  call     string System.Windows.SR::Get(string id, object[] args)
0x7c7d0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7c7d5  throw
0x7c7d6  ldloc.0
0x7c7d7  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass41_0::value
0x7c7dc  ldarg.0
0x7c7dd  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c7e2  beq.s    loc_7C7FF
0x7c7e4  ldarg.0
0x7c7e5  ldfld    bool System.Windows.Data.BindingListCollectionView::_isRemoving
0x7c7ea  brfalse.s loc_7C7FF
0x7c7ec  ldarg.0
0x7c7ed  ldloc.0
0x7c7ee  ldftn    instance void <>c__DisplayClass41_0::<set_NewItemPlaceholderPosition>b__0()
0x7c7f4  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7c7f9  call     instance void System.Windows.Data.BindingListCollectionView::DeferAction(class [mscorlib]System.Action action)
0x7c7fe  ret
0x7c7ff  ldnull
0x7c800  stloc.1
0x7c801  ldc.i4.m1
0x7c802  stloc.2
0x7c803  ldc.i4.m1
0x7c804  stloc.3
0x7c805  ldloc.0
0x7c806  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass41_0::value
0x7c80b  stloc.s  4
0x7c80d  ldloc.s  4
0x7c80f  switch   loc_7C825, loc_7C874, loc_7C8BD
0x7c820  br       loc_7C909
0x7c825  ldarg.0
0x7c826  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c82b  stloc.s  5
0x7c82d  ldloc.s  5
0x7c82f  switch   loc_7C909, loc_7C845, loc_7C859
0x7c840  br       loc_7C909
0x7c845  ldc.i4.0
0x7c846  stloc.2
0x7c847  ldc.i4.1
0x7c848  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c84d  ldloc.2
0x7c84e  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x7c853  stloc.1
0x7c854  br       loc_7C909
0x7c859  ldarg.0
0x7c85a  call     instance int32 System.Windows.Data.BindingListCollectionView::get_InternalCount()
0x7c85f  ldc.i4.1
0x7c860  sub
0x7c861  stloc.2
0x7c862  ldc.i4.1
0x7c863  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c868  ldloc.2
0x7c869  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x7c86e  stloc.1
0x7c86f  br       loc_7C909
0x7c874  ldarg.0
0x7c875  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c87a  stloc.s  6
0x7c87c  ldloc.s  6
0x7c87e  switch   loc_7C891, loc_7C909, loc_7C8A2
0x7c88f  br.s     loc_7C909
0x7c891  ldc.i4.0
0x7c892  stloc.3
0x7c893  ldc.i4.0
0x7c894  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c899  ldloc.3
0x7c89a  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x7c89f  stloc.1
0x7c8a0  br.s     loc_7C909
0x7c8a2  ldarg.0
0x7c8a3  call     instance int32 System.Windows.Data.BindingListCollectionView::get_InternalCount()
0x7c8a8  ldc.i4.1
0x7c8a9  sub
0x7c8aa  stloc.2
0x7c8ab  ldc.i4.0
0x7c8ac  stloc.3
0x7c8ad  ldc.i4.3
0x7c8ae  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c8b3  ldloc.3
0x7c8b4  ldloc.2
0x7c8b5  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x7c8ba  stloc.1
0x7c8bb  br.s     loc_7C909
0x7c8bd  ldarg.0
0x7c8be  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c8c3  stloc.s  7
0x7c8c5  ldloc.s  7
0x7c8c7  switch   loc_7C8DA, loc_7C8F0, loc_7C909
0x7c8d8  br.s     loc_7C909
0x7c8da  ldarg.0
0x7c8db  call     instance int32 System.Windows.Data.BindingListCollectionView::get_InternalCount()
0x7c8e0  stloc.3
0x7c8e1  ldc.i4.0
0x7c8e2  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c8e7  ldloc.3
0x7c8e8  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x7c8ed  stloc.1
0x7c8ee  br.s     loc_7C909
0x7c8f0  ldc.i4.0
0x7c8f1  stloc.2
0x7c8f2  ldarg.0
0x7c8f3  call     instance int32 System.Windows.Data.BindingListCollectionView::get_InternalCount()
0x7c8f8  ldc.i4.1
0x7c8f9  sub
0x7c8fa  stloc.3
0x7c8fb  ldc.i4.3
0x7c8fc  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c901  ldloc.3
0x7c902  ldloc.2
0x7c903  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x7c908  stloc.1
0x7c909  ldloc.1
0x7c90a  brfalse  loc_7C998
0x7c90f  ldarg.0
0x7c910  ldloc.0
0x7c911  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass41_0::value
0x7c916  stfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.BindingListCollectionView::_newItemPlaceholderPosition
0x7c91b  ldarg.0
0x7c91c  ldfld    bool System.Windows.Data.BindingListCollectionView::_isGrouping
0x7c921  brtrue.s loc_7C92D
0x7c923  ldarg.0
0x7c924  ldnull
0x7c925  ldloc.1
0x7c926  call     instance void System.Windows.Data.CollectionView::OnCollectionChanged(object sender, class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args)
0x7c92b  br.s     loc_7C98D
0x7c92d  ldloc.2
0x7c92e  ldc.i4.0
0x7c92f  blt.s    loc_7C95E
0x7c931  ldloc.2
0x7c932  brfalse.s loc_7C948
0x7c934  ldarg.0
0x7c935  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.BindingListCollectionView::_group
0x7c93a  callvirt instance class [System]System.Collections.ObjectModel.ReadOnlyObservableCollection`1<object> System.Windows.Data.CollectionViewGroup::get_Items()
0x7c93f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Count()
0x7c944  ldc.i4.1
0x7c945  sub
0x7c946  br.s     loc_7C949
0x7c948  ldc.i4.0
0x7c949  stloc.s  8
0x7c94b  ldarg.0
0x7c94c  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.BindingListCollectionView::_group
0x7c951  ldloc.s  8
0x7c953  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c958  ldc.i4.0
0x7c959  callvirt instance void MS.Internal.Data.CollectionViewGroupRoot::RemoveSpecialItem(int32 index, object item, bool loading)
0x7c95e  ldloc.3
0x7c95f  ldc.i4.0
0x7c960  blt.s    loc_7C98D
0x7c962  ldloc.3
0x7c963  brfalse.s loc_7C977
0x7c965  ldarg.0
0x7c966  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.BindingListCollectionView::_group
0x7c96b  callvirt instance class [System]System.Collections.ObjectModel.ReadOnlyObservableCollection`1<object> System.Windows.Data.CollectionViewGroup::get_Items()
0x7c970  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Count()
0x7c975  br.s     loc_7C978
0x7c977  ldc.i4.0
0x7c978  stloc.s  9
0x7c97a  ldarg.0
0x7c97b  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.BindingListCollectionView::_group
0x7c980  ldloc.s  9
0x7c982  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x7c987  ldc.i4.0
0x7c988  callvirt instance void MS.Internal.Data.CollectionViewGroupRoot::InsertSpecialItem(int32 index, object item, bool loading)
0x7c98d  ldarg.0
0x7c98e  ldstr    aNewitemplaceho// "NewItemPlaceholderPosition"
0x7c993  call     instance void System.Windows.Data.BindingListCollectionView::OnPropertyChanged(string propertyName)
0x7c998  ret
```
