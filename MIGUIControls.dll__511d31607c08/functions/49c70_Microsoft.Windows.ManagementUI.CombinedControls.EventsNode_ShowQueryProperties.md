# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ShowQueryProperties

- ea: `0x49c70`
- end: `0x49ef1`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ShowQueryProperties`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `41`
- tags: `broker_com_uri`

## callers

- `0x473f0`
- `0x49ab0`

## callees

- `0x12ed0`
- `0x12f00`
- `0x14db0`
- `0x14de0`
- `0x15050`
- `0x26ae0`
- `0x26b30`
- `0x26b40`
- `0x26b80`
- `0x26b90`
- `0x26bb0`
- `0x26bc0`
- `0x26bd0`
- `0x26be0`
- `0x46130`
- `0x46640`
- `0x46e90`
- `0x46ea0`
- `0x49c70`
- `0x49f70`
- `0x4ae40`
- `0x4b170`
- `0x4b350`
- `0x4c780`
- `0x54040`
- `0x540f0`
- `0x5a980`
- `0x5ab90`
- `0x5aba0`
- `0x5abd0`
- `0x5ac30`
- `0x5ad00`
- `0x5ad30`
- `0x5bb50`
- `0x5bbd0`
- `0x5bc20`
- `0x5bc70`
- `0x5bc80`
- `0x5bca0`
- `0x5bd10`
- `0x5bd20`

## string_xrefs

- `0x49cb4`: `QueryPropertiesReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x49c70  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::.ctor()
0x49c75  stloc.0
0x49c76  ldloc.0
0x49c77  ldarg.0
0x49c78  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Context()
0x49c7d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x49c82  ldloc.0
0x49c83  ldarg.0
0x49c84  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewerRootNode()
0x49c89  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::InitializeView(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode rootNode)
0x49c8e  ldloc.0
0x49c8f  ldarg.0
0x49c90  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_QueryConfiguration()
0x49c95  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_QueryConfiguration(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig value)
0x49c9a  ldc.i4.2
0x49c9b  stloc.1
0x49c9c  ldsfld   string [mscorlib]System.String::Empty
0x49ca1  stloc.2
0x49ca2  ldsfld   string [mscorlib]System.String::Empty
0x49ca7  stloc.3
0x49ca8  ldc.i4.0
0x49ca9  stloc.s  4
0x49cab  ldarg.0
0x49cac  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_IsReadOnlyView()
0x49cb1  brfalse.s loc_49CC5
0x49cb3  ldloc.0
0x49cb4  ldstr    aQuerypropertie// "QueryPropertiesReadOnly"
0x49cb9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49cbe  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_DialogTitle(string value)
0x49cc3  br.s     loc_49CD5
0x49cc5  ldloc.0
0x49cc6  ldstr    aQuerypropertie_0// "QueryProperties"
0x49ccb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49cd0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_DialogTitle(string value)
0x49cd5  ldloc.0
0x49cd6  ldarg.0
0x49cd7  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_IsReadOnlyView()
0x49cdc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_ReadOnly(bool value)
0x49ce1  ldarg.1
0x49ce2  brfalse.s loc_49CF5
0x49ce4  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x49ce9  ldloc.0
0x49cea  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x49cef  stloc.1
0x49cf0  br       loc_49D95
0x49cf5  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::.ctor()
0x49cfa  stloc.s  5
0x49cfc  ldloc.s  5
0x49cfe  ldarg.0
0x49cff  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x49d04  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_ViewName(string value)
0x49d09  ldloc.s  5
0x49d0b  ldarg.0
0x49d0c  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Description()
0x49d11  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_ViewDescription(string value)
0x49d16  ldloc.s  5
0x49d18  ldarg.0
0x49d19  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_ViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode value)
0x49d1e  ldloc.s  5
0x49d20  ldarg.0
0x49d21  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_IsReadOnlyView()
0x49d26  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_ReadOnly(bool value)
0x49d2b  ldloc.s  5
0x49d2d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49d32  ldtoken  [mscorlib]System.String
0x49d37  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49d3c  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x49d41  castclass [mscorlib]System.IFormatProvider
0x49d46  ldstr    aViewproperties_0// "ViewPropertiesCaption"
0x49d4b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49d50  ldc.i4.1
0x49d51  newarr   [mscorlib]System.Object
0x49d56  dup
0x49d57  ldc.i4.0
0x49d58  ldarg.0
0x49d59  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x49d5e  stelem.ref
0x49d5f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x49d64  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_DialogCaption(string value)
0x49d69  ldloc.s  5
0x49d6b  ldloc.0
0x49d6c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::set_FilterDialog(class Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg value)
0x49d71  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x49d76  ldloc.s  5
0x49d78  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x49d7d  stloc.1
0x49d7e  ldloc.s  5
0x49d80  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::get_ViewDescription()
0x49d85  stloc.2
0x49d86  ldloc.s  5
0x49d88  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewProperties::get_ViewName()
0x49d8d  stloc.3
0x49d8e  ldloc.s  5
0x49d90  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x49d95  ldloc.1
0x49d96  ldc.i4.1
0x49d97  bne.un   loc_49EE8
0x49d9c  ldarg.1
0x49d9d  brtrue.s loc_49DAD
0x49d9f  ldarg.0
0x49da0  ldloc.2
0x49da1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_Description(string value)
0x49da6  ldarg.0
0x49da7  ldloc.3
0x49da8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x49dad  ldarg.0
0x49dae  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_QueryConfiguration()
0x49db3  callvirt instance string [mscorlib]System.Object::ToString()
0x49db8  ldloc.0
0x49db9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x49dbe  callvirt instance string [mscorlib]System.Object::ToString()
0x49dc3  ldc.i4.0
0x49dc4  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x49dc9  brfalse  loc_49EE8
0x49dce  ldarg.0
0x49dcf  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::IsAdminViewNode()
0x49dd4  brfalse  loc_49EB4
0x49dd9  ldnull
0x49dda  stloc.s  6
0x49ddc  ldarg.0
0x49ddd  ldloca.s 6
0x49ddf  call     void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetViewRootNode(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode nd, [out] class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode& viewRootNode)
0x49de4  ldloc.s  6
0x49de6  ldc.i4.s 9
0x49de8  ldstr    aSaveadminviewa// "SaveAdminViewAs"
0x49ded  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49df2  ldstr    aSelectwheresav// "SelectWhereSaveView"
0x49df7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49dfc  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode root, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType nodeType, string title, string labelText)
0x49e01  stloc.s  7
0x49e03  ldloc.s  7
0x49e05  ldstr    aSaveadminviewa// "SaveAdminViewAs"
0x49e0a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x49e0f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::set_DialogCaption(string value)
0x49e14  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x49e19  ldloc.s  7
0x49e1b  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.Form frm)
0x49e20  stloc.1
0x49e21  ldc.i4.1
0x49e22  ldloc.1
0x49e23  beq.s    loc_49E2E
0x49e25  ldloc.s  7
0x49e27  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_FolderCreated()
0x49e2c  brfalse.s loc_49EAB
0x49e2e  ldloc.s  7
0x49e30  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_NewFolders()
0x49e35  stloc.s  8
0x49e37  ldc.i4.0
0x49e38  stloc.s  9
0x49e3a  br.s     loc_49E60
0x49e3c  ldloc.s  8
0x49e3e  ldloc.s  9
0x49e40  ldelem.ref
0x49e41  stloc.s  0xA
0x49e43  ldloc.s  6
0x49e45  ldloc.0
0x49e46  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x49e4b  ldloc.s  0xA
0x49e4d  ldc.i4.1
0x49e4e  ldloc.s  7
0x49e50  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x49e55  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x49e5a  ldloc.s  9
0x49e5c  ldc.i4.1
0x49e5d  add
0x49e5e  stloc.s  9
0x49e60  ldloc.s  9
0x49e62  ldloc.s  8
0x49e64  ldlen
0x49e65  conv.i4
0x49e66  blt.s    loc_49E3C
0x49e68  ldc.i4.1
0x49e69  ldloc.1
0x49e6a  bne.un.s loc_49EA8
0x49e6c  ldloc.0
0x49e6d  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x49e72  stloc.s  0xB
0x49e74  ldloc.s  0xB
0x49e76  ldloc.s  7
0x49e78  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ViewName()
0x49e7d  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x49e82  ldloc.s  0xB
0x49e84  ldloc.s  7
0x49e86  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_Description()
0x49e8b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Description(string value)
0x49e90  ldloc.s  6
0x49e92  ldloc.s  0xB
0x49e94  ldloc.s  7
0x49e96  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_ParentFolderPath()
0x49e9b  ldc.i4.1
0x49e9c  ldloc.s  7
0x49e9e  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewDlg::get_AllUsers()
0x49ea3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::AddViewNode(class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig qryConfig, string path, bool customView, bool allUserQuery)
0x49ea8  ldc.i4.1
0x49ea9  stloc.s  4
0x49eab  ldloc.s  7
0x49ead  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x49eb2  br.s     loc_49EE8
0x49eb4  ldarg.0
0x49eb5  ldloc.0
0x49eb6  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_QueryConfiguration()
0x49ebb  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x49ec0  ldarg.1
0x49ec1  brtrue.s loc_49EE5
0x49ec3  ldarg.0
0x49ec4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x49ec9  ldarg.0
0x49eca  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_Description()
0x49ecf  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Description(string value)
0x49ed4  ldarg.0
0x49ed5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::qry
0x49eda  ldarg.0
0x49edb  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_Name()
0x49ee0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::set_Name(string value)
0x49ee5  ldc.i4.1
0x49ee6  stloc.s  4
0x49ee8  ldloc.0
0x49ee9  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x49eee  ldloc.s  4
0x49ef0  ret
```
