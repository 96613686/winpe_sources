# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::RefreshConsole

- ea: `0x1010`
- end: `0x1162`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::RefreshConsole`
- size: `338`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x8d0`
- `0x9e0`
- `0x3be0`

## callees

- `0x1010`
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
0x1010  ldarg.0
0x1011  ldstr    aRefreshconsole// "RefreshConsole"
0x1016  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x101b  ldc.i4.0
0x101c  stloc.0
0x101d  ldarg.0
0x101e  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapIn::get_RootNode()
0x1023  castclass Microsoft.EventViewer.SnapIn.MMCRootNode
0x1028  stloc.1
0x1029  ldloc.1
0x102a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x102f  ldc.i4.0
0x1030  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::get_Item(int32)
0x1035  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription
0x103a  brfalse.s loc_103E
0x103c  ldc.i4.1
0x103d  stloc.0
0x103e  ldloc.1
0x103f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x1044  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1049  stloc.2
0x104a  ldarg.1
0x104b  brfalse.s loc_1058
0x104d  ldarg.1
0x104e  brfalse.s loc_106C
0x1050  ldarg.1
0x1051  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_RefreshConsole()
0x1056  brfalse.s loc_106C
0x1058  nop
0x1059  ldloc.1
0x105a  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x105f  ldloc.0
0x1060  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::Refresh(bool)
0x1065  pop
0x1066  leave.s  loc_106C
0x1068  starg.s  1
0x106a  leave.s  loc_106C
0x106c  ldloc.1
0x106d  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1072  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x1077  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x107c  brtrue   loc_111F
0x1081  ldloc.1
0x1082  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions()
0x1087  ldloc.0
0x1088  brtrue   loc_1161
0x108d  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::.ctor()
0x1092  stloc.3
0x1093  ldloc.3
0x1094  ldarg.1
0x1095  brfalse.s loc_109F
0x1097  ldarg.1
0x1098  callvirt instance string [mscorlib]System.Exception::get_Message()
0x109d  br.s     loc_10A4
0x109f  ldsfld   string [mscorlib]System.String::Empty
0x10a4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_BodyText(string)
0x10a9  ldloc.3
0x10aa  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x10af  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_Title(string)
0x10b4  ldloc.3
0x10b5  ldc.i4.1
0x10b6  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription::set_IconId(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewIcon)
0x10bb  ldloc.3
0x10bc  ldloc.1
0x10bd  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x10c2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_DisplayName(string)
0x10c7  ldloc.3
0x10c8  ldtoken  Microsoft.EventViewer.SnapIn.MessageViewEx
0x10cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10d2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_ViewType(class [mscorlib]System.Type)
0x10d7  ldloc.1
0x10d8  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x10dd  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x10e2  ldloc.1
0x10e3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x10e8  ldloc.3
0x10e9  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription)
0x10ee  pop
0x10ef  ldloc.1
0x10f0  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x10f5  ldc.i4.0
0x10f6  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::set_DefaultIndex(int32)
0x10fb  ldloc.1
0x10fc  ldloc.1
0x10fd  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1102  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x1107  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x110c  ldloc.1
0x110d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x1112  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x1117  ldloc.1
0x1118  ldloc.1
0x1119  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x111e  ret
0x111f  ldloc.1
0x1120  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1125  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x112a  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x112f  ldc.i4.1
0x1130  ble.s    loc_1161
0x1132  ldloc.1
0x1133  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes()
0x1138  ldloc.1
0x1139  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::UpdateActions()
0x113e  ldloc.2
0x113f  brtrue.s loc_1161
0x1141  ldloc.1
0x1142  ldloc.1
0x1143  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x1148  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x114d  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x1152  ldc.i4.1
0x1153  cgt
0x1155  callvirt instance void Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage(bool homepage)
0x115a  ldloc.1
0x115b  ldloc.1
0x115c  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::SelectEventsNode(class Microsoft.EventViewer.SnapIn.ViewerRootNode node)
0x1161  ret
```
