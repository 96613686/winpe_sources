# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteCopyViewAction

- ea: `0x484d0`
- end: `0x48675`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ExecuteCopyViewAction`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x473f0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x14db0`
- `0x15050`
- `0x16310`
- `0x46530`
- `0x46640`
- `0x46680`
- `0x46e90`
- `0x46ea0`
- `0x47000`
- `0x484d0`
- `0x4ae40`
- `0x4b350`
- `0x53a10`
- `0x53b00`
- `0x54040`
- `0x540f0`
- `0x54140`
- `0x5bb50`
- `0x5bbd0`
- `0x5bbe0`
- `0x5bc20`
- `0x5bc30`
- `0x5bc80`
- `0x5bc90`
- `0x5bca0`
- `0x5bd10`
- `0x5bd20`

## string_xrefs

- `0x4854d`: `CopyViewDialogCaption`

## pseudocode

```c

```

## disassembly

```asm
0x484d0  ldc.i4.0
0x484d1  stloc.0
0x484d2  ldnull
0x484d3  stloc.1
0x484d4  ldarg.0
0x484d5  ldnull
0x484d6  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x484db  ldarg.0
0x484dc  ldloca.s 1
0x484de  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& viewRootNode)
0x484e3  ldloc.1
0x484e4  brfalse  loc_48673
0x484e9  ldloc.1
0x484ea  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InsertChildren()
0x484ef  ldarg.0
0x484f0  ldarg.0
0x484f1  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::copyCount
0x484f6  ldc.i4.1
0x484f7  add
0x484f8  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::copyCount
0x484fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x48502  ldtoken  [mscorlib]System.String
0x48507  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4850c  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x48511  castclass [mscorlib]System.IFormatProvider
0x48516  ldstr    aGeneratednoden// "GeneratedNodeName"
0x4851b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48520  ldc.i4.2
0x48521  newarr   [mscorlib]System.Object
0x48526  dup
0x48527  ldc.i4.0
0x48528  ldarg.0
0x48529  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x4852e  stelem.ref
0x4852f  dup
0x48530  ldc.i4.1
0x48531  ldarg.0
0x48532  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::copyCount
0x48537  box      [mscorlib]System.Int32
0x4853c  stelem.ref
0x4853d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x48542  stloc.2
0x48543  ldarg.0
0x48544  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Description()
0x48549  stloc.3
0x4854a  ldloc.1
0x4854b  ldc.i4.s 9
0x4854d  ldstr    aCopyviewdialog// "CopyViewDialogCaption"
0x48552  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48557  ldstr    aSelectwheresav// "SelectWhereSaveView"
0x4855c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x48561  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode root, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeType, string title, string labelText)
0x48566  stloc.s  4
0x48568  ldloc.s  4
0x4856a  ldloc.2
0x4856b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_ViewName(string value)
0x48570  ldloc.s  4
0x48572  ldloc.3
0x48573  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_Description(string value)
0x48578  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x4857d  ldloc.s  4
0x4857f  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x48584  stloc.s  5
0x48586  ldloc.s  5
0x48588  ldc.i4.1
0x48589  beq.s    loc_48597
0x4858b  ldloc.s  4
0x4858d  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_FolderCreated()
0x48592  brfalse  loc_4866C
0x48597  ldc.i4.1
0x48598  stloc.0
0x48599  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::.ctor()
0x4859e  stloc.s  6
0x485a0  ldloc.s  4
0x485a2  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NewFolders()
0x485a7  stloc.s  8
0x485a9  ldc.i4.0
0x485aa  stloc.s  9
0x485ac  br.s     loc_485CD
0x485ae  ldloc.s  8
0x485b0  ldloc.s  9
0x485b2  ldelem.ref
0x485b3  stloc.s  0xA
0x485b5  ldloc.1
0x485b6  ldloc.s  6
0x485b8  ldloc.s  0xA
0x485ba  ldc.i4.1
0x485bb  ldloc.s  4
0x485bd  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x485c2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x485c7  ldloc.s  9
0x485c9  ldc.i4.1
0x485ca  add
0x485cb  stloc.s  9
0x485cd  ldloc.s  9
0x485cf  ldloc.s  8
0x485d1  ldlen
0x485d2  conv.i4
0x485d3  blt.s    loc_485AE
0x485d5  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlDocument()
0x485da  stloc.s  7
0x485dc  ldloc.s  6
0x485de  ldarg.0
0x485df  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_QueryConfiguration()
0x485e4  ldloc.s  7
0x485e6  callvirt instance class [System.Xml]System.Xml.XmlElement Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::GetQueryConfigData(class [System.Xml]System.Xml.XmlDocument doc)
0x485eb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::InitializeForXml(class [System.Xml]System.Xml.XmlElement qryElem)
0x485f0  ldloc.s  6
0x485f2  ldloc.s  4
0x485f4  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ViewName()
0x485f9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x485fe  ldloc.s  6
0x48600  ldloc.s  4
0x48602  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x48607  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Description(string value)
0x4860c  ldloc.s  5
0x4860e  ldc.i4.1
0x4860f  bne.un.s loc_4866C
0x48611  ldloc.s  4
0x48613  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x48618  brtrue.s loc_4863C
0x4861a  ldloc.1
0x4861b  ldloc.s  6
0x4861d  ldloc.s  4
0x4861f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ParentFolderPath()
0x48624  ldc.i4.1
0x48625  ldloc.s  4
0x48627  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x4862c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x48631  ldarg.0
0x48632  ldc.i4.1
0x48633  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_NodeState(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeState value)
0x48638  ldc.i4.1
0x48639  stloc.0
0x4863a  br.s     loc_4866C
0x4863c  ldloc.s  4
0x4863e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x48643  ldloc.s  6
0x48645  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_QueryConfiguration(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig value)
0x4864a  ldloc.s  4
0x4864c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x48651  ldloc.s  4
0x48653  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x48658  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x4865d  ldc.i4.1
0x4865e  stloc.0
0x4865f  ldarg.0
0x48660  ldloc.s  4
0x48662  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NodeToBeOverWritten()
0x48667  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::nodeToBeSelected
0x4866c  ldloc.s  4
0x4866e  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x48673  ldloc.0
0x48674  ret
```
