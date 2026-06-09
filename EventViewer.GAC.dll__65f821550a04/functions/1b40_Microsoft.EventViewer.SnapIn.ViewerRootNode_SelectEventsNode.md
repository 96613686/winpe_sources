# Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode

- ea: `0x1b40`
- end: `0x1b6e`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode`
- size: `46`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x15c0`
- `0x1e70`
- `0x2050`
- `0x20b0`
- `0x20e0`
- `0x2230`
- `0x3be0`
- `0x4520`
- `0x4780`

## callees

- `0x1170`
- `0x1770`
- `0x1b40`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  ldarg.0
0x1b41  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x1b46  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x1b4b  stloc.0
0x1b4c  ldloc.0
0x1b4d  brfalse.s loc_1B57
0x1b4f  ldloc.0
0x1b50  ldarg.1
0x1b51  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x1b56  ret
0x1b57  ldarg.0
0x1b58  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x1b5d  isinst   Microsoft.EventViewer.SnapIn.EventViewerExtension
0x1b62  stloc.1
0x1b63  ldloc.1
0x1b64  brfalse.s loc_1B6D
0x1b66  ldloc.1
0x1b67  ldarg.1
0x1b68  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x1b6d  ret
```
