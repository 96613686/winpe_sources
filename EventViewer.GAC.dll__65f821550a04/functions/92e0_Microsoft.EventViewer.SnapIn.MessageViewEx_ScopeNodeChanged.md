# Microsoft.EventViewer.SnapIn.MessageViewEx::ScopeNodeChanged

- ea: `0x92e0`
- end: `0x9300`
- name: `Microsoft.EventViewer.SnapIn.MessageViewEx::ScopeNodeChanged`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x92e0`
- `0x93b0`

## pseudocode

```c

```

## disassembly

```asm
0x92e0  ldarg.0
0x92e1  ldfld    bool Microsoft.EventViewer.SnapIn.MessageViewEx::activeView
0x92e6  brtrue.s loc_92E9
0x92e8  ret
0x92e9  nop
0x92ea  ldarg.1
0x92eb  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x92f0  ldc.i4.s 0xA
0x92f2  bne.un.s loc_92FA
0x92f4  ldarg.0
0x92f5  call     instance void Microsoft.EventViewer.SnapIn.MessageViewEx::SwitchBackToNormalView()
0x92fa  leave.s  loc_92FF
0x92fc  pop
0x92fd  leave.s  loc_92FF
0x92ff  ret
```
