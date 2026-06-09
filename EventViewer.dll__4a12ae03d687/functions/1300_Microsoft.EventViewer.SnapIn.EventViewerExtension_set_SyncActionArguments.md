# Microsoft.EventViewer.SnapIn.EventViewerExtension::set_SyncActionArguments

- ea: `0x1300`
- end: `0x1321`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::set_SyncActionArguments`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1b70`

## callees

- `0x1300`

## pseudocode

```c

```

## disassembly

```asm
0x1300  ldarg.0
0x1301  ldarg.1
0x1302  stfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncActionEventArgs Microsoft.EventViewer.SnapIn.EventViewerExtension::syncArgs
0x1307  ldarg.0
0x1308  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncActionEventArgs Microsoft.EventViewer.SnapIn.EventViewerExtension::syncArgs
0x130d  brfalse.s loc_1320
0x130f  ldarg.0
0x1310  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncActionEventArgs Microsoft.EventViewer.SnapIn.EventViewerExtension::syncArgs
0x1315  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncStatus [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncActionEventArgs::get_Status()
0x131a  ldc.i4.0
0x131b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncStatus::set_CanCancel(bool)
0x1320  ret
```
