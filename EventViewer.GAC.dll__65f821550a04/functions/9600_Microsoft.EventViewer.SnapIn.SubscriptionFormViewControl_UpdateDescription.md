# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateDescription

- ea: `0x9600`
- end: `0x961d`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateDescription`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7cb0`
- `0x9600`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldarg.0
0x9601  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionDetailControl Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::subscriptionControl
0x9606  brfalse.s loc_961C
0x9608  ldarg.0
0x9609  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::get_ValidView()
0x960e  brfalse.s loc_961C
0x9610  ldarg.0
0x9611  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x9616  ldarg.1
0x9617  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::set_DescriptionBarText(string)
0x961c  ret
```
