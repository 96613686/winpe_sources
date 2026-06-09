# System.Windows.Data.ListCollectionView::CommitNew

- ea: `0x83080`
- end: `0x8317b`
- name: `System.Windows.Data.ListCollectionView::CommitNew`
- size: `251`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x82ef0`
- `0x82f50`
- `0x83450`

## callees

- `0x38c70`
- `0x80450`
- `0x82c20`
- `0x83080`
- `0x83180`
- `0x83260`
- `0x83770`
- `0x83da0`
- `0x845a0`
- `0x845e0`
- `0x84630`
- `0x84640`
- `0x84b80`

## string_xrefs

- `0x83088`: `MemberNotAllowedDuringTransaction`
- `0x83095`: `CommitNew`

## pseudocode

```c

```

## disassembly

```asm
0x83080  ldarg.0
0x83081  call     instance bool System.Windows.Data.ListCollectionView::get_IsEditingItem()
0x83086  brfalse.s loc_830AE
0x83088  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x8308d  ldc.i4.2
0x8308e  newarr   [mscorlib]System.Object
0x83093  dup
0x83094  ldc.i4.0
0x83095  ldstr    aCommitnew// "CommitNew"
0x8309a  stelem.ref
0x8309b  dup
0x8309c  ldc.i4.1
0x8309d  ldstr    aEdititem// "EditItem"
0x830a2  stelem.ref
0x830a3  call     string System.Windows.SR::Get(string id, object[] args)
0x830a8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x830ad  throw
0x830ae  ldarg.0
0x830af  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x830b4  ldarg.0
0x830b5  ldfld    object System.Windows.Data.ListCollectionView::_newItem
0x830ba  ldsfld   object System.Windows.Data.CollectionView::NoNewItem
0x830bf  bne.un.s loc_830C2
0x830c1  ret
0x830c2  ldarg.0
0x830c3  call     instance bool System.Windows.Data.ListCollectionView::get_IsGrouping()
0x830c8  brfalse.s loc_830D1
0x830ca  ldarg.0
0x830cb  call     instance void System.Windows.Data.ListCollectionView::CommitNewForGrouping()
0x830d0  ret
0x830d1  ldc.i4.0
0x830d2  stloc.0
0x830d3  ldarg.0
0x830d4  call     instance valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::get_NewItemPlaceholderPosition()
0x830d9  stloc.3
0x830da  ldloc.3
0x830db  switch   loc_830EE, loc_83109, loc_8310D
0x830ec  br.s     loc_83116
0x830ee  ldarg.0
0x830ef  call     instance bool System.Windows.Data.ListCollectionView::get_UsesLocalArray()
0x830f4  brtrue.s loc_830FE
0x830f6  ldarg.0
0x830f7  ldfld    int32 System.Windows.Data.ListCollectionView::_newItemIndex
0x830fc  br.s     loc_83106
0x830fe  ldarg.0
0x830ff  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x83104  ldc.i4.1
0x83105  sub
0x83106  stloc.0
0x83107  br.s     loc_83116
0x83109  ldc.i4.1
0x8310a  stloc.0
0x8310b  br.s     loc_83116
0x8310d  ldarg.0
0x8310e  call     instance int32 System.Windows.Data.ListCollectionView::get_InternalCount()
0x83113  ldc.i4.2
0x83114  sub
0x83115  stloc.0
0x83116  ldarg.0
0x83117  ldc.i4.0
0x83118  call     instance object System.Windows.Data.ListCollectionView::EndAddNew(bool cancel)
0x8311d  stloc.1
0x8311e  ldarg.0
0x8311f  ldc.i4.0
0x83120  ldloc.1
0x83121  ldarg.0
0x83122  ldfld    int32 System.Windows.Data.ListCollectionView::_newItemIndex
0x83127  call     instance int32 System.Windows.Data.ListCollectionView::AdjustBefore(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction action, object item, int32 index)
0x8312c  stloc.2
0x8312d  ldloc.2
0x8312e  ldc.i4.0
0x8312f  bge.s    loc_83142
0x83131  ldarg.0
0x83132  ldc.i4.1
0x83133  ldloc.1
0x83134  ldloc.0
0x83135  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x8313a  ldloc.0
0x8313b  ldc.i4.m1
0x8313c  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x83141  ret
0x83142  ldloc.0
0x83143  ldloc.2
0x83144  bne.un.s loc_83169
0x83146  ldarg.0
0x83147  call     instance bool System.Windows.Data.ListCollectionView::get_UsesLocalArray()
0x8314c  brfalse.s loc_8317A
0x8314e  ldarg.0
0x8314f  call     instance valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::get_NewItemPlaceholderPosition()
0x83154  ldc.i4.1
0x83155  bne.un.s loc_8315B
0x83157  ldloc.2
0x83158  ldc.i4.1
0x83159  sub
0x8315a  stloc.2
0x8315b  ldarg.0
0x8315c  call     instance class [mscorlib]System.Collections.IList System.Windows.Data.ListCollectionView::get_InternalList()
0x83161  ldloc.2
0x83162  ldloc.1
0x83163  callvirt instance void [mscorlib]System.Collections.IList::Insert(int32, object)
0x83168  ret
0x83169  ldarg.0
0x8316a  ldc.i4.3
0x8316b  ldloc.1
0x8316c  ldloc.2
0x8316d  ldloc.0
0x8316e  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x83173  ldloc.0
0x83174  ldloc.2
0x83175  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x8317a  ret
```
