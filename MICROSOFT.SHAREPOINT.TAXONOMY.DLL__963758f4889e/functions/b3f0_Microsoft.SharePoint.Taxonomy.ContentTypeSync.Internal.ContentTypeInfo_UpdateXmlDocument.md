# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateXmlDocument

- ea: `0xb3f0`
- end: `0xb4c9`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateXmlDocument`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xafc0`
- `0xb170`

## callees

- `0xb3f0`
- `0xb4d0`
- `0x13450`

## string_xrefs

- `0xb42e`: `urn:deployment-manifest-schema`
- `0xb3f1`: `dm:XmlDocuments/dm:XmlDocument[@NamespaceURI='Microsoft.SharePoint.Taxonomy.ContentTypeSync']`
- `0xb429`: `XmlDocuments`
- `0xb43f`: `<XmlDocument NamespaceURI="{0}">{1}</XmlDocument>`
- `0xb48f`: `The downloaded content type XML does not have XmlDocuments element: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb3f0  ldarg.1
0xb3f1  ldstr    aDmXmldocuments_0// "dm:XmlDocuments/dm:XmlDocument[@Namespa"...
0xb3f6  ldarg.2
0xb3f7  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0xb3fc  stloc.0
0xb3fd  ldarg.0
0xb3fe  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::termStoreId
0xb403  ldarg.3
0xb404  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb409  brtrue.s loc_B41B
0xb40b  ldarg.0
0xb40c  ldfld    bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::previousValue
0xb411  ldarg.s  4
0xb413  bne.un.s loc_B41B
0xb415  ldloc.0
0xb416  brtrue   loc_B4C8
0xb41b  ldloc.0
0xb41c  brfalse.s loc_B428
0xb41e  ldloc.0
0xb41f  callvirt instance void [System.Xml]System.Xml.XPath.XPathNavigator::DeleteSelf()
0xb424  ldarg.s  5
0xb426  ldc.i4.1
0xb427  stind.i1
0xb428  ldarg.1
0xb429  ldstr    aXmldocuments// "XmlDocuments"
0xb42e  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb433  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToChild(string, string)
0xb438  brfalse.s loc_B483
0xb43a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb43f  ldstr    aXmldocumentNam// "<XmlDocument NamespaceURI=\"{0}\">{1}</"...
0xb444  ldc.i4.2
0xb445  newarr   [mscorlib]System.Object
0xb44a  stloc.2
0xb44b  ldloc.2
0xb44c  ldc.i4.0
0xb44d  ldstr    aMicrosoftShare_1// "Microsoft.SharePoint.Taxonomy.ContentTy"...
0xb452  stelem.ref
0xb453  ldloc.2
0xb454  ldc.i4.1
0xb455  ldarg.3
0xb456  ldarg.0
0xb457  ldflda   valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::id
0xb45c  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xb462  callvirt instance string [mscorlib]System.Object::ToString()
0xb467  ldarg.s  4
0xb469  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SubscriberUtility::CreateXmlDocument(valuetype [mscorlib]System.Guid termStoreId, string contentTypeId, bool previousValue)
0xb46e  stelem.ref
0xb46f  ldloc.2
0xb470  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb475  stloc.1
0xb476  ldarg.1
0xb477  ldloc.1
0xb478  callvirt instance void [System.Xml]System.Xml.XPath.XPathNavigator::AppendChild(string)
0xb47d  ldarg.s  5
0xb47f  ldc.i4.1
0xb480  stind.i1
0xb481  br.s     loc_B4B9
0xb483  ldc.i4   0x61347839
0xb488  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xb48d  ldc.i4.s 0xA
0xb48f  ldstr    aTheDownloadedC// "The downloaded content type XML does no"...
0xb494  ldc.i4.1
0xb495  newarr   [mscorlib]System.Object
0xb49a  stloc.3
0xb49b  ldloc.3
0xb49c  ldc.i4.0
0xb49d  ldarg.0
0xb49e  call     instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_Id()
0xb4a3  stloc.s  4
0xb4a5  ldloca.s 4
0xb4a7  constrained. [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0xb4ad  callvirt instance string [mscorlib]System.Object::ToString()
0xb4b2  stelem.ref
0xb4b3  ldloc.3
0xb4b4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xb4b9  ldarg.0
0xb4ba  ldarg.3
0xb4bb  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::termStoreId
0xb4c0  ldarg.0
0xb4c1  ldarg.s  4
0xb4c3  stfld    bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::previousValue
0xb4c8  ret
```
