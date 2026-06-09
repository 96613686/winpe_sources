# Microsoft.ReportingServices.Rendering.HtmlRenderer.HybridHtmlSnippets::GetPageProperties

- ea: `0x38070`
- end: `0x38347`
- name: `Microsoft.ReportingServices.Rendering.HtmlRenderer.HybridHtmlSnippets::GetPageProperties`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x33c60`

## callees

- `0x8f10`
- `0x24b60`
- `0x24b70`
- `0x24b80`
- `0x24b90`
- `0x24ba0`
- `0x24bb0`
- `0x24bc0`
- `0x24bd0`
- `0x24be0`
- `0x24bf0`
- `0x24c00`
- `0x24c10`
- `0x24c20`
- `0x24c30`
- `0x24c40`
- `0x24c50`
- `0x24c60`
- `0x24c70`
- `0x24c80`
- `0x24c90`
- `0x24ca0`
- `0x24cb0`
- `0x24cc0`
- `0x24cd0`
- `0x24ce0`
- `0x24cf0`
- `0x24d00`
- `0x24d10`
- `0x24d20`
- `0x24d30`
- `0x24d40`
- `0x24d50`
- `0x24d60`
- `0x35bc0`

## string_xrefs

- `0x380a1`: `[PinHasScheduleReadyDataSources]`
- `0x380b2`: `[PinResultDialogNoScheduleReadyDataSources]`
- `0x38116`: `[PinNoDashboardsLinkText]`
- `0x3813e`: `[PinResultDialogSuccessLinkText]`
- `0x3821a`: `[PinDialogUpdateHourlyFrequency]`
- `0x3822e`: `[PinDialogUpdateDailyFrequency]`
- `0x38242`: `[PinDialogUpdateWeeklyFrequency]`
- `0x382e2`: `[PinSignInDialogWindowLinkText]`

## pseudocode

```c

