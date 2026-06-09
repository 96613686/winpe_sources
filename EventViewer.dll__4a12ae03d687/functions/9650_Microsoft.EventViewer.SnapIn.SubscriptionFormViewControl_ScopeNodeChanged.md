# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::ScopeNodeChanged

- ea: `0x9650`
- end: `0x9661`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::ScopeNodeChanged`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x9650`
- `0x96a0`

## pseudocode

```c

```

## disassembly

```asm
0x9650  ldarg.1
0x9651  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9656  ldc.i4.s 0xA
0x9658  bne.un.s loc_9660
0x965a  ldarg.0
0x965b  call     instance void Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::RefreshView()
0x9660  ret
```
