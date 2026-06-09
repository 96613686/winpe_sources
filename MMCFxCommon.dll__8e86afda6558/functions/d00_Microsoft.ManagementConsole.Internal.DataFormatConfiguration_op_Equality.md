# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Equality

- ea: `0xd00`
- end: `0xd14`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Equality`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd20`
- `0xd30`

## callees

- `0xcc0`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarga.s 0
0xd02  call     instance string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId()
0xd07  ldarga.s 1
0xd09  call     instance string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId()
0xd0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd13  ret
```
