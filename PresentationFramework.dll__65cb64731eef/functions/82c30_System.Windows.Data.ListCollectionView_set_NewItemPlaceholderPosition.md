# System.Windows.Data.ListCollectionView::set_NewItemPlaceholderPosition

- ea: `0x82c30`
- end: `0x82e4a`
- name: `System.Windows.Data.ListCollectionView::set_NewItemPlaceholderPosition`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x2638e0`

## callees

- `0x38c70`
- `0x7fc50`
- `0x80450`
- `0x80d70`
- `0x82c30`
- `0x832a0`
- `0x83da0`
- `0x84630`
- `0x84640`
- `0x85720`
- `0x85730`
- `0x22a8f0`
- `0x22a920`
- `0x2638d0`

## string_xrefs

- `0x82c60`: `MemberNotAllowedDuringTransaction`
- `0x82c6d`: `NewItemPlaceholderPosition`
- `0x82e3f`: `NewItemPlaceholderPosition`

## pseudocode

```c

```

## disassembly

```asm
0x82c30  newobj   instance void <>c__DisplayClass40_0::.ctor()
0x82c35  stloc.0
0x82c36  ldloc.0
0x82c37  ldarg.0
0x82c38  stfld    class System.Windows.Data.ListCollectionView <>c__DisplayClass40_0::<>4__this
0x82c3d  ldloc.0
0x82c3e  ldarg.1
0x82c3f  stfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass40_0::value
0x82c44  ldarg.0
0x82c45  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x82c4a  ldloc.0
0x82c4b  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass40_0::value
0x82c50  ldarg.0
0x82c51  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82c56  beq.s    loc_82C86
0x82c58  ldarg.0
0x82c59  call     instance bool System.Windows.Data.ListCollectionView::get_IsAddingNew()
0x82c5e  brfalse.s loc_82C86
0x82c60  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x82c65  ldc.i4.2
0x82c66  newarr   [mscorlib]System.Object
0x82c6b  dup
0x82c6c  ldc.i4.0
0x82c6d  ldstr    aNewitemplaceho// "NewItemPlaceholderPosition"
0x82c72  stelem.ref
0x82c73  dup
0x82c74  ldc.i4.1
0x82c75  ldstr    aAddnew// "AddNew"
0x82c7a  stelem.ref
0x82c7b  call     string System.Windows.SR::Get(string id, object[] args)
0x82c80  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x82c85  throw
0x82c86  ldloc.0
0x82c87  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass40_0::value
0x82c8c  ldarg.0
0x82c8d  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82c92  beq.s    loc_82CAF
0x82c94  ldarg.0
0x82c95  ldfld    bool System.Windows.Data.ListCollectionView::_isRemoving
0x82c9a  brfalse.s loc_82CAF
0x82c9c  ldarg.0
0x82c9d  ldloc.0
0x82c9e  ldftn    instance void <>c__DisplayClass40_0::<set_NewItemPlaceholderPosition>b__0()
0x82ca4  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x82ca9  call     instance void System.Windows.Data.ListCollectionView::DeferAction(class [mscorlib]System.Action action)
0x82cae  ret
0x82caf  ldnull
0x82cb0  stloc.1
0x82cb1  ldc.i4.m1
0x82cb2  stloc.2
0x82cb3  ldc.i4.m1
0x82cb4  stloc.3
0x82cb5  ldloc.0
0x82cb6  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass40_0::value
0x82cbb  stloc.s  4
0x82cbd  ldloc.s  4
0x82cbf  switch   loc_82CD5, loc_82D24, loc_82D6D
0x82cd0  br       loc_82DB9
0x82cd5  ldarg.0
0x82cd6  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82cdb  stloc.s  5
0x82cdd  ldloc.s  5
0x82cdf  switch   loc_82DB9, loc_82CF5, loc_82D09
0x82cf0  br       loc_82DB9
0x82cf5  ldc.i4.0
0x82cf6  stloc.2
0x82cf7  ldc.i4.1
0x82cf8  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82cfd  ldloc.2
0x82cfe  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x82d03  stloc.1
0x82d04  br       loc_82DB9
0x82d09  ldarg.0
0x82d0a  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x82d0f  ldc.i4.1
0x82d10  sub
0x82d11  stloc.2
0x82d12  ldc.i4.1
0x82d13  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82d18  ldloc.2
0x82d19  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x82d1e  stloc.1
0x82d1f  br       loc_82DB9
0x82d24  ldarg.0
0x82d25  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82d2a  stloc.s  6
0x82d2c  ldloc.s  6
0x82d2e  switch   loc_82D41, loc_82DB9, loc_82D52
0x82d3f  br.s     loc_82DB9
0x82d41  ldc.i4.0
0x82d42  stloc.3
0x82d43  ldc.i4.0
0x82d44  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82d49  ldloc.3
0x82d4a  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x82d4f  stloc.1
0x82d50  br.s     loc_82DB9
0x82d52  ldarg.0
0x82d53  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x82d58  ldc.i4.1
0x82d59  sub
0x82d5a  stloc.2
0x82d5b  ldc.i4.0
0x82d5c  stloc.3
0x82d5d  ldc.i4.3
0x82d5e  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82d63  ldloc.3
0x82d64  ldloc.2
0x82d65  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x82d6a  stloc.1
0x82d6b  br.s     loc_82DB9
0x82d6d  ldarg.0
0x82d6e  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82d73  stloc.s  7
0x82d75  ldloc.s  7
0x82d77  switch   loc_82D8A, loc_82DA0, loc_82DB9
0x82d88  br.s     loc_82DB9
0x82d8a  ldarg.0
0x82d8b  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x82d90  stloc.3
0x82d91  ldc.i4.0
0x82d92  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82d97  ldloc.3
0x82d98  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x82d9d  stloc.1
0x82d9e  br.s     loc_82DB9
0x82da0  ldc.i4.0
0x82da1  stloc.2
0x82da2  ldarg.0
0x82da3  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x82da8  ldc.i4.1
0x82da9  sub
0x82daa  stloc.3
0x82dab  ldc.i4.3
0x82dac  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82db1  ldloc.3
0x82db2  ldloc.2
0x82db3  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x82db8  stloc.1
0x82db9  ldloc.1
0x82dba  brfalse  loc_82E49
0x82dbf  ldarg.0
0x82dc0  ldloc.0
0x82dc1  ldfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition <>c__DisplayClass40_0::value
0x82dc6  stfld    valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::_newItemPlaceholderPosition
0x82dcb  ldarg.0
0x82dcc  call     instance bool System.Windows.Data.ListCollectionView::get_IsGrouping()
0x82dd1  brtrue.s loc_82DDE
0x82dd3  ldarg.0
0x82dd4  ldloc.1
0x82dd5  ldloc.2
0x82dd6  ldloc.3
0x82dd7  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x82ddc  br.s     loc_82E3E
0x82dde  ldloc.2
0x82ddf  ldc.i4.0
0x82de0  blt.s    loc_82E0F
0x82de2  ldloc.2
0x82de3  brfalse.s loc_82DF9
0x82de5  ldarg.0
0x82de6  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.ListCollectionView::_group
0x82deb  callvirt instance class [System]System.Collections.ObjectModel.ReadOnlyObservableCollection`1<object> System.Windows.Data.CollectionViewGroup::get_Items()
0x82df0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Count()
0x82df5  ldc.i4.1
0x82df6  sub
0x82df7  br.s     loc_82DFA
0x82df9  ldc.i4.0
0x82dfa  stloc.s  8
0x82dfc  ldarg.0
0x82dfd  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.ListCollectionView::_group
0x82e02  ldloc.s  8
0x82e04  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82e09  ldc.i4.0
0x82e0a  callvirt instance void MS.Internal.Data.CollectionViewGroupRoot::RemoveSpecialItem(int32 index, object item, bool loading)
0x82e0f  ldloc.3
0x82e10  ldc.i4.0
0x82e11  blt.s    loc_82E3E
0x82e13  ldloc.3
0x82e14  brfalse.s loc_82E28
0x82e16  ldarg.0
0x82e17  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.ListCollectionView::_group
0x82e1c  callvirt instance class [System]System.Collections.ObjectModel.ReadOnlyObservableCollection`1<object> System.Windows.Data.CollectionViewGroup::get_Items()
0x82e21  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::get_Count()
0x82e26  br.s     loc_82E29
0x82e28  ldc.i4.0
0x82e29  stloc.s  9
0x82e2b  ldarg.0
0x82e2c  ldfld    class MS.Internal.Data.CollectionViewGroupRoot System.Windows.Data.ListCollectionView::_group
0x82e31  ldloc.s  9
0x82e33  call     object System.Windows.Data.CollectionView::get_NewItemPlaceholder()
0x82e38  ldc.i4.0
0x82e39  callvirt instance void MS.Internal.Data.CollectionViewGroupRoot::InsertSpecialItem(int32 index, object item, bool loading)
0x82e3e  ldarg.0
0x82e3f  ldstr    aNewitemplaceho// "NewItemPlaceholderPosition"
0x82e44  call     instance void System.Windows.Data.ListCollectionView::OnPropertyChanged(string propertyName)
0x82e49  ret
```
