# Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage

- ea: `0x4690`
- end: `0x4725`
- name: `Microsoft.EventViewer.SnapIn.MMCRootNode::SetViewerHomePage`
- size: `149`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x15c0`
- `0x4520`
- `0x4780`

## callees

- `0x4310`
- `0x4690`

## pseudocode

```c

```

## disassembly

```asm
0x4690  ldarg.0
0x4691  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x4696  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x469b  ldarg.1
0x469c  brfalse.s loc_46EA
0x469e  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormViewDescription::.ctor()
0x46a3  stloc.0
0x46a4  ldloc.0
0x46a5  ldarg.0
0x46a6  call     instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x46ab  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_DisplayName(string)
0x46b0  ldloc.0
0x46b1  ldtoken  Microsoft.EventViewer.SnapIn.EventViewerHomepage
0x46b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46bb  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::set_ViewType(class [mscorlib]System.Type)
0x46c0  ldloc.0
0x46c1  ldtoken  [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl
0x46c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46cb  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormViewDescription::set_ControlType(class [mscorlib]System.Type)
0x46d0  ldarg.0
0x46d1  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x46d6  ldloc.0
0x46d7  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription)
0x46dc  pop
0x46dd  ldarg.0
0x46de  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x46e3  ldc.i4.0
0x46e4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::set_DefaultIndex(int32)
0x46e9  ret
0x46ea  ldarg.0
0x46eb  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x46f0  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x46f5  ldarg.0
0x46f6  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x46fb  ldarg.0
0x46fc  ldfld    string Microsoft.EventViewer.SnapIn.MMCRootNode::legacyMachine
0x4701  newobj   instance void Microsoft.EventViewer.SnapIn.MMCLegacyRootNode::.ctor(string remotecomputerName)
0x4706  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x470b  pop
0x470c  ldarg.0
0x470d  ldc.i4.1
0x470e  stfld    bool Microsoft.EventViewer.SnapIn.ViewerRootNode::expanded
0x4713  ldarg.0
0x4714  ldarg.0
0x4715  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x471a  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x471f  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::set_DisplayName(string)
0x4724  ret
```
