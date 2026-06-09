# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::get_Count

- ea: `0x5880`
- end: `0x588c`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::get_Count`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0x7960`

## pseudocode

```c

```

## disassembly

```asm
0x5880  ldarg.0
0x5881  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5886  callvirt instance int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::get_Count()
0x588b  ret
```
