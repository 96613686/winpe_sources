# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::DeleteNode

- ea: `0x48a70`
- end: `0x48ae5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::DeleteNode`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x481e0`

## callees

- `0x12ed0`
- `0x14e30`
- `0x33aa0`
- `0x46530`
- `0x48a70`
- `0x48b00`
- `0x4c020`

## string_xrefs

- `0x48aa3`: `DeleteAccessDenied`
- `0x48ab7`: `DeleteAccessDenied`

## pseudocode

```c

```

## disassembly

```asm
0x48a70  ldc.i4.1
0x48a71  stloc.0
0x48a72  ldarg.0
0x48a73  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x48a78  ldarg.1
0x48a79  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x48a7e  brfalse.s loc_48AD8
0x48a80  ldarg.0
0x48a81  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x48a86  ldarg.1
0x48a87  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x48a8c  castclass Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x48a91  stloc.1
0x48a92  ldloc.1
0x48a93  ldc.i4.4
0x48a94  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x48a99  ldloc.1
0x48a9a  ldc.i4.1
0x48a9b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::SaveNode(bool handleException)
0x48aa0  leave.s  loc_48ACA
0x48aa2  pop
0x48aa3  ldstr    aDeleteaccessde// "DeleteAccessDenied"
0x48aa8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48aad  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x48ab2  ldc.i4.0
0x48ab3  stloc.0
0x48ab4  leave.s  loc_48ACA
0x48ab6  pop
0x48ab7  ldstr    aDeleteaccessde// "DeleteAccessDenied"
0x48abc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48ac1  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowErrorMessageBox(string message)
0x48ac6  ldc.i4.0
0x48ac7  stloc.0
0x48ac8  leave.s  loc_48ACA
0x48aca  ldarg.0
0x48acb  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x48ad0  ldarg.1
0x48ad1  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x48ad6  br.s     loc_48ADA
0x48ad8  ldc.i4.0
0x48ad9  stloc.0
0x48ada  ldloc.0
0x48adb  brfalse.s loc_48AE3
0x48add  ldarg.0
0x48ade  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::SetNodeStateModified()
0x48ae3  ldloc.0
0x48ae4  ret
```
