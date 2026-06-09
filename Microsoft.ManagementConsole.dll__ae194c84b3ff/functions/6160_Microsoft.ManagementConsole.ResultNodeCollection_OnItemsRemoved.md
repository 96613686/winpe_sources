# Microsoft.ManagementConsole.ResultNodeCollection::OnItemsRemoved

- ea: `0x6160`
- end: `0x61eb`
- name: `Microsoft.ManagementConsole.ResultNodeCollection::OnItemsRemoved`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x280`
- `0x670`
- `0x840`
- `0x870`
- `0x20c0`
- `0x6160`
- `0x61f0`
- `0x8440`
- `0xcc20`

## pseudocode

```c

```

## disassembly

```asm
0x6160  ldarg.0
0x6161  ldfld    bool Microsoft.ManagementConsole.ResultNodeCollection::_ignoreChanges
0x6166  brfalse.s loc_6169
0x6168  ret
0x6169  ldarg.0
0x616a  ldfld    class Microsoft.ManagementConsole.MmcListView Microsoft.ManagementConsole.ResultNodeCollection::_listView
0x616f  callvirt instance bool Microsoft.ManagementConsole.MmcListView::get_SortingInProgress()
0x6174  brfalse.s loc_6186
0x6176  call     string Microsoft.ManagementConsole.Internal.Strings::get_ResultNodeCollectionOnItemsRemovedResultNode()
0x617b  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x6180  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6185  throw
0x6186  ldarg.2
0x6187  stloc.2
0x6188  ldc.i4.0
0x6189  stloc.3
0x618a  br.s     loc_61C8
0x618c  ldloc.2
0x618d  ldloc.3
0x618e  ldelem.ref
0x618f  castclass Microsoft.ManagementConsole.ResultNode
0x6194  stloc.0
0x6195  ldloc.0
0x6196  ldnull
0x6197  callvirt instance void Microsoft.ManagementConsole.ResultNode::set_ListView(class Microsoft.ManagementConsole.MmcListView value)
0x619c  ldloc.0
0x619d  ldarg.0
0x619e  ldftn    instance void Microsoft.ManagementConsole.ResultNodeCollection::ItemChanged(object sender, class Microsoft.ManagementConsole.NodeChangedEventArgs e)
0x61a4  newobj   instance void NodeChangedEventHandler::.ctor(object object, native int method)
0x61a9  callvirt instance void Microsoft.ManagementConsole.Node::remove_Changed(class NodeChangedEventHandler value)
0x61ae  ldarg.0
0x61af  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ManagementConsole.ResultNodeCollection::_itemsById
0x61b4  ldloc.0
0x61b5  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x61ba  box      [mscorlib]System.Int32
0x61bf  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x61c4  ldloc.3
0x61c5  ldc.i4.1
0x61c6  add
0x61c7  stloc.3
0x61c8  ldloc.3
0x61c9  ldloc.2
0x61ca  ldlen
0x61cb  conv.i4
0x61cc  blt.s    loc_618C
0x61ce  ldarg.2
0x61cf  ldlen
0x61d0  conv.i4
0x61d1  newarr   Microsoft.ManagementConsole.ResultNode
0x61d6  stloc.1
0x61d7  ldarg.2
0x61d8  ldloc.1
0x61d9  ldarg.2
0x61da  ldlen
0x61db  conv.i4
0x61dc  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x61e1  ldarg.0
0x61e2  ldarg.1
0x61e3  ldloc.1
0x61e4  ldc.i4.1
0x61e5  call     instance void Microsoft.ManagementConsole.ResultNodeCollection::Notify(int32 index, class Microsoft.ManagementConsole.ResultNode[] items, valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ResultNodeCollectionChangeType action)
0x61ea  ret
```
