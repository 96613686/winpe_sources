# Microsoft.SharePoint.SPSolutionExporter::ExportListsManifest

- ea: `0x481be0`
- end: `0x482a52`
- name: `Microsoft.SharePoint.SPSolutionExporter::ExportListsManifest`
- size: `3698`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x481910`
- `0x482a60`

## callees

- `0x3462c0`
- `0x47e320`
- `0x481be0`
- `0x482ac0`
- `0x482b50`
- `0x484f20`
- `0x4866a0`
- `0x486700`
- `0x4881d0`
- `0x488690`
- `0x489130`
- `0x48c160`
- `0x48c490`
- `0x48c4e0`
- `0x48c8b0`
- `0x48c970`
- `0x48d5d0`
- `0x48d610`
- `0x48d9e0`
- `0x48ea30`
- `0x48ebf0`
- `0x552b80`
- `0x577060`
- `0x5c0860`
- `0x5c3b50`
- `0x5c3ce0`
- `0x5c5760`
- `0x5cdca0`
- `0x5cdce0`
- `0x93dae0`
- `0x945c90`
- `0x946300`
- `0x957cd0`
- `0xbc61c0`
- `0xbc61e0`

## string_xrefs

- `0x481c5b`: `http://schemas.microsoft.com/sharepoint/`
- `0x482364`: `http://schemas.microsoft.com/sharepoint/`
- `0x481f32`: `TemplateType`
- `0x4821a4`: `TemplateType`
- `0x482639`: `ElementManifest`
- `0x4826b7`: `ElementManifest`
- `0x482733`: `ElementManifest`
- `0x4826db`: `ElementsFields.xml`
- `0x482757`: `ElementsContentType.xml`
- `0x481bf1`: `Elements.xml`
- `0x481c12`: `Creating list instances feature manifest file '{0}'`
- `0x481fc8`: `HyperlinkBaseUrl`
- `0x482122`: `WorkflowServiceStoreFeature`
- `0x48218a`: `WorkflowServiceStoreFeature`
- `0x482137`: `WorkflowStoreListTemplate`
- `0x4821b0`: `WorkflowStoreListTemplate`
- `0x4822df`: `Feature.xml`
- `0x48242d`: `SitePackaging_WorkflowTemplateFeatureTitle`
- `0x48261b`: `ElementManifests`

## pseudocode

```c

```

## disassembly

