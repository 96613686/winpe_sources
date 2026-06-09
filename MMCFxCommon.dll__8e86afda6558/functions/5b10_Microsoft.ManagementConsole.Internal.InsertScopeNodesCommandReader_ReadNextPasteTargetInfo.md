# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextPasteTargetInfo

- ea: `0x5b10`
- end: `0x5b7a`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextPasteTargetInfo`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x5970`

## callees

- `0xeb0`
- `0xed0`
- `0x5b10`
- `0x7ae0`
- `0x7b00`

## pseudocode

```c

```

## disassembly

```asm
0x5b10  ldarg.1
0x5b11  ldarg.0
0x5b12  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5b17  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_PasteTargetInfo_DefaultDragAndDropVerb()
0x5b1c  ldarg.0
0x5b1d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5b22  ldelem.i4
0x5b23  callvirt instance void Microsoft.ManagementConsole.Internal.PasteTargetInfo::set_DefaultDragAndDropVerb(valuetype Microsoft.ManagementConsole.Internal.DragAndDropVerb value)
0x5b28  ldarg.0
0x5b29  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5b2e  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_PasteTargetInfo_AllowedClipboardFormats_Count()
0x5b33  ldarg.0
0x5b34  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5b39  ldelem.i4
0x5b3a  stloc.0
0x5b3b  ldnull
0x5b3c  stloc.1
0x5b3d  ldloc.0
0x5b3e  ldc.i4.0
0x5b3f  blt.s    loc_5B48
0x5b41  ldloc.0
0x5b42  newarr   [mscorlib]System.String
0x5b47  stloc.1
0x5b48  ldc.i4.0
0x5b49  stloc.2
0x5b4a  ldc.i4.0
0x5b4b  stloc.2
0x5b4c  br.s     loc_5B6E
0x5b4e  ldloc.1
0x5b4f  ldloc.2
0x5b50  ldarg.0
0x5b51  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5b56  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5b5b  stelem.ref
0x5b5c  ldarg.0
0x5b5d  ldarg.0
0x5b5e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_NodeData_PasteTargetInfo_AllowedClipboardFormats_Offset
0x5b63  ldc.i4.1
0x5b64  add
0x5b65  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_NodeData_PasteTargetInfo_AllowedClipboardFormats_Offset
0x5b6a  ldloc.2
0x5b6b  ldc.i4.1
0x5b6c  add
0x5b6d  stloc.2
0x5b6e  ldloc.2
0x5b6f  ldloc.0
0x5b70  blt.s    loc_5B4E
0x5b72  ldarg.1
0x5b73  ldloc.1
0x5b74  callvirt instance void Microsoft.ManagementConsole.Internal.PasteTargetInfo::SetAllowedClipboardFormats(string[] allowedClipboardFormats)
0x5b79  ret
```
