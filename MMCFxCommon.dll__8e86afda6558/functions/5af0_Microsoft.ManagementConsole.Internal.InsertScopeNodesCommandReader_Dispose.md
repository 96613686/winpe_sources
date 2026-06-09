# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::Dispose

- ea: `0x5af0`
- end: `0x5b0c`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::Dispose`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5af0`

## pseudocode

```c

```

## disassembly

```asm
0x5af0  ldarg.0
0x5af1  ldfld    bool Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_disposed
0x5af6  brfalse.s loc_5AF9
0x5af8  ret
0x5af9  ldarg.0
0x5afa  ldc.i4.1
0x5afb  stfld    bool Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_disposed
0x5b00  ldarg.0
0x5b01  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5b06  callvirt instance void [mscorlib]System.IO.BinaryReader::Close()
0x5b0b  ret
```
