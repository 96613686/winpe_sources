# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read

- ea: `0x3ce0`
- end: `0x3d42`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x3a70`
- `0x3a80`
- `0x3ce0`
- `0x3d50`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  ldc.i4.0
0x3ce1  stloc.0
0x3ce2  ldc.i4.0
0x3ce3  stloc.1
0x3ce4  ldc.i4.0
0x3ce5  stloc.2
0x3ce6  ldc.i4.0
0x3ce7  stloc.3
0x3ce8  ldnull
0x3ce9  stloc.s  4
0x3ceb  ldarg.0
0x3cec  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_id
0x3cf1  brtrue.s loc_3CF5
0x3cf3  ldnull
0x3cf4  ret
0x3cf5  ldarg.0
0x3cf6  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_id
0x3cfb  ldlen
0x3cfc  conv.i4
0x3cfd  ldc.i4.0
0x3cfe  ble.s    loc_3D10
0x3d00  ldarg.0
0x3d01  ldloca.s 0
0x3d03  ldloca.s 1
0x3d05  ldloca.s 2
0x3d07  ldloca.s 3
0x3d09  call     instance class Microsoft.ManagementConsole.Internal.ActionsPaneItemData Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read(int32& index, int32& exItemIndex, int32& actionIndex, int32& colIndex)
0x3d0e  stloc.s  4
0x3d10  ldloc.s  4
0x3d12  isinst   Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData
0x3d17  stloc.s  5
0x3d19  ldloc.s  5
0x3d1b  brtrue.s loc_3D3F
0x3d1d  newobj   instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::.ctor()
0x3d22  stloc.s  5
0x3d24  ldloc.s  4
0x3d26  brfalse.s loc_3D3F
0x3d28  ldloc.s  5
0x3d2a  ldc.i4.1
0x3d2b  newarr   Microsoft.ManagementConsole.Internal.ActionsPaneItemData
0x3d30  stloc.s  6
0x3d32  ldloc.s  6
0x3d34  ldc.i4.0
0x3d35  ldloc.s  4
0x3d37  stelem.ref
0x3d38  ldloc.s  6
0x3d3a  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::SetItems(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData[] items)
0x3d3f  ldloc.s  5
0x3d41  ret
```
