# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextNodeData

- ea: `0x5970`
- end: `0x5af0`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextNodeData`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0x7b0`
- `0x7d0`
- `0x7f0`
- `0x830`
- `0x8c0`
- `0x8e0`
- `0x900`
- `0x920`
- `0x940`
- `0x960`
- `0x980`
- `0x9c0`
- `0x9e0`
- `0x9f0`
- `0xa10`
- `0x5970`
- `0x5b10`
- `0x5b80`
- `0x79c0`
- `0x79e0`
- `0x7a00`
- `0x7a20`
- `0x7a40`
- `0x7a60`
- `0x7a80`
- `0x7aa0`
- `0x7b20`
- `0x7b40`
- `0x7b60`

## pseudocode

```c

```

## disassembly

```asm
0x5970  newobj   instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::.ctor()
0x5975  stloc.0
0x5976  ldloc.0
0x5977  ldarg.0
0x5978  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x597d  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_NodeType()
0x5982  ldarg.0
0x5983  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5988  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_NodeType_Id()
0x598d  ldarg.0
0x598e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5993  ldelem.i4
0x5994  ldelema  [mscorlib]System.Guid
0x5999  ldobj    [mscorlib]System.Guid
0x599e  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_NodeType(valuetype [mscorlib]System.Guid value)
0x59a3  ldloc.0
0x59a4  ldarg.0
0x59a5  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x59aa  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_SelectedImageIndex()
0x59af  ldarg.0
0x59b0  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x59b5  ldelem.i4
0x59b6  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SelectedImageIndex(int32 value)
0x59bb  ldloc.0
0x59bc  ldarg.0
0x59bd  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x59c2  callvirt instance bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_HideExpandIcon()
0x59c7  ldarg.0
0x59c8  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x59cd  ldelem.i1
0x59ce  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_HideExpandIcon(bool value)
0x59d3  ldloc.0
0x59d4  ldarg.0
0x59d5  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x59da  callvirt instance bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_SendActivation()
0x59df  ldarg.0
0x59e0  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x59e5  ldelem.i1
0x59e6  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SendActivation(bool value)
0x59eb  ldloc.0
0x59ec  ldarg.0
0x59ed  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x59f2  callvirt instance bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_SendDeactivation()
0x59f7  ldarg.0
0x59f8  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x59fd  ldelem.i1
0x59fe  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_SendDeactivation(bool value)
0x5a03  ldloc.0
0x5a04  ldarg.0
0x5a05  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5a0a  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_ViewSetId()
0x5a0f  ldarg.0
0x5a10  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5a15  ldelem.i4
0x5a16  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_ViewSetId(int32 value)
0x5a1b  ldloc.0
0x5a1c  ldarg.0
0x5a1d  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5a22  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_EnabledVerbs()
0x5a27  ldarg.0
0x5a28  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5a2d  ldelem.i4
0x5a2e  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_EnabledVerbs(valuetype Microsoft.ManagementConsole.Internal.StandardVerbs value)
0x5a33  ldloc.0
0x5a34  ldarg.0
0x5a35  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5a3a  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5a3f  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_LanguageIndependentName(string value)
0x5a44  ldloc.0
0x5a45  ldarg.0
0x5a46  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5a4b  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5a50  callvirt instance void Microsoft.ManagementConsole.Internal.ScopeNodeData::set_HelpTopic(string value)
0x5a55  ldarg.0
0x5a56  ldloc.0
0x5a57  callvirt instance class Microsoft.ManagementConsole.Internal.PasteTargetInfo Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo()
0x5a5c  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextPasteTargetInfo(class Microsoft.ManagementConsole.Internal.PasteTargetInfo obj)
0x5a61  ldloc.0
0x5a62  ldarg.0
0x5a63  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5a68  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_Id()
0x5a6d  ldarg.0
0x5a6e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5a73  ldelem.i4
0x5a74  callvirt instance void Microsoft.ManagementConsole.Internal.NodeData::set_Id(int32 value)
0x5a79  ldloc.0
0x5a7a  ldarg.0
0x5a7b  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5a80  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_ImageIndex()
0x5a85  ldarg.0
0x5a86  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5a8b  ldelem.i4
0x5a8c  callvirt instance void Microsoft.ManagementConsole.Internal.NodeData::set_ImageIndex(int32 value)
0x5a91  ldloc.0
0x5a92  ldarg.0
0x5a93  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5a98  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5a9d  callvirt instance void Microsoft.ManagementConsole.Internal.NodeData::set_DisplayName(string value)
0x5aa2  ldarg.0
0x5aa3  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5aa8  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_NodeData_SubItems_Count()
0x5aad  ldarg.0
0x5aae  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5ab3  ldelem.i4
0x5ab4  stloc.1
0x5ab5  ldnull
0x5ab6  stloc.2
0x5ab7  ldloc.1
0x5ab8  ldc.i4.0
0x5ab9  blt.s    loc_5AC2
0x5abb  ldloc.1
0x5abc  newarr   Microsoft.ManagementConsole.Internal.NodeSubItemData
0x5ac1  stloc.2
0x5ac2  ldc.i4.0
0x5ac3  stloc.3
0x5ac4  ldc.i4.0
0x5ac5  stloc.3
0x5ac6  br.s     loc_5AE3
0x5ac8  ldloc.2
0x5ac9  ldloc.3
0x5aca  ldarg.0
0x5acb  call     instance class Microsoft.ManagementConsole.Internal.NodeSubItemData Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextSubItems()
0x5ad0  stelem.ref
0x5ad1  ldarg.0
0x5ad2  ldarg.0
0x5ad3  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_NodeData_SubItems_Offset
0x5ad8  ldc.i4.1
0x5ad9  add
0x5ada  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_NodeData_SubItems_Offset
0x5adf  ldloc.3
0x5ae0  ldc.i4.1
0x5ae1  add
0x5ae2  stloc.3
0x5ae3  ldloc.3
0x5ae4  ldloc.1
0x5ae5  blt.s    loc_5AC8
0x5ae7  ldloc.0
0x5ae8  ldloc.2
0x5ae9  callvirt instance void Microsoft.ManagementConsole.Internal.NodeData::SetSubItems(class Microsoft.ManagementConsole.Internal.NodeSubItemData[] subItems)
0x5aee  ldloc.0
0x5aef  ret
```
