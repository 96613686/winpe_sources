# Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes

- ea: `0x3530`
- end: `0x36e5`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes`
- size: `437`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x9e0`
- `0x3530`
- `0x37c0`
- `0x39e0`
- `0x7810`

## callees

- `0x2280`
- `0x33c0`
- `0x3530`
- `0x3830`
- `0x3d70`
- `0x3d90`
- `0x3dd0`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldnull
0x3531  stloc.0
0x3532  ldnull
0x3533  stloc.1
0x3534  ldnull
0x3535  stloc.2
0x3536  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x353b  stloc.3
0x353c  ldc.i4.0
0x353d  stloc.s  4
0x353f  ldarg.0
0x3540  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3545  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x354a  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x354f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x3554  stloc.s  5
0x3556  br       loc_3689
0x355b  ldloc.s  5
0x355d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3562  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x3567  stloc.s  6
0x3569  ldloc.s  6
0x356b  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x3570  ldc.i4.4
0x3571  beq      loc_3689
0x3576  ldloc.s  6
0x3578  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x357d  ldc.i4.1
0x357e  bne.un.s loc_35A8
0x3580  ldarg.0
0x3581  ldloc.s  6
0x3583  call     instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetChildNode(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode evtNode)
0x3588  stloc.0
0x3589  ldloc.0
0x358a  brfalse.s loc_35A8
0x358c  ldloc.0
0x358d  callvirt instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes()
0x3592  stloc.2
0x3593  ldarg.0
0x3594  ldloc.1
0x3595  ldloc.2
0x3596  call     instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::ChooseBetterReturnNode(class Microsoft.EventViewer.SnapIn.MMCEventsNode currentReturnNode, class Microsoft.EventViewer.SnapIn.MMCEventsNode newReturnNodeCandidate)
0x359b  stloc.1
0x359c  ldloc.0
0x359d  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x35a2  ldc.i4.0
0x35a3  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState)
0x35a8  ldloc.s  6
0x35aa  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x35af  ldc.i4.3
0x35b0  beq.s    loc_35C5
0x35b2  ldloc.s  6
0x35b4  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x35b9  ldc.i4.1
0x35ba  bne.un   loc_3689
0x35bf  ldloc.0
0x35c0  brtrue   loc_3689
0x35c5  ldloc.s  6
0x35c7  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsFolderNode()
0x35cc  brfalse.s loc_35DB
0x35ce  ldloc.s  6
0x35d0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x35d5  ldc.i4.s 0xB
0x35d7  ceq
0x35d9  br.s     loc_35DC
0x35db  ldc.i4.1
0x35dc  stloc.s  4
0x35de  ldloc.s  6
0x35e0  ldloc.s  4
0x35e2  newobj   instance void Microsoft.EventViewer.SnapIn.MMCEventsNode::.ctor(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode node, bool expandNode)
0x35e7  stloc.s  7
0x35e9  ldloc.s  6
0x35eb  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x35f0  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x35f5  ldc.i4.0
0x35f6  ble.s    loc_3616
0x35f8  ldloc.s  7
0x35fa  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x35ff  ldc.i4.1
0x3600  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState)
0x3605  ldloc.s  7
0x3607  callvirt instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes()
0x360c  stloc.2
0x360d  ldarg.0
0x360e  ldloc.1
0x360f  ldloc.2
0x3610  call     instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::ChooseBetterReturnNode(class Microsoft.EventViewer.SnapIn.MMCEventsNode currentReturnNode, class Microsoft.EventViewer.SnapIn.MMCEventsNode newReturnNodeCandidate)
0x3615  stloc.1
0x3616  ldloc.s  7
0x3618  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x361d  ldc.i4.0
0x361e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState)
0x3623  ldloc.s  6
0x3625  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x362a  ldc.i4.5
0x362b  bne.un.s loc_3659
0x362d  ldarg.0
0x362e  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3633  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x3638  ldc.i4.4
0x3639  blt.s    loc_3659
0x363b  ldarg.0
0x363c  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3641  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x3646  ldc.i4.2
0x3647  bne.un.s loc_3659
0x3649  ldarg.0
0x364a  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x364f  ldc.i4.3
0x3650  ldloc.s  7
0x3652  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Insert(int32, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x3657  br.s     loc_3662
0x3659  ldloc.3
0x365a  ldloc.s  7
0x365c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3661  pop
0x3662  ldloc.s  6
0x3664  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x3669  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x366e  brtrue.s loc_3673
0x3670  ldloc.s  7
0x3672  stloc.1
0x3673  ldloc.s  7
0x3675  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.MMCEventsNode::get_EventsNode()
0x367a  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x367f  ldc.i4.3
0x3680  bne.un.s loc_3689
0x3682  ldloc.s  7
0x3684  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::ExpandNode()
0x3689  ldloc.s  5
0x368b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3690  brtrue   loc_355B
0x3695  leave.s  loc_36AC
0x3697  ldloc.s  5
0x3699  isinst   [mscorlib]System.IDisposable
0x369e  stloc.s  8
0x36a0  ldloc.s  8
0x36a2  brfalse.s loc_36AB
0x36a4  ldloc.s  8
0x36a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ab  endfinally
0x36ac  ldloc.3
0x36ad  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x36b2  ldc.i4.0
0x36b3  ble.s    loc_36DD
0x36b5  ldloc.3
0x36b6  ldtoken  Microsoft.EventViewer.SnapIn.MMCEventsNode
0x36bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36c0  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x36c5  castclass class Microsoft.EventViewer.SnapIn.MMCEventsNode[]
0x36ca  stloc.s  9
0x36cc  ldarg.0
0x36cd  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x36d2  ldloc.s  9
0x36d4  stloc.s  0xA
0x36d6  ldloc.s  0xA
0x36d8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::AddRange(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode[])
0x36dd  ldarg.0
0x36de  call     instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshResultView()
0x36e3  ldloc.1
0x36e4  ret
```