```

## disassembly

```asm
0x38070  ldarg.0
0x38071  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider Microsoft.ReportingServices.Rendering.HtmlRenderer.HybridHtmlSnippets::_provider
0x38076  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider::GetAuthorizationUrl()
0x3807b  stloc.0
0x3807c  ldc.i4.4
0x3807d  call     string [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.TemplateHelper::GetTemplate(valuetype [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.Template)
0x38082  ldstr    aAuthurl// "[authUrl]"
0x38087  ldloc.0
0x38088  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3808d  ldstr    aPinresultdialo_5// "[PinResultDialogNoItemsToPin]"
0x38092  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogNoItemsToPin()
0x38097  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3809c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x380a1  ldstr    aPinhasschedule// "[PinHasScheduleReadyDataSources]"
0x380a6  ldarga.s 1
0x380a8  call     instance string [mscorlib]System.Boolean::ToString()
0x380ad  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x380b2  ldstr    aPinresultdialo_6// "[PinResultDialogNoScheduleReadyDataSour"...
0x380b7  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogNoScheduleReadyDataSources()
0x380bc  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x380c1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x380c6  ldstr    aPinresultdialo_7// "[PinResultDialogErrorTitle]"
0x380cb  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogErrorTitle()
0x380d0  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x380d5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x380da  ldstr    aSomethingwentw_0// "[SomethingWentWrong]"
0x380df  call     string Microsoft.Reporting.WebForms.Strings::get_SomethingWentWrong()
0x380e4  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x380e9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x380ee  ldstr    aPinresultdialo_8// "[PinResultDialogSuccessMessage]"
0x380f3  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogSuccessMessage()
0x380f8  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x380fd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38102  ldstr    aPinnodashboard_2// "[PinNoDashboards]"
0x38107  call     string Microsoft.Reporting.WebForms.Strings::get_PinNoDashboards()
0x3810c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38111  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38116  ldstr    aPinnodashboard_3// "[PinNoDashboardsLinkText]"
0x3811b  call     string Microsoft.Reporting.WebForms.Strings::get_PinNoDashboardsLinkText()
0x38120  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38125  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3812a  ldstr    aPinnodashboard_4// "[PinNoDashboardsTitle]"
0x3812f  call     string Microsoft.Reporting.WebForms.Strings::get_PinNoDashboardsTitle()
0x38134  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38139  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3813e  ldstr    aPinresultdialo_9// "[PinResultDialogSuccessLinkText]"
0x38143  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogSuccessLinkText()
0x38148  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3814d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38152  ldstr    aPinresultdialo_10// "[PinResultDialogSuccessTitle]"
0x38157  call     string Microsoft.Reporting.WebForms.Strings::get_PinResultDialogSuccessTitle()
0x3815c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38161  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38166  ldstr    aPindialogwindo_0// "[PinDialogWindowTitle]"
0x3816b  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogWindowTitle()
0x38170  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38175  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3817a  ldstr    aPindialogtitle_0// "[PinDialogTitle]"
0x3817f  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogTitle()
0x38184  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38189  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3818e  ldstr    aPindialogcance_0// "[PinDialogCancel]"
0x38193  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogCancel()
0x38198  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3819d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x381a2  ldstr    aPindialogclose_0// "[PinDialogClose]"
0x381a7  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogClose()
0x381ac  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x381b1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x381b6  ldstr    aPindialogpin_0// "[PinDialogPin]"
0x381bb  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogPin()
0x381c0  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x381c5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x381ca  ldstr    aPindialogselec_0// "[PinDialogSelectDashboard]"
0x381cf  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogSelectDashboard()
0x381d4  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x381d9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x381de  ldstr    aPindialoggroup_0// "[PinDialogGroupLabel]"
0x381e3  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogGroupLabel()
0x381e8  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x381ed  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x381f2  ldstr    aPindialogwhere_0// "[PinDialogWhereToPinTo]"
0x381f7  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogWhereToPinTo()
0x381fc  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38201  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38206  ldstr    aPindialogfrequ_0// "[PinDialogFrequency]"
0x3820b  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogFrequency()
0x38210  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38215  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3821a  ldstr    aPindialogupdat_2// "[PinDialogUpdateHourlyFrequency]"
0x3821f  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateHourlyFrequency()
0x38224  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38229  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3822e  ldstr    aPindialogupdat_3// "[PinDialogUpdateDailyFrequency]"
0x38233  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateDailyFrequency()
0x38238  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3823d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38242  ldstr    aPindialogupdat_4// "[PinDialogUpdateWeeklyFrequency]"
0x38247  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogUpdateWeeklyFrequency()
0x3824c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38251  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38256  ldstr    aPindialogloadi_1// "[PinDialogLoadingDashboards]"
0x3825b  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogLoadingDashboards()
0x38260  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38265  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3826a  ldstr    aPindialogloadi_2// "[PinDialogLoadingGroups]"
0x3826f  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogLoadingGroups()
0x38274  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38279  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3827e  ldstr    aPindialogmywor_0// "[PinDialogMyWorkspaceName]"
0x38283  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogMyWorkspaceName()
0x38288  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3828d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38292  ldstr    aPindialogpopup_0// "[PinDialogPopupBlocked]"
0x38297  call     string Microsoft.Reporting.WebForms.Strings::get_PinDialogPopupBlocked()
0x3829c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x382a1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x382a6  ldstr    aPinmasktitle_0// "[PinMaskTitle]"
0x382ab  call     string Microsoft.Reporting.WebForms.Strings::get_PinMaskTitle()
0x382b0  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x382b5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x382ba  ldstr    aPinhovertitle_0// "[PinHoverTitle]"
0x382bf  call     string Microsoft.Reporting.WebForms.Strings::get_PinHoverTitle()
0x382c4  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x382c9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x382ce  ldstr    aPinsignindialo_4// "[PinSignInDialogWindowTitle]"
0x382d3  call     string Microsoft.Reporting.WebForms.Strings::get_PinSignInDialogWindowTitle()
0x382d8  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x382dd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x382e2  ldstr    aPinsignindialo_5// "[PinSignInDialogWindowLinkText]"
0x382e7  call     string Microsoft.Reporting.WebForms.Strings::get_PinSignInDialogWindowLinkText()
0x382ec  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x382f1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x382f6  ldstr    aPinsignindialo_6// "[PinSignInDialogWindowText]"
0x382fb  call     string Microsoft.Reporting.WebForms.Strings::get_PinSignInDialogWindowText()
0x38300  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38305  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3830a  ldstr    aPinsignindialo_7// "[PinSignInDialogCancel]"
0x3830f  call     string Microsoft.Reporting.WebForms.Strings::get_PinSignInDialogCancel()
0x38314  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38319  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x3831e  ldstr    aPinsignindialo_8// "[PinSignInDialogSignIn]"
0x38323  call     string Microsoft.Reporting.WebForms.Strings::get_PinSignInDialogSignIn()
0x38328  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3832d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38332  ldstr    aCloseimage// "[closeImage]"
0x38337  ldstr    aMicrosoftRepor_102// "Microsoft.Reporting.WebForms.Icons.Clos"...
0x3833c  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x38341  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x38346  ret
```
