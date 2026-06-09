# Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes

- ea: `0x39e0`
- end: `0x3b7b`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes`
- size: `411`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1010`
- `0x15c0`
- `0x1cc0`
- `0x39e0`
- `0x3c50`

## callees

- `0x1850`
- `0x1860`
- `0x1a00`
- `0x3530`
- `0x39e0`
- `0x3b80`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  ldarg.0
0x39e1  call     instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x39e6  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x39eb  ldc.i4.4
0x39ec  bne.un.s loc_3A00
0x39ee  ldarg.0
0x39ef  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Parent()
0x39f4  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x39f9  ldarg.0
0x39fa  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Remove(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x39ff  ret
0x3a00  ldc.i4.0
0x3a01  stloc.1
0x3a02  ldarg.0
0x3a03  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3a08  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3a0d  stloc.2
0x3a0e  br.s     loc_3A2B
0x3a10  ldloc.2
0x3a11  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a16  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x3a1b  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3a20  stloc.0
0x3a21  ldloc.0
0x3a22  brfalse.s loc_3A2B
0x3a24  ldloc.0
0x3a25  ldc.i4.1
0x3a26  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::set_MarkNodeDeleted(bool value)
0x3a2b  ldloc.2
0x3a2c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3a31  brtrue.s loc_3A10
0x3a33  leave.s  loc_3A46
0x3a35  ldloc.2
0x3a36  isinst   [mscorlib]System.IDisposable
0x3a3b  stloc.3
0x3a3c  ldloc.3
0x3a3d  brfalse.s loc_3A45
0x3a3f  ldloc.3
0x3a40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3a45  endfinally
0x3a46  ldarg.0
0x3a47  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::eventsNode
0x3a4c  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x3a51  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x3a56  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x3a5b  stloc.2
0x3a5c  br.s     loc_3AC0
0x3a5e  ldloc.2
0x3a5f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a64  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x3a69  stloc.s  4
0x3a6b  ldarg.0
0x3a6c  ldloc.s  4
0x3a6e  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x3a73  call     instance class Microsoft.EventViewer.SnapIn.ViewerRootNode Microsoft.EventViewer.SnapIn.ViewerRootNode::GetChildNode(string name)
0x3a78  stloc.0
0x3a79  ldloc.0
0x3a7a  brfalse.s loc_3AA0
0x3a7c  ldloc.0
0x3a7d  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x3a82  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x3a87  ldc.i4.4
0x3a88  beq.s    loc_3AA0
0x3a8a  ldloc.0
0x3a8b  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::get_Node()
0x3a90  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeVisible()
0x3a95  brfalse.s loc_3AA0
0x3a97  ldloc.0
0x3a98  ldc.i4.0
0x3a99  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::set_MarkNodeDeleted(bool value)
0x3a9e  br.s     loc_3AC0
0x3aa0  ldloc.0
0x3aa1  brtrue.s loc_3AC0
0x3aa3  ldloc.s  4
0x3aa5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x3aaa  ldc.i4.4
0x3aab  beq.s    loc_3AC0
0x3aad  ldloc.s  4
0x3aaf  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeVisible()
0x3ab4  brfalse.s loc_3AC0
0x3ab6  ldc.i4.1
0x3ab7  stloc.1
0x3ab8  ldloc.s  4
0x3aba  ldc.i4.3
0x3abb  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState)
0x3ac0  ldloc.2
0x3ac1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3ac6  brtrue.s loc_3A5E
0x3ac8  leave.s  loc_3ADB
0x3aca  ldloc.2
0x3acb  isinst   [mscorlib]System.IDisposable
0x3ad0  stloc.3
0x3ad1  ldloc.3
0x3ad2  brfalse.s loc_3ADA
0x3ad4  ldloc.3
0x3ad5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ada  endfinally
0x3adb  ldloc.1
0x3adc  brfalse.s loc_3AE5
0x3ade  ldarg.0
0x3adf  call     instance class Microsoft.EventViewer.SnapIn.MMCEventsNode Microsoft.EventViewer.SnapIn.ViewerRootNode::AddNewNodes()
0x3ae4  pop
0x3ae5  ldc.i4.0
0x3ae6  stloc.s  5
0x3ae8  br.s     loc_3B20
0x3aea  ldarg.0
0x3aeb  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3af0  ldloc.s  5
0x3af2  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::get_Item(int32)
0x3af7  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3afc  stloc.0
0x3afd  ldloc.0
0x3afe  brfalse.s loc_3B1A
0x3b00  ldloc.0
0x3b01  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x3b06  brfalse.s loc_3B1A
0x3b08  ldarg.0
0x3b09  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3b0e  ldloc.0
0x3b0f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection::Remove(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x3b14  ldloc.s  5
0x3b16  ldc.i4.1
0x3b17  sub
0x3b18  stloc.s  5
0x3b1a  ldloc.s  5
0x3b1c  ldc.i4.1
0x3b1d  add
0x3b1e  stloc.s  5
0x3b20  ldloc.s  5
0x3b22  ldarg.0
0x3b23  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3b28  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x3b2d  blt.s    loc_3AEA
0x3b2f  ldarg.0
0x3b30  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNodeCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_Children()
0x3b35  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3b3a  stloc.2
0x3b3b  br.s     loc_3B5F
0x3b3d  ldloc.2
0x3b3e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3b43  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x3b48  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x3b4d  stloc.0
0x3b4e  ldloc.0
0x3b4f  brfalse.s loc_3B5F
0x3b51  ldloc.0
0x3b52  callvirt instance bool Microsoft.EventViewer.SnapIn.ViewerRootNode::get_MarkNodeDeleted()
0x3b57  brtrue.s loc_3B5F
0x3b59  ldloc.0
0x3b5a  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::RefreshAllSubNodes()
0x3b5f  ldloc.2
0x3b60  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3b65  brtrue.s loc_3B3D
0x3b67  leave.s  loc_3B7A
0x3b69  ldloc.2
0x3b6a  isinst   [mscorlib]System.IDisposable
0x3b6f  stloc.3
0x3b70  ldloc.3
0x3b71  brfalse.s loc_3B79
0x3b73  ldloc.3
0x3b74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b79  endfinally
0x3b7a  ret
```
