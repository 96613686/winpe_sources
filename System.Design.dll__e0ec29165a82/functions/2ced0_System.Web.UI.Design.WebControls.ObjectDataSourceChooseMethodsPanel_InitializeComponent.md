# System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::InitializeComponent

- ea: `0x2ced0`
- end: `0x2d369`
- name: `System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::InitializeComponent`
- size: `1177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x2ce30`

## callees

- `0x2f600`
- `0x2f680`

## string_xrefs

- `0x2d125`: `_updateTabPage`
- `0x2d15c`: `UPDATE`
- `0x2d18a`: `_updateObjectDataSourceMethodEditor`
- `0x2d279`: `_deleteTabPage`
- `0x2d2b0`: `DELETE`
- `0x2d2de`: `_deleteObjectDataSourceMethodEditor`

## pseudocode

```c

```

## disassembly

```asm
0x2ced0  ldarg.0
0x2ced1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabControl::.ctor()
0x2ced6  stfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cedb  ldarg.0
0x2cedc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x2cee1  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2cee6  ldarg.0
0x2cee7  newobj   instance void System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::.ctor()
0x2ceec  stfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2cef1  ldarg.0
0x2cef2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x2cef7  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2cefc  ldarg.0
0x2cefd  newobj   instance void System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::.ctor()
0x2cf02  stfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2cf07  ldarg.0
0x2cf08  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x2cf0d  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2cf12  ldarg.0
0x2cf13  newobj   instance void System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::.ctor()
0x2cf18  stfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2cf1d  ldarg.0
0x2cf1e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x2cf23  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2cf28  ldarg.0
0x2cf29  newobj   instance void System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::.ctor()
0x2cf2e  stfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2cf33  ldarg.0
0x2cf34  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cf39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf3e  ldarg.0
0x2cf3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2cf44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf49  ldarg.0
0x2cf4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2cf4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf54  ldarg.0
0x2cf55  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2cf5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf5f  ldarg.0
0x2cf60  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2cf65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf6a  ldarg.0
0x2cf6b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2cf70  ldarg.0
0x2cf71  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cf76  ldc.i4.s 0xF
0x2cf78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x2cf7d  ldarg.0
0x2cf7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cf83  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2cf88  ldarg.0
0x2cf89  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2cf8e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2cf93  ldarg.0
0x2cf94  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cf99  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2cf9e  ldarg.0
0x2cf9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2cfa4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2cfa9  ldarg.0
0x2cfaa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cfaf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2cfb4  ldarg.0
0x2cfb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2cfba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2cfbf  ldarg.0
0x2cfc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cfc5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2cfca  ldarg.0
0x2cfcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2cfd0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2cfd5  ldarg.0
0x2cfd6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cfdb  ldc.i4.0
0x2cfdc  ldc.i4.0
0x2cfdd  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2cfe2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2cfe7  ldarg.0
0x2cfe8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cfed  ldstr    aMethodstabcont// "_methodsTabControl"
0x2cff2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2cff7  ldarg.0
0x2cff8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2cffd  ldc.i4.0
0x2cffe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x2d003  ldarg.0
0x2d004  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2d009  ldc.i4.1
0x2d00a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_ShowToolTips(bool)
0x2d00f  ldarg.0
0x2d010  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2d015  ldc.i4   0x220
0x2d01a  ldc.i4   0x112
0x2d01f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2d024  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2d029  ldarg.0
0x2d02a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_methodsTabControl
0x2d02f  ldc.i4.0
0x2d030  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2d035  ldarg.0
0x2d036  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d03b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2d040  ldarg.0
0x2d041  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d046  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2d04b  ldarg.0
0x2d04c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d051  ldc.i4.4
0x2d052  ldc.i4.s 0x16
0x2d054  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d059  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d05e  ldarg.0
0x2d05f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d064  ldstr    aSelecttabpage// "_selectTabPage"
0x2d069  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d06e  ldarg.0
0x2d06f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d074  ldc.i4   0x218
0x2d079  ldc.i4   0xF8
0x2d07e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2d083  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2d088  ldarg.0
0x2d089  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d08e  ldc.i4.s 0xA
0x2d090  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x2d095  ldarg.0
0x2d096  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectTabPage
0x2d09b  ldstr    aSelect// "SELECT"
0x2d0a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2d0a5  ldarg.0
0x2d0a6  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d0ab  ldc.i4.5
0x2d0ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x2d0b1  ldarg.0
0x2d0b2  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d0b7  ldc.i4.0
0x2d0b8  ldc.i4.0
0x2d0b9  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d0be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d0c3  ldarg.0
0x2d0c4  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d0c9  ldstr    aSelectobjectda// "_selectObjectDataSourceMethodEditor"
0x2d0ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d0d3  ldarg.0
0x2d0d4  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d0d9  ldc.i4.0
0x2d0da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2d0df  ldarg.0
0x2d0e0  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_selectObjectDataSourceMethodEditor
0x2d0e5  ldarg.0
0x2d0e6  ldftn    instance void System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::OnSelectMethodChanged(object sender, class [mscorlib]System.EventArgs e)
0x2d0ec  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2d0f1  callvirt instance void System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor::add_MethodChanged(class [mscorlib]System.EventHandler value)
0x2d0f6  ldarg.0
0x2d0f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d0fc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2d101  ldarg.0
0x2d102  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2d107  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2d10c  ldarg.0
0x2d10d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d112  ldc.i4.4
0x2d113  ldc.i4.s 0x16
0x2d115  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d11a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d11f  ldarg.0
0x2d120  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d125  ldstr    aUpdatetabpage// "_updateTabPage"
0x2d12a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d12f  ldarg.0
0x2d130  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d135  ldc.i4   0x218
0x2d13a  ldc.i4   0xF8
0x2d13f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2d144  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2d149  ldarg.0
0x2d14a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d14f  ldc.i4.s 0x14
0x2d151  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x2d156  ldarg.0
0x2d157  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateTabPage
0x2d15c  ldstr    aUpdate_0// "UPDATE"
0x2d161  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2d166  ldarg.0
0x2d167  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2d16c  ldc.i4.5
0x2d16d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x2d172  ldarg.0
0x2d173  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2d178  ldc.i4.0
0x2d179  ldc.i4.0
0x2d17a  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d17f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d184  ldarg.0
0x2d185  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2d18a  ldstr    aUpdateobjectda// "_updateObjectDataSourceMethodEditor"
0x2d18f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d194  ldarg.0
0x2d195  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_updateObjectDataSourceMethodEditor
0x2d19a  ldc.i4.0
0x2d19b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2d1a0  ldarg.0
0x2d1a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d1a6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2d1ab  ldarg.0
0x2d1ac  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2d1b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2d1b6  ldarg.0
0x2d1b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d1bc  ldc.i4.4
0x2d1bd  ldc.i4.s 0x16
0x2d1bf  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d1c4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d1c9  ldarg.0
0x2d1ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d1cf  ldstr    aInserttabpage// "_insertTabPage"
0x2d1d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d1d9  ldarg.0
0x2d1da  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d1df  ldc.i4   0x218
0x2d1e4  ldc.i4   0xF8
0x2d1e9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2d1ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2d1f3  ldarg.0
0x2d1f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d1f9  ldc.i4.s 0x1E
0x2d1fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x2d200  ldarg.0
0x2d201  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertTabPage
0x2d206  ldstr    aInsert_0// "INSERT"
0x2d20b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2d210  ldarg.0
0x2d211  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2d216  ldc.i4.5
0x2d217  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x2d21c  ldarg.0
0x2d21d  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2d222  ldc.i4.0
0x2d223  ldc.i4.0
0x2d224  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d229  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d22e  ldarg.0
0x2d22f  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2d234  ldstr    aInsertobjectda// "_insertObjectDataSourceMethodEditor"
0x2d239  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d23e  ldarg.0
0x2d23f  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_insertObjectDataSourceMethodEditor
0x2d244  ldc.i4.0
0x2d245  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2d24a  ldarg.0
0x2d24b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d250  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2d255  ldarg.0
0x2d256  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2d25b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2d260  ldarg.0
0x2d261  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d266  ldc.i4.4
0x2d267  ldc.i4.s 0x16
0x2d269  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d26e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d273  ldarg.0
0x2d274  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d279  ldstr    aDeletetabpage// "_deleteTabPage"
0x2d27e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d283  ldarg.0
0x2d284  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d289  ldc.i4   0x218
0x2d28e  ldc.i4   0xF8
0x2d293  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x2d298  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x2d29d  ldarg.0
0x2d29e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d2a3  ldc.i4.s 0x28
0x2d2a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabPage::set_TabIndex(int32)
0x2d2aa  ldarg.0
0x2d2ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteTabPage
0x2d2b0  ldstr    aDelete_0// "DELETE"
0x2d2b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2d2ba  ldarg.0
0x2d2bb  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2d2c0  ldc.i4.5
0x2d2c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x2d2c6  ldarg.0
0x2d2c7  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2d2cc  ldc.i4.0
0x2d2cd  ldc.i4.0
0x2d2ce  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x2d2d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x2d2d8  ldarg.0
0x2d2d9  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2d2de  ldstr    aDeleteobjectda// "_deleteObjectDataSourceMethodEditor"
0x2d2e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2d2e8  ldarg.0
0x2d2e9  ldfld    class System.Web.UI.Design.WebControls.ObjectDataSourceMethodEditor System.Web.UI.Design.WebControls.ObjectDataSourceChooseMethodsPanel::_deleteObjectDataSourceMethodEditor
0x2d2ee  ldc.i4.0
0x2d2ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x2d2f4  ldarg.0
0x2d2f5  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
  ... truncated ...
```
