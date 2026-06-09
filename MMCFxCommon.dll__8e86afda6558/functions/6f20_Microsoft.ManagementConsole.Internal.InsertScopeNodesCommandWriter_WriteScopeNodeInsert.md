# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteScopeNodeInsert

- ea: `0x6f20`
- end: `0x6fa4`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteScopeNodeInsert`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0xfa0`
- `0xfd0`
- `0x1000`
- `0x1020`
- `0x1040`
- `0x1060`
- `0x6f20`
- `0x6fb0`
- `0x71b0`
- `0x7350`
- `0x7630`
- `0x7960`

## pseudocode

```c

```

## disassembly

```asm
0x6f20  ldarg.0
0x6f21  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6f26  ldarg.0
0x6f27  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6f2c  callvirt instance int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::get_Count()
0x6f31  blt.s    loc_6F39
0x6f33  newobj   instance void [mscorlib]System.IO.EndOfStreamException::.ctor()
0x6f38  throw
0x6f39  ldarg.0
0x6f3a  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_ParentScopeNodeId
0x6f3f  ldarg.0
0x6f40  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6f45  ldarga.s 1
0x6f47  call     instance int32 Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_ParentScopeNodeId()
0x6f4c  stelem.i4
0x6f4d  ldarg.0
0x6f4e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InsertionIndex
0x6f53  ldarg.0
0x6f54  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6f59  ldarga.s 1
0x6f5b  call     instance int32 Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_InsertionIndex()
0x6f60  stelem.i4
0x6f61  ldarg.0
0x6f62  ldarga.s 1
0x6f64  call     instance class Microsoft.ManagementConsole.Internal.ScopeNodeData Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_NodeData()
0x6f69  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextNodeData(class Microsoft.ManagementConsole.Internal.ScopeNodeData obj)
0x6f6e  ldarg.0
0x6f6f  ldarga.s 1
0x6f71  call     instance class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_InitialSharedData()
0x6f76  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextInitialSharedData(class Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate obj)
0x6f7b  ldarg.0
0x6f7c  ldarga.s 1
0x6f7e  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_Actions()
0x6f83  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextActions(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData obj)
0x6f88  ldarg.0
0x6f89  ldarga.s 1
0x6f8b  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData Microsoft.ManagementConsole.Internal.ScopeNodeInsert::get_HelpActions()
0x6f90  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextHelpActions(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootData obj)
0x6f95  ldarg.0
0x6f96  ldarg.0
0x6f97  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6f9c  ldc.i4.1
0x6f9d  add
0x6f9e  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x6fa3  ret
```
