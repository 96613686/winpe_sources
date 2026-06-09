# System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::InitializeUI

- ea: `0x4a1b0`
- end: `0x4a2d1`
- name: `System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::InitializeUI`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x49a40`

## callees

- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x4a2ad`: `ConfigureDataSource_Title`
- `0x4a1b6`: `XmlDataSourceConfigureDataSourceForm_DataFileLabel`
- `0x4a1cb`: `XmlDataSourceConfigureDataSourceForm_TransformFileLabel`
- `0x4a1e0`: `XmlDataSourceConfigureDataSourceForm_XPathExpressionLabel`
- `0x4a1f5`: `XmlDataSourceConfigureDataSourceForm_TransformFileHelpLabel`
- `0x4a20a`: `XmlDataSourceConfigureDataSourceForm_XPathExpressionHelpLabel`
- `0x4a21f`: `XmlDataSourceConfigureDataSourceForm_Browse`
- `0x4a234`: `XmlDataSourceConfigureDataSourceForm_Browse`
- `0x4a249`: `XmlDataSourceConfigureDataSourceForm_HelpLabel`
- `0x4a288`: `XmlDataFileEditor_Ellipses`

## pseudocode

```c

```

## disassembly

```asm
0x4a1b0  ldarg.0
0x4a1b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x4a1b6  ldstr    aXmldatasourcec_0// "XmlDataSourceConfigureDataSourceForm_Da"...
0x4a1bb  call     string System.Design.SR::GetString(string name)
0x4a1c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a1c5  ldarg.0
0x4a1c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x4a1cb  ldstr    aXmldatasourcec_1// "XmlDataSourceConfigureDataSourceForm_Tr"...
0x4a1d0  call     string System.Design.SR::GetString(string name)
0x4a1d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a1da  ldarg.0
0x4a1db  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x4a1e0  ldstr    aXmldatasourcec_2// "XmlDataSourceConfigureDataSourceForm_XP"...
0x4a1e5  call     string System.Design.SR::GetString(string name)
0x4a1ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a1ef  ldarg.0
0x4a1f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x4a1f5  ldstr    aXmldatasourcec_3// "XmlDataSourceConfigureDataSourceForm_Tr"...
0x4a1fa  call     string System.Design.SR::GetString(string name)
0x4a1ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a204  ldarg.0
0x4a205  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionHelpLabel
0x4a20a  ldstr    aXmldatasourcec_4// "XmlDataSourceConfigureDataSourceForm_XP"...
0x4a20f  call     string System.Design.SR::GetString(string name)
0x4a214  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a219  ldarg.0
0x4a21a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x4a21f  ldstr    aXmldatasourcec_5// "XmlDataSourceConfigureDataSourceForm_Br"...
0x4a224  call     string System.Design.SR::GetString(string name)
0x4a229  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a22e  ldarg.0
0x4a22f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x4a234  ldstr    aXmldatasourcec_5// "XmlDataSourceConfigureDataSourceForm_Br"...
0x4a239  call     string System.Design.SR::GetString(string name)
0x4a23e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a243  ldarg.0
0x4a244  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x4a249  ldstr    aXmldatasourcec_6// "XmlDataSourceConfigureDataSourceForm_He"...
0x4a24e  call     string System.Design.SR::GetString(string name)
0x4a253  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a258  ldarg.0
0x4a259  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_okButton
0x4a25e  ldstr    aOk// "OK"
0x4a263  call     string System.Design.SR::GetString(string name)
0x4a268  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a26d  ldarg.0
0x4a26e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_cancelButton
0x4a273  ldstr    aCancel// "Cancel"
0x4a278  call     string System.Design.SR::GetString(string name)
0x4a27d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a282  ldarg.0
0x4a283  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x4a288  ldstr    aXmldatafileedi_1// "XmlDataFileEditor_Ellipses"
0x4a28d  call     string System.Design.SR::GetString(string name)
0x4a292  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x4a297  ldarg.0
0x4a298  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x4a29d  ldstr    aXsltransformfi_1// "XslTransformFileEditor_Ellipses"
0x4a2a2  call     string System.Design.SR::GetString(string name)
0x4a2a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x4a2ac  ldarg.0
0x4a2ad  ldstr    aConfiguredatas// "ConfigureDataSource_Title"
0x4a2b2  ldc.i4.1
0x4a2b3  newarr   [mscorlib]System.Object
0x4a2b8  dup
0x4a2b9  ldc.i4.0
0x4a2ba  ldarg.0
0x4a2bb  ldfld    class [System.Web]System.Web.UI.WebControls.XmlDataSource System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xmlDataSource
0x4a2c0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x4a2c5  stelem.ref
0x4a2c6  call     string System.Design.SR::GetString(string name, object[] args)
0x4a2cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4a2d0  ret
```
