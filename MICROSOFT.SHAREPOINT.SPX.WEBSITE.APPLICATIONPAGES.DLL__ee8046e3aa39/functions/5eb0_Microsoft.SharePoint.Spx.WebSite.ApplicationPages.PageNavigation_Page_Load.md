# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::Page_Load

- ea: `0x5eb0`
- end: `0x5f1d`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::Page_Load`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5eb0`
- `0x5f30`

## string_xrefs

- `0x5efd`: `commitWindow();`

## pseudocode

```c

```

## disassembly

```asm
0x5eb0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x5eb5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x5eba  stloc.0
0x5ebb  ldarg.0
0x5ebc  call     instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x5ec1  brfalse.s loc_5F08
0x5ec3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ValidateFormDigest()
0x5ec8  pop
0x5ec9  ldloc.0
0x5eca  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x5ecf  stloc.1
0x5ed0  ldloc.1
0x5ed1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5ed6  ldarg.0
0x5ed7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::changedNavs
0x5edc  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x5ee1  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::UpdatePageNavigation(valuetype [mscorlib]System.Guid, string)
0x5ee6  ldloc.1
0x5ee7  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::Update()
0x5eec  ldarg.0
0x5eed  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x5ef2  ldarg.0
0x5ef3  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5ef8  ldstr    aClosewindow// "closeWindow"
0x5efd  ldstr    aCommitwindow// "commitWindow();"
0x5f02  ldc.i4.1
0x5f03  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string, bool)
0x5f08  ldloc.0
0x5f09  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigation [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Navigation()
0x5f0e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigation::get_GlobalNodes()
0x5f13  stloc.2
0x5f14  ldarg.0
0x5f15  ldloc.2
0x5f16  ldloc.0
0x5f17  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::PopulateControls(class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection navNodeCollection, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web)
0x5f1c  ret
```
