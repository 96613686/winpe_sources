# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString

- ea: `0x7130`
- end: `0x7147`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString`
- size: `23`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6fb0`
- `0x7150`
- `0x71a0`
- `0x71b0`
- `0x72d0`
- `0x72f0`
- `0x7310`
- `0x7350`
- `0x7630`

## callees

- `0x7130`

## pseudocode

```c

```

## disassembly

```asm
0x7130  ldarg.1
0x7131  brtrue.s loc_713A
0x7133  ldsfld   string [mscorlib]System.String::Empty
0x7138  starg.s  1
0x713a  ldarg.0
0x713b  ldfld    class [mscorlib]System.IO.BinaryWriter Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_strings
0x7140  ldarg.1
0x7141  callvirt instance void [mscorlib]System.IO.BinaryWriter::Write(string)
0x7146  ret
```
