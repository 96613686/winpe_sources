# Microsoft.SharePoint.SPSolutionExporter::ExportList

- ea: `0x482f10`
- end: `0x483d01`
- name: `Microsoft.SharePoint.SPSolutionExporter::ExportList`
- size: `3569`
- prototype: ``
- caller_count: `1`
- callee_count: `102`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x481910`

## callees

- `0x342e50`
- `0x342e60`
- `0x342f70`
- `0x3431e0`
- `0x343640`
- `0x343930`
- `0x343980`
- `0x343aa0`
- `0x343e80`
- `0x344030`
- `0x344680`
- `0x3446d0`
- `0x344790`
- `0x344830`
- `0x344a10`
- `0x344aa0`
- `0x344c40`
- `0x344e10`
- `0x345490`
- `0x345560`
- `0x345780`
- `0x345950`
- `0x345a20`
- `0x345ab0`
- `0x345b40`
- `0x345c30`
- `0x345d00`
- `0x345e40`
- `0x345f90`
- `0x346060`
- `0x346150`
- `0x346240`
- `0x3462c0`
- `0x346350`
- `0x346550`
- `0x346630`
- `0x3466f0`
- `0x3467e0`
- `0x346860`
- `0x3468d0`
- `0x346ba0`
- `0x346c40`
- `0x346d00`
- `0x346dc0`
- `0x346e60`
- `0x346ef0`
- `0x347060`
- `0x3471d0`
- `0x3474d0`
- `0x347690`

## string_xrefs

- `0x4831a8`: `http://schemas.microsoft.com/sharepoint/`
- `0x483c1b`: `xmlns`
- `0x483c37`: `xmlns`
- `0x483991`: `DefaultItemOpen`
- `0x4839af`: `DefaultItemOpenUseListSetting`
- `0x4832d6`: `DontSaveInTemplate`
- `0x483366`: `CacheSchema`
- `0x483585`: `NeedUpdateSiteClientTag`
- `0x483465`: `ReadOnlyUI`
- `0x483489`: `RestrictUserUpdates`
- `0x4830b8`: `Unable to find template file in collection: {0}`
- `0x4830dd`: `Marked file as template file for list: {0}`
- `0x48310f`: `Schema.xml`
- `0x48313b`: `Creating schema file for list '{0}' from '{1}' at staging area path '{2}'`
- `0x483342`: `RestrictedTemplate`
- `0x483bd7`: `SecurityBits`
- `0x483c42`: `http://schemas.microsoft.com/sharepoint/v3/contenttype/forms`

## pseudocode

```c

```

## disassembly

