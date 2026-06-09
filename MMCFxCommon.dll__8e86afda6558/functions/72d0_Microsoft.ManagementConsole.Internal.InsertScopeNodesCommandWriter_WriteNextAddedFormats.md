# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextAddedFormats

- ea: `0x72d0`
- end: `0x72f0`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextAddedFormats`
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
0x72d0  ldarg.0
0x72d1  ldarga.s 1
0x72d3  call     instance string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId()
0x72d8  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x72dd  ldarg.0
0x72de  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_RequiresQuery
0x72e3  ldarga.s 1
0x72e5  call     instance bool Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_RequiresQuery()
0x72ea  callvirt instance void Microsoft.ManagementConsole.Internal.BooleanList::Add(bool item)
0x72ef  ret
```
