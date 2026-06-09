# System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::LoadColumnProperties

- ea: `0x4d790`
- end: `0x4d949`
- name: `System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::LoadColumnProperties`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x4e1e0`

## callees

- `0x4d790`
- `0x8eec0`
- `0x8ef40`
- `0x100f60`
- `0x100f80`
- `0x100fa0`
- `0x100fd0`
- `0x100ff0`
- `0x101e30`

## string_xrefs

- `0x4d8b5`: `HyperLinkColumn`
- `0x4d8e9`: `EditCommandColumn`
- `0x4d911`: `TemplateColumn`

## pseudocode

```c

```

## disassembly

```asm
0x4d790  ldstr    aDgcolColumnpro// "DGCol_ColumnPropsGroup1"
0x4d795  call     string System.Design.SR::GetString(string name)
0x4d79a  stloc.0
0x4d79b  ldarg.0
0x4d79c  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d7a1  brfalse  loc_4D93C
0x4d7a6  ldarg.0
0x4d7a7  call     instance void [System.Windows.Forms]System.Windows.Forms.Design.ComponentEditorPage::EnterLoadingMode()
0x4d7ac  ldarg.0
0x4d7ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnHeaderTextEdit
0x4d7b2  ldarg.0
0x4d7b3  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d7b8  callvirt instance string ColumnItem::get_HeaderText()
0x4d7bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4d7c2  ldarg.0
0x4d7c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnHeaderImageEdit
0x4d7c8  ldarg.0
0x4d7c9  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d7ce  callvirt instance string ColumnItem::get_HeaderImageUrl()
0x4d7d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4d7d8  ldarg.0
0x4d7d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnFooterTextEdit
0x4d7de  ldarg.0
0x4d7df  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d7e4  callvirt instance string ColumnItem::get_FooterText()
0x4d7e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4d7ee  ldarg.0
0x4d7ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnSortExprCombo
0x4d7f4  ldarg.0
0x4d7f5  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d7fa  callvirt instance string ColumnItem::get_SortExpression()
0x4d7ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4d804  ldarg.0
0x4d805  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnVisibleCheck
0x4d80a  ldarg.0
0x4d80b  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d810  callvirt instance bool ColumnItem::get_Visible()
0x4d815  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x4d81a  ldarg.0
0x4d81b  ldnull
0x4d81c  stfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d821  ldarg.0
0x4d822  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d827  isinst   BoundColumnItem
0x4d82c  brfalse.s loc_4D858
0x4d82e  ldarg.0
0x4d82f  ldarg.0
0x4d830  ldfld    class BoundColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::boundColumnEditor
0x4d835  stfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d83a  ldstr    aDgcolColumnpro_0// "DGCol_ColumnPropsGroup2"
0x4d83f  ldc.i4.1
0x4d840  newarr   [mscorlib]System.Object
0x4d845  dup
0x4d846  ldc.i4.0
0x4d847  ldstr    aBoundcolumn// "BoundColumn"
0x4d84c  stelem.ref
0x4d84d  call     string System.Design.SR::GetString(string name, object[] args)
0x4d852  stloc.0
0x4d853  br       loc_4D91D
0x4d858  ldarg.0
0x4d859  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d85e  isinst   ButtonColumnItem
0x4d863  brfalse.s loc_4D88F
0x4d865  ldarg.0
0x4d866  ldarg.0
0x4d867  ldfld    class ButtonColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::buttonColumnEditor
0x4d86c  stfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d871  ldstr    aDgcolColumnpro_0// "DGCol_ColumnPropsGroup2"
0x4d876  ldc.i4.1
0x4d877  newarr   [mscorlib]System.Object
0x4d87c  dup
0x4d87d  ldc.i4.0
0x4d87e  ldstr    aButtoncolumn// "ButtonColumn"
0x4d883  stelem.ref
0x4d884  call     string System.Design.SR::GetString(string name, object[] args)
0x4d889  stloc.0
0x4d88a  br       loc_4D91D
0x4d88f  ldarg.0
0x4d890  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d895  isinst   HyperLinkColumnItem
0x4d89a  brfalse.s loc_4D8C3
0x4d89c  ldarg.0
0x4d89d  ldarg.0
0x4d89e  ldfld    class HyperLinkColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::hyperLinkColumnEditor
0x4d8a3  stfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d8a8  ldstr    aDgcolColumnpro_0// "DGCol_ColumnPropsGroup2"
0x4d8ad  ldc.i4.1
0x4d8ae  newarr   [mscorlib]System.Object
0x4d8b3  dup
0x4d8b4  ldc.i4.0
0x4d8b5  ldstr    aHyperlinkcolum// "HyperLinkColumn"
0x4d8ba  stelem.ref
0x4d8bb  call     string System.Design.SR::GetString(string name, object[] args)
0x4d8c0  stloc.0
0x4d8c1  br.s     loc_4D91D
0x4d8c3  ldarg.0
0x4d8c4  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d8c9  isinst   EditCommandColumnItem
0x4d8ce  brfalse.s loc_4D8F7
0x4d8d0  ldarg.0
0x4d8d1  ldarg.0
0x4d8d2  ldfld    class EditCommandColumnEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::editCommandColumnEditor
0x4d8d7  stfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d8dc  ldstr    aDgcolColumnpro_0// "DGCol_ColumnPropsGroup2"
0x4d8e1  ldc.i4.1
0x4d8e2  newarr   [mscorlib]System.Object
0x4d8e7  dup
0x4d8e8  ldc.i4.0
0x4d8e9  ldstr    aEditcommandcol// "EditCommandColumn"
0x4d8ee  stelem.ref
0x4d8ef  call     string System.Design.SR::GetString(string name, object[] args)
0x4d8f4  stloc.0
0x4d8f5  br.s     loc_4D91D
0x4d8f7  ldarg.0
0x4d8f8  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d8fd  isinst   TemplateColumnItem
0x4d902  brfalse.s loc_4D91D
0x4d904  ldstr    aDgcolColumnpro_0// "DGCol_ColumnPropsGroup2"
0x4d909  ldc.i4.1
0x4d90a  newarr   [mscorlib]System.Object
0x4d90f  dup
0x4d910  ldc.i4.0
0x4d911  ldstr    aTemplatecolumn// "TemplateColumn"
0x4d916  stelem.ref
0x4d917  call     string System.Design.SR::GetString(string name, object[] args)
0x4d91c  stloc.0
0x4d91d  ldarg.0
0x4d91e  ldfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d923  brfalse.s loc_4D936
0x4d925  ldarg.0
0x4d926  ldfld    class ColumnItemEditor System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnEditor
0x4d92b  ldarg.0
0x4d92c  ldfld    class ColumnItem System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::currentColumnItem
0x4d931  callvirt instance void ColumnItemEditor::LoadColumn(class ColumnItem columnItem)
0x4d936  ldarg.0
0x4d937  call     instance void [System.Windows.Forms]System.Windows.Forms.Design.ComponentEditorPage::ExitLoadingMode()
0x4d93c  ldarg.0
0x4d93d  ldfld    class System.Web.UI.Design.Util.GroupLabel System.Web.UI.Design.WebControls.ListControls.DataGridColumnsPage::columnPropsGroup
0x4d942  ldloc.0
0x4d943  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4d948  ret
```
