# Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateSelectionAction

- ea: `0x7950`
- end: `0x79e1`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateSelectionAction`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x68d0`

## callees

- `0x7950`
- `0x79f0`
- `0x7a80`

## pseudocode

```c

```

## disassembly

```asm
0x7950  ldarg.2
0x7951  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs/RootNodeNotificationType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::get_NotificationType()
0x7956  stloc.0
0x7957  ldloc.0
0x7958  ldc.i4.1
0x7959  beq.s    loc_7960
0x795b  ldloc.0
0x795c  ldc.i4.2
0x795d  beq.s    loc_797C
0x795f  ret
0x7960  ldarg.0
0x7961  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7966  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_ActionsPaneItems()
0x796b  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x7970  ldarg.0
0x7971  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7976  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Clear()
0x797b  ret
0x797c  ldarg.0
0x797d  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7982  ldarg.2
0x7983  callvirt instance object [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::get_NotificationData()
0x7988  ldc.i4.0
0x7989  ldnull
0x798a  ldnull
0x798b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::Update(object, bool, valuetype [mscorlib]System.Guid[], class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.WritableSharedData)
0x7990  ldarg.0
0x7991  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7996  ldarg.0
0x7997  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x799c  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_HelpTopic()
0x79a1  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_HelpTopic(string)
0x79a6  ldarg.0
0x79a7  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x79ac  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_ActionsPaneItems()
0x79b1  ldarg.0
0x79b2  ldarg.1
0x79b3  ldarg.2
0x79b4  callvirt instance object [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::get_NotificationData()
0x79b9  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action Microsoft.EventViewer.SnapIn.EventViewerHomepage::GenerateAction(object GenerateFor, object data)
0x79be  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x79c3  pop
0x79c4  ldarg.0
0x79c5  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x79ca  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::get_ActionsPaneHelpItems()
0x79cf  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x79d4  ldarg.0
0x79d5  ldarg.2
0x79d6  callvirt instance object [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::get_NotificationData()
0x79db  call     instance void Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateSelectionDataDisplayName(object args)
0x79e0  ret
```
