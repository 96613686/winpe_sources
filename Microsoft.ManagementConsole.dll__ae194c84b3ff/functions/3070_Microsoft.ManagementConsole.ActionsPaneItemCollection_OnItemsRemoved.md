# Microsoft.ManagementConsole.ActionsPaneItemCollection::OnItemsRemoved

- ea: `0x3070`
- end: `0x30be`
- name: `Microsoft.ManagementConsole.ActionsPaneItemCollection::OnItemsRemoved`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2200`
- `0x3070`
- `0x30c0`
- `0x3200`

## pseudocode

```c

```

## disassembly

```asm
0x3070  ldarg.2
0x3071  stloc.2
0x3072  ldc.i4.0
0x3073  stloc.3
0x3074  br.s     loc_3095
0x3076  ldloc.2
0x3077  ldloc.3
0x3078  ldelem.ref
0x3079  castclass Microsoft.ManagementConsole.ActionsPaneItem
0x307e  stloc.0
0x307f  ldloc.0
0x3080  ldarg.0
0x3081  ldftn    instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::ItemChanged(object sender, class [mscorlib]System.EventArgs e)
0x3087  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x308c  callvirt instance void Microsoft.ManagementConsole.ActionsPaneItem::remove_Changed(class [mscorlib]System.EventHandler value)
0x3091  ldloc.3
0x3092  ldc.i4.1
0x3093  add
0x3094  stloc.3
0x3095  ldloc.3
0x3096  ldloc.2
0x3097  ldlen
0x3098  conv.i4
0x3099  blt.s    loc_3076
0x309b  ldarg.2
0x309c  ldlen
0x309d  conv.i4
0x309e  newarr   Microsoft.ManagementConsole.ActionsPaneItem
0x30a3  stloc.1
0x30a4  ldarg.2
0x30a5  ldloc.1
0x30a6  ldarg.2
0x30a7  ldlen
0x30a8  conv.i4
0x30a9  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x30ae  ldarg.0
0x30af  call     instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::SyncData()
0x30b4  ldarg.0
0x30b5  ldarg.1
0x30b6  ldloc.1
0x30b7  ldc.i4.1
0x30b8  call     instance void Microsoft.ManagementConsole.ActionsPaneItemCollection::Notify(int32 index, class Microsoft.ManagementConsole.ActionsPaneItem[] items, valuetype Microsoft.ManagementConsole.ActionsPaneItemCollectionChangeType action)
0x30bd  ret
```
