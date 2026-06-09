# System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::InitializeComponent

- ea: `0x3ca10`
- end: `0x3cf1e`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::InitializeComponent`
- size: `1294`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x3c9a0`

## callees

- `0x3bd20`
- `0x3bd80`

## string_xrefs

- `0x3ccc6`: `_updateTabPage`
- `0x3ccfd`: `UPDATE`
- `0x3ce1c`: `_deleteTabPage`
- `0x3ce53`: `DELETE`
- `0x3cb8c`: `_commandsTabControl`
- `0x3cc69`: `_selectCommandEditor`
- `0x3cd2b`: `_updateCommandEditor`
- `0x3cdd6`: `_insertCommandEditor`
- `0x3ce81`: `_deleteCommandEditor`
- `0x3cebb`: `SqlDataSourceCustomCommandPanel`

## pseudocode

```c

```

## disassembly

```asm
0x3ca10  ldarg.0
0x3ca11  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabControl::.ctor()
0x3ca16  stfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3ca1b  ldarg.0
0x3ca1c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x3ca21  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3ca26  ldarg.0
0x3ca27  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::.ctor()
0x3ca2c  stfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3ca31  ldarg.0
0x3ca32  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x3ca37  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ca3c  ldarg.0
0x3ca3d  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::.ctor()
0x3ca42  stfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3ca47  ldarg.0
0x3ca48  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x3ca4d  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3ca52  ldarg.0
0x3ca53  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::.ctor()
0x3ca58  stfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3ca5d  ldarg.0
0x3ca5e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x3ca63  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3ca68  ldarg.0
0x3ca69  newobj   instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::.ctor()
0x3ca6e  stfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteCommandEditor
0x3ca73  ldarg.0
0x3ca74  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x3ca79  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3ca7e  ldarg.0
0x3ca7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3ca84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3ca89  ldarg.0
0x3ca8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3ca8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3ca94  ldarg.0
0x3ca95  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ca9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3ca9f  ldarg.0
0x3caa0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3caa5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3caaa  ldarg.0
0x3caab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3cab0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3cab5  ldarg.0
0x3cab6  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3cabb  ldarg.0
0x3cabc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3cac1  ldc.i4.s 0xD
0x3cac3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3cac8  ldarg.0
0x3cac9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3cace  ldc.i4.0
0x3cacf  ldc.i4.0
0x3cad0  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cad5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cada  ldarg.0
0x3cadb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3cae0  ldstr    aHelplabel// "_helpLabel"
0x3cae5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3caea  ldarg.0
0x3caeb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3caf0  ldc.i4   0x220
0x3caf5  ldc.i4.s 0x10
0x3caf7  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3cafc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3cb01  ldarg.0
0x3cb02  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_helpLabel
0x3cb07  ldc.i4.s 0xA
0x3cb09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3cb0e  ldarg.0
0x3cb0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb14  ldc.i4.s 0xF
0x3cb16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3cb1b  ldarg.0
0x3cb1c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb21  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cb26  ldarg.0
0x3cb27  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cb2c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cb31  ldarg.0
0x3cb32  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb37  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cb3c  ldarg.0
0x3cb3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3cb42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cb47  ldarg.0
0x3cb48  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb4d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cb52  ldarg.0
0x3cb53  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cb58  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cb5d  ldarg.0
0x3cb5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb63  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cb68  ldarg.0
0x3cb69  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3cb6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cb73  ldarg.0
0x3cb74  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb79  ldc.i4.0
0x3cb7a  ldc.i4.s 0x16
0x3cb7c  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cb81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cb86  ldarg.0
0x3cb87  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb8c  ldstr    aCommandstabcon// "_commandsTabControl"
0x3cb91  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cb96  ldarg.0
0x3cb97  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cb9c  ldc.i4.0
0x3cb9d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x3cba2  ldarg.0
0x3cba3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cba8  ldc.i4.1
0x3cba9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_ShowToolTips(bool)
0x3cbae  ldarg.0
0x3cbaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cbb4  ldc.i4   0x220
0x3cbb9  ldc.i4   0xFC
0x3cbbe  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3cbc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3cbc8  ldarg.0
0x3cbc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_commandsTabControl
0x3cbce  ldc.i4.s 0x14
0x3cbd0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3cbd5  ldarg.0
0x3cbd6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cbdb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cbe0  ldarg.0
0x3cbe1  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cbe6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cbeb  ldarg.0
0x3cbec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cbf1  ldc.i4.4
0x3cbf2  ldc.i4.s 0x16
0x3cbf4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cbf9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cbfe  ldarg.0
0x3cbff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cc04  ldstr    aSelecttabpage// "_selectTabPage"
0x3cc09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cc0e  ldarg.0
0x3cc0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cc14  ldc.i4   0x218
0x3cc19  ldc.i4   0xE2
0x3cc1e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3cc23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3cc28  ldarg.0
0x3cc29  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cc2e  ldc.i4.s 0xA
0x3cc30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x3cc35  ldarg.0
0x3cc36  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectTabPage
0x3cc3b  ldstr    aSelect// "SELECT"
0x3cc40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3cc45  ldarg.0
0x3cc46  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cc4b  ldc.i4.5
0x3cc4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x3cc51  ldarg.0
0x3cc52  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cc57  ldc.i4.0
0x3cc58  ldc.i4.0
0x3cc59  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cc5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cc63  ldarg.0
0x3cc64  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cc69  ldstr    aSelectcommande// "_selectCommandEditor"
0x3cc6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cc73  ldarg.0
0x3cc74  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cc79  ldc.i4.s 0xA
0x3cc7b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3cc80  ldarg.0
0x3cc81  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_selectCommandEditor
0x3cc86  ldarg.0
0x3cc87  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::OnSelectCommandChanged(object sender, class [mscorlib]System.EventArgs e)
0x3cc8d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3cc92  callvirt instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::add_CommandChanged(class [mscorlib]System.EventHandler value)
0x3cc97  ldarg.0
0x3cc98  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3cc9d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cca2  ldarg.0
0x3cca3  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3cca8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3ccad  ldarg.0
0x3ccae  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ccb3  ldc.i4.4
0x3ccb4  ldc.i4.s 0x16
0x3ccb6  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3ccbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ccc0  ldarg.0
0x3ccc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ccc6  ldstr    aUpdatetabpage// "_updateTabPage"
0x3cccb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3ccd0  ldarg.0
0x3ccd1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ccd6  ldc.i4   0x218
0x3ccdb  ldc.i4   0xE2
0x3cce0  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3cce5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ccea  ldarg.0
0x3cceb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ccf0  ldc.i4.s 0x14
0x3ccf2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x3ccf7  ldarg.0
0x3ccf8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateTabPage
0x3ccfd  ldstr    aUpdate_0// "UPDATE"
0x3cd02  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3cd07  ldarg.0
0x3cd08  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3cd0d  ldc.i4.5
0x3cd0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x3cd13  ldarg.0
0x3cd14  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3cd19  ldc.i4.0
0x3cd1a  ldc.i4.0
0x3cd1b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cd20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cd25  ldarg.0
0x3cd26  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3cd2b  ldstr    aUpdatecommande// "_updateCommandEditor"
0x3cd30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cd35  ldarg.0
0x3cd36  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_updateCommandEditor
0x3cd3b  ldc.i4.s 0xA
0x3cd3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3cd42  ldarg.0
0x3cd43  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cd48  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cd4d  ldarg.0
0x3cd4e  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3cd53  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3cd58  ldarg.0
0x3cd59  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cd5e  ldc.i4.4
0x3cd5f  ldc.i4.s 0x16
0x3cd61  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cd66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cd6b  ldarg.0
0x3cd6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cd71  ldstr    aInserttabpage// "_insertTabPage"
0x3cd76  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cd7b  ldarg.0
0x3cd7c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cd81  ldc.i4   0x218
0x3cd86  ldc.i4   0xE2
0x3cd8b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3cd90  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3cd95  ldarg.0
0x3cd96  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cd9b  ldc.i4.s 0x1E
0x3cd9d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x3cda2  ldarg.0
0x3cda3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertTabPage
0x3cda8  ldstr    aInsert_0// "INSERT"
0x3cdad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3cdb2  ldarg.0
0x3cdb3  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3cdb8  ldc.i4.5
0x3cdb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x3cdbe  ldarg.0
0x3cdbf  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3cdc4  ldc.i4.0
0x3cdc5  ldc.i4.0
0x3cdc6  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3cdcb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3cdd0  ldarg.0
0x3cdd1  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3cdd6  ldstr    aInsertcommande// "_insertCommandEditor"
0x3cddb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3cde0  ldarg.0
0x3cde1  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_insertCommandEditor
0x3cde6  ldc.i4.s 0xA
0x3cde8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3cded  ldarg.0
0x3cdee  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3cdf3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3cdf8  ldarg.0
0x3cdf9  ldfld    class System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteCommandEditor
0x3cdfe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3ce03  ldarg.0
0x3ce04  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3ce09  ldc.i4.4
0x3ce0a  ldc.i4.s 0x16
0x3ce0c  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3ce11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ce16  ldarg.0
0x3ce17  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3ce1c  ldstr    aDeletetabpage// "_deleteTabPage"
0x3ce21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3ce26  ldarg.0
0x3ce27  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandPanel::_deleteTabPage
0x3ce2c  ldc.i4   0x20A
0x3ce31  ldc.i4   0xE2
0x3ce36  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ce3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ce40  ldarg.0
  ... truncated ...
```