```asm
0x482f10  ldc.i4   0xDA3D4
0x482f15  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x482f1a  ldarg.1
0x482f1b  ldstr    aList// "list"
0x482f20  call     void Microsoft.SharePoint.Utilities.Verify::ArgumentNotNullTag(unsigned int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat category, object parameterValue, string parameterName)
0x482f25  ldc.i4   0xDA3D5
0x482f2a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x482f2f  ldc.i4.s 0x64
0x482f31  ldstr    aExportingList0// "Exporting list '{0}' with root folder '"...
0x482f36  ldc.i4.2
0x482f37  newarr   [mscorlib]System.Object
0x482f3c  stloc.s  0xA
0x482f3e  ldloc.s  0xA
0x482f40  ldc.i4.0
0x482f41  ldarg.1
0x482f42  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x482f47  stelem.ref
0x482f48  ldloc.s  0xA
0x482f4a  ldc.i4.1
0x482f4b  ldarg.1
0x482f4c  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x482f51  callvirt instance string Microsoft.SharePoint.SPFolder::get_Url()
0x482f56  stelem.ref
0x482f57  ldloc.s  0xA
0x482f59  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x482f5e  newobj   instance void ListExportSummaryInfo::.ctor()
0x482f63  stloc.0
0x482f64  ldloc.0
0x482f65  ldarg.1
0x482f66  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x482f6b  stfld    string ListExportSummaryInfo::Title
0x482f70  ldloc.0
0x482f71  ldarg.1
0x482f72  callvirt instance string Microsoft.SharePoint.SPList::get_Description()
0x482f77  stfld    string ListExportSummaryInfo::Description
0x482f7c  ldloc.0
0x482f7d  ldarg.1
0x482f7e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_TemplateFeatureId()
0x482f83  stfld    valuetype [mscorlib]System.Guid ListExportSummaryInfo::TemplateFeatureId
0x482f88  ldloc.0
0x482f89  ldarg.1
0x482f8a  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0x482f8f  stfld    valuetype Microsoft.SharePoint.SPListTemplateType ListExportSummaryInfo::BaseTemplate
0x482f94  ldloc.0
0x482f95  ldarg.1
0x482f96  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x482f9b  callvirt instance string Microsoft.SharePoint.SPFolder::get_Url()
0x482fa0  stfld    string ListExportSummaryInfo::RootFolderUrl
0x482fa5  ldloc.0
0x482fa6  ldarg.1
0x482fa7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0x482fac  stfld    valuetype [mscorlib]System.Guid ListExportSummaryInfo::ID
0x482fb1  ldc.i4.0
0x482fb2  conv.i8
0x482fb3  ldarg.1
0x482fb4  callvirt instance unsigned int64 Microsoft.SharePoint.SPList::get_Flags()
0x482fb9  ldc.i4   0x4000
0x482fbe  conv.i8
0x482fbf  and
0x482fc0  beq.s    loc_482FCB
0x482fc2  ldloc.0
0x482fc3  ldc.i4.1
0x482fc4  stfld    bool ListExportSummaryInfo::IsRootWebOnly
0x482fc9  br.s     loc_482FD2
0x482fcb  ldloc.0
0x482fcc  ldc.i4.0
0x482fcd  stfld    bool ListExportSummaryInfo::IsRootWebOnly
0x482fd2  ldarg.0
0x482fd3  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class ExportPropertyBag> Microsoft.SharePoint.SPSolutionExporter::propertiesOfFolders
0x482fd8  ldarg.1
0x482fd9  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x482fde  callvirt instance string Microsoft.SharePoint.SPFolder::get_Url()
0x482fe3  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class ExportPropertyBag>::ContainsKey(var<u1>)
0x482fe8  brtrue.s loc_48301C
0x482fea  ldarg.0
0x482feb  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class ExportPropertyBag> Microsoft.SharePoint.SPSolutionExporter::propertiesOfFolders
0x482ff0  ldarg.1
0x482ff1  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x482ff6  callvirt instance string Microsoft.SharePoint.SPFolder::get_Url()
0x482ffb  ldarg.1
0x482ffc  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x483001  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPFolder::get_Properties()
0x483006  ldstr    aFolder_0// "Folder"
0x48300b  ldc.i4.0
0x48300c  ldloc.0
0x48300d  ldfld    bool ListExportSummaryInfo::IsRootWebOnly
0x483012  newobj   instance void ExportPropertyBag::.ctor(class [mscorlib]System.Collections.Hashtable properties, string _parentType, bool _includeItem, bool _isRootWebOnly)
0x483017  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, class ExportPropertyBag>::Add(var<u1>, !!T0)
0x48301c  ldloc.0
0x48301d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class EventReceiver>::.ctor()
0x483022  stfld    class [mscorlib]System.Collections.Generic.List`1<class EventReceiver> ListExportSummaryInfo::eventReceivers
0x483027  ldarg.1
0x483028  callvirt instance class Microsoft.SharePoint.SPListDataSource Microsoft.SharePoint.SPList::get_DataSource()
0x48302d  brfalse.s loc_483040
0x48302f  ldloc.0
0x483030  ldarg.1
0x483031  callvirt instance class Microsoft.SharePoint.SPListDataSource Microsoft.SharePoint.SPList::get_DataSource()
0x483036  callvirt instance string Microsoft.SharePoint.SPListDataSource::ToXml()
0x48303b  stfld    string ListExportSummaryInfo::DataSourceXml
0x483040  ldarg.0
0x483041  ldarg.1
0x483042  callvirt instance class Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection Microsoft.SharePoint.SPList::get_WorkflowAssociations()
0x483047  ldloc.0
0x483048  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class WorkflowAssociationExportSummaryInfo> ListExportSummaryInfo::WorkflowAssociationSummaryInfoEntries
0x48304d  ldnull
0x48304e  call     instance void Microsoft.SharePoint.SPSolutionExporter::ExportWorkflowAssociations(class Microsoft.SharePoint.Workflow.SPWorkflowAssociationCollection workflowAssociations, class [System]System.Collections.Generic.SortedList`2<string, class WorkflowAssociationExportSummaryInfo> summaryInfo, string contentTypeName)
0x483053  ldarg.0
0x483054  ldarg.1
0x483055  callvirt instance class Microsoft.SharePoint.SPEventReceiverDefinitionCollection Microsoft.SharePoint.SPList::get_EventReceivers()
0x48305a  ldloc.0
0x48305b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class EventReceiver> ListExportSummaryInfo::eventReceivers
0x483060  call     instance void Microsoft.SharePoint.SPSolutionExporter::ExportEventReceivers(class Microsoft.SharePoint.SPEventReceiverDefinitionCollection listEventReceiver, class [mscorlib]System.Collections.Generic.List`1<class EventReceiver> summaryInfo)
0x483065  ldarg.1
0x483066  isinst   Microsoft.SharePoint.SPDocumentLibrary
0x48306b  stloc.1
0x48306c  ldloc.1
0x48306d  brfalse  loc_4830FB
0x483072  ldloc.1
0x483073  callvirt instance string Microsoft.SharePoint.SPDocumentLibrary::get_DocumentTemplateUrl()
0x483078  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48307d  brtrue.s loc_4830FB
0x48307f  ldarg.1
0x483080  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x483085  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x48308a  ldloc.1
0x48308b  callvirt instance string Microsoft.SharePoint.SPDocumentLibrary::get_DocumentTemplateUrl()
0x483090  call     string Microsoft.SharePoint.SPSolutionExporter::GetWebRelativeUrl(string webUrl, string itemUrl)
0x483095  stloc.2
0x483096  ldloc.2
0x483097  brfalse.s loc_4830FB
0x483099  ldarg.0
0x48309a  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class SPFileInfo> Microsoft.SharePoint.SPSolutionExporter::filesNotExportedYet
0x48309f  ldloc.2
0x4830a0  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<string, class SPFileInfo>::get_Item(void)
0x4830a5  stloc.3
0x4830a6  ldloc.3
0x4830a7  ldc.i4.1
0x4830a8  stfld    bool SPFileInfo::IsDocumentTemplate
0x4830ad  ldc.i4   0xDA3D6
0x4830b2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x4830b7  ldloc.3
0x4830b8  ldstr    aUnableToFindTe// "Unable to find template file in collect"...
0x4830bd  ldc.i4.1
0x4830be  newarr   [mscorlib]System.Object
0x4830c3  stloc.s  0xB
0x4830c5  ldloc.s  0xB
0x4830c7  ldc.i4.0
0x4830c8  ldloc.2
0x4830c9  stelem.ref
0x4830ca  ldloc.s  0xB
0x4830cc  call     void Microsoft.SharePoint.Utilities.Verify::NotNullTag(unsigned int32 tag, class Microsoft.SharePoint.Diagnostics.ULSCat category, object obj, string format, object[] args)
0x4830d1  ldc.i4   0xDA3D7
0x4830d6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x4830db  ldc.i4.s 0x64
0x4830dd  ldstr    aMarkedFileAsTe// "Marked file as template file for list: "...
0x4830e2  ldc.i4.1
0x4830e3  newarr   [mscorlib]System.Object
0x4830e8  stloc.s  0xC
0x4830ea  ldloc.s  0xC
0x4830ec  ldc.i4.0
0x4830ed  ldloc.3
0x4830ee  ldfld    string SPFileInfo::Url
0x4830f3  stelem.ref
0x4830f4  ldloc.s  0xC
0x4830f6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x4830fb  ldloc.0
0x4830fc  ldfld    string ListExportSummaryInfo::RootFolderUrl
0x483101  ldstr    aFiles// "Files"
0x483106  call     string Microsoft.SharePoint.SPSolutionExporter::ConvertWebRelativeUrlToPartitionedRelativePath(string webRelativeUrl, string partitionName)
0x48310b  stloc.s  4
0x48310d  ldloc.s  4
0x48310f  ldstr    aSchemaXml// "Schema.xml"
0x483114  call     string Microsoft.SharePoint.SPSolutionExporter::PathCombine(string path1, string path2)
0x483119  stloc.s  5
0x48311b  ldarg.0
0x48311c  ldloc.s  5
0x48311e  ldc.i4.s 0x5C
0x483120  call     instance string Microsoft.SharePoint.SPSolutionExporter::CleanPathName(string pathname, char splitOn)
0x483125  stloc.s  5
0x483127  ldloc.0
0x483128  ldloc.s  5
0x48312a  stfld    string ListExportSummaryInfo::SchemaFilePath
0x48312f  ldc.i4   0xDA3D8
0x483134  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x483139  ldc.i4.s 0x64
0x48313b  ldstr    aCreatingSchema// "Creating schema file for list '{0}' fro"...
0x483140  ldc.i4.3
0x483141  newarr   [mscorlib]System.Object
0x483146  stloc.s  0xD
0x483148  ldloc.s  0xD
0x48314a  ldc.i4.0
0x48314b  ldarg.1
0x48314c  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x483151  stelem.ref
0x483152  ldloc.s  0xD
0x483154  ldc.i4.1
0x483155  ldloc.0
0x483156  ldfld    string ListExportSummaryInfo::RootFolderUrl
0x48315b  stelem.ref
0x48315c  ldloc.s  0xD
0x48315e  ldc.i4.2
0x48315f  ldarg.0
0x483160  ldfld    string Microsoft.SharePoint.SPSolutionExporter::ListInstancesPartitionName
0x483165  ldloc.s  5
0x483167  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x48316c  stelem.ref
0x48316d  ldloc.s  0xD
0x48316f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x483174  ldarg.0
0x483175  ldarg.0
0x483176  ldfld    string Microsoft.SharePoint.SPSolutionExporter::ListInstancesPartitionName
0x48317b  ldloc.s  5
0x48317d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x483182  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.SPSolutionExporter::CreateXmlWriterInStagingArea(string xmlFileRelativeName)
0x483187  ldarg.0
0x483188  ldfld    string Microsoft.SharePoint.SPSolutionExporter::ListInstancesPartitionName
0x48318d  ldloc.s  5
0x48318f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x483194  newobj   instance void Microsoft.SharePoint.ScopedXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string streamIdentifier)
0x483199  stloc.s  6
0x48319b  ldloc.s  6
0x48319d  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4831a2  ldnull
0x4831a3  ldstr    aList_0// "List"
0x4831a8  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sharepoint"...
0x4831ad  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x4831b2  stloc.s  7
0x4831b4  ldloc.s  6
0x4831b6  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4831bb  ldnull
0x4831bc  ldstr    aTitle_0// "Title"
0x4831c1  ldnull
0x4831c2  ldarg.1
0x4831c3  callvirt instance string Microsoft.SharePoint.SPList::get_Title()
0x4831c8  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x4831cd  ldloc.s  6
0x4831cf  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4831d4  ldnull
0x4831d5  ldstr    aDirection_0// "Direction"
0x4831da  ldnull
0x4831db  ldarg.1
0x4831dc  callvirt instance string Microsoft.SharePoint.SPList::get_Direction()
0x4831e1  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x4831e6  ldloc.s  6
0x4831e8  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4831ed  ldnull
0x4831ee  ldstr    aUrl// "Url"
0x4831f3  ldnull
0x4831f4  ldloc.0
0x4831f5  ldfld    string ListExportSummaryInfo::RootFolderUrl
0x4831fa  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x4831ff  ldloc.s  6
0x483201  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x483206  ldnull
0x483207  ldstr    aBasetype_1// "BaseType"
0x48320c  ldnull
0x48320d  ldarg.1
0x48320e  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x483213  box      [mscorlib]System.Int32
0x483218  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x48321d  ldloc.s  6
0x48321f  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x483224  ldnull
0x483225  ldstr    aType// "Type"
0x48322a  ldnull
0x48322b  ldarg.1
0x48322c  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0x483231  box      [mscorlib]System.Int32
0x483236  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x48323b  ldloc.s  6
0x48323d  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x483242  ldnull
0x483243  ldstr    aAllowdeletion// "AllowDeletion"
0x483248  ldnull
0x483249  ldarg.1
0x48324a  callvirt instance bool Microsoft.SharePoint.SPList::get_AllowDeletion()
0x48324f  box      [mscorlib]System.Boolean
0x483254  ldc.i4.1
0x483255  box      [mscorlib]System.Boolean
0x48325a  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x48325f  ldloc.s  6
0x483261  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x483266  ldnull
0x483267  ldstr    aMultipledatali// "MultipleDataList"
0x48326c  ldnull
0x48326d  ldarg.1
0x48326e  callvirt instance bool Microsoft.SharePoint.SPList::get_MultipleDataList()
0x483273  box      [mscorlib]System.Boolean
0x483278  ldc.i4.1
0x483279  box      [mscorlib]System.Boolean
0x48327e  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x483283  ldloc.s  6
0x483285  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x48328a  ldnull
0x48328b  ldstr    aEmailassignto// "EmailAssignTo"
0x483290  ldnull
0x483291  ldarg.1
0x483292  callvirt instance bool Microsoft.SharePoint.SPList::get_EnableAssignToEmail()
0x483297  box      [mscorlib]System.Boolean
0x48329c  ldc.i4.0
  ... truncated ...
```
