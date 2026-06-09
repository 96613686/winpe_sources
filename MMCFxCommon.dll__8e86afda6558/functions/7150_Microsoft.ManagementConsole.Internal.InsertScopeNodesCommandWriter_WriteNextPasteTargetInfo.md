# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextPasteTargetInfo

- ea: `0x7150`
- end: `0x7199`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextPasteTargetInfo`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x6fb0`

## callees

- `0xea0`
- `0xec0`
- `0x7130`
- `0x7150`

## pseudocode

```c

```

## disassembly

```asm
0x7150  ldarg.0
0x7151  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_DefaultDragAndDropVerb
0x7156  ldarg.0
0x7157  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x715c  ldarg.1
0x715d  callvirt instance valuetype Microsoft.ManagementConsole.Internal.DragAndDropVerb Microsoft.ManagementConsole.Internal.PasteTargetInfo::get_DefaultDragAndDropVerb()
0x7162  stelem.i4
0x7163  ldarg.1
0x7164  callvirt instance string[] Microsoft.ManagementConsole.Internal.PasteTargetInfo::GetAllowedClipboardFormats()
0x7169  stloc.0
0x716a  ldc.i4.m1
0x716b  stloc.1
0x716c  ldloc.0
0x716d  brfalse.s loc_718A
0x716f  ldloc.0
0x7170  ldlen
0x7171  conv.i4
0x7172  stloc.1
0x7173  ldc.i4.0
0x7174  stloc.2
0x7175  ldc.i4.0
0x7176  stloc.2
0x7177  br.s     loc_7186
0x7179  ldarg.0
0x717a  ldloc.0
0x717b  ldloc.2
0x717c  ldelem.ref
0x717d  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x7182  ldloc.2
0x7183  ldc.i4.1
0x7184  add
0x7185  stloc.2
0x7186  ldloc.2
0x7187  ldloc.1
0x7188  blt.s    loc_7179
0x718a  ldarg.0
0x718b  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_AllowedClipboardFormats_Count
0x7190  ldarg.0
0x7191  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7196  ldloc.1
0x7197  stelem.i4
0x7198  ret
```
