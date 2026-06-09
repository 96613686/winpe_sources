# Microsoft.SharePoint.SPList::PopulateEcbQuery

- ea: `0x34ed40`
- end: `0x34f063`
- name: `Microsoft.SharePoint.SPList::PopulateEcbQuery`
- size: `803`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x34e9a0`
- `0x34eab0`

## callees

- `0x342f00`
- `0x343230`
- `0x344680`
- `0x34ed40`
- `0x34f070`
- `0x507700`
- `0x575160`
- `0x575190`
- `0x5751a0`
- `0x789af0`

## string_xrefs

- `0x34ed70`: `LinkFilename`
- `0x34ed86`: `LinkFilename`
- `0x34ee1f`: `LinkFilename`
- `0x34ee97`: `LinkFilename`
- `0x34ed92`: `LinkDiscussionTitle`
- `0x34ed9f`: `LinkDiscussionTitle`
- `0x34ee2f`: `LinkDiscussionTitle`
- `0x34eed0`: `LinkDiscussionTitle`
- `0x34eddd`: `LinkTitle`
- `0x34edea`: `LinkTitle`
- `0x34ee6f`: `LinkTitle`
- `0x34ef5d`: `LinkTitle`
- `0x34ee0f`: `LinkToItem="TRUE" `
- `0x34ee80`: `LinkToItem="TRUE" `
- `0x34eeaf`: `LinkFilename2`
- `0x34eec5`: `LinkFilename2`
- `0x34eee8`: `LinkDiscussionTitle2`
- `0x34eef5`: `LinkDiscussionTitle2`
- `0x34ef75`: `LinkTitle2`
- `0x34ef82`: `LinkTitle2`
- `0x34efb7`: ` ListItemMenu="TRUE" LinkToItem="TRUE"`
- `0x34f00a`: `<FieldRef Name="FileLeafRef" Explicit="TRUE"/><FieldRef Name="FSObjType" Explicit="TRUE"/><FieldRef Name="Created_x0020_Date" Explicit="TRUE"/><FieldRef Name="FileRef" Explicit="TRUE"/><FieldRef Name="FileDirRef" Explicit="TRUE"/><FieldRef Name="ID" Explicit="TRUE"/><FieldRef Name="ServerUrl" Explicit="TRUE"/><FieldRef Name="HTML_x0020_File_x0020_Type" Explicit="TRUE"/><FieldRef Name="File_x0020_Type" Explicit="TRUE"/><FieldRef Name="PermMask" Explicit="TRUE"/><FieldRef Name="Author" Explicit="T`

## pseudocode

```c

```

## disassembly

