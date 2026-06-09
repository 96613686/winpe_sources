# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextAddedFormats

- ea: `0x5d20`
- end: `0x5d55`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextAddedFormats`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5ba0`

## callees

- `0xcd0`
- `0xcf0`
- `0x7ba0`

## pseudocode

```c

```

## disassembly

```asm
0x5d20  ldloca.s 0
0x5d22  initobj  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5d28  ldloca.s 0
0x5d2a  ldarg.0
0x5d2b  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5d30  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5d35  call     instance void Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_ClipboardFormatId(string value)
0x5d3a  ldloca.s 0
0x5d3c  ldarg.0
0x5d3d  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5d42  callvirt instance bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_AddedFormats_RequiresQuery()
0x5d47  ldarg.0
0x5d48  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_AddedFormats_Offset
0x5d4d  ldelem.i1
0x5d4e  call     instance void Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_RequiresQuery(bool value)
0x5d53  ldloc.0
0x5d54  ret
```
