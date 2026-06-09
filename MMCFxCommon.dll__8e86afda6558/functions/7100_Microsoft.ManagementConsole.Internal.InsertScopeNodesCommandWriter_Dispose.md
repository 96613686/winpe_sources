# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::Dispose

- ea: `0x7100`
- end: `0x7127`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::Dispose`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7100`

## pseudocode

```c

```

## disassembly

```asm
0x7100  ldarg.0
0x7101  ldfld    bool Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_disposed
0x7106  brfalse.s loc_7109
0x7108  ret
0x7109  ldarg.0
0x710a  ldc.i4.1
0x710b  stfld    bool Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_disposed
0x7110  ldarg.0
0x7111  ldfld    class [mscorlib]System.IO.BinaryWriter Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_strings
0x7116  callvirt instance void [mscorlib]System.IO.BinaryWriter::Close()
0x711b  ldarg.0
0x711c  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_stream_strings
0x7121  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x7126  ret
```