```asm
0x34ed40  ldarg.s  4
0x34ed42  stloc.0
0x34ed43  ldsfld   string [mscorlib]System.String::Empty
0x34ed48  stloc.1
0x34ed49  ldarg.s  6
0x34ed4b  ldc.i4.0
0x34ed4c  stind.i1
0x34ed4d  ldarg.3
0x34ed4e  brfalse  loc_34EE90
0x34ed53  ldstr    aListitemmenuTr// " ListItemMenu=\"TRUE\" "
0x34ed58  stloc.1
0x34ed59  ldarg.s  6
0x34ed5b  ldc.i4.1
0x34ed5c  stind.i1
0x34ed5d  ldloc.0
0x34ed5e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ed63  brfalse  loc_34EE1F
0x34ed68  ldarg.0
0x34ed69  call     instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x34ed6e  stloc.2
0x34ed6f  ldloc.2
0x34ed70  ldstr    aLinkfilename// "LinkFilename"
0x34ed75  ldc.i4.0
0x34ed76  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ed7b  brfalse.s loc_34ED91
0x34ed7d  ldarg.0
0x34ed7e  call     instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x34ed83  ldc.i4.1
0x34ed84  bne.un.s loc_34ED91
0x34ed86  ldstr    aLinkfilename// "LinkFilename"
0x34ed8b  stloc.0
0x34ed8c  br       loc_34EFC1
0x34ed91  ldloc.2
0x34ed92  ldstr    aLinkdiscussion// "LinkDiscussionTitle"
0x34ed97  ldc.i4.0
0x34ed98  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ed9d  brfalse.s loc_34EDAA
0x34ed9f  ldstr    aLinkdiscussion// "LinkDiscussionTitle"
0x34eda4  stloc.0
0x34eda5  br       loc_34EFC1
0x34edaa  ldloc.2
0x34edab  ldstr    aDisplayrespons// "DisplayResponse"
0x34edb0  ldc.i4.0
0x34edb1  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34edb6  brfalse.s loc_34EDC3
0x34edb8  ldstr    aDisplayrespons// "DisplayResponse"
0x34edbd  stloc.0
0x34edbe  br       loc_34EFC1
0x34edc3  ldloc.2
0x34edc4  ldstr    aRefwhereabout// "RefWhereabout"
0x34edc9  ldc.i4.0
0x34edca  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34edcf  brfalse.s loc_34EDDC
0x34edd1  ldstr    aRefwhereabout// "RefWhereabout"
0x34edd6  stloc.0
0x34edd7  br       loc_34EFC1
0x34eddc  ldloc.2
0x34eddd  ldstr    aLinktitle// "LinkTitle"
0x34ede2  ldc.i4.0
0x34ede3  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ede8  brfalse.s loc_34EDF5
0x34edea  ldstr    aLinktitle// "LinkTitle"
0x34edef  stloc.0
0x34edf0  br       loc_34EFC1
0x34edf5  ldloc.2
0x34edf6  ldstr    aUrlwmenu// "URLwMenu"
0x34edfb  ldc.i4.0
0x34edfc  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ee01  brfalse.s loc_34EE0E
0x34ee03  ldstr    aUrlwmenu// "URLwMenu"
0x34ee08  stloc.0
0x34ee09  br       loc_34EFC1
0x34ee0e  ldloc.1
0x34ee0f  ldstr    aLinktoitemTrue// "LinkToItem=\"TRUE\" "
0x34ee14  call     string [mscorlib]System.String::Concat(string, string)
0x34ee19  stloc.1
0x34ee1a  br       loc_34EFC1
0x34ee1f  ldstr    aLinkfilename// "LinkFilename"
0x34ee24  ldloc.0
0x34ee25  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee2a  brtrue   loc_34EFC1
0x34ee2f  ldstr    aLinkdiscussion// "LinkDiscussionTitle"
0x34ee34  ldloc.0
0x34ee35  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee3a  brtrue   loc_34EFC1
0x34ee3f  ldstr    aDisplayrespons// "DisplayResponse"
0x34ee44  ldloc.0
0x34ee45  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee4a  brtrue   loc_34EFC1
0x34ee4f  ldstr    aUrlwmenu// "URLwMenu"
0x34ee54  ldloc.0
0x34ee55  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee5a  brtrue   loc_34EFC1
0x34ee5f  ldstr    aRefwhereabout// "RefWhereabout"
0x34ee64  ldloc.0
0x34ee65  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee6a  brtrue   loc_34EFC1
0x34ee6f  ldstr    aLinktitle// "LinkTitle"
0x34ee74  ldloc.0
0x34ee75  call     bool [mscorlib]System.String::Equals(string, string)
0x34ee7a  brtrue   loc_34EFC1
0x34ee7f  ldloc.1
0x34ee80  ldstr    aLinktoitemTrue// "LinkToItem=\"TRUE\" "
0x34ee85  call     string [mscorlib]System.String::Concat(string, string)
0x34ee8a  stloc.1
0x34ee8b  br       loc_34EFC1
0x34ee90  ldarg.0
0x34ee91  call     instance class Microsoft.SharePoint.SPFieldCollection Microsoft.SharePoint.SPList::get_Fields()
0x34ee96  stloc.3
0x34ee97  ldstr    aLinkfilename// "LinkFilename"
0x34ee9c  ldarg.s  4
0x34ee9e  call     bool [mscorlib]System.String::Equals(string, string)
0x34eea3  brtrue.s loc_34EEC5
0x34eea5  ldarg.s  4
0x34eea7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34eeac  brfalse.s loc_34EED0
0x34eeae  ldloc.3
0x34eeaf  ldstr    aLinkfilename2// "LinkFilename2"
0x34eeb4  ldc.i4.0
0x34eeb5  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34eeba  brfalse.s loc_34EED0
0x34eebc  ldarg.0
0x34eebd  call     instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x34eec2  ldc.i4.1
0x34eec3  bne.un.s loc_34EED0
0x34eec5  ldstr    aLinkfilename2// "LinkFilename2"
0x34eeca  stloc.0
0x34eecb  br       loc_34EFC1
0x34eed0  ldstr    aLinkdiscussion// "LinkDiscussionTitle"
0x34eed5  ldarg.s  4
0x34eed7  call     bool [mscorlib]System.String::Equals(string, string)
0x34eedc  brtrue.s loc_34EEF5
0x34eede  ldarg.s  4
0x34eee0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34eee5  brfalse.s loc_34EF00
0x34eee7  ldloc.3
0x34eee8  ldstr    aLinkdiscussion_0// "LinkDiscussionTitle2"
0x34eeed  ldc.i4.0
0x34eeee  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34eef3  brfalse.s loc_34EF00
0x34eef5  ldstr    aLinkdiscussion_0// "LinkDiscussionTitle2"
0x34eefa  stloc.0
0x34eefb  br       loc_34EFC1
0x34ef00  ldstr    aDisplayrespons// "DisplayResponse"
0x34ef05  ldarg.s  4
0x34ef07  call     bool [mscorlib]System.String::Equals(string, string)
0x34ef0c  brtrue.s loc_34EF25
0x34ef0e  ldarg.s  4
0x34ef10  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ef15  brfalse.s loc_34EF30
0x34ef17  ldloc.3
0x34ef18  ldstr    aDisplayrespons_0// "DisplayResponse2"
0x34ef1d  ldc.i4.0
0x34ef1e  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ef23  brfalse.s loc_34EF30
0x34ef25  ldstr    aDisplayrespons_0// "DisplayResponse2"
0x34ef2a  stloc.0
0x34ef2b  br       loc_34EFC1
0x34ef30  ldstr    aRefwhereabout// "RefWhereabout"
0x34ef35  ldarg.s  4
0x34ef37  call     bool [mscorlib]System.String::Equals(string, string)
0x34ef3c  brtrue.s loc_34EF55
0x34ef3e  ldarg.s  4
0x34ef40  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ef45  brfalse.s loc_34EF5D
0x34ef47  ldloc.3
0x34ef48  ldstr    aRefwhereabout2// "RefWhereabout2"
0x34ef4d  ldc.i4.0
0x34ef4e  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ef53  brfalse.s loc_34EF5D
0x34ef55  ldstr    aRefwhereabout2// "RefWhereabout2"
0x34ef5a  stloc.0
0x34ef5b  br.s     loc_34EFC1
0x34ef5d  ldstr    aLinktitle// "LinkTitle"
0x34ef62  ldarg.s  4
0x34ef64  call     bool [mscorlib]System.String::Equals(string, string)
0x34ef69  brtrue.s loc_34EF82
0x34ef6b  ldarg.s  4
0x34ef6d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ef72  brfalse.s loc_34EF8A
0x34ef74  ldloc.3
0x34ef75  ldstr    aLinktitle2// "LinkTitle2"
0x34ef7a  ldc.i4.0
0x34ef7b  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34ef80  brfalse.s loc_34EF8A
0x34ef82  ldstr    aLinktitle2// "LinkTitle2"
0x34ef87  stloc.0
0x34ef88  br.s     loc_34EFC1
0x34ef8a  ldstr    aUrlwmenu// "URLwMenu"
0x34ef8f  ldarg.s  4
0x34ef91  call     bool [mscorlib]System.String::Equals(string, string)
0x34ef96  brtrue.s loc_34EFAF
0x34ef98  ldarg.s  4
0x34ef9a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34ef9f  brfalse.s loc_34EFB7
0x34efa1  ldloc.3
0x34efa2  ldstr    aUrlwmenu2// "URLwMenu2"
0x34efa7  ldc.i4.0
0x34efa8  callvirt instance class Microsoft.SharePoint.SPField Microsoft.SharePoint.SPFieldCollection::GetFieldByInternalName(string strName, bool bThrowException)
0x34efad  brfalse.s loc_34EFB7
0x34efaf  ldstr    aUrlwmenu2// "URLwMenu2"
0x34efb4  stloc.0
0x34efb5  br.s     loc_34EFC1
0x34efb7  ldstr    aListitemmenuTr_0// " ListItemMenu=\"TRUE\" LinkToItem=\"TRU"...
0x34efbc  stloc.1
0x34efbd  ldarg.s  6
0x34efbf  ldc.i4.1
0x34efc0  stind.i1
0x34efc1  ldarg.2
0x34efc2  ldc.i4.5
0x34efc3  newarr   [mscorlib]System.String
0x34efc8  stloc.s  4
0x34efca  ldloc.s  4
0x34efcc  ldc.i4.0
0x34efcd  ldstr    aFieldrefName// "<FieldRef Name=\""
0x34efd2  stelem.ref
0x34efd3  ldloc.s  4
0x34efd5  ldc.i4.1
0x34efd6  ldloc.0
0x34efd7  stelem.ref
0x34efd8  ldloc.s  4
0x34efda  ldc.i4.2
0x34efdb  ldstr    asc_C83F68// "\""
0x34efe0  stelem.ref
0x34efe1  ldloc.s  4
0x34efe3  ldc.i4.3
0x34efe4  ldloc.1
0x34efe5  stelem.ref
0x34efe6  ldloc.s  4
0x34efe8  ldc.i4.4
0x34efe9  ldstr    asc_DF074A// " />"
0x34efee  stelem.ref
0x34efef  ldloc.s  4
0x34eff1  call     string [mscorlib]System.String::Concat(string[])
0x34eff6  callvirt instance void Microsoft.SharePoint.SPQuery::set_ViewFields(string value)
0x34effb  ldarg.0
0x34effc  call     instance bool Microsoft.SharePoint.SPList::get_HasExternalDataSource()
0x34f001  brtrue.s loc_34F019
0x34f003  ldarg.2
0x34f004  dup
0x34f005  callvirt instance string Microsoft.SharePoint.SPQuery::get_ViewFields()
0x34f00a  ldstr    aFieldrefNameFi// "<FieldRef Name=\"FileLeafRef\" Explicit"...
0x34f00f  call     string [mscorlib]System.String::Concat(string, string)
0x34f014  callvirt instance void Microsoft.SharePoint.SPQuery::set_ViewFields(string value)
0x34f019  ldarg.s  5
0x34f01b  brfalse.s loc_34F05A
0x34f01d  ldarg.0
0x34f01e  call     instance bool Microsoft.SharePoint.SPList::get_HasExternalDataSource()
0x34f023  brfalse.s loc_34F043
0x34f025  ldarg.2
0x34f026  ldstr    aWhereEqFieldre_5// "<Where><Eq><FieldRef Name='BdcIdentity'"...
0x34f02b  ldarg.s  5
0x34f02d  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlKeyValueDecode(string keyOrValueToDecode)
0x34f032  ldstr    aValueEqWhere// "</Value></Eq></Where>"
0x34f037  call     string [mscorlib]System.String::Concat(string, string, string)
0x34f03c  callvirt instance void Microsoft.SharePoint.SPQuery::set_Query(string value)
0x34f041  br.s     loc_34F05A
0x34f043  ldarg.2
0x34f044  ldstr    aWhereEqFieldre_6// "<Where><Eq><FieldRef Name='ID'/><Value "...
0x34f049  ldarg.s  5
0x34f04b  ldstr    aValueEqWhere// "</Value></Eq></Where>"
0x34f050  call     string [mscorlib]System.String::Concat(string, string, string)
0x34f055  callvirt instance void Microsoft.SharePoint.SPQuery::set_Query(string value)
0x34f05a  ldarg.0
0x34f05b  ldarg.1
0x34f05c  ldarg.2
0x34f05d  call     instance void Microsoft.SharePoint.SPList::EnsureEcbViewFieldsInOverrideSelectCommand(class Microsoft.SharePoint.SPView view, class Microsoft.SharePoint.SPQuery qry)
0x34f062  ret
```
