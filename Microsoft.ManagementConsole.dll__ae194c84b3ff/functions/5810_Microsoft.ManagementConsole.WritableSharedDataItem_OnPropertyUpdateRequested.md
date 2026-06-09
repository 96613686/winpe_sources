# Microsoft.ManagementConsole.WritableSharedDataItem::OnPropertyUpdateRequested

- ea: `0x5810`
- end: `0x582d`
- name: `Microsoft.ManagementConsole.WritableSharedDataItem::OnPropertyUpdateRequested`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b00`

## callees

- `0x54b0`
- `0x5810`
- `0x5920`

## pseudocode

```c

```

## disassembly

```asm
0x5810  ldarg.0
0x5811  ldfld    class SharedDataChangeRequestEventHandler Microsoft.ManagementConsole.WritableSharedDataItem::PropertyChangeRequested
0x5816  brfalse.s loc_582C
0x5818  ldarg.0
0x5819  ldfld    class SharedDataChangeRequestEventHandler Microsoft.ManagementConsole.WritableSharedDataItem::PropertyChangeRequested
0x581e  ldarg.0
0x581f  ldarg.1
0x5820  ldarg.2
0x5821  ldarg.0
0x5822  newobj   instance void Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs::.ctor(unsigned int8[] newValue, class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus, class Microsoft.ManagementConsole.WritableSharedDataItem publishedDataItem)
0x5827  callvirt instance void SharedDataChangeRequestEventHandler::Invoke(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs e)
0x582c  ret
```
