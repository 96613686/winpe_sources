# Microsoft.ManagementConsole.Advanced.PropertySheetExtension::SharedDataChanged

- ea: `0x4e10`
- end: `0x4e1d`
- name: `Microsoft.ManagementConsole.Advanced.PropertySheetExtension::SharedDataChanged`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4e20`
- `0x4e70`

## pseudocode

```c

```

## disassembly

```asm
0x4e10  ldarg.0
0x4e11  ldarg.2
0x4e12  callvirt instance class Microsoft.ManagementConsole.SharedDataItem Microsoft.ManagementConsole.SharedDataChangedEventArgs::get_SharedDataItem()
0x4e17  callvirt instance void Microsoft.ManagementConsole.Advanced.PropertySheetExtension::OnSharedDataChanged(class Microsoft.ManagementConsole.SharedDataItem item)
0x4e1c  ret
```
