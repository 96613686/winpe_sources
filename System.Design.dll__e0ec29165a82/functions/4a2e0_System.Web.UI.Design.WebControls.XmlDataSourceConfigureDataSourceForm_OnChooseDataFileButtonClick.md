# System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::OnChooseDataFileButtonClick

- ea: `0x4a2e0`
- end: `0x4a312`
- name: `System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::OnChooseDataFileButtonClick`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x11c70`
- `0x49a90`
- `0x49aa0`
- `0x4a2e0`
- `0x8ef40`

## string_xrefs

- `0x4a2ed`: `XmlDataFileEditor_Caption`
- `0x4a2f7`: `XmlDataFileEditor_Filter`

## pseudocode

```c

```

## disassembly

```asm
0x4a2e0  ldarg.0
0x4a2e1  ldfld    class [System.Web]System.Web.UI.WebControls.XmlDataSource System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xmlDataSource
0x4a2e6  ldarg.0
0x4a2e7  ldarg.0
0x4a2e8  call     instance string System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::get_DataFile()
0x4a2ed  ldstr    aXmldatafileedi// "XmlDataFileEditor_Caption"
0x4a2f2  call     string System.Design.SR::GetString(string name)
0x4a2f7  ldstr    aXmldatafileedi_0// "XmlDataFileEditor_Filter"
0x4a2fc  call     string System.Design.SR::GetString(string name)
0x4a301  call     string System.Web.UI.Design.UrlBuilder::BuildUrl(class [System]System.ComponentModel.IComponent component, class [System.Windows.Forms]System.Windows.Forms.Control owner, string initialUrl, string caption, string filter)
0x4a306  stloc.0
0x4a307  ldloc.0
0x4a308  brfalse.s loc_4A311
0x4a30a  ldarg.0
0x4a30b  ldloc.0
0x4a30c  call     instance void System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::set_DataFile(string value)
0x4a311  ret
```
