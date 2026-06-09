# Microsoft.EventViewer.SnapIn.EventViewerExtension::RefreshConsole

- ea: `0x15c0`
- end: `0x176f`
- name: `Microsoft.EventViewer.SnapIn.EventViewerExtension::RefreshConsole`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3be0`

## callees

- `0x15c0`
- `0x1a00`
- `0x1b40`
- `0x22a0`
- `0x39e0`
- `0x4690`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x15c0  ldc.i4.0
0x15c1  stloc.0
0x15c2  ldarg.0
0x15c3  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x15c8  brfalse  loc_176E
0x15cd  ldarg.0
0x15ce  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x15d3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x15d8  ldc.i4.0
0x15d9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::get_Item(int32)
0x15de  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription
0x15e3  brfalse.s loc_15E7
0x15e5  ldc.i4.1
0x15e6  stloc.0
0x15e7  ldarg.0
0x15e8  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x15ed  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x15f2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x15f7  stloc.1
0x15f8  ldarg.1
0x15f9  brfalse.s loc_1606
0x15fb  ldarg.1
0x15fc  brfalse.s loc_161F
0x15fe  ldarg.1
0x15ff  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x1604  brfalse.s loc_161F
0x1606  nop
0x1607  ldarg.0
0x1608  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x160d  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1612  ldc.i4.0
0x1613  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::Refresh(bool)
0x1618  pop
0x1619  leave.s  loc_161F
0x161b  starg.s  1
0x161d  leave.s  loc_161F
0x161f  ldarg.0
0x1620  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1625  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x162a  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x162f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x1634  brtrue   loc_1709
0x1639  ldarg.0
0x163a  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x163f  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions()
0x1644  ldloc.0
0x1645  brtrue   loc_176E
0x164a  ldarg.0
0x164b  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1650  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x1655  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x165a  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::.ctor()
0x165f  stloc.2
0x1660  ldloc.2
0x1661  ldarg.1
0x1662  brfalse.s loc_166C
0x1664  ldarg.1
0x1665  callvirt instance string [mscorlib]System.Exception::get_Message()
0x166a  br.s     loc_1671
0x166c  ldsfld   string [mscorlib]System.String::Empty
0x1671  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_BodyText(string)
0x1676  ldloc.2
0x1677  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x167c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_Title(string)
0x1681  ldloc.2
0x1682  ldc.i4.1
0x1683  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_IconId(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewIcon)
0x1688  ldloc.2
0x1689  ldarg.0
0x168a  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x168f  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x1694  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_DisplayName(string)
0x1699  ldloc.2
0x169a  ldtoken  Microsoft.EventViewer.SnapIn.MessageViewEx
0x169f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_ViewType(class [mscorlib]System.Type)
0x16a9  ldarg.0
0x16aa  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16af  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x16b4  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x16b9  ldarg.0
0x16ba  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16bf  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x16c4  ldloc.2
0x16c5  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription)
0x16ca  pop
0x16cb  ldarg.0
0x16cc  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16d1  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x16d6  ldc.i4.0
0x16d7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::set_DefaultIndex(int32)
0x16dc  ldarg.0
0x16dd  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16e2  ldarg.0
0x16e3  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16e8  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x16ed  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x16f2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x16f7  ldarg.0
0x16f8  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x16fd  ldarg.0
0x16fe  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1703  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x1708  ret
0x1709  ldarg.0
0x170a  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x170f  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1714  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x1719  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x171e  ldc.i4.1
0x171f  ble.s    loc_176E
0x1721  ldarg.0
0x1722  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1727  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes()
0x172c  ldarg.0
0x172d  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1732  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions()
0x1737  ldloc.1
0x1738  brtrue.s loc_176E
0x173a  ldarg.0
0x173b  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1740  ldarg.0
0x1741  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1746  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x174b  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x1750  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x1755  ldc.i4.1
0x1756  cgt
0x1758  callvirt instance void Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage(bool homepage)
0x175d  ldarg.0
0x175e  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1763  ldarg.0
0x1764  ldfld    class Microsoft.EventViewer.SnapIn.MMCRootNode Microsoft.EventViewer.SnapIn.EventViewerExtension::rootNode
0x1769  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x176e  ret
```
