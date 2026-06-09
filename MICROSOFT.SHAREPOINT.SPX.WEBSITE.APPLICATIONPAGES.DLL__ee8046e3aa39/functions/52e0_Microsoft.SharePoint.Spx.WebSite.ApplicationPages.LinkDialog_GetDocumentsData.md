# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetDocumentsData

- ea: `0x52e0`
- end: `0x5375`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetDocumentsData`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5140`

## callees

- `0x52e0`

## pseudocode

```c

```

## disassembly

```asm
0x52e0  ldstr    aDocuments// "Documents"
0x52e5  newobj   instance void [System.Data]System.Data.DataTable::.ctor(string)
0x52ea  stloc.0
0x52eb  ldloc.0
0x52ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52f1  callvirt instance void [System.Data]System.Data.DataTable::set_Locale(class [mscorlib]System.Globalization.CultureInfo)
0x52f6  ldloc.0
0x52f7  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x52fc  ldstr    aUrl_1// "URL"
0x5301  callvirt instance class [System.Data]System.Data.DataColumn [System.Data]System.Data.DataColumnCollection::Add(string)
0x5306  pop
0x5307  ldloc.0
0x5308  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x530d  ldstr    aName_0// "Name"
0x5312  callvirt instance class [System.Data]System.Data.DataColumn [System.Data]System.Data.DataColumnCollection::Add(string)
0x5317  pop
0x5318  ldarg.0
0x5319  ldfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::fileManager
0x531e  ldc.i4.0
0x531f  ldc.i4.0
0x5320  ldloca.s 1
0x5322  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::GetDocumentsData(valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileOrderBy, valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.SortOrder, class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile[]&)
0x5327  ldc.i4.0
0x5328  stloc.2
0x5329  br.s     loc_535D
0x532b  ldloc.1
0x532c  ldloc.2
0x532d  ldelem.ref
0x532e  stloc.3
0x532f  ldloc.0
0x5330  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x5335  ldc.i4.2
0x5336  newarr   [mscorlib]System.Object
0x533b  stloc.s  4
0x533d  ldloc.s  4
0x533f  ldc.i4.0
0x5340  ldloc.3
0x5341  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ServerRelativeUrl()
0x5346  stelem.ref
0x5347  ldloc.s  4
0x5349  ldc.i4.1
0x534a  ldloc.3
0x534b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x5350  stelem.ref
0x5351  ldloc.s  4
0x5353  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::Add(object[])
0x5358  pop
0x5359  ldloc.2
0x535a  ldc.i4.1
0x535b  add
0x535c  stloc.2
0x535d  ldloc.2
0x535e  ldloc.1
0x535f  ldlen
0x5360  conv.i4
0x5361  blt.s    loc_532B
0x5363  ldloc.0
0x5364  callvirt instance class [System.Data]System.Data.DataView [System.Data]System.Data.DataTable::get_DefaultView()
0x5369  ldstr    aName_0// "Name"
0x536e  callvirt instance void [System.Data]System.Data.DataView::set_Sort(string)
0x5373  ldloc.0
0x5374  ret
```
