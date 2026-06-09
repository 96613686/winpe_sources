# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextChangedFormats

- ea: `0x72f0`
- end: `0x7310`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextChangedFormats`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x71b0`

## callees

- `0xcc0`
- `0xce0`
- `0x7130`
- `0x82f0`

## pseudocode

```c

```

## disassembly

```asm
0x72f0  ldarg.0
0x72f1  ldarga.s 1
0x72f3  call     instance string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId()
0x72f8  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x72fd  ldarg.0
0x72fe  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_RequiresQuery
0x7303  ldarga.s 1
0x7305  call     instance bool Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_RequiresQuery()
0x730a  callvirt instance void Microsoft.ManagementConsole.Internal.BooleanList::Add(bool item)
0x730f  ret
```
