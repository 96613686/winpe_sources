# System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::InitializePanelControls

- ea: `0x28360`
- end: `0x2841f`
- name: `System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::InitializePanelControls`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x27fc0`

## callees

- `0x27c60`
- `0x27cc0`
- `0x526f0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x28377`: `ListControlCreateDataSource_SelectDataSource`
- `0x2838c`: `ListControlCreateDataSource_SelectDataTextField`
- `0x283ab`: `ListControlCreateDataSource_SelectDataValueField`
- `0x283da`: `ListControlCreateDataSource_Title`
- `0x283ea`: `ListControlCreateDataSource_Description`
- `0x28409`: `ListControlCreateDataSource_Caption`

## pseudocode

```c

```

## disassembly

```asm
0x28360  ldarg.0
0x28361  call     instance class [System.Web]System.Web.UI.WebControls.ListControl System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::get_Control()
0x28366  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2836b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x28370  stloc.0
0x28371  ldarg.0
0x28372  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::_dataSourceLabel
0x28377  ldstr    aListcontrolcre// "ListControlCreateDataSource_SelectDataS"...
0x2837c  call     string System.Design.SR::GetString(string name)
0x28381  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x28386  ldarg.0
0x28387  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::_dataTextFieldLabel
0x2838c  ldstr    aListcontrolcre_0// "ListControlCreateDataSource_SelectDataT"...
0x28391  ldc.i4.1
0x28392  newarr   [mscorlib]System.Object
0x28397  dup
0x28398  ldc.i4.0
0x28399  ldloc.0
0x2839a  stelem.ref
0x2839b  call     string System.Design.SR::GetString(string name, object[] args)
0x283a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x283a5  ldarg.0
0x283a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::_dataValueFieldLabel
0x283ab  ldstr    aListcontrolcre_1// "ListControlCreateDataSource_SelectDataV"...
0x283b0  ldc.i4.1
0x283b1  newarr   [mscorlib]System.Object
0x283b6  dup
0x283b7  ldc.i4.0
0x283b8  ldloc.0
0x283b9  stelem.ref
0x283ba  call     string System.Design.SR::GetString(string name, object[] args)
0x283bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x283c4  ldarg.0
0x283c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::_refreshSchemaLink
0x283ca  ldstr    aDatasourcedesi// "DataSourceDesigner_RefreshSchemaNoHotke"...
0x283cf  call     string System.Design.SR::GetString(string name)
0x283d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x283d9  ldarg.0
0x283da  ldstr    aListcontrolcre_2// "ListControlCreateDataSource_Title"
0x283df  call     string System.Design.SR::GetString(string name)
0x283e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x283e9  ldarg.0
0x283ea  ldstr    aListcontrolcre_3// "ListControlCreateDataSource_Description"
0x283ef  ldc.i4.1
0x283f0  newarr   [mscorlib]System.Object
0x283f5  dup
0x283f6  ldc.i4.0
0x283f7  ldloc.0
0x283f8  stelem.ref
0x283f9  call     string System.Design.SR::GetString(string name, object[] args)
0x283fe  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x28403  ldarg.0
0x28404  call     instance class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::get_CaptionLabel()
0x28409  ldstr    aListcontrolcre_4// "ListControlCreateDataSource_Caption"
0x2840e  call     string System.Design.SR::GetString(string name)
0x28413  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x28418  ldarg.0
0x28419  call     instance void System.Web.UI.Design.WebControls.ListControlConnectToDataSourceDialog::FillDataSourceList()
0x2841e  ret
```
