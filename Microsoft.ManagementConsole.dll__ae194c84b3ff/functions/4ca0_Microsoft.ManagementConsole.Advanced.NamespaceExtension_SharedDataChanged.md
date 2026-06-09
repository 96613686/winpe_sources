# Microsoft.ManagementConsole.Advanced.NamespaceExtension::SharedDataChanged

- ea: `0x4ca0`
- end: `0x4cad`
- name: `Microsoft.ManagementConsole.Advanced.NamespaceExtension::SharedDataChanged`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4cb0`
- `0x4e70`

## pseudocode

```c

```

## disassembly

```asm
0x4ca0  ldarg.0
0x4ca1  ldarg.2
0x4ca2  callvirt instance class Microsoft.ManagementConsole.SharedDataItem Microsoft.ManagementConsole.SharedDataChangedEventArgs::get_SharedDataItem()
0x4ca7  callvirt instance void Microsoft.ManagementConsole.Advanced.NamespaceExtension::OnSharedDataChanged(class Microsoft.ManagementConsole.SharedDataItem item)
0x4cac  ret
```
