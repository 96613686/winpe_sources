# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextNodeData

- ea: `0x6fb0`
- end: `0x70f2`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextNodeData`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x6f20`

## callees

- `0x7a0`
- `0x7c0`
- `0x7e0`
- `0x820`
- `0x8b0`
- `0x8d0`
- `0x8f0`
- `0x910`
- `0x930`
- `0x950`
- `0x970`
- `0x990`
- `0x9d0`
- `0x9f0`
- `0x6fb0`
- `0x7130`
- `0x7150`
- `0x71a0`
- `0x81a0`
- `0x81b0`
- `0x8200`

## pseudocode

```c

```

## disassembly

```asm
0x6fb0  ldarg.1
0x6fb1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ManagementConsole.Internal.ScopeNodeData::get_NodeType()
0x6fb6  stloc.0
0x6fb7  ldarg.0
0x6fb8  ldfld    class Microsoft.ManagementConsole.Internal.GuidList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType
0x6fbd  ldloc.0
0x6fbe  callvirt instance int32 Microsoft.ManagementConsole.Internal.GuidList::IndexOf(valuetype [mscorlib]System.Guid item)
0x6fc3  stloc.1
0x6fc4  ldloc.1
0x6fc5  ldc.i4.0
0x6fc6  bge.s    loc_6FE0
0x6fc8  ldarg.0
0x6fc9  ldfld    class Microsoft.ManagementConsole.Internal.GuidList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType
0x6fce  callvirt instance int32 Microsoft.ManagementConsole.Internal.GuidList::get_Count()
0x6fd3  stloc.1
0x6fd4  ldarg.0
0x6fd5  ldfld    class Microsoft.ManagementConsole.Internal.GuidList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType
0x6fda  ldloc.0
0x6fdb  callvirt instance void Microsoft.ManagementConsole.Internal.GuidList::Add(valuetype [mscorlib]System.Guid item)
0x6fe0  ldarg.0
0x6fe1  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType_Id
0x6fe6  ldarg.0
0x6fe7  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6fec  ldloc.1
0x6fed  stelem.i4
0x6fee  ldarg.0
0x6fef  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SelectedImageIndex
0x6ff4  ldarg.0
0x6ff5  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6ffa  ldarg.1
0x6ffb  callvirt instance int32 Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SelectedImageIndex()
0x7000  stelem.i4
0x7001  ldarg.0
0x7002  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_HideExpandIcon
0x7007  ldarg.0
0x7008  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x700d  ldarg.1
0x700e  callvirt instance bool Microsoft.ManagementConsole.Internal.ScopeNodeData::get_HideExpandIcon()
0x7013  stelem.i1
0x7014  ldarg.0
0x7015  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendActivation
0x701a  ldarg.0
0x701b  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7020  ldarg.1
0x7021  callvirt instance bool Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SendActivation()
0x7026  stelem.i1
0x7027  ldarg.0
0x7028  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendDeactivation
0x702d  ldarg.0
0x702e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7033  ldarg.1
0x7034  callvirt instance bool Microsoft.ManagementConsole.Internal.ScopeNodeData::get_SendDeactivation()
0x7039  stelem.i1
0x703a  ldarg.0
0x703b  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ViewSetId
0x7040  ldarg.0
0x7041  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7046  ldarg.1
0x7047  callvirt instance int32 Microsoft.ManagementConsole.Internal.ScopeNodeData::get_ViewSetId()
0x704c  stelem.i4
0x704d  ldarg.0
0x704e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_EnabledVerbs
0x7053  ldarg.0
0x7054  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7059  ldarg.1
0x705a  callvirt instance valuetype Microsoft.ManagementConsole.Internal.StandardVerbs Microsoft.ManagementConsole.Internal.ScopeNodeData::get_EnabledVerbs()
0x705f  stelem.i4
0x7060  ldarg.0
0x7061  ldarg.1
0x7062  callvirt instance string Microsoft.ManagementConsole.Internal.ScopeNodeData::get_LanguageIndependentName()
0x7067  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x706c  ldarg.0
0x706d  ldarg.1
0x706e  callvirt instance string Microsoft.ManagementConsole.Internal.ScopeNodeData::get_HelpTopic()
0x7073  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x7078  ldarg.0
0x7079  ldarg.1
0x707a  callvirt instance class Microsoft.ManagementConsole.Internal.PasteTargetInfo Microsoft.ManagementConsole.Internal.ScopeNodeData::get_PasteTargetInfo()
0x707f  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextPasteTargetInfo(class Microsoft.ManagementConsole.Internal.PasteTargetInfo obj)
0x7084  ldarg.0
0x7085  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_Id
0x708a  ldarg.0
0x708b  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7090  ldarg.1
0x7091  callvirt instance int32 Microsoft.ManagementConsole.Internal.NodeData::get_Id()
0x7096  stelem.i4
0x7097  ldarg.0
0x7098  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ImageIndex
0x709d  ldarg.0
0x709e  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x70a3  ldarg.1
0x70a4  callvirt instance int32 Microsoft.ManagementConsole.Internal.NodeData::get_ImageIndex()
0x70a9  stelem.i4
0x70aa  ldarg.0
0x70ab  ldarg.1
0x70ac  callvirt instance string Microsoft.ManagementConsole.Internal.NodeData::get_DisplayName()
0x70b1  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x70b6  ldarg.1
0x70b7  callvirt instance class Microsoft.ManagementConsole.Internal.NodeSubItemData[] Microsoft.ManagementConsole.Internal.NodeData::GetSubItems()
0x70bc  stloc.2
0x70bd  ldc.i4.m1
0x70be  stloc.3
0x70bf  ldloc.2
0x70c0  brfalse.s loc_70E3
0x70c2  ldloc.2
0x70c3  ldlen
0x70c4  conv.i4
0x70c5  stloc.3
0x70c6  ldc.i4.0
0x70c7  stloc.s  4
0x70c9  ldc.i4.0
0x70ca  stloc.s  4
0x70cc  br.s     loc_70DE
0x70ce  ldarg.0
0x70cf  ldloc.2
0x70d0  ldloc.s  4
0x70d2  ldelem.ref
0x70d3  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextSubItems(class Microsoft.ManagementConsole.Internal.NodeSubItemData obj)
0x70d8  ldloc.s  4
0x70da  ldc.i4.1
0x70db  add
0x70dc  stloc.s  4
0x70de  ldloc.s  4
0x70e0  ldloc.3
0x70e1  blt.s    loc_70CE
0x70e3  ldarg.0
0x70e4  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SubItems_Count
0x70e9  ldarg.0
0x70ea  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x70ef  ldloc.3
0x70f0  stelem.i4
0x70f1  ret
```
