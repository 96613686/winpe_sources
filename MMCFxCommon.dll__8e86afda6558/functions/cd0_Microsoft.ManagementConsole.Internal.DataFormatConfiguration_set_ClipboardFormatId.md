# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_ClipboardFormatId

- ea: `0xcd0`
- end: `0xcde`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::set_ClipboardFormatId`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5d20`
- `0x5d60`

## callees

- `0xbd0`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldarg.1
0xcd1  call     void Microsoft.ManagementConsole.Internal.CommonValidation::ValidateClipboardFormatId(string clipboardFormatId)
0xcd6  ldarg.0
0xcd7  ldarg.1
0xcd8  stfld    string Microsoft.ManagementConsole.Internal.DataFormatConfiguration::_clipboardFormatId
0xcdd  ret
```
