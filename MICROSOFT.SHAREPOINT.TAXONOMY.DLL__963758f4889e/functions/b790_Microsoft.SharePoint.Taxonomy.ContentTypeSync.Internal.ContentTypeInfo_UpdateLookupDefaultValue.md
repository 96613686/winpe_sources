# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateLookupDefaultValue

- ea: `0xb790`
- end: `0xb948`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateLookupDefaultValue`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xb680`

## callees

- `0xb790`
- `0xb950`
- `0xc460`
- `0x2ad40`
- `0x44d10`

## string_xrefs

- `0xb7c8`: `urn:deployment-manifest-schema`
- `0xb814`: `urn:deployment-manifest-schema`
- `0xb82a`: `urn:deployment-manifest-schema`
- `0xb865`: `urn:deployment-manifest-schema`
- `0xb89e`: `urn:deployment-manifest-schema`

## pseudocode

```c

```

## disassembly

```asm
0xb790  ldarg.s  4
0xb792  ldstr    aType// "Type"
0xb797  ldstr    asc_794BA// ""
0xb79c  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0xb7a1  stloc.0
0xb7a2  ldloc.0
0xb7a3  ldstr    aTaxonomyfieldt// "TaxonomyFieldType"
0xb7a8  ldc.i4.5
0xb7a9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb7ae  brtrue.s loc_B7C1
0xb7b0  ldloc.0
0xb7b1  ldstr    aTaxonomyfieldt_0// "TaxonomyFieldTypeMulti"
0xb7b6  ldc.i4.5
0xb7b7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb7bc  brfalse  loc_B947
0xb7c1  ldarg.s  4
0xb7c3  ldstr    aDefault// "Default"
0xb7c8  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb7cd  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToChild(string, string)
0xb7d2  brfalse  loc_B947
0xb7d7  ldarg.s  4
0xb7d9  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xb7de  stloc.1
0xb7df  ldloc.1
0xb7e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb7e5  brtrue   loc_B947
0xb7ea  ldloc.1
0xb7eb  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomyFieldValueCollection::.ctor(string fieldValue)
0xb7f0  stloc.2
0xb7f1  ldarg.2
0xb7f2  brfalse.s loc_B802
0xb7f4  ldarg.0
0xb7f5  dup
0xb7f6  ldfld    int32 Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::numberOfLookupDefaultValue
0xb7fb  ldc.i4.1
0xb7fc  add.ovf
0xb7fd  stfld    int32 Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::numberOfLookupDefaultValue
0xb802  ldnull
0xb803  stloc.3
0xb804  ldnull
0xb805  stloc.s  4
0xb807  ldc.i4.0
0xb808  stloc.s  5
0xb80a  ldc.i4.0
0xb80b  stloc.s  6
0xb80d  ldarg.s  4
0xb80f  ldstr    aCustomization// "Customization"
0xb814  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb819  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0xb81e  brfalse  loc_B8CF
0xb823  ldarg.s  4
0xb825  ldstr    aName// "Name"
0xb82a  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb82f  ldc.i4.0
0xb830  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::SelectDescendants(string, string, bool)
0xb835  stloc.s  7
0xb837  br       loc_B8C3
0xb83c  ldloc.s  7
0xb83e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xb843  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xb848  stloc.s  8
0xb84a  ldloc.s  8
0xb84c  ldstr    aSspid_0// "SspId"
0xb851  ldc.i4.5
0xb852  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb857  brfalse.s loc_B883
0xb859  ldloc.s  7
0xb85b  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xb860  ldstr    aValue// "Value"
0xb865  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb86a  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0xb86f  brfalse.s loc_B8BB
0xb871  ldloc.s  7
0xb873  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xb878  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xb87d  stloc.3
0xb87e  ldc.i4.1
0xb87f  stloc.s  5
0xb881  br.s     loc_B8BB
0xb883  ldloc.s  8
0xb885  ldstr    aTermsetid// "TermSetId"
0xb88a  ldc.i4.5
0xb88b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb890  brfalse.s loc_B8BB
0xb892  ldloc.s  7
0xb894  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xb899  ldstr    aValue// "Value"
0xb89e  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb8a3  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToNext(string, string)
0xb8a8  brfalse.s loc_B8BB
0xb8aa  ldloc.s  7
0xb8ac  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0xb8b1  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0xb8b6  stloc.s  4
0xb8b8  ldc.i4.1
0xb8b9  stloc.s  6
0xb8bb  ldloc.s  5
0xb8bd  brfalse.s loc_B8C3
0xb8bf  ldloc.s  6
0xb8c1  brtrue.s loc_B8CF
0xb8c3  ldloc.s  7
0xb8c5  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0xb8ca  brtrue   loc_B83C
0xb8cf  ldloc.s  5
0xb8d1  brfalse.s loc_B8FD
0xb8d3  ldloc.s  6
0xb8d5  brfalse.s loc_B8FD
0xb8d7  ldloc.3
0xb8d8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8dd  brtrue.s loc_B8FD
0xb8df  ldloc.s  4
0xb8e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8e6  brtrue.s loc_B8FD
0xb8e8  ldarg.0
0xb8e9  ldarg.1
0xb8ea  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0xb8ef  ldarg.s  4
0xb8f1  ldloc.2
0xb8f2  ldloc.3
0xb8f3  ldloc.s  4
0xb8f5  ldarg.s  5
0xb8f7  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateLookupDefaultValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite targetSite, class [System.Xml]System.Xml.XPath.XPathNavigator currentNode, class Microsoft.SharePoint.Taxonomy.TaxonomyFieldValueCollection fieldValueCollection, string termStoreIdString, string termSetIdString, bool& needUpdate)
0xb8fc  ret
0xb8fd  ldc.i4   0x66657034
0xb902  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xb907  ldc.i4.s 0xA
0xb909  ldstr    aATaxonomyField// "A taxonomy field with default value is "...
0xb90e  ldc.i4.1
0xb90f  newarr   [mscorlib]System.Object
0xb914  stloc.s  9
0xb916  ldloc.s  9
0xb918  ldc.i4.0
0xb919  ldarg.s  4
0xb91b  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0xb920  stelem.ref
0xb921  ldloc.s  9
0xb923  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xb928  ldstr    aErrorinvalidta// "ErrorInvalidTaxField"
0xb92d  ldc.i4.1
0xb92e  newarr   [mscorlib]System.Object
0xb933  stloc.s  0xA
0xb935  ldloc.s  0xA
0xb937  ldc.i4.0
0xb938  ldarg.3
0xb939  stelem.ref
0xb93a  ldloc.s  0xA
0xb93c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0xb941  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.ContentTypeSyndicationException::.ctor(string message)
0xb946  throw
0xb947  ret
```
