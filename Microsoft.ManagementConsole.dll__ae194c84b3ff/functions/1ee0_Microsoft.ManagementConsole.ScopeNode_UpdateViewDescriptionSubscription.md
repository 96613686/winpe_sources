# Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription

- ea: `0x1ee0`
- end: `0x1f3e`
- name: `Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1640`
- `0x1e60`
- `0x1ea0`

## callees

- `0x16a0`
- `0x1ee0`
- `0x8f00`
- `0x8f20`
- `0x8f50`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  ldarg.1
0x1ee1  brfalse.s loc_1F0C
0x1ee3  ldarg.0
0x1ee4  call     instance class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptionsInternal()
0x1ee9  brfalse.s loc_1F0C
0x1eeb  ldarg.0
0x1eec  ldfld    bool Microsoft.ManagementConsole.ScopeNode::_fSubscribedToViewDescriptionEvents
0x1ef1  brtrue.s loc_1F0C
0x1ef3  ldarg.0
0x1ef4  call     instance class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptionsInternal()
0x1ef9  ldarg.0
0x1efa  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnViewDescriptionsChanged(object sender, class Microsoft.ManagementConsole.ViewDescriptionCollectionEventArgs e)
0x1f00  newobj   instance void ViewDescriptionCollectionEventHandler::.ctor(object object, native int method)
0x1f05  callvirt instance void Microsoft.ManagementConsole.ViewDescriptionCollection::add_ItemsChanged(class ViewDescriptionCollectionEventHandler value)
0x1f0a  br.s     loc_1F36
0x1f0c  ldarg.1
0x1f0d  brtrue.s loc_1F36
0x1f0f  ldarg.0
0x1f10  call     instance class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptionsInternal()
0x1f15  brfalse.s loc_1F36
0x1f17  ldarg.0
0x1f18  ldfld    bool Microsoft.ManagementConsole.ScopeNode::_fSubscribedToViewDescriptionEvents
0x1f1d  brfalse.s loc_1F36
0x1f1f  ldarg.0
0x1f20  call     instance class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptionsInternal()
0x1f25  ldarg.0
0x1f26  ldftn    instance void Microsoft.ManagementConsole.ScopeNode::OnViewDescriptionsChanged(object sender, class Microsoft.ManagementConsole.ViewDescriptionCollectionEventArgs e)
0x1f2c  newobj   instance void ViewDescriptionCollectionEventHandler::.ctor(object object, native int method)
0x1f31  callvirt instance void Microsoft.ManagementConsole.ViewDescriptionCollection::remove_ItemsChanged(class ViewDescriptionCollectionEventHandler value)
0x1f36  ldarg.0
0x1f37  ldarg.1
0x1f38  stfld    bool Microsoft.ManagementConsole.ScopeNode::_fSubscribedToViewDescriptionEvents
0x1f3d  ret
```
