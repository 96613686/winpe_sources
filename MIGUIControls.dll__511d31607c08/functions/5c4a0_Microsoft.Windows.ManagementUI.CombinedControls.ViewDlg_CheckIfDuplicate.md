# Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::CheckIfDuplicate

- ea: `0x5c4a0`
- end: `0x5c623`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::CheckIfDuplicate`
- size: `387`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x5bd50`
- `0x5bfe0`

## callees

- `0x12ed0`
- `0x14db0`
- `0x14e30`
- `0x33b40`
- `0x46520`
- `0x46580`
- `0x46eb0`
- `0x49f70`
- `0x5c4a0`

## string_xrefs

- `0x5c53d`: `DuplicateExternalLogNodeReadOnly`
- `0x5c554`: `DuplicateExternalLogNodeReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x5c4a0  ldc.i4.0
0x5c4a1  stloc.0
0x5c4a2  ldstr    aHomepageviewno// "HomePageViewNodeName"
0x5c4a7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c4ac  stloc.1
0x5c4ad  ldarg.3
0x5c4ae  ldnull
0x5c4af  stind.ref
0x5c4b0  ldarg.1
0x5c4b1  brfalse  loc_5C621
0x5c4b6  ldarg.1
0x5c4b7  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x5c4bc  ldc.i4.7
0x5c4bd  bne.un.s loc_5C4E5
0x5c4bf  ldloc.1
0x5c4c0  ldarg.2
0x5c4c1  ldc.i4.5
0x5c4c2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5c4c7  brtrue.s loc_5C4E5
0x5c4c9  ldc.i4.1
0x5c4ca  ldarg.0
0x5c4cb  ldstr    aStandardnodeer// "StandardNodeError2"
0x5c4d0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c4d5  ldc.i4.0
0x5c4d6  ldc.i4.s 0x10
0x5c4d8  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5c4dd  pop
0x5c4de  ldc.i4.1
0x5c4df  stloc.0
0x5c4e0  br       loc_5C621
0x5c4e5  ldarg.1
0x5c4e6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x5c4eb  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x5c4f0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x5c4f5  stloc.2
0x5c4f6  br       loc_5C600
0x5c4fb  ldloc.2
0x5c4fc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5c501  castclass Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x5c506  stloc.3
0x5c507  ldloc.3
0x5c508  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x5c50d  ldarg.2
0x5c50e  ldc.i4.5
0x5c50f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5c514  brtrue   loc_5C600
0x5c519  ldloc.3
0x5c51a  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeState()
0x5c51f  ldc.i4.4
0x5c520  beq      loc_5C600
0x5c525  ldc.i4.1
0x5c526  stloc.0
0x5c527  ldstr    aErrorDuplicate// "ERROR_DUPLICATE_QRY_NODE"
0x5c52c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c531  stloc.s  4
0x5c533  ldarg.0
0x5c534  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5c539  ldc.i4.s 9
0x5c53b  bne.un.s loc_5C54B
0x5c53d  ldstr    aDuplicateexter_1// "DuplicateExternalLogNodeReadOnly"
0x5c542  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c547  stloc.s  4
0x5c549  br.s     loc_5C560
0x5c54b  ldarg.0
0x5c54c  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5c551  ldc.i4.6
0x5c552  bne.un.s loc_5C560
0x5c554  ldstr    aDuplicateexter_1// "DuplicateExternalLogNodeReadOnly"
0x5c559  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c55e  stloc.s  4
0x5c560  ldloc.3
0x5c561  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_IsReadOnlyView()
0x5c566  brtrue.s loc_5C57B
0x5c568  ldloc.3
0x5c569  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_AllUserQuery()
0x5c56e  ldarg.0
0x5c56f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::checkAllUsers
0x5c574  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x5c579  bne.un.s loc_5C58A
0x5c57b  ldarg.s  4
0x5c57d  ldc.i4.s 9
0x5c57f  beq.s    loc_5C5B9
0x5c581  ldarg.0
0x5c582  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5c587  ldc.i4.6
0x5c588  beq.s    loc_5C5B9
0x5c58a  ldarg.0
0x5c58b  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5c590  ldc.i4.s 9
0x5c592  bne.un.s loc_5C5A2
0x5c594  ldstr    aDuplicatecusto// "DuplicateCustomViewNode"
0x5c599  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c59e  stloc.s  4
0x5c5a0  br.s     loc_5C5E8
0x5c5a2  ldarg.0
0x5c5a3  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5c5a8  ldc.i4.6
0x5c5a9  bne.un.s loc_5C5E8
0x5c5ab  ldstr    aDuplicateexter// "DuplicateExternalLogNode"
0x5c5b0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5c5b5  stloc.s  4
0x5c5b7  br.s     loc_5C5E8
0x5c5b9  ldloc.3
0x5c5ba  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_IsReadOnlyView()
0x5c5bf  brtrue.s loc_5C5E8
0x5c5c1  ldloc.3
0x5c5c2  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x5c5c7  ldc.i4.s 9
0x5c5c9  beq.s    loc_5C5D4
0x5c5cb  ldloc.3
0x5c5cc  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x5c5d1  ldc.i4.6
0x5c5d2  bne.un.s loc_5C5E8
0x5c5d4  ldarg.s  4
0x5c5d6  ldloc.3
0x5c5d7  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x5c5dc  bne.un.s loc_5C5E8
0x5c5de  ldsfld   string [mscorlib]System.String::Empty
0x5c5e3  stloc.s  4
0x5c5e5  ldarg.3
0x5c5e6  ldloc.3
0x5c5e7  stind.ref
0x5c5e8  ldloc.s  4
0x5c5ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5c5ef  brtrue.s loc_5C60B
0x5c5f1  ldc.i4.1
0x5c5f2  ldarg.0
0x5c5f3  ldloc.s  4
0x5c5f5  ldc.i4.0
0x5c5f6  ldc.i4.s 0x10
0x5c5f8  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5c5fd  pop
0x5c5fe  leave.s  loc_5C621
0x5c600  ldloc.2
0x5c601  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5c606  brtrue   loc_5C4FB
0x5c60b  leave.s  loc_5C621
0x5c60d  ldloc.2
0x5c60e  isinst   [mscorlib]System.IDisposable
0x5c613  stloc.s  5
0x5c615  ldloc.s  5
0x5c617  brfalse.s loc_5C620
0x5c619  ldloc.s  5
0x5c61b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c620  endfinally
0x5c621  ldloc.0
0x5c622  ret
```
