# System.Web.UI.Design.WebControls.DataListDesigner::RefreshSchemaCallback

- ea: `0x20880`
- end: `0x2098f`
- name: `System.Web.UI.Design.WebControls.DataListDesigner::RefreshSchemaCallback`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x3c40`
- `0x15c00`
- `0x20210`
- `0x20530`
- `0x20880`
- `0x52c90`
- `0x584f0`
- `0x8ef40`

## string_xrefs

- `0x208de`: `DataList_RegenerateTemplates`
- `0x208e8`: `DataList_ClearTemplatesCaption`
- `0x2094e`: `DataList_ClearTemplatesCaption`
- `0x20944`: `DataList_ClearTemplates`

## pseudocode

```c

```

## disassembly

```asm
0x20880  ldarg.0
0x20881  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x20886  castclass [System.Web]System.Web.UI.WebControls.DataList
0x2088b  stloc.0
0x2088c  ldloc.0
0x2088d  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.DataList::get_ItemTemplate()
0x20892  brtrue.s loc_208AF
0x20894  ldloc.0
0x20895  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.DataList::get_EditItemTemplate()
0x2089a  brtrue.s loc_208AF
0x2089c  ldloc.0
0x2089d  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.DataList::get_AlternatingItemTemplate()
0x208a2  brtrue.s loc_208AF
0x208a4  ldloc.0
0x208a5  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.DataList::get_SelectedItemTemplate()
0x208aa  ldnull
0x208ab  ceq
0x208ad  br.s     loc_208B0
0x208af  ldc.i4.0
0x208b0  stloc.1
0x208b1  ldarg.0
0x208b2  call     instance class System.Web.UI.Design.IDataSourceViewSchema System.Web.UI.Design.WebControls.DataListDesigner::GetDataSourceSchema()
0x208b7  stloc.2
0x208b8  ldarg.0
0x208b9  call     instance string System.Web.UI.Design.WebControls.BaseDataListDesigner::get_DataSourceID()
0x208be  callvirt instance int32 [mscorlib]System.String::get_Length()
0x208c3  ldc.i4.0
0x208c4  ble.s    loc_20932
0x208c6  ldloc.2
0x208c7  brfalse.s loc_20932
0x208c9  ldloc.1
0x208ca  brtrue.s loc_208FD
0x208cc  ldloc.1
0x208cd  brtrue   loc_2098D
0x208d2  ldc.i4.6
0x208d3  ldarg.0
0x208d4  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x208d9  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x208de  ldstr    aDatalistRegene// "DataList_RegenerateTemplates"
0x208e3  call     string System.Design.SR::GetString(string name)
0x208e8  ldstr    aDatalistCleart// "DataList_ClearTemplatesCaption"
0x208ed  call     string System.Design.SR::GetString(string name)
0x208f2  ldc.i4.4
0x208f3  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult System.Web.UI.Design.Util.UIServiceHelper::ShowMessage(class [mscorlib]System.IServiceProvider serviceProvider, string message, string caption, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons)
0x208f8  bne.un   loc_2098D
0x208fd  ldloc.0
0x208fe  ldnull
0x208ff  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_ItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x20904  ldloc.0
0x20905  ldnull
0x20906  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_EditItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x2090b  ldloc.0
0x2090c  ldnull
0x2090d  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_AlternatingItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x20912  ldloc.0
0x20913  ldnull
0x20914  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_SelectedItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x20919  ldloc.0
0x2091a  ldsfld   string [mscorlib]System.String::Empty
0x2091f  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseDataList::set_DataKeyField(string)
0x20924  ldarg.0
0x20925  call     instance void System.Web.UI.Design.WebControls.DataListDesigner::CreateDefaultTemplate()
0x2092a  ldarg.0
0x2092b  callvirt instance void System.Web.UI.Design.ControlDesigner::UpdateDesignTimeHtml()
0x20930  br.s     loc_2098D
0x20932  ldloc.1
0x20933  brtrue.s loc_20960
0x20935  ldloc.1
0x20936  brtrue.s loc_2098D
0x20938  ldc.i4.6
0x20939  ldarg.0
0x2093a  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x2093f  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x20944  ldstr    aDatalistCleart_0// "DataList_ClearTemplates"
0x20949  call     string System.Design.SR::GetString(string name)
0x2094e  ldstr    aDatalistCleart// "DataList_ClearTemplatesCaption"
0x20953  call     string System.Design.SR::GetString(string name)
0x20958  ldc.i4.4
0x20959  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult System.Web.UI.Design.Util.UIServiceHelper::ShowMessage(class [mscorlib]System.IServiceProvider serviceProvider, string message, string caption, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons)
0x2095e  bne.un.s loc_2098D
0x20960  ldloc.0
0x20961  ldnull
0x20962  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_ItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x20967  ldloc.0
0x20968  ldnull
0x20969  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_EditItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x2096e  ldloc.0
0x2096f  ldnull
0x20970  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_AlternatingItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x20975  ldloc.0
0x20976  ldnull
0x20977  callvirt instance void [System.Web]System.Web.UI.WebControls.DataList::set_SelectedItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x2097c  ldloc.0
0x2097d  ldsfld   string [mscorlib]System.String::Empty
0x20982  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseDataList::set_DataKeyField(string)
0x20987  ldarg.0
0x20988  callvirt instance void System.Web.UI.Design.ControlDesigner::UpdateDesignTimeHtml()
0x2098d  ldc.i4.1
0x2098e  ret
```
