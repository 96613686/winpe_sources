# Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::CreateChildControls

- ea: `0x8270`
- end: `0x8d70`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::CreateChildControls`
- size: `2816`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7bc0`
- `0x8020`
- `0x8270`

## pseudocode

```c

```

## disassembly

```asm
0x8270  newobj   instance void [System.Web]System.Web.UI.WebControls.Table::.ctor()
0x8275  stloc.0
0x8276  newobj   instance void [System.Web]System.Web.UI.WebControls.TableRow::.ctor()
0x827b  stloc.1
0x827c  newobj   instance void [System.Web]System.Web.UI.WebControls.TableCell::.ctor()
0x8281  stloc.2
0x8282  ldloc.2
0x8283  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x8288  ldc.i4.s 0x1E
0x828a  ldstr    a4px// "4px"
0x828f  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x8294  ldloc.1
0x8295  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0x829a  ldloc.2
0x829b  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableCellCollection::Add(class [System.Web]System.Web.UI.WebControls.TableCell)
0x82a0  pop
0x82a1  ldloc.0
0x82a2  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0x82a7  ldc.i4.s 0xD
0x82a9  ldstr    a100// "100%"
0x82ae  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x82b3  ldloc.0
0x82b4  callvirt instance class [System.Web]System.Web.UI.WebControls.TableRowCollection [System.Web]System.Web.UI.WebControls.Table::get_Rows()
0x82b9  ldloc.1
0x82ba  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableRowCollection::Add(class [System.Web]System.Web.UI.WebControls.TableRow)
0x82bf  pop
0x82c0  ldarg.0
0x82c1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x82c6  ldloc.0
0x82c7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x82cc  ldarg.0
0x82cd  ldstr    aDiv// "div"
0x82d2  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x82d7  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x82dc  ldarg.0
0x82dd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x82e2  ldc.i4.0
0x82e3  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x82e8  ldarg.0
0x82e9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x82ee  ldc.i4.0
0x82ef  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x82f4  ldloc.2
0x82f5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x82fa  ldarg.0
0x82fb  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x8300  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8305  ldarg.0
0x8306  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x830b  stfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::responseMsg
0x8310  ldarg.0
0x8311  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::responseMsg
0x8316  ldc.i4.0
0x8317  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x831c  ldarg.0
0x831d  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::responseMsg
0x8322  ldstr    aContactuscontr_1// "ContactUsControl.EmailSent_Msg"
0x8327  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x832c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string)
0x8331  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x8336  ldarg.0
0x8337  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x833c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8341  ldarg.0
0x8342  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::responseMsg
0x8347  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x834c  ldarg.0
0x834d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x8352  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8357  ldstr    aDivStyle// "<div style=\""
0x835c  ldstr    aContactuscontr_2// "ContactUsControl.BackBtnDiv_Style"
0x8361  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x8366  ldstr    asc_23FA4// "\">"
0x836b  call     string [mscorlib]System.String::Concat(string, string, string)
0x8370  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x8375  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x837a  newobj   instance void [System.Web]System.Web.UI.WebControls.Button::.ctor()
0x837f  stloc.3
0x8380  ldloc.3
0x8381  ldstr    aBack// "Back"
0x8386  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x838b  ldloc.3
0x838c  ldstr    aContactuscontr_3// "ContactUsControl.BackBtn.Text"
0x8391  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x8396  callvirt instance void [System.Web]System.Web.UI.WebControls.Button::set_Text(string)
0x839b  ldloc.3
0x839c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x83a1  ldstr    aStyle_0// "style"
0x83a6  ldstr    aContactuscontr_4// "ContactUsControl.BackBtn_Style"
0x83ab  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x83b0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x83b5  ldloc.3
0x83b6  ldc.i4.0
0x83b7  callvirt instance void [System.Web]System.Web.UI.WebControls.Button::set_CausesValidation(bool)
0x83bc  ldloc.3
0x83bd  ldc.i4.0
0x83be  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x83c3  ldarg.0
0x83c4  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x83c9  brtrue.s loc_83F0
0x83cb  ldloc.3
0x83cc  ldstr    aVarMarkerThank// "var marker = '#ThankYou'; var form = wi"...
0x83d1  ldarg.0
0x83d2  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x83d7  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlForm [System.Web]System.Web.UI.Page::get_Form()
0x83dc  callvirt instance string [System.Web]System.Web.UI.Control::get_UniqueID()
0x83e1  ldstr    aIfFormNullForm// "'); if ((form != null) && (form.action."...
0x83e6  call     string [mscorlib]System.String::Concat(string, string, string)
0x83eb  callvirt instance void [System.Web]System.Web.UI.WebControls.Button::set_OnClientClick(string)
0x83f0  ldarg.0
0x83f1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x83f6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x83fb  ldloc.3
0x83fc  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8401  ldarg.0
0x8402  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::thankYouContainer
0x8407  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x840c  ldstr    aDiv_0// "</div>"
0x8411  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x8416  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x841b  ldarg.0
0x841c  ldstr    aDiv// "div"
0x8421  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x8426  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::submitContainer
0x842b  ldarg.0
0x842c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::submitContainer
0x8431  ldc.i4.0
0x8432  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x8437  ldloc.2
0x8438  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x843d  ldarg.0
0x843e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::submitContainer
0x8443  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8448  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x844d  stloc.s  4
0x844f  ldstr    aLabel// "label"
0x8454  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x8459  stloc.s  5
0x845b  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x8460  stloc.s  6
0x8462  ldloc.s  6
0x8464  ldc.i4.0
0x8465  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x846a  ldloc.s  6
0x846c  ldstr    aContactuscontr_5// "ContactUsControl.FirstName_Label"
0x8471  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x8476  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string)
0x847b  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x8480  ldloc.s  5
0x8482  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8487  ldloc.s  6
0x8489  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x848e  ldloc.s  4
0x8490  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8495  ldloc.s  5
0x8497  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x849c  ldarg.0
0x849d  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x84a2  brtrue.s loc_8503
0x84a4  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x84a9  stloc.s  7
0x84ab  ldloc.s  7
0x84ad  ldstr    aFirstname// "firstName"
0x84b2  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string)
0x84b7  ldloc.s  7
0x84b9  ldarg.0
0x84ba  callvirt instance string [System.Web]System.Web.UI.Control::get_UniqueID()
0x84bf  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string)
0x84c4  ldloc.s  7
0x84c6  ldc.i4.0
0x84c7  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_Display(valuetype [System.Web]System.Web.UI.WebControls.ValidatorDisplay)
0x84cc  ldloc.s  7
0x84ce  ldstr    aContactuscontr_6// "ContactUsControl.ErrorSummary.FirstName"...
0x84d3  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x84d8  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string)
0x84dd  ldloc.s  7
0x84df  ldc.i4.1
0x84e0  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_SetFocusOnError(bool)
0x84e5  ldloc.s  7
0x84e7  ldc.i4.1
0x84e8  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_EnableClientScript(bool)
0x84ed  ldloc.s  7
0x84ef  ldc.i4.0
0x84f0  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x84f5  ldloc.s  4
0x84f7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x84fc  ldloc.s  7
0x84fe  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8503  ldloc.s  4
0x8505  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x850a  ldstr    aBr// "<br />"
0x850f  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x8514  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8519  ldarg.0
0x851a  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x851f  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x8524  ldarg.0
0x8525  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x852a  ldstr    aFirstname// "firstName"
0x852f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8534  ldarg.0
0x8535  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x853a  ldc.i4   0xC8
0x853f  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_MaxLength(int32)
0x8544  ldarg.0
0x8545  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x854a  ldc.r8   100.0
0x8553  ldc.i4.7
0x8554  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(float64, valuetype [System.Web]System.Web.UI.WebControls.UnitType)
0x8559  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Width(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x855e  ldarg.0
0x855f  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x8564  ldc.i4.0
0x8565  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x856a  ldloc.s  4
0x856c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8571  ldarg.0
0x8572  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::firstName
0x8577  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x857c  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x8581  stloc.s  8
0x8583  ldstr    aLabel// "label"
0x8588  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x858d  stloc.s  9
0x858f  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x8594  stloc.s  0xA
0x8596  ldloc.s  0xA
0x8598  ldc.i4.0
0x8599  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x859e  ldloc.s  0xA
0x85a0  ldstr    aContactuscontr_7// "ContactUsControl.LastName_Label"
0x85a5  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x85aa  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::NoEncode(string)
0x85af  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x85b4  ldloc.s  9
0x85b6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x85bb  ldloc.s  0xA
0x85bd  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x85c2  ldloc.s  8
0x85c4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x85c9  ldloc.s  9
0x85cb  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x85d0  ldarg.0
0x85d1  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x85d6  brtrue.s loc_8637
0x85d8  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x85dd  stloc.s  0xB
0x85df  ldloc.s  0xB
0x85e1  ldstr    aLastname// "lastName"
0x85e6  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string)
0x85eb  ldloc.s  0xB
0x85ed  ldarg.0
0x85ee  callvirt instance string [System.Web]System.Web.UI.Control::get_UniqueID()
0x85f3  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string)
0x85f8  ldloc.s  0xB
0x85fa  ldc.i4.0
0x85fb  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_Display(valuetype [System.Web]System.Web.UI.WebControls.ValidatorDisplay)
0x8600  ldloc.s  0xB
0x8602  ldstr    aContactuscontr_8// "ContactUsControl.ErrorSummary.LastNameF"...
0x8607  call     string Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::GetString(string resName)
0x860c  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string)
0x8611  ldloc.s  0xB
0x8613  ldc.i4.1
0x8614  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_SetFocusOnError(bool)
0x8619  ldloc.s  0xB
0x861b  ldc.i4.1
0x861c  callvirt instance void [System.Web]System.Web.UI.WebControls.BaseValidator::set_EnableClientScript(bool)
0x8621  ldloc.s  0xB
0x8623  ldc.i4.0
0x8624  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
0x8629  ldloc.s  8
0x862b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x8630  ldloc.s  0xB
0x8632  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x8637  ldloc.s  8
0x8639  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x863e  ldstr    aBr// "<br />"
0x8643  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x8648  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x864d  ldarg.0
0x864e  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x8653  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x8658  ldarg.0
0x8659  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x865e  ldstr    aLastname// "lastName"
0x8663  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8668  ldarg.0
0x8669  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x866e  ldc.i4   0xC8
0x8673  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_MaxLength(int32)
0x8678  ldarg.0
0x8679  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x867e  ldc.r8   100.0
0x8687  ldc.i4.7
0x8688  newobj   instance void [System.Web]System.Web.UI.WebControls.Unit::.ctor(float64, valuetype [System.Web]System.Web.UI.WebControls.UnitType)
0x868d  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Width(valuetype [System.Web]System.Web.UI.WebControls.Unit)
0x8692  ldarg.0
0x8693  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Spx.WebSite.Controls.ContactUsControl::lastName
0x8698  ldc.i4.0
0x8699  callvirt instance void [System.Web]System.Web.UI.Control::set_EnableViewState(bool)
  ... truncated ...
```
