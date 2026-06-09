# System.Web.UI.WebControls.WebParts.BehaviorEditorPart::RenderContents

- ea: `0xf0440`
- end: `0xf0661`
- name: `System.Web.UI.WebControls.WebParts.BehaviorEditorPart::RenderContents`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x34fa0`
- `0x5f680`
- `0x61960`
- `0x77010`
- `0xf0440`
- `0xf77d0`

## string_xrefs

- `0xf0470`: `BehaviorEditorPart_TitleLink`
- `0xf047d`: `BehaviorEditorPart_TitleIconImageLink`
- `0xf048a`: `BehaviorEditorPart_CatalogIconImageLink`
- `0xf0497`: `BehaviorEditorPart_HelpLink`

## pseudocode

```c

```

## disassembly

```asm
0xf0440  ldarg.0
0xf0441  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xf0446  brfalse.s loc_F0454
0xf0448  ldarg.0
0xf0449  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0xf044e  ldarg.0
0xf044f  callvirt instance void System.Web.UI.Page::VerifyRenderingInServerForm(class System.Web.UI.Control control)
0xf0454  ldarg.0
0xf0455  callvirt instance void System.Web.UI.Control::EnsureChildControls()
0xf045a  ldc.i4.s 0xF
0xf045c  newarr   [mscorlib]System.String
0xf0461  dup
0xf0462  ldc.i4.0
0xf0463  ldstr    aBehavioreditor_6// "BehaviorEditorPart_Description"
0xf0468  call     string System.Web.SR::GetString(string name)
0xf046d  stelem.ref
0xf046e  dup
0xf046f  ldc.i4.1
0xf0470  ldstr    aBehavioreditor_7// "BehaviorEditorPart_TitleLink"
0xf0475  call     string System.Web.SR::GetString(string name)
0xf047a  stelem.ref
0xf047b  dup
0xf047c  ldc.i4.2
0xf047d  ldstr    aBehavioreditor_8// "BehaviorEditorPart_TitleIconImageLink"
0xf0482  call     string System.Web.SR::GetString(string name)
0xf0487  stelem.ref
0xf0488  dup
0xf0489  ldc.i4.3
0xf048a  ldstr    aBehavioreditor_9// "BehaviorEditorPart_CatalogIconImageLink"
0xf048f  call     string System.Web.SR::GetString(string name)
0xf0494  stelem.ref
0xf0495  dup
0xf0496  ldc.i4.4
0xf0497  ldstr    aBehavioreditor_10// "BehaviorEditorPart_HelpLink"
0xf049c  call     string System.Web.SR::GetString(string name)
0xf04a1  stelem.ref
0xf04a2  dup
0xf04a3  ldc.i4.5
0xf04a4  ldstr    aBehavioreditor_11// "BehaviorEditorPart_HelpMode"
0xf04a9  call     string System.Web.SR::GetString(string name)
0xf04ae  stelem.ref
0xf04af  dup
0xf04b0  ldc.i4.6
0xf04b1  ldstr    aBehavioreditor_12// "BehaviorEditorPart_ImportErrorMessage"
0xf04b6  call     string System.Web.SR::GetString(string name)
0xf04bb  stelem.ref
0xf04bc  dup
0xf04bd  ldc.i4.7
0xf04be  ldstr    aBehavioreditor_13// "BehaviorEditorPart_ExportMode"
0xf04c3  call     string System.Web.SR::GetString(string name)
0xf04c8  stelem.ref
0xf04c9  dup
0xf04ca  ldc.i4.8
0xf04cb  ldstr    aBehavioreditor_14// "BehaviorEditorPart_AuthorizationFilter"
0xf04d0  call     string System.Web.SR::GetString(string name)
0xf04d5  stelem.ref
0xf04d6  dup
0xf04d7  ldc.i4.s 9
0xf04d9  ldstr    aBehavioreditor_15// "BehaviorEditorPart_AllowClose"
0xf04de  call     string System.Web.SR::GetString(string name)
0xf04e3  stelem.ref
0xf04e4  dup
0xf04e5  ldc.i4.s 0xA
0xf04e7  ldstr    aBehavioreditor_16// "BehaviorEditorPart_AllowConnect"
0xf04ec  call     string System.Web.SR::GetString(string name)
0xf04f1  stelem.ref
0xf04f2  dup
0xf04f3  ldc.i4.s 0xB
0xf04f5  ldstr    aBehavioreditor_17// "BehaviorEditorPart_AllowEdit"
0xf04fa  call     string System.Web.SR::GetString(string name)
0xf04ff  stelem.ref
0xf0500  dup
0xf0501  ldc.i4.s 0xC
0xf0503  ldstr    aBehavioreditor_18// "BehaviorEditorPart_AllowHide"
0xf0508  call     string System.Web.SR::GetString(string name)
0xf050d  stelem.ref
0xf050e  dup
0xf050f  ldc.i4.s 0xD
0xf0511  ldstr    aBehavioreditor_19// "BehaviorEditorPart_AllowMinimize"
0xf0516  call     string System.Web.SR::GetString(string name)
0xf051b  stelem.ref
0xf051c  dup
0xf051d  ldc.i4.s 0xE
0xf051f  ldstr    aBehavioreditor_20// "BehaviorEditorPart_AllowZoneChange"
0xf0524  call     string System.Web.SR::GetString(string name)
0xf0529  stelem.ref
0xf052a  stloc.0
0xf052b  ldc.i4.s 0xF
0xf052d  newarr   System.Web.UI.WebControls.WebControl
0xf0532  dup
0xf0533  ldc.i4.0
0xf0534  ldarg.0
0xf0535  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_description
0xf053a  stelem.ref
0xf053b  dup
0xf053c  ldc.i4.1
0xf053d  ldarg.0
0xf053e  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_titleUrl
0xf0543  stelem.ref
0xf0544  dup
0xf0545  ldc.i4.2
0xf0546  ldarg.0
0xf0547  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_titleIconImageUrl
0xf054c  stelem.ref
0xf054d  dup
0xf054e  ldc.i4.3
0xf054f  ldarg.0
0xf0550  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_catalogIconImageUrl
0xf0555  stelem.ref
0xf0556  dup
0xf0557  ldc.i4.4
0xf0558  ldarg.0
0xf0559  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_helpUrl
0xf055e  stelem.ref
0xf055f  dup
0xf0560  ldc.i4.5
0xf0561  ldarg.0
0xf0562  ldfld    class System.Web.UI.WebControls.DropDownList System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_helpMode
0xf0567  stelem.ref
0xf0568  dup
0xf0569  ldc.i4.6
0xf056a  ldarg.0
0xf056b  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_importErrorMessage
0xf0570  stelem.ref
0xf0571  dup
0xf0572  ldc.i4.7
0xf0573  ldarg.0
0xf0574  ldfld    class System.Web.UI.WebControls.DropDownList System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_exportMode
0xf0579  stelem.ref
0xf057a  dup
0xf057b  ldc.i4.8
0xf057c  ldarg.0
0xf057d  ldfld    class System.Web.UI.WebControls.TextBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_authorizationFilter
0xf0582  stelem.ref
0xf0583  dup
0xf0584  ldc.i4.s 9
0xf0586  ldarg.0
0xf0587  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowClose
0xf058c  stelem.ref
0xf058d  dup
0xf058e  ldc.i4.s 0xA
0xf0590  ldarg.0
0xf0591  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowConnect
0xf0596  stelem.ref
0xf0597  dup
0xf0598  ldc.i4.s 0xB
0xf059a  ldarg.0
0xf059b  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowEdit
0xf05a0  stelem.ref
0xf05a1  dup
0xf05a2  ldc.i4.s 0xC
0xf05a4  ldarg.0
0xf05a5  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowHide
0xf05aa  stelem.ref
0xf05ab  dup
0xf05ac  ldc.i4.s 0xD
0xf05ae  ldarg.0
0xf05af  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowMinimize
0xf05b4  stelem.ref
0xf05b5  dup
0xf05b6  ldc.i4.s 0xE
0xf05b8  ldarg.0
0xf05b9  ldfld    class System.Web.UI.WebControls.CheckBox System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowZoneChange
0xf05be  stelem.ref
0xf05bf  stloc.1
0xf05c0  ldc.i4.s 0xF
0xf05c2  newarr   [mscorlib]System.String
0xf05c7  dup
0xf05c8  ldc.i4.0
0xf05c9  ldarg.0
0xf05ca  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_descriptionErrorMessage
0xf05cf  stelem.ref
0xf05d0  dup
0xf05d1  ldc.i4.1
0xf05d2  ldarg.0
0xf05d3  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_titleUrlErrorMessage
0xf05d8  stelem.ref
0xf05d9  dup
0xf05da  ldc.i4.2
0xf05db  ldarg.0
0xf05dc  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_titleIconImageUrlErrorMessage
0xf05e1  stelem.ref
0xf05e2  dup
0xf05e3  ldc.i4.3
0xf05e4  ldarg.0
0xf05e5  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_catalogIconImageUrlErrorMessage
0xf05ea  stelem.ref
0xf05eb  dup
0xf05ec  ldc.i4.4
0xf05ed  ldarg.0
0xf05ee  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_helpUrlErrorMessage
0xf05f3  stelem.ref
0xf05f4  dup
0xf05f5  ldc.i4.5
0xf05f6  ldarg.0
0xf05f7  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_helpModeErrorMessage
0xf05fc  stelem.ref
0xf05fd  dup
0xf05fe  ldc.i4.6
0xf05ff  ldarg.0
0xf0600  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_importErrorMessageErrorMessage
0xf0605  stelem.ref
0xf0606  dup
0xf0607  ldc.i4.7
0xf0608  ldarg.0
0xf0609  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_exportModeErrorMessage
0xf060e  stelem.ref
0xf060f  dup
0xf0610  ldc.i4.8
0xf0611  ldarg.0
0xf0612  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_authorizationFilterErrorMessage
0xf0617  stelem.ref
0xf0618  dup
0xf0619  ldc.i4.s 9
0xf061b  ldarg.0
0xf061c  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowCloseErrorMessage
0xf0621  stelem.ref
0xf0622  dup
0xf0623  ldc.i4.s 0xA
0xf0625  ldarg.0
0xf0626  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowConnectErrorMessage
0xf062b  stelem.ref
0xf062c  dup
0xf062d  ldc.i4.s 0xB
0xf062f  ldarg.0
0xf0630  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowEditErrorMessage
0xf0635  stelem.ref
0xf0636  dup
0xf0637  ldc.i4.s 0xC
0xf0639  ldarg.0
0xf063a  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowHideErrorMessage
0xf063f  stelem.ref
0xf0640  dup
0xf0641  ldc.i4.s 0xD
0xf0643  ldarg.0
0xf0644  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowMinimizeErrorMessage
0xf0649  stelem.ref
0xf064a  dup
0xf064b  ldc.i4.s 0xE
0xf064d  ldarg.0
0xf064e  ldfld    string System.Web.UI.WebControls.WebParts.BehaviorEditorPart::_allowZoneChangeErrorMessage
0xf0653  stelem.ref
0xf0654  stloc.2
0xf0655  ldarg.0
0xf0656  ldarg.1
0xf0657  ldloc.0
0xf0658  ldnull
0xf0659  ldloc.1
0xf065a  ldloc.2
0xf065b  call     instance void System.Web.UI.WebControls.WebParts.EditorPart::RenderPropertyEditors(class System.Web.UI.HtmlTextWriter writer, string[] propertyDisplayNames, string[] propertyDescriptions, class System.Web.UI.WebControls.WebControl[] propertyEditors, string[] errorMessages)
0xf0660  ret
```
