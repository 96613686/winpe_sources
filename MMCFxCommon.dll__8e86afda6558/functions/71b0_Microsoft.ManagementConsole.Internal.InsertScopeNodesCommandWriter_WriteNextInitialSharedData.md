# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextInitialSharedData

- ea: `0x71b0`
- end: `0x72c6`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextInitialSharedData`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x6f20`

## callees

- `0xd70`
- `0xd90`
- `0xdb0`
- `0xdd0`
- `0x7130`
- `0x71b0`
- `0x72d0`
- `0x72f0`
- `0x7310`

## pseudocode

```c

```

## disassembly

```asm
0x71b0  ldarg.1
0x71b1  callvirt instance valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration[] Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::GetAddedFormats()
0x71b6  stloc.0
0x71b7  ldc.i4.m1
0x71b8  stloc.1
0x71b9  ldloc.0
0x71ba  brfalse.s loc_71E0
0x71bc  ldloc.0
0x71bd  ldlen
0x71be  conv.i4
0x71bf  stloc.1
0x71c0  ldc.i4.0
0x71c1  stloc.2
0x71c2  ldc.i4.0
0x71c3  stloc.2
0x71c4  br.s     loc_71DC
0x71c6  ldarg.0
0x71c7  ldloc.0
0x71c8  ldloc.2
0x71c9  ldelema  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x71ce  ldobj    Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x71d3  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextAddedFormats(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration obj)
0x71d8  ldloc.2
0x71d9  ldc.i4.1
0x71da  add
0x71db  stloc.2
0x71dc  ldloc.2
0x71dd  ldloc.1
0x71de  blt.s    loc_71C6
0x71e0  ldarg.0
0x71e1  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_Count
0x71e6  ldarg.0
0x71e7  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x71ec  ldloc.1
0x71ed  stelem.i4
0x71ee  ldarg.1
0x71ef  callvirt instance valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration[] Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::GetChangedFormats()
0x71f4  stloc.3
0x71f5  ldc.i4.m1
0x71f6  stloc.s  4
0x71f8  ldloc.3
0x71f9  brfalse.s loc_7227
0x71fb  ldloc.3
0x71fc  ldlen
0x71fd  conv.i4
0x71fe  stloc.s  4
0x7200  ldc.i4.0
0x7201  stloc.s  5
0x7203  ldc.i4.0
0x7204  stloc.s  5
0x7206  br.s     loc_7221
0x7208  ldarg.0
0x7209  ldloc.3
0x720a  ldloc.s  5
0x720c  ldelema  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x7211  ldobj    Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x7216  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextChangedFormats(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration obj)
0x721b  ldloc.s  5
0x721d  ldc.i4.1
0x721e  add
0x721f  stloc.s  5
0x7221  ldloc.s  5
0x7223  ldloc.s  4
0x7225  blt.s    loc_7208
0x7227  ldarg.0
0x7228  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_Count
0x722d  ldarg.0
0x722e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7233  ldloc.s  4
0x7235  stelem.i4
0x7236  ldarg.1
0x7237  callvirt instance valuetype Microsoft.ManagementConsole.Internal.ClipboardData[] Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::GetUpdatedData()
0x723c  stloc.s  6
0x723e  ldc.i4.m1
0x723f  stloc.s  7
0x7241  ldloc.s  6
0x7243  brfalse.s loc_7273
0x7245  ldloc.s  6
0x7247  ldlen
0x7248  conv.i4
0x7249  stloc.s  7
0x724b  ldc.i4.0
0x724c  stloc.s  8
0x724e  ldc.i4.0
0x724f  stloc.s  8
0x7251  br.s     loc_726D
0x7253  ldarg.0
0x7254  ldloc.s  6
0x7256  ldloc.s  8
0x7258  ldelema  Microsoft.ManagementConsole.Internal.ClipboardData
0x725d  ldobj    Microsoft.ManagementConsole.Internal.ClipboardData
0x7262  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextUpdatedData(valuetype Microsoft.ManagementConsole.Internal.ClipboardData obj)
0x7267  ldloc.s  8
0x7269  ldc.i4.1
0x726a  add
0x726b  stloc.s  8
0x726d  ldloc.s  8
0x726f  ldloc.s  7
0x7271  blt.s    loc_7253
0x7273  ldarg.0
0x7274  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Count
0x7279  ldarg.0
0x727a  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x727f  ldloc.s  7
0x7281  stelem.i4
0x7282  ldarg.1
0x7283  callvirt instance string[] Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::GetRemovedClipboardFormatIds()
0x7288  stloc.s  9
0x728a  ldc.i4.m1
0x728b  stloc.s  0xA
0x728d  ldloc.s  9
0x728f  brfalse.s loc_72B6
0x7291  ldloc.s  9
0x7293  ldlen
0x7294  conv.i4
0x7295  stloc.s  0xA
0x7297  ldc.i4.0
0x7298  stloc.s  0xB
0x729a  ldc.i4.0
0x729b  stloc.s  0xB
0x729d  br.s     loc_72B0
0x729f  ldarg.0
0x72a0  ldloc.s  9
0x72a2  ldloc.s  0xB
0x72a4  ldelem.ref
0x72a5  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x72aa  ldloc.s  0xB
0x72ac  ldc.i4.1
0x72ad  add
0x72ae  stloc.s  0xB
0x72b0  ldloc.s  0xB
0x72b2  ldloc.s  0xA
0x72b4  blt.s    loc_729F
0x72b6  ldarg.0
0x72b7  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_RemovedClipboardFormatIds_Count
0x72bc  ldarg.0
0x72bd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x72c2  ldloc.s  0xA
0x72c4  stelem.i4
0x72c5  ret
```
