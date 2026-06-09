# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetPagesData

- ea: `0x51f0`
- end: `0x52d5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::GetPagesData`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5140`

## callees

- `0x51f0`

## pseudocode

```c

```

## disassembly

```asm
0x51f0  ldstr    aPages// "Pages"
0x51f5  newobj   instance void [System.Data]System.Data.DataTable::.ctor(string)
0x51fa  stloc.0
0x51fb  ldloc.0
0x51fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5201  callvirt instance void [System.Data]System.Data.DataTable::set_Locale(class [mscorlib]System.Globalization.CultureInfo)
0x5206  ldloc.0
0x5207  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x520c  ldstr    aUrl_1// "URL"
0x5211  callvirt instance class [System.Data]System.Data.DataColumn [System.Data]System.Data.DataColumnCollection::Add(string)
0x5216  pop
0x5217  ldloc.0
0x5218  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x521d  ldstr    aTitle// "Title"
0x5222  callvirt instance class [System.Data]System.Data.DataColumn [System.Data]System.Data.DataColumnCollection::Add(string)
0x5227  pop
0x5228  ldloc.0
0x5229  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x522e  ldstr    aName_0// "Name"
0x5233  callvirt instance class [System.Data]System.Data.DataColumn [System.Data]System.Data.DataColumnCollection::Add(string)
0x5238  pop
0x5239  ldarg.0
0x523a  ldfld    class [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager Microsoft.SharePoint.Spx.WebSite.ApplicationPages.LinkDialog::fileManager
0x523f  ldc.i4.6
0x5240  ldc.i4.0
0x5241  ldloca.s 1
0x5243  callvirt instance void [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::GetOrderedArray(valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileOrderBy, valuetype [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.SortOrder, class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile[]&)
0x5248  ldsfld   string [mscorlib]System.String::Empty
0x524d  stloc.2
0x524e  ldc.i4.0
0x524f  stloc.3
0x5250  br.s     loc_52BD
0x5252  ldloc.1
0x5253  ldloc.3
0x5254  ldelem.ref
0x5255  stloc.s  4
0x5257  ldloc.s  4
0x5259  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x525e  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x5263  ldstr    aAspx// ".aspx"
0x5268  ldc.i4.5
0x5269  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x526e  brfalse.s loc_52B9
0x5270  ldloc.s  4
0x5272  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Title()
0x5277  brfalse.s loc_5282
0x5279  ldloc.s  4
0x527b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Title()
0x5280  br.s     loc_5287
0x5282  ldsfld   string [mscorlib]System.String::Empty
0x5287  stloc.2
0x5288  ldloc.0
0x5289  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x528e  ldc.i4.3
0x528f  newarr   [mscorlib]System.Object
0x5294  stloc.s  5
0x5296  ldloc.s  5
0x5298  ldc.i4.0
0x5299  ldloc.s  4
0x529b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ServerRelativeUrl()
0x52a0  stelem.ref
0x52a1  ldloc.s  5
0x52a3  ldc.i4.1
0x52a4  ldloc.2
0x52a5  stelem.ref
0x52a6  ldloc.s  5
0x52a8  ldc.i4.2
0x52a9  ldloc.s  4
0x52ab  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Name()
0x52b0  stelem.ref
0x52b1  ldloc.s  5
0x52b3  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataRowCollection::Add(object[])
0x52b8  pop
0x52b9  ldloc.3
0x52ba  ldc.i4.1
0x52bb  add
0x52bc  stloc.3
0x52bd  ldloc.3
0x52be  ldloc.1
0x52bf  ldlen
0x52c0  conv.i4
0x52c1  blt.s    loc_5252
0x52c3  ldloc.0
0x52c4  callvirt instance class [System.Data]System.Data.DataView [System.Data]System.Data.DataTable::get_DefaultView()
0x52c9  ldstr    aTitle// "Title"
0x52ce  callvirt instance void [System.Data]System.Data.DataView::set_Sort(string)
0x52d3  ldloc.0
0x52d4  ret
```
