# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::GenerateContentTypeInfo

- ea: `0xafc0`
- end: `0xb165`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::GenerateContentTypeInfo`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11cd0`

## callees

- `0xafa0`
- `0xafc0`
- `0xb270`
- `0xb280`
- `0xb360`
- `0xb3f0`
- `0xb520`
- `0xb5a0`
- `0xb5c0`
- `0xb680`
- `0xbc50`

## string_xrefs

- `0xb02e`: `urn:deployment-manifest-schema`
- `0xb0ae`: `ReadOnly`
- `0xb0de`: `dm:XmlDocuments/dm:XmlDocument[@NamespaceURI='office.server.policy']`

## pseudocode

```c

```

## disassembly

```asm
0xafc0  ldc.i4   0x63386A38
0xafc5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xafca  ldc.i4.s 0x64
0xafcc  ldstr    aGettingContent// "Getting content type information from t"...
0xafd1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0xafd6  ldarg.0
0xafd7  call     string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::GetManifestFile(string folderPath)
0xafdc  stloc.0
0xafdd  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::.ctor()
0xafe2  stloc.1
0xafe3  ldc.i4.0
0xafe4  stloc.2
0xafe5  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xafea  stloc.3
0xafeb  ldloc.0
0xafec  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(string)
0xaff1  stloc.s  4
0xaff3  ldloc.s  4
0xaff5  ldc.i4.0
0xaff6  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0xaffb  ldloc.3
0xaffc  ldloc.s  4
0xaffe  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xb003  leave.s  loc_B011
0xb005  ldloc.s  4
0xb007  brfalse.s loc_B010
0xb009  ldloc.s  4
0xb00b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb010  endfinally
0xb011  ldloc.3
0xb012  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0xb017  stloc.s  5
0xb019  ldloc.s  5
0xb01b  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0xb020  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xb025  stloc.s  6
0xb027  ldloc.s  6
0xb029  ldstr    aDm// "dm"
0xb02e  ldstr    aUrnDeploymentM// "urn:deployment-manifest-schema"
0xb033  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xb038  ldloc.1
0xb039  ldloc.s  5
0xb03b  ldloc.s  6
0xb03d  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::ReadResourceNodes(class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0xb042  ldloc.1
0xb043  ldarg.1
0xb044  ldloc.s  5
0xb046  ldloc.s  6
0xb048  ldc.i4.1
0xb049  ldloca.s 2
0xb04b  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateFields(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb targetWeb, class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager mgr, bool isNew, bool& needUpdate)
0xb050  ldloc.s  5
0xb052  ldloc.s  6
0xb054  call     class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::GetContentTypeNode(class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0xb059  stloc.s  7
0xb05b  ldloc.1
0xb05c  ldloc.s  7
0xb05e  ldstr    aId_0// "ID"
0xb063  ldstr    asc_794BA// ""
0xb068  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0xb06d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId::.ctor(string)
0xb072  stfld    valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::id
0xb077  ldloc.1
0xb078  ldarg.1
0xb079  ldloc.s  7
0xb07b  ldc.i4.1
0xb07c  ldloca.s 2
0xb07e  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateContentTypeResource(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb targetWeb, class [System.Xml]System.Xml.XPath.XPathNavigator ctnode, bool isNew, bool& needUpdate)
0xb083  ldloc.s  7
0xb085  ldstr    aFeatureid// "FeatureId"
0xb08a  ldstr    asc_794BA// ""
0xb08f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0xb094  stloc.s  8
0xb096  ldloc.s  8
0xb098  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb09d  brtrue.s loc_B0AC
0xb09f  ldloc.1
0xb0a0  ldloc.s  8
0xb0a2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb0a7  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::featureId
0xb0ac  ldloc.s  7
0xb0ae  ldstr    aReadonly// "ReadOnly"
0xb0b3  ldstr    asc_794BA// ""
0xb0b8  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0xb0bd  stloc.s  9
0xb0bf  ldloc.s  9
0xb0c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb0c6  brtrue.s loc_B0DB
0xb0c8  ldloc.1
0xb0c9  ldloc.s  9
0xb0cb  ldstr    aTrue_1// "TRUE"
0xb0d0  ldc.i4.5
0xb0d1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb0d6  stfld    bool Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::isReadOnly
0xb0db  ldloc.1
0xb0dc  ldloc.s  7
0xb0de  ldstr    aDmXmldocuments// "dm:XmlDocuments/dm:XmlDocument[@Namespa"...
0xb0e3  ldloc.s  6
0xb0e5  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string, class [System.Xml]System.Xml.IXmlNamespaceResolver)
0xb0ea  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::policyXml
0xb0ef  ldloc.1
0xb0f0  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_PolicyXml()
0xb0f5  brfalse.s loc_B12C
0xb0f7  ldloc.1
0xb0f8  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_PolicyXml()
0xb0fd  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0xb102  stloc.s  0xA
0xb104  ldloc.s  0xA
0xb106  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0xb10b  stloc.s  0xB
0xb10d  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor()
0xb112  stloc.s  0xC
0xb114  ldloc.s  0xC
0xb116  ldloc.s  0xB
0xb118  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0xb11d  stloc.s  0xD
0xb11f  ldloc.1
0xb120  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::get_PolicyXml()
0xb125  ldloc.s  0xD
0xb127  callvirt instance void [System.Xml]System.Xml.XPath.XPathNavigator::set_InnerXml(string)
0xb12c  ldloc.1
0xb12d  ldloc.s  7
0xb12f  ldarg.2
0xb130  ldloca.s 2
0xb132  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdatePushdown(class [System.Xml]System.Xml.XPath.XPathNavigator ctnode, bool newShouldPushdown, bool& needUpdate)
0xb137  ldloc.1
0xb138  ldloc.s  7
0xb13a  ldloc.s  6
0xb13c  ldarg.3
0xb13d  ldarg.s  4
0xb13f  ldloca.s 2
0xb141  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::UpdateXmlDocument(class [System.Xml]System.Xml.XPath.XPathNavigator ctnode, class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager, valuetype [mscorlib]System.Guid newTermStoreId, bool newPreviousValue, bool& needUpdate)
0xb146  ldloc.2
0xb147  brfalse.s loc_B15C
0xb149  ldloc.3
0xb14a  ldloc.0
0xb14b  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(string)
0xb150  ldloc.1
0xb151  ldarg.1
0xb152  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Language()
0xb157  stfld    unsigned int32 Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::lcid
0xb15c  ldloc.1
0xb15d  ldarg.0
0xb15e  callvirt instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeInfo::LoadWorkflowAssociations(string folderPath)
0xb163  ldloc.1
0xb164  ret
```
