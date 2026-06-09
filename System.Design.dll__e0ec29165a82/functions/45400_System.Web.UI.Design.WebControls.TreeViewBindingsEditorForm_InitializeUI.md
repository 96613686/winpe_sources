# System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::InitializeUI

- ea: `0x45400`
- end: `0x455c2`
- name: `System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::InitializeUI`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x44710`

## callees

- `0x8ef40`
- `0xef300`

## string_xrefs

- `0x4556e`: `Delete.ico`
- `0x454ea`: `TreeViewBindingsEditor_MoveBindingUpName`
- `0x454ff`: `TreeViewBindingsEditor_MoveBindingUpDescription`
- `0x45540`: `TreeViewBindingsEditor_MoveBindingDownName`
- `0x45555`: `TreeViewBindingsEditor_MoveBindingDownDescription`
- `0x45596`: `TreeViewBindingsEditor_DeleteBindingName`
- `0x455ab`: `TreeViewBindingsEditor_DeleteBindingDescription`

## pseudocode

```c

```

## disassembly

```asm
0x45400  ldarg.0
0x45401  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_bindingsLabel
0x45406  ldstr    aTreeviewbindin_1// "TreeViewBindingsEditor_Bindings"
0x4540b  call     string System.Design.SR::GetString(string name)
0x45410  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x45415  ldarg.0
0x45416  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_schemaLabel
0x4541b  ldstr    aTreeviewbindin_2// "TreeViewBindingsEditor_Schema"
0x45420  call     string System.Design.SR::GetString(string name)
0x45425  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4542a  ldarg.0
0x4542b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_okButton
0x45430  ldstr    aTreeviewbindin_3// "TreeViewBindingsEditor_OK"
0x45435  call     string System.Design.SR::GetString(string name)
0x4543a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4543f  ldarg.0
0x45440  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_applyButton
0x45445  ldstr    aTreeviewbindin_4// "TreeViewBindingsEditor_Apply"
0x4544a  call     string System.Design.SR::GetString(string name)
0x4544f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x45454  ldarg.0
0x45455  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_cancelButton
0x4545a  ldstr    aTreeviewbindin_5// "TreeViewBindingsEditor_Cancel"
0x4545f  call     string System.Design.SR::GetString(string name)
0x45464  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x45469  ldarg.0
0x4546a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_propertiesLabel
0x4546f  ldstr    aTreeviewbindin_6// "TreeViewBindingsEditor_BindingPropertie"...
0x45474  call     string System.Design.SR::GetString(string name)
0x45479  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x4547e  ldarg.0
0x4547f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_autogenerateBindingsCheckBox
0x45484  ldstr    aTreeviewbindin// "TreeViewBindingsEditor_AutoGenerateBind"...
0x45489  call     string System.Design.SR::GetString(string name)
0x4548e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x45493  ldarg.0
0x45494  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_addBindingButton
0x45499  ldstr    aTreeviewbindin_7// "TreeViewBindingsEditor_AddBinding"
0x4549e  call     string System.Design.SR::GetString(string name)
0x454a3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x454a8  ldarg.0
0x454a9  ldstr    aTreeviewbindin_8// "TreeViewBindingsEditor_Title"
0x454ae  call     string System.Design.SR::GetString(string name)
0x454b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x454b8  ldtoken  System.Web.UI.Design.WebControls.TreeViewBindingsEditor
0x454bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x454c2  ldstr    aSortupIco// "SortUp.ico"
0x454c7  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x454cc  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x454d1  stloc.0
0x454d2  ldloc.0
0x454d3  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x454d8  ldarg.0
0x454d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingUpButton
0x454de  ldloc.0
0x454df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x454e4  ldarg.0
0x454e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingUpButton
0x454ea  ldstr    aTreeviewbindin_9// "TreeViewBindingsEditor_MoveBindingUpNam"...
0x454ef  call     string System.Design.SR::GetString(string name)
0x454f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x454f9  ldarg.0
0x454fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingUpButton
0x454ff  ldstr    aTreeviewbindin_10// "TreeViewBindingsEditor_MoveBindingUpDes"...
0x45504  call     string System.Design.SR::GetString(string name)
0x45509  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x4550e  ldtoken  System.Web.UI.Design.WebControls.TreeViewBindingsEditor
0x45513  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45518  ldstr    aSortdownIco// "SortDown.ico"
0x4551d  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x45522  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x45527  stloc.1
0x45528  ldloc.1
0x45529  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x4552e  ldarg.0
0x4552f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingDownButton
0x45534  ldloc.1
0x45535  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x4553a  ldarg.0
0x4553b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingDownButton
0x45540  ldstr    aTreeviewbindin_11// "TreeViewBindingsEditor_MoveBindingDownN"...
0x45545  call     string System.Design.SR::GetString(string name)
0x4554a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x4554f  ldarg.0
0x45550  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_moveBindingDownButton
0x45555  ldstr    aTreeviewbindin_12// "TreeViewBindingsEditor_MoveBindingDownD"...
0x4555a  call     string System.Design.SR::GetString(string name)
0x4555f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x45564  ldtoken  System.Web.UI.Design.WebControls.TreeViewBindingsEditor
0x45569  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4556e  ldstr    aDeleteIco// "Delete.ico"
0x45573  call     class [System.Drawing]System.Drawing.Icon System.Drawing.BitmapSelector::CreateIcon(class [mscorlib]System.Type type, string originalName)
0x45578  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x4557d  stloc.2
0x4557e  ldloc.2
0x4557f  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent()
0x45584  ldarg.0
0x45585  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_deleteBindingButton
0x4558a  ldloc.2
0x4558b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0x45590  ldarg.0
0x45591  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_deleteBindingButton
0x45596  ldstr    aTreeviewbindin_13// "TreeViewBindingsEditor_DeleteBindingNam"...
0x4559b  call     string System.Design.SR::GetString(string name)
0x455a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x455a5  ldarg.0
0x455a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.TreeViewBindingsEditorForm::_deleteBindingButton
0x455ab  ldstr    aTreeviewbindin_14// "TreeViewBindingsEditor_DeleteBindingDes"...
0x455b0  call     string System.Design.SR::GetString(string name)
0x455b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x455ba  ldarg.0
0x455bb  ldnull
0x455bc  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_Icon(class [System.Drawing]System.Drawing.Icon)
0x455c1  ret
```
