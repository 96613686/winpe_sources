# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadScopeNodeInsert

- ea: `0x58d0`
- end: `0x5962`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadScopeNodeInsert`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0xfb0`
- `0xfe0`
- `0x1010`
- `0x1020`
- `0x1050`
- `0x1070`
- `0x5880`
- `0x58d0`
- `0x5970`
- `0x5ba0`
- `0x5e10`
- `0x6280`
- `0x7980`
- `0x79a0`

## pseudocode

```c

```

## disassembly

```asm
0x58d0  ldarg.0
0x58d1  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x58d6  ldarg.0
0x58d7  call     instance int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::get_Count()
0x58dc  blt.s    loc_58E4
0x58de  newobj   instance void [mscorlib]System.IO.EndOfStreamException::.ctor()
0x58e3  throw
0x58e4  ldloca.s 0
0x58e6  initobj  Microsoft.ManagementConsole.Internal.ScopeNodeInsert
0x58ec  ldloca.s 0
0x58ee  ldarg.0
0x58ef  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x58f4  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_ParentScopeNodeId()
0x58f9  ldarg.0
0x58fa  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x58ff  ldelem.i4
0x5900  call     instance void Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_ParentScopeNodeId(int32 value)
0x5905  ldloca.s 0
0x5907  ldarg.0
0x5908  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x590d  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InsertionIndex()
0x5912  ldarg.0
0x5913  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5918  ldelem.i4
0x5919  call     instance void Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_InsertionIndex(int32 value)
0x591e  ldloca.s 0
0x5920  ldarg.0
0x5921  call     instance class Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextNodeData()
0x5926  call     instance void Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_NodeData(class Microsoft.ManagementConsole.Internal.ScopeNodeData value)
0x592b  ldarg.0
0x592c  ldloca.s 0
0x592e  call     instance class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_InitialSharedData()
0x5933  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextInitialSharedData(class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate obj)
0x5938  ldloca.s 0
0x593a  ldarg.0
0x593b  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextActions()
0x5940  call     instance void Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_Actions(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData value)
0x5945  ldloca.s 0
0x5947  ldarg.0
0x5948  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextHelpActions()
0x594d  call     instance void Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_HelpActions(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData value)
0x5952  ldarg.0
0x5953  ldarg.0
0x5954  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5959  ldc.i4.1
0x595a  add
0x595b  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5960  ldloc.0
0x5961  ret
```
