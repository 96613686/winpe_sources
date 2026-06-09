# System.Web.UI.WebControls.ListView::HandleEvent

- ea: `0x20780`
- end: `0x20915`
- name: `System.Web.UI.WebControls.ListView::HandleEvent`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x21330`

## callees

- `0x20370`
- `0x203a0`
- `0x204b0`
- `0x20510`
- `0x20740`
- `0x20780`
- `0x20920`
- `0x20a60`
- `0x20ba0`
- `0x20bf0`
- `0x20cb0`
- `0x21450`
- `0x21ad0`
- `0x22300`
- `0x22310`

## string_xrefs

- `0x20866`: `Update`
- `0x2089a`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x20780  ldc.i4.0
0x20781  stloc.0
0x20782  ldarg.0
0x20783  ldarg.2
0x20784  ldarg.3
0x20785  call     instance void System.Web.UI.WebControls.ListView::ResetModelValidationGroup(bool causesValidation, string validationGroup)
0x2078a  ldarg.1
0x2078b  isinst   System.Web.UI.WebControls.ListViewCommandEventArgs
0x20790  stloc.1
0x20791  ldloc.1
0x20792  brfalse  loc_20913
0x20797  ldarg.0
0x20798  ldloc.1
0x20799  callvirt instance void System.Web.UI.WebControls.ListView::OnItemCommand(class System.Web.UI.WebControls.ListViewCommandEventArgs e)
0x2079e  ldloc.1
0x2079f  callvirt instance bool System.Web.UI.WebControls.ListViewCommandEventArgs::get_Handled()
0x207a4  brfalse.s loc_207A8
0x207a6  ldc.i4.1
0x207a7  ret
0x207a8  ldc.i4.1
0x207a9  stloc.0
0x207aa  ldloc.1
0x207ab  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandName()
0x207b0  stloc.2
0x207b1  ldloc.2
0x207b2  ldstr    aSelect// "Select"
0x207b7  ldc.i4.5
0x207b8  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x207bd  brfalse.s loc_207E1
0x207bf  ldarg.0
0x207c0  ldarg.0
0x207c1  ldloc.1
0x207c2  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x207c7  ldloc.1
0x207c8  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x207cd  castclass [mscorlib]System.String
0x207d2  call     instance int32 System.Web.UI.WebControls.ListView::GetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument)
0x207d7  call     instance void System.Web.UI.WebControls.ListView::HandleSelect(int32 itemIndex)
0x207dc  br       loc_20913
0x207e1  ldloc.2
0x207e2  ldstr    aSort// "Sort"
0x207e7  ldc.i4.5
0x207e8  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x207ed  brfalse.s loc_20805
0x207ef  ldarg.0
0x207f0  ldloc.1
0x207f1  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x207f6  castclass [mscorlib]System.String
0x207fb  call     instance void System.Web.UI.WebControls.ListView::HandleSort(string sortExpression)
0x20800  br       loc_20913
0x20805  ldloc.2
0x20806  ldstr    aEdit// "Edit"
0x2080b  ldc.i4.5
0x2080c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x20811  brfalse.s loc_20835
0x20813  ldarg.0
0x20814  ldarg.0
0x20815  ldloc.1
0x20816  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x2081b  ldloc.1
0x2081c  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x20821  castclass [mscorlib]System.String
0x20826  call     instance int32 System.Web.UI.WebControls.ListView::GetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument)
0x2082b  call     instance void System.Web.UI.WebControls.ListView::HandleEdit(int32 itemIndex)
0x20830  br       loc_20913
0x20835  ldloc.2
0x20836  ldstr    aCancel// "Cancel"
0x2083b  ldc.i4.5
0x2083c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x20841  brfalse.s loc_20865
0x20843  ldarg.0
0x20844  ldarg.0
0x20845  ldloc.1
0x20846  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x2084b  ldloc.1
0x2084c  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x20851  castclass [mscorlib]System.String
0x20856  call     instance int32 System.Web.UI.WebControls.ListView::GetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument)
0x2085b  call     instance void System.Web.UI.WebControls.ListView::HandleCancel(int32 itemIndex)
0x20860  br       loc_20913
0x20865  ldloc.2
0x20866  ldstr    aUpdate// "Update"
0x2086b  ldc.i4.5
0x2086c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x20871  brfalse.s loc_20899
0x20873  ldarg.0
0x20874  ldloc.1
0x20875  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x2087a  ldarg.0
0x2087b  ldloc.1
0x2087c  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x20881  ldloc.1
0x20882  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x20887  castclass [mscorlib]System.String
0x2088c  call     instance int32 System.Web.UI.WebControls.ListView::GetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument)
0x20891  ldarg.2
0x20892  call     instance void System.Web.UI.WebControls.ListView::HandleUpdate(class System.Web.UI.WebControls.ListViewItem item, int32 itemIndex, bool causesValidation)
0x20897  br.s     loc_20913
0x20899  ldloc.2
0x2089a  ldstr    aDelete// "Delete"
0x2089f  ldc.i4.5
0x208a0  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x208a5  brfalse.s loc_208CC
0x208a7  ldarg.0
0x208a8  ldloc.1
0x208a9  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x208ae  ldarg.0
0x208af  ldloc.1
0x208b0  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x208b5  ldloc.1
0x208b6  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x208bb  castclass [mscorlib]System.String
0x208c0  call     instance int32 System.Web.UI.WebControls.ListView::GetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument)
0x208c5  call     instance void System.Web.UI.WebControls.ListView::HandleDelete(class System.Web.UI.WebControls.ListViewItem item, int32 itemIndex)
0x208ca  br.s     loc_20913
0x208cc  ldloc.2
0x208cd  ldstr    aInsert// "Insert"
0x208d2  ldc.i4.5
0x208d3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x208d8  brfalse.s loc_208E9
0x208da  ldarg.0
0x208db  ldloc.1
0x208dc  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x208e1  ldarg.2
0x208e2  call     instance void System.Web.UI.WebControls.ListView::HandleInsert(class System.Web.UI.WebControls.ListViewItem item, bool causesValidation)
0x208e7  br.s     loc_20913
0x208e9  ldarg.0
0x208ea  ldloc.1
0x208eb  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x208f0  ldloc.1
0x208f1  callvirt instance object [System.Web]System.Web.UI.WebControls.CommandEventArgs::get_CommandArgument()
0x208f6  castclass [mscorlib]System.String
0x208fb  ldloca.s 3
0x208fd  call     instance bool System.Web.UI.WebControls.ListView::TryGetItemIndex(class System.Web.UI.WebControls.ListViewItem item, string commandArgument, [out] int32& itemIndex)
0x20902  brfalse.s loc_20913
0x20904  ldarg.0
0x20905  ldloc.1
0x20906  callvirt instance class System.Web.UI.WebControls.ListViewItem System.Web.UI.WebControls.ListViewCommandEventArgs::get_Item()
0x2090b  ldloc.3
0x2090c  ldloc.2
0x2090d  call     instance bool System.Web.UI.WebControls.ListView::HandleCommand(class System.Web.UI.WebControls.ListViewItem item, int32 itemIndex, string commandName)
0x20912  stloc.0
0x20913  ldloc.0
0x20914  ret
```
