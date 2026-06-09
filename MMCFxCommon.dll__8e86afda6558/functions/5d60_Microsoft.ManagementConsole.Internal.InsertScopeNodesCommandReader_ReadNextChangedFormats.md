# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextChangedFormats

- ea: `0x5d60`
- end: `0x5d95`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextChangedFormats`
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
- `0x7be0`

## pseudocode

```c

```

## disassembly

```asm
0x5d60  ldloca.s 0
0x5d62  initobj  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5d68  ldloca.s 0
0x5d6a  ldarg.0
0x5d6b  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5d70  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5d75  call     instance void Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_ClipboardFormatId(string value)
0x5d7a  ldloca.s 0
0x5d7c  ldarg.0
0x5d7d  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5d82  callvirt instance bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_ChangedFormats_RequiresQuery()
0x5d87  ldarg.0
0x5d88  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_ChangedFormats_Offset
0x5d8d  ldelem.i1
0x5d8e  call     instance void Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_RequiresQuery(bool value)
0x5d93  ldloc.0
0x5d94  ret
```
