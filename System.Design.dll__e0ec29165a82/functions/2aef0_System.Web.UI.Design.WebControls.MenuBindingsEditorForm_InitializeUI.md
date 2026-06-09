# System.Web.UI.Design.WebControls.MenuBindingsEditorForm::InitializeUI

- ea: `0x2aef0`
- end: `0x2b09d`
- name: `System.Web.UI.Design.WebControls.MenuBindingsEditorForm::InitializeUI`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x2a370`

## callees

- `0x8ef40`
- `0xef300`

## string_xrefs

- `0x2b049`: `Delete.ico`
- `0x2afc5`: `MenuBindingsEditor_MoveBindingUpName`
- `0x2afda`: `MenuBindingsEditor_MoveBindingUpDescription`
- `0x2b01b`: `MenuBindingsEditor_MoveBindingDownName`
- `0x2b030`: `MenuBindingsEditor_MoveBindingDownDescription`
- `0x2b071`: `MenuBindingsEditor_DeleteBindingName`
- `0x2b086`: `MenuBindingsEditor_DeleteBindingDescription`

## pseudocode

```c

```

## disassembly

```asm
0x2aef0  ldarg.0
0x2aef1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_bindingsLabel
0x2aef6  ldstr    aMenubindingsed_0// "MenuBindingsEditor_Bindings"
0x2aefb  call     string System.Design.SR::GetString(string name)
0x2af00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af05  ldarg.0
0x2af06  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_schemaLabel
0x2af0b  ldstr    aMenubindingsed_1// "MenuBindingsEditor_Schema"
0x2af10  call     string System.Design.SR::GetString(string name)
0x2af15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af1a  ldarg.0
0x2af1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_okButton
0x2af20  ldstr    aMenubindingsed_2// "MenuBindingsEditor_OK"
0x2af25  call     string System.Design.SR::GetString(string name)
0x2af2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af2f  ldarg.0
0x2af30  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_applyButton
0x2af35  ldstr    aMenubindingsed_3// "MenuBindingsEditor_Apply"
0x2af3a  call     string System.Design.SR::GetString(string name)
0x2af3f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af44  ldarg.0
0x2af45  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_cancelButton
0x2af4a  ldstr    aMenubindingsed_4// "MenuBindingsEditor_Cancel"
0x2af4f  call     string System.Design.SR::GetString(string name)
0x2af54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af59  ldarg.0
0x2af5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_propertiesLabel
0x2af5f  ldstr    aMenubindingsed_5// "MenuBindingsEditor_BindingProperties"
0x2af64  call     string System.Design.SR::GetString(string name)
0x2af69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af6e  ldarg.0
0x2af6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_addBindingButton
0x2af74  ldstr    aMenubindingsed_6// "MenuBindingsEditor_AddBinding"
0x2af79  call     string System.Design.SR::GetString(string name)
0x2af7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af83  ldarg.0
0x2af84  ldstr    aMenubindingsed_7// "MenuBindingsEditor_Title"
0x2af89  call     string System.Design.SR::GetString(string name)
0x2af8e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2af93  ldtoken  System.Web.UI.Design.WebControls.MenuBindingsEditorForm
0x2af98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2af9d  ldstr    aSortupIco// "SortUp.ico"
0x2afa2  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x2afa7  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x2afac  stloc.0
0x2afad  ldloc.0
0x2afae  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x2afb3  ldarg.0
0x2afb4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingUpButton
0x2afb9  ldloc.0
0x2afba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x2afbf  ldarg.0
0x2afc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingUpButton
0x2afc5  ldstr    aMenubindingsed_8// "MenuBindingsEditor_MoveBindingUpName"
0x2afca  call     string System.Design.SR::GetString(string name)
0x2afcf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x2afd4  ldarg.0
0x2afd5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingUpButton
0x2afda  ldstr    aMenubindingsed_9// "MenuBindingsEditor_MoveBindingUpDescrip"...
0x2afdf  call     string System.Design.SR::GetString(string name)
0x2afe4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x2afe9  ldtoken  System.Web.UI.Design.WebControls.MenuBindingsEditorForm
0x2afee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aff3  ldstr    aSortdownIco// "SortDown.ico"
0x2aff8  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x2affd  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x2b002  stloc.1
0x2b003  ldloc.1
0x2b004  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x2b009  ldarg.0
0x2b00a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingDownButton
0x2b00f  ldloc.1
0x2b010  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x2b015  ldarg.0
0x2b016  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingDownButton
0x2b01b  ldstr    aMenubindingsed_10// "MenuBindingsEditor_MoveBindingDownName"
0x2b020  call     string System.Design.SR::GetString(string name)
0x2b025  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x2b02a  ldarg.0
0x2b02b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_moveBindingDownButton
0x2b030  ldstr    aMenubindingsed_11// "MenuBindingsEditor_MoveBindingDownDescr"...
0x2b035  call     string System.Design.SR::GetString(string name)
0x2b03a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x2b03f  ldtoken  System.Web.UI.Design.WebControls.MenuBindingsEditorForm
0x2b044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2b049  ldstr    aDeleteIco// "Delete.ico"
0x2b04e  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x2b053  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x2b058  stloc.2
0x2b059  ldloc.2
0x2b05a  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x2b05f  ldarg.0
0x2b060  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_deleteBindingButton
0x2b065  ldloc.2
0x2b066  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x2b06b  ldarg.0
0x2b06c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_deleteBindingButton
0x2b071  ldstr    aMenubindingsed_12// "MenuBindingsEditor_DeleteBindingName"
0x2b076  call     string System.Design.SR::GetString(string name)
0x2b07b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x2b080  ldarg.0
0x2b081  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.MenuBindingsEditorForm::_deleteBindingButton
0x2b086  ldstr    aMenubindingsed_13// "MenuBindingsEditor_DeleteBindingDescrip"...
0x2b08b  call     string System.Design.SR::GetString(string name)
0x2b090  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x2b095  ldarg.0
0x2b096  ldnull
0x2b097  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_Icon(class [System.Drawing]System.Drawing.Icon)
0x2b09c  ret
```
