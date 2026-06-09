# Microsoft.EventViewer.SnapIn.ViewerRootNode::get_NodePath

- ea: `0x1870`
- end: `0x18df`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::get_NodePath`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7d50`

## callees

- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1870  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath::.ctor()
0x1875  stloc.0
0x1876  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x187b  stloc.1
0x187c  ldarg.0
0x187d  stloc.2
0x187e  br.s     loc_1899
0x1880  ldloc.1
0x1881  ldloc.2
0x1882  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_DisplayName()
0x1887  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x188c  pop
0x188d  ldloc.2
0x188e  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x1893  castclass Microsoft.EventViewer.SnapIn.ViewerRootNode
0x1898  stloc.2
0x1899  ldloc.2
0x189a  isinst   Microsoft.EventViewer.SnapIn.MMCRootNode
0x189f  brfalse.s loc_1880
0x18a1  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath::.ctor()
0x18a6  stloc.0
0x18a7  ldloc.1
0x18a8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x18ad  ldc.i4.1
0x18ae  sub
0x18af  stloc.3
0x18b0  br.s     loc_18C8
0x18b2  ldloc.0
0x18b3  ldloc.1
0x18b4  ldloc.3
0x18b5  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x18ba  castclass [mscorlib]System.String
0x18bf  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath::AddPath(string)
0x18c4  ldloc.3
0x18c5  ldc.i4.1
0x18c6  sub
0x18c7  stloc.3
0x18c8  ldloc.3
0x18c9  ldc.i4.0
0x18ca  bge.s    loc_18B2
0x18cc  ldloc.0
0x18cd  ldarg.0
0x18ce  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x18d3  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Description()
0x18d8  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath::set_Description(string)
0x18dd  ldloc.0
0x18de  ret
```
