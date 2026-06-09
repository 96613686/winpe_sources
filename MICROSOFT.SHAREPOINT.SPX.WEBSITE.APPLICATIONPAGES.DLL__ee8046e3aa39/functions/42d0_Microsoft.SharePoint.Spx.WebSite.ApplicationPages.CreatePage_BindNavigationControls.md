# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindNavigationControls

- ea: `0x42d0`
- end: `0x43d5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::BindNavigationControls`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3e40`

## callees

- `0x42d0`

## pseudocode

```c

```

## disassembly

```asm
0x42d0  ldarg.0
0x42d1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::parentSelectBox
0x42d6  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x42db  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Clear()
0x42e0  ldarg.0
0x42e1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::parentSelectBox
0x42e6  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x42eb  ldstr    aCpRootnode// "CP_RootNode"
0x42f0  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x42f5  ldstr    a0// "0"
0x42fa  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x42ff  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x4304  ldstr    aNew// "new"
0x4309  stloc.0
0x430a  ldstr    aNew// "new"
0x430f  stloc.1
0x4310  ldc.i4.m1
0x4311  stloc.2
0x4312  ldarg.0
0x4313  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::web
0x4318  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigation [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Navigation()
0x431d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigation::get_GlobalNodes()
0x4322  stloc.3
0x4323  ldloc.3
0x4324  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x4329  stloc.s  6
0x432b  br.s     loc_4379
0x432d  ldloc.s  6
0x432f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4334  castclass [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode
0x4339  stloc.s  4
0x433b  ldloc.s  4
0x433d  call     bool [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::IsNavNodeVisible(class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode)
0x4342  brfalse.s loc_4379
0x4344  ldloc.s  4
0x4346  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x434b  ldloc.s  4
0x434d  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x4352  stloc.s  7
0x4354  ldloca.s 7
0x4356  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x435b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4360  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x4365  stloc.s  5
0x4367  ldarg.0
0x4368  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::parentSelectBox
0x436d  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x4372  ldloc.s  5
0x4374  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x4379  ldloc.s  6
0x437b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4380  brtrue.s loc_432D
0x4382  leave.s  loc_4399
0x4384  ldloc.s  6
0x4386  isinst   [mscorlib]System.IDisposable
0x438b  stloc.s  8
0x438d  ldloc.s  8
0x438f  brfalse.s loc_4398
0x4391  ldloc.s  8
0x4393  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4398  endfinally
0x4399  ldarg.0
0x439a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentNavPositionOldParent
0x439f  ldloc.0
0x43a0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x43a5  ldarg.0
0x43a6  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentNavPositionOldRank
0x43ab  ldloca.s 2
0x43ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43b2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x43b7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x43bc  ldarg.0
0x43bd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::parentSelectBox
0x43c2  ldloc.0
0x43c3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlSelect::set_Value(string)
0x43c8  ldarg.0
0x43c9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::currentNavId
0x43ce  ldloc.1
0x43cf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x43d4  ret
```
