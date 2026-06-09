# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextSubItems

- ea: `0x5b80`
- end: `0x5b99`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextSubItems`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5970`

## callees

- `0x850`
- `0x880`

## pseudocode

```c

```

## disassembly

```asm
0x5b80  newobj   instance void Microsoft.ManagementConsole.Internal.NodeSubItemData::.ctor()
0x5b85  stloc.0
0x5b86  ldloc.0
0x5b87  ldarg.0
0x5b88  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5b8d  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5b92  callvirt instance void Microsoft.ManagementConsole.Internal.NodeSubItemData::set_DisplayName(string value)
0x5b97  ldloc.0
0x5b98  ret
```
