# System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::InitializeUI

- ea: `0x3c420`
- end: `0x3c460`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::InitializeUI`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3bd20`

## callees

- `0x8ef40`

## string_xrefs

- `0x3c426`: `SqlDataSourceCustomCommandEditor_QueryBuilderButton`
- `0x3c43b`: `SqlDataSourceCustomCommandEditor_SqlLabel`
- `0x3c450`: `SqlDataSourceCustomCommandEditor_StoredProcedureLabel`

## pseudocode

```c

```

## disassembly

```asm
0x3c420  ldarg.0
0x3c421  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c426  ldstr    aSqldatasourcec_45// "SqlDataSourceCustomCommandEditor_QueryB"...
0x3c42b  call     string System.Design.SR::GetString(string name)
0x3c430  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3c435  ldarg.0
0x3c436  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3c43b  ldstr    aSqldatasourcec_46// "SqlDataSourceCustomCommandEditor_SqlLab"...
0x3c440  call     string System.Design.SR::GetString(string name)
0x3c445  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3c44a  ldarg.0
0x3c44b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3c450  ldstr    aSqldatasourcec_47// "SqlDataSourceCustomCommandEditor_Stored"...
0x3c455  call     string System.Design.SR::GetString(string name)
0x3c45a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x3c45f  ret
```
