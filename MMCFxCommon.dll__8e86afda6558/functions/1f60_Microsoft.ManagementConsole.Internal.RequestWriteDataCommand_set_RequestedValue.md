# Microsoft.ManagementConsole.Internal.RequestWriteDataCommand::set_RequestedValue

- ea: `0x1f60`
- end: `0x1f74`
- name: `Microsoft.ManagementConsole.Internal.RequestWriteDataCommand::set_RequestedValue`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xbd0`
- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0x1f60  ldarga.s 1
0x1f62  call     instance string Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0x1f67  call     void Microsoft.ManagementConsole.Internal.CommonValidation::ValidateClipboardFormatId(string clipboardFormatId)
0x1f6c  ldarg.0
0x1f6d  ldarg.1
0x1f6e  stfld    valuetype Microsoft.ManagementConsole.Internal.ClipboardData Microsoft.ManagementConsole.Internal.RequestWriteDataCommand::_requestedValue
0x1f73  ret
```
