# System.Windows.Data.ListCollectionView::CommitEdit

- ea: `0x834b0`
- end: `0x836c3`
- name: `System.Windows.Data.ListCollectionView::CommitEdit`
- size: `531`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x82ef0`
- `0x82f50`
- `0x83450`

## callees

- `0x38c70`
- `0x7fb20`
- `0x80450`
- `0x82c20`
- `0x832a0`
- `0x834b0`
- `0x83790`
- `0x83da0`
- `0x84370`
- `0x845a0`
- `0x845e0`
- `0x845f0`
- `0x84630`
- `0x848b0`
- `0x84b80`
- `0x85260`
- `0x852e0`
- `0x22f120`
- `0x232db0`
- `0x232e20`

## string_xrefs

- `0x834b8`: `MemberNotAllowedDuringTransaction`
- `0x834c5`: `CommitEdit`

## pseudocode

```c

```

## disassembly

```asm
0x834b0  ldarg.0
0x834b1  call     instance bool System.Windows.Data.ListCollectionView::get_IsAddingNew()
0x834b6  brfalse.s loc_834DE
0x834b8  ldstr    aMembernotallow_0// "MemberNotAllowedDuringTransaction"
0x834bd  ldc.i4.2
0x834be  newarr   [mscorlib]System.Object
0x834c3  dup
0x834c4  ldc.i4.0
0x834c5  ldstr    aCommitedit// "CommitEdit"
0x834ca  stelem.ref
0x834cb  dup
0x834cc  ldc.i4.1
0x834cd  ldstr    aAddnew// "AddNew"
0x834d2  stelem.ref
0x834d3  call     string System.Windows.SR::Get(string id, object[] args)
0x834d8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x834dd  throw
0x834de  ldarg.0
0x834df  call     instance void System.Windows.Data.CollectionView::VerifyRefreshNotDeferred()
0x834e4  ldarg.0
0x834e5  ldfld    object System.Windows.Data.ListCollectionView::_editItem
0x834ea  brtrue.s loc_834ED
0x834ec  ret
0x834ed  ldarg.0
0x834ee  ldfld    object System.Windows.Data.ListCollectionView::_editItem
0x834f3  stloc.0
0x834f4  ldarg.0
0x834f5  ldfld    object System.Windows.Data.ListCollectionView::_editItem
0x834fa  isinst   [System]System.ComponentModel.IEditableObject
0x834ff  stloc.1
0x83500  ldarg.0
0x83501  ldnull
0x83502  call     instance void System.Windows.Data.ListCollectionView::SetEditItem(object item)
0x83507  ldloc.1
0x83508  brfalse.s loc_83510
0x8350a  ldloc.1
0x8350b  callvirt instance void [System]System.ComponentModel.IEditableObject::EndEdit()
0x83510  ldarg.0
0x83511  ldloc.0
0x83512  call     instance int32 System.Windows.Data.ListCollectionView::InternalIndexOf(object item)
0x83517  stloc.2
0x83518  ldloc.2
0x83519  ldc.i4.0
0x8351a  clt
0x8351c  ldc.i4.0
0x8351d  ceq
0x8351f  stloc.3
0x83520  ldloc.3
0x83521  brtrue.s loc_8353D
0x83523  ldarg.0
0x83524  call     instance class [mscorlib]System.Collections.IList System.Windows.Data.ListCollectionView::get_SourceList()
0x83529  ldloc.0
0x8352a  callvirt instance bool [mscorlib]System.Collections.IList::Contains(object)
0x8352f  brfalse.s loc_8353A
0x83531  ldarg.0
0x83532  ldloc.0
0x83533  callvirt instance bool System.Windows.Data.CollectionView::PassesFilter(object item)
0x83538  br.s     loc_83544
0x8353a  ldc.i4.0
0x8353b  br.s     loc_83544
0x8353d  ldarg.0
0x8353e  ldloc.0
0x8353f  callvirt instance bool System.Windows.Data.CollectionView::PassesFilter(object item)
0x83544  stloc.s  4
0x83546  ldarg.0
0x83547  call     instance bool System.Windows.Data.ListCollectionView::get_IsGrouping()
0x8354c  brfalse.s loc_8358B
0x8354e  ldloc.3
0x8354f  brfalse.s loc_83558
0x83551  ldarg.0
0x83552  ldloc.0
0x83553  call     instance void System.Windows.Data.ListCollectionView::RemoveItemFromGroups(object item)
0x83558  ldloc.s  4
0x8355a  brfalse.s loc_8358A
0x8355c  ldarg.0
0x8355d  call     instance class [mscorlib]System.Collections.IList System.Windows.Data.ListCollectionView::get_InternalList()
0x83562  isinst   MS.Internal.Data.LiveShapingList
0x83567  stloc.s  5
0x83569  ldloc.s  5
0x8356b  brfalse.s loc_8357E
0x8356d  ldloc.s  5
0x8356f  ldloc.s  5
0x83571  ldloc.0
0x83572  callvirt instance int32 MS.Internal.Data.LiveShapingList::IndexOf(object value)
0x83577  callvirt instance class MS.Internal.Data.LiveShapingItem MS.Internal.Data.LiveShapingList::ItemAt(int32 index)
0x8357c  br.s     loc_8357F
0x8357e  ldnull
0x8357f  stloc.s  6
0x83581  ldarg.0
0x83582  ldloc.0
0x83583  ldloc.s  6
0x83585  call     instance void System.Windows.Data.ListCollectionView::AddItemToGroups(object item, class MS.Internal.Data.LiveShapingItem lsi)
0x8358a  ret
0x8358b  ldarg.0
0x8358c  call     instance bool System.Windows.Data.ListCollectionView::get_UsesLocalArray()
0x83591  brfalse  loc_836C2
0x83596  ldarg.0
0x83597  call     instance class [mscorlib]System.Collections.IList System.Windows.Data.ListCollectionView::get_InternalList()
0x8359c  stloc.s  7
0x8359e  ldarg.0
0x8359f  call     instance valuetype [WindowsBase]System.ComponentModel.NewItemPlaceholderPosition System.Windows.Data.ListCollectionView::get_NewItemPlaceholderPosition()
0x835a4  ldc.i4.1
0x835a5  beq.s    loc_835AA
0x835a7  ldc.i4.0
0x835a8  br.s     loc_835AB
0x835aa  ldc.i4.1
0x835ab  stloc.s  8
0x835ad  ldc.i4.m1
0x835ae  stloc.s  9
0x835b0  ldloc.3
0x835b1  brfalse  loc_83690
0x835b6  ldloc.s  4
0x835b8  brtrue.s loc_835CB
0x835ba  ldarg.0
0x835bb  ldc.i4.1
0x835bc  ldloc.0
0x835bd  ldloc.2
0x835be  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x835c3  ldloc.2
0x835c4  ldc.i4.m1
0x835c5  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x835ca  ret
0x835cb  ldarg.0
0x835cc  call     instance class [mscorlib]System.Collections.IComparer System.Windows.Data.ListCollectionView::get_ActiveComparer()
0x835d1  brfalse  loc_836C2
0x835d6  ldloc.2
0x835d7  ldloc.s  8
0x835d9  sub
0x835da  stloc.s  0xA
0x835dc  ldloc.s  0xA
0x835de  ldc.i4.0
0x835df  ble.s    loc_8361A
0x835e1  ldarg.0
0x835e2  call     instance class [mscorlib]System.Collections.IComparer System.Windows.Data.ListCollectionView::get_ActiveComparer()
0x835e7  ldloc.s  7
0x835e9  ldloc.s  0xA
0x835eb  ldc.i4.1
0x835ec  sub
0x835ed  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x835f2  ldloc.0
0x835f3  callvirt instance int32 [mscorlib]System.Collections.IComparer::Compare(object, object)
0x835f8  ldc.i4.0
0x835f9  ble.s    loc_8361A
0x835fb  ldloc.s  7
0x835fd  ldc.i4.0
0x835fe  ldloc.s  0xA
0x83600  ldloc.0
0x83601  ldarg.0
0x83602  call     instance class [mscorlib]System.Collections.IComparer System.Windows.Data.ListCollectionView::get_ActiveComparer()
0x83607  call     int32 MS.Internal.Data.DataExtensionMethods::Search(class [mscorlib]System.Collections.IList list, int32 index, int32 count, object value, class [mscorlib]System.Collections.IComparer comparer)
0x8360c  stloc.s  9
0x8360e  ldloc.s  9
0x83610  ldc.i4.0
0x83611  bge.s    loc_83671
0x83613  ldloc.s  9
0x83615  not
0x83616  stloc.s  9
0x83618  br.s     loc_83671
0x8361a  ldloc.s  0xA
0x8361c  ldloc.s  7
0x8361e  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x83623  ldc.i4.1
0x83624  sub
0x83625  bge.s    loc_83671
0x83627  ldarg.0
0x83628  call     instance class [mscorlib]System.Collections.IComparer System.Windows.Data.ListCollectionView::get_ActiveComparer()
0x8362d  ldloc.0
0x8362e  ldloc.s  7
0x83630  ldloc.s  0xA
0x83632  ldc.i4.1
0x83633  add
0x83634  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x83639  callvirt instance int32 [mscorlib]System.Collections.IComparer::Compare(object, object)
0x8363e  ldc.i4.0
0x8363f  ble.s    loc_83671
0x83641  ldloc.s  7
0x83643  ldloc.s  0xA
0x83645  ldc.i4.1
0x83646  add
0x83647  ldloc.s  7
0x83649  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x8364e  ldloc.s  0xA
0x83650  sub
0x83651  ldc.i4.1
0x83652  sub
0x83653  ldloc.0
0x83654  ldarg.0
0x83655  call     instance class [mscorlib]System.Collections.IComparer System.Windows.Data.ListCollectionView::get_ActiveComparer()
0x8365a  call     int32 MS.Internal.Data.DataExtensionMethods::Search(class [mscorlib]System.Collections.IList list, int32 index, int32 count, object value, class [mscorlib]System.Collections.IComparer comparer)
0x8365f  stloc.s  9
0x83661  ldloc.s  9
0x83663  ldc.i4.0
0x83664  bge.s    loc_8366B
0x83666  ldloc.s  9
0x83668  not
0x83669  stloc.s  9
0x8366b  ldloc.s  9
0x8366d  ldc.i4.1
0x8366e  sub
0x8366f  stloc.s  9
0x83671  ldloc.s  9
0x83673  ldc.i4.0
0x83674  blt.s    loc_836C2
0x83676  ldarg.0
0x83677  ldc.i4.3
0x83678  ldloc.0
0x83679  ldloc.s  9
0x8367b  ldloc.s  8
0x8367d  add
0x8367e  ldloc.2
0x8367f  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32, int32)
0x83684  ldloc.2
0x83685  ldloc.s  9
0x83687  ldloc.s  8
0x83689  add
0x8368a  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x8368f  ret
0x83690  ldloc.s  4
0x83692  brfalse.s loc_836C2
0x83694  ldarg.0
0x83695  ldc.i4.0
0x83696  ldloc.0
0x83697  ldarg.0
0x83698  call     instance class [mscorlib]System.Collections.IList System.Windows.Data.ListCollectionView::get_SourceList()
0x8369d  ldloc.0
0x8369e  callvirt instance int32 [mscorlib]System.Collections.IList::IndexOf(object)
0x836a3  call     instance int32 System.Windows.Data.ListCollectionView::AdjustBefore(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction action, object item, int32 index)
0x836a8  stloc.s  9
0x836aa  ldarg.0
0x836ab  ldc.i4.0
0x836ac  ldloc.0
0x836ad  ldloc.s  9
0x836af  ldloc.s  8
0x836b1  add
0x836b2  newobj   instance void [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs::.ctor(valuetype [System]System.Collections.Specialized.NotifyCollectionChangedAction, object, int32)
0x836b7  ldc.i4.m1
0x836b8  ldloc.s  9
0x836ba  ldloc.s  8
0x836bc  add
0x836bd  call     instance void System.Windows.Data.ListCollectionView::ProcessCollectionChangedWithAdjustedIndex(class [System]System.Collections.Specialized.NotifyCollectionChangedEventArgs args, int32 adjustedOldIndex, int32 adjustedNewIndex)
0x836c2  ret
```
