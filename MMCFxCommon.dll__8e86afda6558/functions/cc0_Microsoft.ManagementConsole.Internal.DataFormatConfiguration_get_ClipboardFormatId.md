# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId

- ea: `0xcc0`
- end: `0xcc7`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::get_ClipboardFormatId`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd00`
- `0xd50`
- `0x72d0`
- `0x72f0`

## pseudocode

```c

```

## disassembly

```asm
0xcc0  ldarg.0
0xcc1  ldfld    string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::_clipboardFormatId
0xcc6  ret
```
