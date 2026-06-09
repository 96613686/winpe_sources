# System.Web.UI.Design.WebControls.ParameterEditorUserControl::InitializeComponent

- ea: `0x30b50`
- end: `0x31150`
- name: `System.Web.UI.Design.WebControls.ParameterEditorUserControl::InitializeComponent`
- size: `1536`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x308f0`

## callees

- `0x518a0`

## string_xrefs

- `0x30e46`: `_moveUpButton`
- `0x30ea5`: `_moveDownButton`
- `0x30f04`: `_deleteParameterButton`
- `0x30fc6`: `_parameterTypeComboBox`

## pseudocode

```c

```

## disassembly

```asm
0x30b50  ldarg.0
0x30b51  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x30b56  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30b5b  ldarg.0
0x30b5c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x30b61  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30b66  ldarg.0
0x30b67  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x30b6c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x30b71  ldarg.0
0x30b72  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x30b77  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_sourceLabel
0x30b7c  ldarg.0
0x30b7d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x30b82  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30b87  ldarg.0
0x30b88  ldstr    asc_12DF92// ""
0x30b8d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x30b92  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_nameColumnHeader
0x30b97  ldarg.0
0x30b98  ldstr    asc_12DF92// ""
0x30b9d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x30ba2  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_valueColumnHeader
0x30ba7  ldarg.0
0x30ba8  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x30bad  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parameterTypeComboBox
0x30bb2  ldarg.0
0x30bb3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x30bb8  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30bbd  ldarg.0
0x30bbe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x30bc3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30bc8  ldarg.0
0x30bc9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x30bce  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30bd3  ldarg.0
0x30bd4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x30bd9  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_editorPanel
0x30bde  ldarg.0
0x30bdf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30be4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x30be9  ldarg.0
0x30bea  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x30bef  ldarg.0
0x30bf0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x30bf5  ldc.i4.0
0x30bf6  ldc.i4.0
0x30bf7  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30bfc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30c01  ldarg.0
0x30c02  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x30c07  ldstr    aParameterslabe// "_parametersLabel"
0x30c0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30c11  ldarg.0
0x30c12  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x30c17  ldc.i4   0xFC
0x30c1c  ldc.i4.s 0x10
0x30c1e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30c23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30c28  ldarg.0
0x30c29  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x30c2e  ldc.i4.s 0xA
0x30c30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30c35  ldarg.0
0x30c36  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c3b  ldc.i4.7
0x30c3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x30c41  ldarg.0
0x30c42  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c47  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Columns()
0x30c4c  ldc.i4.2
0x30c4d  newarr   [System.Windows.Forms]System.Windows.Forms.ColumnHeader
0x30c52  dup
0x30c53  ldc.i4.0
0x30c54  ldarg.0
0x30c55  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_nameColumnHeader
0x30c5a  stelem.ref
0x30c5b  dup
0x30c5c  ldc.i4.1
0x30c5d  ldarg.0
0x30c5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_valueColumnHeader
0x30c63  stelem.ref
0x30c64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ColumnHeaderCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ColumnHeader[])
0x30c69  ldarg.0
0x30c6a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c6f  ldc.i4.1
0x30c70  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x30c75  ldarg.0
0x30c76  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c7b  ldc.i4.1
0x30c7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HeaderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ColumnHeaderStyle)
0x30c81  ldarg.0
0x30c82  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c87  ldc.i4.0
0x30c88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_HideSelection(bool)
0x30c8d  ldarg.0
0x30c8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c93  ldc.i4.1
0x30c94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_LabelEdit(bool)
0x30c99  ldarg.0
0x30c9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30c9f  ldc.i4.0
0x30ca0  ldc.i4.s 0x12
0x30ca2  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30ca7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30cac  ldarg.0
0x30cad  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30cb2  ldc.i4.0
0x30cb3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_MultiSelect(bool)
0x30cb8  ldarg.0
0x30cb9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30cbe  ldstr    aParameterslist// "_parametersListView"
0x30cc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30cc8  ldarg.0
0x30cc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30cce  ldc.i4   0xFC
0x30cd3  ldc.i4   0xE0
0x30cd8  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30cdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30ce2  ldarg.0
0x30ce3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30ce8  ldc.i4.s 0x14
0x30cea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30cef  ldarg.0
0x30cf0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30cf5  ldc.i4.1
0x30cf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x30cfb  ldarg.0
0x30cfc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30d01  ldarg.0
0x30d02  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnParametersListViewSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x30d08  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x30d0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x30d12  ldarg.0
0x30d13  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersListView
0x30d18  ldarg.0
0x30d19  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnParametersListViewAfterLabelEdit(object sender, class [System.Windows.Forms]System.Windows.Forms.LabelEditEventArgs e)
0x30d1f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LabelEditEventHandler::.ctor(object, native int)
0x30d24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::add_AfterLabelEdit(class [System.Windows.Forms]System.Windows.Forms.LabelEditEventHandler)
0x30d29  ldarg.0
0x30d2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_nameColumnHeader
0x30d2f  ldc.i4.s 0x55
0x30d31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Width(int32)
0x30d36  ldarg.0
0x30d37  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_valueColumnHeader
0x30d3c  ldc.i4   0x86
0x30d41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Width(int32)
0x30d46  ldarg.0
0x30d47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30d4c  ldc.i4.6
0x30d4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x30d52  ldarg.0
0x30d53  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30d58  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x30d5d  ldarg.0
0x30d5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30d63  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x30d68  ldarg.0
0x30d69  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30d6e  ldc.i4.0
0x30d6f  ldc.i4   0xF8
0x30d74  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30d79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30d7e  ldarg.0
0x30d7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30d84  ldstr    aAddbuttonpanel// "_addButtonPanel"
0x30d89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30d8e  ldarg.0
0x30d8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30d94  ldc.i4   0xFC
0x30d99  ldc.i4.s 0x1E
0x30d9b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30da0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30da5  ldarg.0
0x30da6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addButtonPanel
0x30dab  ldc.i4.s 0x1E
0x30dad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30db2  ldarg.0
0x30db3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30db8  ldc.i4.s 9
0x30dba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x30dbf  ldarg.0
0x30dc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30dc5  ldc.i4.1
0x30dc6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x30dcb  ldarg.0
0x30dcc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30dd1  ldc.i4.s 0x7C
0x30dd3  ldc.i4.0
0x30dd4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30dd9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30dde  ldarg.0
0x30ddf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30de4  ldstr    aAddparameterbu// "_addParameterButton"
0x30de9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30dee  ldarg.0
0x30def  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30df4  ldc.i4   0x80
0x30df9  ldc.i4.s 0x17
0x30dfb  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30e00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30e05  ldarg.0
0x30e06  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30e0b  ldc.i4.s 0xA
0x30e0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30e12  ldarg.0
0x30e13  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x30e18  ldarg.0
0x30e19  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnAddParameterButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x30e1f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x30e24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x30e29  ldarg.0
0x30e2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30e2f  ldc.i4   0x102
0x30e34  ldc.i4.s 0x12
0x30e36  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30e3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30e40  ldarg.0
0x30e41  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30e46  ldstr    aMoveupbutton// "_moveUpButton"
0x30e4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30e50  ldarg.0
0x30e51  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30e56  ldc.i4.s 0x1A
0x30e58  ldc.i4.s 0x17
0x30e5a  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30e5f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30e64  ldarg.0
0x30e65  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30e6a  ldc.i4.s 0x28
0x30e6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30e71  ldarg.0
0x30e72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x30e77  ldarg.0
0x30e78  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnMoveUpButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x30e7e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x30e83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x30e88  ldarg.0
0x30e89  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30e8e  ldc.i4   0x102
0x30e93  ldc.i4.s 0x2A
0x30e95  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30e9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30e9f  ldarg.0
0x30ea0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30ea5  ldstr    aMovedownbutton// "_moveDownButton"
0x30eaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30eaf  ldarg.0
0x30eb0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30eb5  ldc.i4.s 0x1A
0x30eb7  ldc.i4.s 0x17
0x30eb9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30ebe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30ec3  ldarg.0
0x30ec4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30ec9  ldc.i4.s 0x32
0x30ecb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30ed0  ldarg.0
0x30ed1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x30ed6  ldarg.0
0x30ed7  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnMoveDownButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x30edd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x30ee2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x30ee7  ldarg.0
0x30ee8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30eed  ldc.i4   0x102
0x30ef2  ldc.i4.s 0x47
0x30ef4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30ef9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30efe  ldarg.0
0x30eff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30f04  ldstr    aDeleteparamete// "_deleteParameterButton"
0x30f09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x30f0e  ldarg.0
0x30f0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30f14  ldc.i4.s 0x1A
0x30f16  ldc.i4.s 0x17
0x30f18  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x30f1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x30f22  ldarg.0
0x30f23  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30f28  ldc.i4.s 0x3C
0x30f2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x30f2f  ldarg.0
0x30f30  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x30f35  ldarg.0
0x30f36  ldftn    instance void System.Web.UI.Design.WebControls.ParameterEditorUserControl::OnDeleteParameterButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x30f3c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x30f41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x30f46  ldarg.0
0x30f47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_sourceLabel
0x30f4c  ldc.i4.s 0xD
0x30f4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x30f53  ldarg.0
0x30f54  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_sourceLabel
0x30f59  ldc.i4   0x124
0x30f5e  ldc.i4.0
0x30f5f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x30f64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x30f69  ldarg.0
  ... truncated ...
```
