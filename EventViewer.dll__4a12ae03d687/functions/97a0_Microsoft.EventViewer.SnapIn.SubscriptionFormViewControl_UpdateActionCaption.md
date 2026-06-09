# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateActionCaption

- ea: `0x97a0`
- end: `0x97e4`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::UpdateActionCaption`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9c80`

## callees

- `0x97a0`

## pseudocode

```c

```

## disassembly

```asm
0x97a0  ldarg.0
0x97a1  ldfld    string Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionDisplay
0x97a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x97ab  brtrue.s loc_97E3
0x97ad  ldarg.0
0x97ae  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x97b3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x97b8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::BeginUpdates()
0x97bd  ldarg.0
0x97be  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x97c3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x97c8  ldarg.0
0x97c9  ldfld    string Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::selectionDisplay
0x97ce  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x97d3  ldarg.0
0x97d4  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x97d9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x97de  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::EndUpdates()
0x97e3  ret
```