```asm
0x481be0  newobj   instance void <>c__DisplayClass35::.ctor()
0x481be5  stloc.s  0x27
0x481be7  ldloc.s  0x27
0x481be9  ldarg.0
0x481bea  stfld    class Microsoft.SharePoint.SPSolutionExporter <>c__DisplayClass35::<>4__this
0x481bef  ldloc.s  0x27
0x481bf1  ldstr    aElementsXml// "Elements.xml"
0x481bf6  ldarg.0
0x481bf7  ldfld    string Microsoft.SharePoint.SPSolutionExporter::ListInstancesPartitionName
0x481bfc  call     string Microsoft.SharePoint.SPSolutionExporter::ConvertWebRelativeUrlToPartitionedRelativePath(string webRelativeUrl, string partitionName)
0x481c01  stfld    string <>c__DisplayClass35::featureManifestFileRelativePath
0x481c06  ldc.i4   0xDA3D1
0x481c0b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x481c10  ldc.i4.s 0x64
0x481c12  ldstr    aCreatingListIn// "Creating list instances feature manifes"...
0x481c17  ldc.i4.1
0x481c18  newarr   [mscorlib]System.Object
0x481c1d  stloc.s  0x28
0x481c1f  ldloc.s  0x28
0x481c21  ldc.i4.0
0x481c22  ldloc.s  0x27
0x481c24  ldfld    string <>c__DisplayClass35::featureManifestFileRelativePath
0x481c29  stelem.ref
0x481c2a  ldloc.s  0x28
0x481c2c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x481c31  ldarg.0
0x481c32  ldloc.s  0x27
0x481c34  ldfld    string <>c__DisplayClass35::featureManifestFileRelativePath
0x481c39  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.SPSolutionExporter::CreateXmlWriterInStagingArea(string xmlFileRelativeName)
0x481c3e  ldloc.s  0x27
0x481c40  ldfld    string <>c__DisplayClass35::featureManifestFileRelativePath
0x481c45  newobj   instance void Microsoft.SharePoint.ScopedXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string streamIdentifier)
0x481c4a  stloc.0
0x481c4b  ldloc.0
0x481c4c  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481c51  ldstr    asc_C00000// ""
0x481c56  ldstr    aElements// "Elements"
0x481c5b  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sharepoint"...
0x481c60  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x481c65  stloc.1
0x481c66  ldarg.0
0x481c67  call     instance bool Microsoft.SharePoint.SPSolutionExporter::get_WorkflowExportModeIsEnabled()
0x481c6c  brfalse  loc_481EAC
0x481c71  ldarg.0
0x481c72  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> Microsoft.SharePoint.SPSolutionExporter::WorkFlowFields
0x481c77  brfalse.s loc_481CD6
0x481c79  ldarg.0
0x481c7a  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> Microsoft.SharePoint.SPSolutionExporter::WorkFlowFields
0x481c7f  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, string>::get_Count()
0x481c84  ldc.i4.0
0x481c85  ble.s    loc_481CD6
0x481c87  ldarg.0
0x481c88  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> Microsoft.SharePoint.SPSolutionExporter::WorkFlowFields
0x481c8d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, string>::get_Keys()
0x481c92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x481c97  stloc.s  0x29
0x481c99  br.s     loc_481CBF
0x481c9b  ldloc.s  0x29
0x481c9d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x481ca2  stloc.2
0x481ca3  ldloc.0
0x481ca4  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481ca9  ldarg.0
0x481caa  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> Microsoft.SharePoint.SPSolutionExporter::WorkFlowFields
0x481caf  ldloc.2
0x481cb0  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<string, string>::get_Item(void)
0x481cb5  callvirt instance string [mscorlib]System.Object::ToString()
0x481cba  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlToWriter(class [System.Xml]System.Xml.XmlWriter output, string xml)
0x481cbf  ldloc.s  0x29
0x481cc1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x481cc6  brtrue.s loc_481C9B
0x481cc8  leave.s  loc_481CD6
0x481cca  ldloc.s  0x29
0x481ccc  brfalse.s loc_481CD5
0x481cce  ldloc.s  0x29
0x481cd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481cd5  endfinally
0x481cd6  ldarg.3
0x481cd7  brfalse  loc_481EAC
0x481cdc  ldarg.3
0x481cdd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class WorkflowContentType>::get_Count()
0x481ce2  ldc.i4.0
0x481ce3  ble      loc_481EAC
0x481ce8  ldarg.3
0x481ce9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class WorkflowContentType>::GetEnumerator()
0x481cee  stloc.s  0x2A
0x481cf0  br       loc_481E90
0x481cf5  ldloca.s 0x2A
0x481cf7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class WorkflowContentType>::get_Current()
0x481cfc  stloc.3
0x481cfd  ldloc.3
0x481cfe  ldfld    string WorkflowContentType::ContentTypeSchema
0x481d03  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x481d08  brtrue.s loc_481D53
0x481d0a  ldloc.3
0x481d0b  ldfld    string WorkflowContentType::ContentTypeSchema
0x481d10  ldarg.s  5
0x481d12  callvirt instance bool [mscorlib]System.String::Contains(string)
0x481d17  brtrue.s loc_481D3D
0x481d19  ldloc.3
0x481d1a  ldfld    string WorkflowContentType::ContentTypeSchema
0x481d1f  ldarg.s  4
0x481d21  callvirt instance bool [mscorlib]System.String::Contains(string)
0x481d26  brfalse.s loc_481D3D
0x481d28  ldloc.3
0x481d29  ldloc.3
0x481d2a  ldfld    string WorkflowContentType::ContentTypeSchema
0x481d2f  ldarg.s  4
0x481d31  ldarg.s  5
0x481d33  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x481d38  stfld    string WorkflowContentType::ContentTypeSchema
0x481d3d  ldloc.0
0x481d3e  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481d43  ldloc.3
0x481d44  ldfld    string WorkflowContentType::ContentTypeSchema
0x481d49  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlToWriter(class [System.Xml]System.Xml.XmlWriter output, string xml)
0x481d4e  br       loc_481E90
0x481d53  ldloc.0
0x481d54  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481d59  ldsfld   string [mscorlib]System.String::Empty
0x481d5e  ldstr    aContenttype// "ContentType"
0x481d63  ldnull
0x481d64  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x481d69  stloc.s  4
0x481d6b  ldloc.0
0x481d6c  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481d71  ldsfld   string [mscorlib]System.String::Empty
0x481d76  ldstr    aName_0// "Name"
0x481d7b  ldnull
0x481d7c  ldloc.3
0x481d7d  ldfld    string WorkflowContentType::ContentTypeName
0x481d82  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481d87  ldloc.0
0x481d88  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481d8d  ldsfld   string [mscorlib]System.String::Empty
0x481d92  ldstr    aId_0// "ID"
0x481d97  ldnull
0x481d98  ldloc.3
0x481d99  ldfld    string WorkflowContentType::ContentTypeId
0x481d9e  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481da3  ldloc.0
0x481da4  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481da9  ldsfld   string [mscorlib]System.String::Empty
0x481dae  ldstr    aDescription// "Description"
0x481db3  ldnull
0x481db4  ldloc.3
0x481db5  ldfld    string WorkflowContentType::ContentTypeDescription
0x481dba  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481dbf  ldloc.0
0x481dc0  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481dc5  ldsfld   string [mscorlib]System.String::Empty
0x481dca  ldstr    aFieldrefs// "FieldRefs"
0x481dcf  ldnull
0x481dd0  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x481dd5  stloc.s  5
0x481dd7  ldloc.3
0x481dd8  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> WorkflowContentType::FieldRefs
0x481ddd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [System]System.Collections.Generic.SortedList`2<string, string>::GetEnumerator()
0x481de2  stloc.s  0x2B
0x481de4  br.s     loc_481E4F
0x481de6  ldloc.s  0x2B
0x481de8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x481ded  stloc.s  6
0x481def  ldloc.0
0x481df0  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481df5  ldsfld   string [mscorlib]System.String::Empty
0x481dfa  ldstr    aFieldref// "FieldRef"
0x481dff  ldnull
0x481e00  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x481e05  stloc.s  7
0x481e07  ldloc.0
0x481e08  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481e0d  ldsfld   string [mscorlib]System.String::Empty
0x481e12  ldstr    aId_0// "ID"
0x481e17  ldnull
0x481e18  ldloca.s 6
0x481e1a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x481e1f  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481e24  ldloc.0
0x481e25  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481e2a  ldsfld   string [mscorlib]System.String::Empty
0x481e2f  ldstr    aName_0// "Name"
0x481e34  ldnull
0x481e35  ldloca.s 6
0x481e37  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x481e3c  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481e41  leave.s  loc_481E4F
0x481e43  ldloc.s  7
0x481e45  brfalse.s loc_481E4E
0x481e47  ldloc.s  7
0x481e49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481e4e  endfinally
0x481e4f  ldloc.s  0x2B
0x481e51  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x481e56  brtrue.s loc_481DE6
0x481e58  leave.s  loc_481E66
0x481e5a  ldloc.s  0x2B
0x481e5c  brfalse.s loc_481E65
0x481e5e  ldloc.s  0x2B
0x481e60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481e65  endfinally
0x481e66  leave.s  loc_481E74
0x481e68  ldloc.s  5
0x481e6a  brfalse.s loc_481E73
0x481e6c  ldloc.s  5
0x481e6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481e73  endfinally
0x481e74  ldarg.0
0x481e75  ldloc.0
0x481e76  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481e7b  ldarg.s  5
0x481e7d  call     instance void Microsoft.SharePoint.SPSolutionExporter::WriteWFDocuments(class [System.Xml]System.Xml.XmlWriter wfDoc, string workflowForm)
0x481e82  leave.s  loc_481E90
0x481e84  ldloc.s  4
0x481e86  brfalse.s loc_481E8F
0x481e88  ldloc.s  4
0x481e8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481e8f  endfinally
0x481e90  ldloca.s 0x2A
0x481e92  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class WorkflowContentType>::MoveNext()
0x481e97  brtrue   loc_481CF5
0x481e9c  leave.s  loc_481EAC
0x481e9e  ldloca.s 0x2A
0x481ea0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class WorkflowContentType>
0x481ea6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x481eab  endfinally
0x481eac  ldc.i4.0
0x481ead  stloc.s  8
0x481eaf  ldarg.1
0x481eb0  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class ListExportSummaryInfo> ListInstancesExportSummaryInfo::ListExportSummaryInfoEntries
0x481eb5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [System]System.Collections.Generic.SortedList`2<string, class ListExportSummaryInfo>::GetEnumerator()
0x481eba  stloc.s  0x2C
0x481ebc  br       loc_4820F7
0x481ec1  ldloc.s  0x2C
0x481ec3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class ListExportSummaryInfo>>::get_Current()
0x481ec8  stloc.s  9
0x481eca  ldloca.s 9
0x481ecc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class ListExportSummaryInfo>::get_Value()
0x481ed1  stloc.s  0xA
0x481ed3  ldloc.s  0xA
0x481ed5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class EventReceiver> ListExportSummaryInfo::eventReceivers
0x481eda  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class EventReceiver>::get_Count()
0x481edf  ldc.i4.0
0x481ee0  ble.s    loc_481EED
0x481ee2  ldarg.0
0x481ee3  ldfld    bool Microsoft.SharePoint.SPSolutionExporter::isExportingWorkflowServiceFolder
0x481ee8  brtrue.s loc_481EED
0x481eea  ldc.i4.1
0x481eeb  stloc.s  8
0x481eed  ldloc.0
0x481eee  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481ef3  ldsfld   string [mscorlib]System.String::Empty
0x481ef8  ldstr    aListinstance// "ListInstance"
0x481efd  ldnull
0x481efe  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x481f03  stloc.s  0xB
0x481f05  ldloc.0
0x481f06  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481f0b  ldsfld   string [mscorlib]System.String::Empty
0x481f10  ldstr    aFeatureid// "FeatureId"
0x481f15  ldnull
0x481f16  ldloc.s  0xA
0x481f18  ldfld    valuetype [mscorlib]System.Guid ListExportSummaryInfo::TemplateFeatureId
0x481f1d  box      [mscorlib]System.Guid
0x481f22  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x481f27  ldloc.0
0x481f28  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481f2d  ldsfld   string [mscorlib]System.String::Empty
0x481f32  ldstr    aTemplatetype// "TemplateType"
0x481f37  ldnull
0x481f38  ldloc.s  0xA
0x481f3a  ldfld    valuetype Microsoft.SharePoint.SPListTemplateType ListExportSummaryInfo::BaseTemplate
0x481f3f  box      [mscorlib]System.Int32
0x481f44  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x481f49  ldloc.0
0x481f4a  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481f4f  ldsfld   string [mscorlib]System.String::Empty
0x481f54  ldstr    aTitle_0// "Title"
0x481f59  ldnull
0x481f5a  ldloc.s  0xA
0x481f5c  ldfld    string ListExportSummaryInfo::Title
0x481f61  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481f66  ldloc.0
0x481f67  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481f6c  ldsfld   string [mscorlib]System.String::Empty
0x481f71  ldstr    aDescription// "Description"
0x481f76  ldnull
0x481f77  ldloc.s  0xA
0x481f79  ldfld    string ListExportSummaryInfo::Description
0x481f7e  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481f83  ldloc.0
0x481f84  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x481f89  ldsfld   string [mscorlib]System.String::Empty
0x481f8e  ldstr    aUrl// "Url"
0x481f93  ldnull
0x481f94  ldloc.s  0xA
0x481f96  ldfld    string ListExportSummaryInfo::RootFolderUrl
0x481f9b  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x481fa0  ldloc.0
0x481fa1  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
  ... truncated ...
```
