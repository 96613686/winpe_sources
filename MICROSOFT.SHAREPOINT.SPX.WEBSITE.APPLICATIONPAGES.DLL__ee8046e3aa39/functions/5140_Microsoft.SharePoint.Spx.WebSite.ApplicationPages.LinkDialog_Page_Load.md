# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::Page_Load

- ea: `0x5140`
- end: `0x51e5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::Page_Load`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x5140`
- `0x51f0`
- `0x52e0`

## pseudocode

```c

```

## disassembly

```asm
0x5140  ldarg.0
0x5141  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x5146  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x514b  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::web
0x5150  ldarg.0
0x5151  ldarg.0
0x5152  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::web
0x5157  newobj   instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x515c  stfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::fileManager
0x5161  ldarg.0
0x5162  call     instance class [System.Data]System.Data.DataTable Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetPagesData()
0x5167  stloc.0
0x5168  ldloc.0
0x5169  callvirt instance class [System.Data]System.Data.DataView [System.Data]System.Data.DataTable::get_DefaultView()
0x516e  stloc.1
0x516f  ldarg.0
0x5170  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::pageRepeater
0x5175  ldloc.1
0x5176  callvirt instance void [System.Web]System.Web.UI.WebControls.Repeater::set_DataSource(object)
0x517b  ldarg.0
0x517c  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::pageRepeater
0x5181  callvirt instance void [System.Web]System.Web.UI.Control::DataBind()
0x5186  ldarg.0
0x5187  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::pageRepeater
0x518c  ldc.i4.1
0x518d  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x5192  ldarg.0
0x5193  call     instance class [System.Data]System.Data.DataTable Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetDocumentsData()
0x5198  stloc.2
0x5199  ldloc.2
0x519a  callvirt instance class [System.Data]System.Data.DataView [System.Data]System.Data.DataTable::get_DefaultView()
0x519f  stloc.3
0x51a0  ldloc.3
0x51a1  callvirt instance int32 [System.Data]System.Data.DataView::get_Count()
0x51a6  ldc.i4.0
0x51a7  ble.s    loc_51CD
0x51a9  ldarg.0
0x51aa  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::docRepeater
0x51af  ldloc.3
0x51b0  callvirt instance void [System.Web]System.Web.UI.WebControls.Repeater::set_DataSource(object)
0x51b5  ldarg.0
0x51b6  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::docRepeater
0x51bb  callvirt instance void [System.Web]System.Web.UI.Control::DataBind()
0x51c0  ldarg.0
0x51c1  ldfld    class [System.Web]System.Web.UI.WebControls.Repeater Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::docRepeater
0x51c6  ldc.i4.1
0x51c7  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x51cc  ret
0x51cd  ldarg.0
0x51ce  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::messageNoDoc
0x51d3  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x51d8  ldc.i4.s 0x12
0x51da  ldstr    aBlock// "block"
0x51df  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0x51e4  ret
```
