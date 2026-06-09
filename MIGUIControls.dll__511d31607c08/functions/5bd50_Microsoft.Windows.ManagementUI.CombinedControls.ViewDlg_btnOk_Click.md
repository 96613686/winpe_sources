# Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::btnOk_Click

- ea: `0x5bd50`
- end: `0x5bf91`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::btnOk_Click`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x14db0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15020`
- `0x33b40`
- `0x363c0`
- `0x46eb0`
- `0x489c0`
- `0x5bd50`
- `0x5c350`
- `0x5c4a0`

## string_xrefs

- `0x5bde9`: `DuplicateCustomViewOverwriteQuestion`
- `0x5bdfe`: `DuplicateExternalLogOverwriteQuestion`

## pseudocode

```c

```

## disassembly

```asm
0x5bd50  ldc.i4.0
0x5bd51  stloc.0
0x5bd52  ldc.i4.1
0x5bd53  stloc.1
0x5bd54  ldnull
0x5bd55  stloc.2
0x5bd56  ldarg.0
0x5bd57  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::viewTree
0x5bd5c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNode [System.Windows.Forms]System.Windows.Forms.TreeView::get_SelectedNode()
0x5bd61  brfalse  loc_5BF90
0x5bd66  ldarg.0
0x5bd67  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bd6c  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5bd71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bd76  brtrue   loc_5BF68
0x5bd7b  ldarg.0
0x5bd7c  ldarg.0
0x5bd7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bd82  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5bd87  call     bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::CheckIfValidName(class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string name)
0x5bd8c  brfalse  loc_5BF54
0x5bd91  ldarg.0
0x5bd92  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::viewTree
0x5bd97  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNode [System.Windows.Forms]System.Windows.Forms.TreeView::get_SelectedNode()
0x5bd9c  callvirt instance object [System.Windows.Forms]System.Windows.Forms.TreeNode::get_Tag()
0x5bda1  brfalse  loc_5BF43
0x5bda6  ldarg.0
0x5bda7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::viewTree
0x5bdac  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TreeNode [System.Windows.Forms]System.Windows.Forms.TreeView::get_SelectedNode()
0x5bdb1  callvirt instance object [System.Windows.Forms]System.Windows.Forms.TreeNode::get_Tag()
0x5bdb6  isinst   Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x5bdbb  stloc.3
0x5bdbc  ldloc.3
0x5bdbd  brfalse  loc_5BF43
0x5bdc2  ldarg.0
0x5bdc3  ldloc.3
0x5bdc4  ldarg.0
0x5bdc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bdca  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5bdcf  ldloca.s 2
0x5bdd1  ldarg.0
0x5bdd2  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeAddedType
0x5bdd7  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::CheckIfDuplicate(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode node, string newNodeName, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& existingNode, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeTypeTobeAdded)
0x5bddc  stloc.1
0x5bddd  ldloc.1
0x5bdde  brfalse  loc_5BE87
0x5bde3  ldloc.2
0x5bde4  brfalse  loc_5BE87
0x5bde9  ldstr    aDuplicatecusto_0// "DuplicateCustomViewOverwriteQuestion"
0x5bdee  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5bdf3  stloc.s  4
0x5bdf5  ldloc.2
0x5bdf6  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x5bdfb  ldc.i4.6
0x5bdfc  bne.un.s loc_5BE0A
0x5bdfe  ldstr    aDuplicateexter_0// "DuplicateExternalLogOverwriteQuestion"
0x5be03  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5be08  stloc.s  4
0x5be0a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x5be0f  dup
0x5be10  ldc.i4.4
0x5be11  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x5be16  dup
0x5be17  ldc.i4.s 0x20
0x5be19  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x5be1e  dup
0x5be1f  ldc.i4.0
0x5be20  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x5be25  dup
0x5be26  ldc.i4.0
0x5be27  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x5be2c  dup
0x5be2d  ldstr    aViewername// "ViewerName"
0x5be32  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5be37  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x5be3c  ldnull
0x5be3d  ldloc.s  4
0x5be3f  ldc.i4.1
0x5be40  newarr   [mscorlib]System.Object
0x5be45  dup
0x5be46  ldc.i4.0
0x5be47  ldloc.2
0x5be48  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x5be4d  stelem.ref
0x5be4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5be53  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x5be58  ldc.i4.1
0x5be59  ldarg.0
0x5be5a  ldnull
0x5be5b  ldloc.s  4
0x5be5d  ldc.i4.1
0x5be5e  newarr   [mscorlib]System.Object
0x5be63  dup
0x5be64  ldc.i4.0
0x5be65  ldloc.2
0x5be66  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x5be6b  stelem.ref
0x5be6c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5be71  ldc.i4.4
0x5be72  ldc.i4.s 0x20
0x5be74  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5be79  stloc.s  5
0x5be7b  ldc.i4.6
0x5be7c  ldloc.s  5
0x5be7e  bne.un.s loc_5BE87
0x5be80  ldarg.0
0x5be81  ldloc.2
0x5be82  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeOverWritten
0x5be87  ldloc.1
0x5be88  brfalse.s loc_5BE8D
0x5be8a  ldloc.2
0x5be8b  brfalse.s loc_5BE9B
0x5be8d  ldloc.1
0x5be8e  brfalse.s loc_5BEBB
0x5be90  ldloc.2
0x5be91  brfalse.s loc_5BEBB
0x5be93  ldarg.0
0x5be94  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeOverWritten
0x5be99  brtrue.s loc_5BEBB
0x5be9b  ldarg.0
0x5be9c  ldc.i4.0
0x5be9d  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bea2  ldarg.0
0x5bea3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bea8  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x5bead  pop
0x5beae  ldarg.0
0x5beaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5beb4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::Select()
0x5beb9  ldc.i4.1
0x5beba  stloc.0
0x5bebb  ldloc.0
0x5bebc  brtrue.s loc_5BF02
0x5bebe  ldarg.0
0x5bebf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeOverWritten
0x5bec4  brtrue.s loc_5BF02
0x5bec6  ldarg.0
0x5bec7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5becc  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x5bed1  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::IsValidViewName(string name)
0x5bed6  brtrue.s loc_5BF02
0x5bed8  ldc.i4.1
0x5bed9  ldarg.0
0x5beda  ldstr    aInvalidnodenam// "InvalidNodeName"
0x5bedf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5bee4  ldc.i4.0
0x5bee5  ldc.i4.s 0x10
0x5bee7  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5beec  pop
0x5beed  ldarg.0
0x5beee  ldc.i4.0
0x5beef  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bef4  ldarg.0
0x5bef5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5befa  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x5beff  pop
0x5bf00  ldc.i4.1
0x5bf01  stloc.0
0x5bf02  ldloc.0
0x5bf03  brtrue.s loc_5BF43
0x5bf05  ldarg.0
0x5bf06  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::nodeToBeOverWritten
0x5bf0b  brtrue.s loc_5BF43
0x5bf0d  ldarg.0
0x5bf0e  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::CheckName()
0x5bf13  brtrue.s loc_5BF43
0x5bf15  ldstr    aGenericlongnam// "GenericLongName"
0x5bf1a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5bf1f  stloc.s  6
0x5bf21  ldc.i4.1
0x5bf22  ldarg.0
0x5bf23  ldloc.s  6
0x5bf25  ldc.i4.0
0x5bf26  ldc.i4.s 0x10
0x5bf28  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5bf2d  pop
0x5bf2e  ldarg.0
0x5bf2f  ldc.i4.0
0x5bf30  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bf35  ldarg.0
0x5bf36  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bf3b  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x5bf40  pop
0x5bf41  ldc.i4.1
0x5bf42  stloc.0
0x5bf43  ldloc.0
0x5bf44  brtrue.s loc_5BF90
0x5bf46  ldarg.0
0x5bf47  ldc.i4.1
0x5bf48  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bf4d  ldarg.0
0x5bf4e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::Close()
0x5bf53  ret
0x5bf54  ldarg.0
0x5bf55  ldc.i4.0
0x5bf56  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bf5b  ldarg.0
0x5bf5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bf61  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x5bf66  pop
0x5bf67  ret
0x5bf68  ldarg.0
0x5bf69  ldc.i4.0
0x5bf6a  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x5bf6f  ldc.i4.1
0x5bf70  ldarg.0
0x5bf71  ldstr    aQrydlgErrmsg1// "QRYDLG_ERRMSG1"
0x5bf76  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5bf7b  ldc.i4.0
0x5bf7c  ldc.i4.s 0x10
0x5bf7e  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowMessageBox(bool parentIsModal, class [System.Windows.Forms]System.Windows.Forms.Control parentControl, string message, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x5bf83  pop
0x5bf84  ldarg.0
0x5bf85  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::textBox1
0x5bf8a  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x5bf8f  pop
0x5bf90  ret
```
