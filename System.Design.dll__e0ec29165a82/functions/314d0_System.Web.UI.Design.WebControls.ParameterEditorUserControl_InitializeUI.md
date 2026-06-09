# System.Web.UI.Design.WebControls.ParameterEditorUserControl::InitializeUI

- ea: `0x314d0`
- end: `0x31608`
- name: `System.Web.UI.Design.WebControls.ParameterEditorUserControl::InitializeUI`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x308f0`

## callees

- `0x8ef40`
- `0xef300`

## string_xrefs

- `0x3159f`: `Delete.ico`
- `0x315ce`: `ParameterEditorUserControl_MoveParameterUp`
- `0x315e3`: `ParameterEditorUserControl_MoveParameterDown`
- `0x315f8`: `ParameterEditorUserControl_DeleteParameter`

## pseudocode

```c

```

## disassembly

```asm
0x314d0  ldarg.0
0x314d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_parametersLabel
0x314d6  ldstr    aParameteredito_1// "ParameterEditorUserControl_ParametersLa"...
0x314db  call     string System.Design.SR::GetString(string name)
0x314e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x314e5  ldarg.0
0x314e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_nameColumnHeader
0x314eb  ldstr    aParameteredito_2// "ParameterEditorUserControl_ParameterNam"...
0x314f0  call     string System.Design.SR::GetString(string name)
0x314f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Text(string)
0x314fa  ldarg.0
0x314fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.ParameterEditorUserControl::_valueColumnHeader
0x31500  ldstr    aParameteredito_3// "ParameterEditorUserControl_ParameterVal"...
0x31505  call     string System.Design.SR::GetString(string name)
0x3150a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Text(string)
0x3150f  ldarg.0
0x31510  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_addParameterButton
0x31515  ldstr    aParameteredito_4// "ParameterEditorUserControl_AddButton"
0x3151a  call     string System.Design.SR::GetString(string name)
0x3151f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x31524  ldarg.0
0x31525  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.ParameterEditorUserControl::_sourceLabel
0x3152a  ldstr    aParameteredito_5// "ParameterEditorUserControl_SourceLabel"
0x3152f  call     string System.Design.SR::GetString(string name)
0x31534  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x31539  ldtoken  System.Web.UI.Design.WebControls.ParameterEditorUserControl
0x3153e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31543  ldstr    aSortupIco// "SortUp.ico"
0x31548  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x3154d  stloc.0
0x3154e  ldloc.0
0x3154f  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x31554  stloc.1
0x31555  ldloc.1
0x31556  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x3155b  ldarg.0
0x3155c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x31561  ldloc.1
0x31562  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x31567  ldtoken  System.Web.UI.Design.WebControls.ParameterEditorUserControl
0x3156c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31571  ldstr    aSortdownIco// "SortDown.ico"
0x31576  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x3157b  stloc.2
0x3157c  ldloc.2
0x3157d  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x31582  stloc.3
0x31583  ldloc.3
0x31584  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x31589  ldarg.0
0x3158a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x3158f  ldloc.3
0x31590  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x31595  ldtoken  System.Web.UI.Design.WebControls.ParameterEditorUserControl
0x3159a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3159f  ldstr    aDeleteIco// "Delete.ico"
0x315a4  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x315a9  stloc.s  4
0x315ab  ldloc.s  4
0x315ad  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x315b2  stloc.s  5
0x315b4  ldloc.s  5
0x315b6  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x315bb  ldarg.0
0x315bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x315c1  ldloc.s  5
0x315c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x315c8  ldarg.0
0x315c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveUpButton
0x315ce  ldstr    aParameteredito_6// "ParameterEditorUserControl_MoveParamete"...
0x315d3  call     string System.Design.SR::GetString(string name)
0x315d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x315dd  ldarg.0
0x315de  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_moveDownButton
0x315e3  ldstr    aParameteredito_7// "ParameterEditorUserControl_MoveParamete"...
0x315e8  call     string System.Design.SR::GetString(string name)
0x315ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x315f2  ldarg.0
0x315f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.ParameterEditorUserControl::_deleteParameterButton
0x315f8  ldstr    aParameteredito_8// "ParameterEditorUserControl_DeleteParame"...
0x315fd  call     string System.Design.SR::GetString(string name)
0x31602  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x31607  ret
```
