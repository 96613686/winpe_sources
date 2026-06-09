# Microsoft.ManagementConsole.MmcListViewColumnCollection::OnItemsRemoved

- ea: `0x96c0`
- end: `0x9767`
- name: `Microsoft.ManagementConsole.MmcListViewColumnCollection::OnItemsRemoved`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x240`
- `0x250`
- `0x8440`
- `0x96c0`
- `0x97b0`
- `0xcb80`
- `0xcee0`
- `0xcf10`
- `0xcf80`
- `0xcfb0`

## pseudocode

```c

```

## disassembly

```asm
0x96c0  ldarg.1
0x96c1  brtrue.s loc_96D8
0x96c3  call     string Microsoft.ManagementConsole.Internal.Strings::get_ColumnCollectionOnItemsRemovedFirstColumn()
0x96c8  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x96cd  ldstr    aIndex// "index"
0x96d2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x96d7  throw
0x96d8  ldarg.0
0x96d9  ldfld    class Microsoft.ManagementConsole.MmcListView Microsoft.ManagementConsole.MmcListViewColumnCollection::_listView
0x96de  brfalse.s loc_9702
0x96e0  ldarg.0
0x96e1  ldfld    class Microsoft.ManagementConsole.MmcListView Microsoft.ManagementConsole.MmcListViewColumnCollection::_listView
0x96e6  callvirt instance class Microsoft.ManagementConsole.ResultNodeCollection Microsoft.ManagementConsole.MmcListView::get_ResultNodes()
0x96eb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x96f0  brfalse.s loc_9702
0x96f2  call     string Microsoft.ManagementConsole.Internal.Strings::get_ColumnCollectionOnItemsRemovedResultNode()
0x96f7  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x96fc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9701  throw
0x9702  ldarg.2
0x9703  stloc.2
0x9704  ldc.i4.0
0x9705  stloc.3
0x9706  br.s     loc_9744
0x9708  ldloc.2
0x9709  ldloc.3
0x970a  ldelem.ref
0x970b  castclass Microsoft.ManagementConsole.MmcListViewColumn
0x9710  stloc.0
0x9711  ldloc.0
0x9712  ldarg.0
0x9713  ldftn    instance void Microsoft.ManagementConsole.MmcListViewColumnCollection::ItemChanged(object sender, class [mscorlib]System.EventArgs e)
0x9719  newobj   instance void ColumnChangedEventHandler::.ctor(object object, native int method)
0x971e  callvirt instance void Microsoft.ManagementConsole.MmcListViewColumn::remove_Changed(class ColumnChangedEventHandler value)
0x9723  ldloc.0
0x9724  ldnull
0x9725  callvirt instance void Microsoft.ManagementConsole.MmcListViewColumn::set_ListView(class Microsoft.ManagementConsole.MmcListView value)
0x972a  ldarg.0
0x972b  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ManagementConsole.MmcListViewColumnCollection::_itemsById
0x9730  ldloc.0
0x9731  callvirt instance int32 Microsoft.ManagementConsole.MmcListViewColumn::get_Id()
0x9736  box      [mscorlib]System.Int32
0x973b  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x9740  ldloc.3
0x9741  ldc.i4.1
0x9742  add
0x9743  stloc.3
0x9744  ldloc.3
0x9745  ldloc.2
0x9746  ldlen
0x9747  conv.i4
0x9748  blt.s    loc_9708
0x974a  ldarg.2
0x974b  ldlen
0x974c  conv.i4
0x974d  newarr   Microsoft.ManagementConsole.MmcListViewColumn
0x9752  stloc.1
0x9753  ldarg.2
0x9754  ldloc.1
0x9755  ldarg.2
0x9756  ldlen
0x9757  conv.i4
0x9758  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x975d  ldarg.0
0x975e  ldarg.1
0x975f  ldloc.1
0x9760  ldc.i4.1
0x9761  call     instance void Microsoft.ManagementConsole.MmcListViewColumnCollection::Notify(int32 index, class Microsoft.ManagementConsole.MmcListViewColumn[] columns, valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ColumnCollectionChangeType action)
0x9766  ret
```
