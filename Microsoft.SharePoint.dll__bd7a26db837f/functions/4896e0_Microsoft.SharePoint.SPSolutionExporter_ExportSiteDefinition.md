# Microsoft.SharePoint.SPSolutionExporter::ExportSiteDefinition

- ea: `0x4896e0`
- end: `0x48a134`
- name: `Microsoft.SharePoint.SPSolutionExporter::ExportSiteDefinition`
- size: `2644`
- prototype: ``
- caller_count: `1`
- callee_count: `51`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x47f9b0`

## callees

- `0x26cdd0`
- `0x26ce20`
- `0x489370`
- `0x4896e0`
- `0x48c490`
- `0x48c4e0`
- `0x48c550`
- `0x48c8b0`
- `0x48d1b0`
- `0x48d5d0`
- `0x48d890`
- `0x48e320`
- `0x48ea30`
- `0x48ebf0`
- `0x576060`
- `0x5760b0`
- `0x576190`
- `0x5761b0`
- `0x5761d0`
- `0x5761f0`
- `0x5adb80`
- `0x5c24f0`
- `0x5c2b20`
- `0x5c2bb0`
- `0x5c2c50`
- `0x5c2cd0`
- `0x5c2fc0`
- `0x5c3b50`
- `0x5c3e90`
- `0x5c43d0`
- `0x5c4440`
- `0x5c4cc0`
- `0x5c4e10`
- `0x5c4e60`
- `0x5c5090`
- `0x5c5100`
- `0x5c5160`
- `0x5c5200`
- `0x5c5430`
- `0x5c54a0`
- `0x5c5510`
- `0x5c55e0`
- `0x5c5760`
- `0x5c57f0`
- `0x5c5830`
- `0x5c5850`
- `0x5c5ac0`
- `0x5cea00`
- `0x6c9890`
- `0x93dae0`

## string_xrefs

- `0x4897c3`: `WebTemplate`
- `0x4897ab`: `http://schemas.microsoft.com/sharepoint/`
- `0x4897c8`: `http://schemas.microsoft.com/sharepoint/`
- `0x489de6`: `http://schemas.microsoft.com/sharepoint/`
- `0x48a08d`: `http://schemas.microsoft.com/sharepoint/`
- `0x48a0aa`: `http://schemas.microsoft.com/sharepoint/`
- `0x489f81`: `ElementManifest`
- `0x489a31`: `HasPendingWebTemplateExtension`
- `0x489a49`: `HasPendingWebTemplateExtension`
- `0x489751`: `Elements.xml`
- `0x489d84`: `Feature.xml`
- `0x489f68`: `ElementManifests`
- `0x4896ec`: `ONet.xml`
- `0x48976f`: `Creating site template feature manifest file '{0}'`
- `0x489854`: `BaseTemplateID`
- `0x48987b`: `BaseTemplateName`
- `0x48989d`: `BaseConfigurationID`
- `0x48990a`: `CommentsOnSitePagesDisabled`
- `0x489c11`: `HideSiteContentsLink`
- `0x489d3f`: `UIVersionConfigurationEnabled`
- `0x489e26`: `Web Template feature of exported web template `
- `0x48a0c8`: `GeneratedBySaveAsTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4896e0  newobj   instance void SiteTemplateExportSummaryInfo::.ctor()
0x4896e5  stloc.0
0x4896e6  ldarg.0
0x4896e7  ldfld    string Microsoft.SharePoint.SPSolutionExporter::solutionName
0x4896ec  ldstr    aOnetXml// "ONet.xml"
0x4896f1  call     string Microsoft.SharePoint.SPSolutionExporter::PathCombine(string path1, string path2)
0x4896f6  stloc.2
0x4896f7  ldloc.2
0x4896f8  ldarg.0
0x4896f9  ldfld    string Microsoft.SharePoint.SPSolutionExporter::SiteDefinitionPartitionName
0x4896fe  call     string Microsoft.SharePoint.SPSolutionExporter::ConvertWebRelativeUrlToPartitionedRelativePath(string webRelativeUrl, string partitionName)
0x489703  stloc.3
0x489704  ldc.i4   0xDA45B
0x489709  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x48970e  ldc.i4.s 0x64
0x489710  ldstr    aCreatingSiteDe// "Creating site definition file '{0}'"
0x489715  ldc.i4.1
0x489716  newarr   [mscorlib]System.Object
0x48971b  stloc.s  0x16
0x48971d  ldloc.s  0x16
0x48971f  ldc.i4.0
0x489720  ldloc.3
0x489721  stelem.ref
0x489722  ldloc.s  0x16
0x489724  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x489729  ldarg.0
0x48972a  ldloc.3
0x48972b  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.SPSolutionExporter::CreateXmlWriterInStagingArea(string xmlFileRelativeName)
0x489730  ldloc.3
0x489731  newobj   instance void Microsoft.SharePoint.ScopedXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string streamIdentifier)
0x489736  stloc.s  4
0x489738  ldarg.0
0x489739  ldarg.1
0x48973a  ldarg.2
0x48973b  ldloc.s  4
0x48973d  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.SPSolutionExporter::SiteTemplateExportDocElemAndAttrs(valuetype [mscorlib]System.Guid[] featureGuids, string[] comments, class Microsoft.SharePoint.ScopedXmlWriter scopedSiteDefinitionWriter)
0x489742  stloc.1
0x489743  leave.s  loc_489751
0x489745  ldloc.s  4
0x489747  brfalse.s loc_489750
0x489749  ldloc.s  4
0x48974b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x489750  endfinally
0x489751  ldstr    aElementsXml// "Elements.xml"
0x489756  ldarg.0
0x489757  ldfld    string Microsoft.SharePoint.SPSolutionExporter::SiteDefinitionPartitionName
0x48975c  call     string Microsoft.SharePoint.SPSolutionExporter::ConvertWebRelativeUrlToPartitionedRelativePath(string webRelativeUrl, string partitionName)
0x489761  stloc.s  5
0x489763  ldc.i4   0xDA45C
0x489768  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SolutionExporter()
0x48976d  ldc.i4.s 0x64
0x48976f  ldstr    aCreatingSiteTe// "Creating site template feature manifest"...
0x489774  ldc.i4.1
0x489775  newarr   [mscorlib]System.Object
0x48977a  stloc.s  0x17
0x48977c  ldloc.s  0x17
0x48977e  ldc.i4.0
0x48977f  ldloc.s  5
0x489781  stelem.ref
0x489782  ldloc.s  0x17
0x489784  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x489789  ldarg.0
0x48978a  ldloc.s  5
0x48978c  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.SPSolutionExporter::CreateXmlWriterInStagingArea(string xmlFileRelativeName)
0x489791  ldloc.s  5
0x489793  newobj   instance void Microsoft.SharePoint.ScopedXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string streamIdentifier)
0x489798  stloc.s  6
0x48979a  ldloc.s  6
0x48979c  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4897a1  ldstr    asc_C00000// ""
0x4897a6  ldstr    aElements// "Elements"
0x4897ab  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sharepoint"...
0x4897b0  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x4897b5  stloc.s  7
0x4897b7  ldloc.s  6
0x4897b9  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4897be  ldstr    asc_C00000// ""
0x4897c3  ldstr    aWebtemplate// "WebTemplate"
0x4897c8  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sharepoint"...
0x4897cd  newobj   instance void Microsoft.SharePoint.ScopedXmlWriterElement::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string prefix, string localName, string ns)
0x4897d2  stloc.s  8
0x4897d4  ldarg.0
0x4897d5  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x4897da  callvirt instance class Microsoft.SharePoint.SPRegionalSettings Microsoft.SharePoint.SPWeb::get_RegionalSettings()
0x4897df  stloc.s  9
0x4897e1  ldloc.s  6
0x4897e3  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4897e8  ldsfld   string [mscorlib]System.String::Empty
0x4897ed  ldstr    aAdjusthijriday_0// "AdjustHijriDays"
0x4897f2  ldnull
0x4897f3  ldloc.s  9
0x4897f5  callvirt instance int16 Microsoft.SharePoint.SPRegionalSettings::get_AdjustHijriDays()
0x4897fa  box      [mscorlib]System.Int16
0x4897ff  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489804  ldloc.s  6
0x489806  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x48980b  ldsfld   string [mscorlib]System.String::Empty
0x489810  ldstr    aAlternatecssur_0// "AlternateCssUrl"
0x489815  ldnull
0x489816  ldarg.0
0x489817  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x48981c  callvirt instance string Microsoft.SharePoint.SPWeb::get_AlternateCssUrl()
0x489821  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x489826  ldloc.s  6
0x489828  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x48982d  ldsfld   string [mscorlib]System.String::Empty
0x489832  ldstr    aAlternateheade_2// "AlternateHeader"
0x489837  ldnull
0x489838  ldarg.0
0x489839  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x48983e  callvirt instance string Microsoft.SharePoint.SPWeb::get_AlternateHeader()
0x489843  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x489848  ldloc.s  6
0x48984a  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x48984f  ldsfld   string [mscorlib]System.String::Empty
0x489854  ldstr    aBasetemplateid_0// "BaseTemplateID"
0x489859  ldnull
0x48985a  ldarg.0
0x48985b  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489860  callvirt instance int32 Microsoft.SharePoint.SPWeb::get_WebTemplateId()
0x489865  box      [mscorlib]System.Int32
0x48986a  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x48986f  ldloc.s  6
0x489871  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489876  ldsfld   string [mscorlib]System.String::Empty
0x48987b  ldstr    aBasetemplatena// "BaseTemplateName"
0x489880  ldnull
0x489881  ldarg.0
0x489882  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489887  callvirt instance string Microsoft.SharePoint.SPWeb::get_WebTemplate()
0x48988c  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x489891  ldloc.s  6
0x489893  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489898  ldsfld   string [mscorlib]System.String::Empty
0x48989d  ldstr    aBaseconfigurat// "BaseConfigurationID"
0x4898a2  ldnull
0x4898a3  ldarg.0
0x4898a4  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x4898a9  callvirt instance int16 Microsoft.SharePoint.SPWeb::get_Configuration()
0x4898ae  box      [mscorlib]System.Int16
0x4898b3  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x4898b8  ldloc.s  6
0x4898ba  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4898bf  ldsfld   string [mscorlib]System.String::Empty
0x4898c4  ldstr    aCalendartype_0// "CalendarType"
0x4898c9  ldnull
0x4898ca  ldloc.s  9
0x4898cc  callvirt instance int16 Microsoft.SharePoint.SPRegionalSettings::get_CalendarType()
0x4898d1  box      [mscorlib]System.Int16
0x4898d6  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x4898db  ldloc.s  6
0x4898dd  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4898e2  ldsfld   string [mscorlib]System.String::Empty
0x4898e7  ldstr    aCollation_2// "Collation"
0x4898ec  ldnull
0x4898ed  ldloc.s  9
0x4898ef  callvirt instance int16 Microsoft.SharePoint.SPRegionalSettings::get_Collation()
0x4898f4  box      [mscorlib]System.Int16
0x4898f9  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x4898fe  ldloc.s  6
0x489900  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489905  ldsfld   string [mscorlib]System.String::Empty
0x48990a  ldstr    aCommentsonsite_2// "CommentsOnSitePagesDisabled"
0x48990f  ldnull
0x489910  ldarg.0
0x489911  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489916  callvirt instance bool Microsoft.SharePoint.SPWeb::get_CommentsOnSitePagesDisabled()
0x48991b  box      [mscorlib]System.Boolean
0x489920  ldc.i4.0
0x489921  box      [mscorlib]System.Boolean
0x489926  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x48992b  ldloc.s  6
0x48992d  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489932  ldsfld   string [mscorlib]System.String::Empty
0x489937  ldstr    aContainsdefaul// "ContainsDefaultLists"
0x48993c  ldnull
0x48993d  ldc.i4.1
0x48993e  box      [mscorlib]System.Boolean
0x489943  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489948  ldloc.s  6
0x48994a  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x48994f  ldsfld   string [mscorlib]System.String::Empty
0x489954  ldstr    aCustomizedcssf_0// "CustomizedCssFiles"
0x489959  ldnull
0x48995a  ldarg.0
0x48995b  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489960  callvirt instance string Microsoft.SharePoint.SPWeb::BuildCustomizedCssFileListForExport()
0x489965  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x48996a  ldloc.s  6
0x48996c  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489971  ldsfld   string [mscorlib]System.String::Empty
0x489976  ldstr    aCustomjsurl_0// "CustomJSUrl"
0x48997b  ldnull
0x48997c  ldarg.0
0x48997d  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489982  callvirt instance string Microsoft.SharePoint.SPWeb::get_CustomJSUrl()
0x489987  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, string unencodedAttributeValue)
0x48998c  ldloc.s  6
0x48998e  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489993  ldsfld   string [mscorlib]System.String::Empty
0x489998  ldstr    aDescription// "Description"
0x48999d  ldnull
0x48999e  ldarg.0
0x48999f  ldfld    string Microsoft.SharePoint.SPSolutionExporter::solutionDescription
0x4899a4  ldsfld   string [mscorlib]System.String::Empty
0x4899a9  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x4899ae  ldloc.s  6
0x4899b0  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x4899b5  ldsfld   string [mscorlib]System.String::Empty
0x4899ba  ldstr    aDesignpackagei_0// "DesignPackageId"
0x4899bf  ldnull
0x4899c0  ldarg.0
0x4899c1  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x4899c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_DesignPackageId()
0x4899cb  box      [mscorlib]System.Guid
0x4899d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4899d5  box      [mscorlib]System.Guid
0x4899da  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x4899df  ldstr    a01c1e5aa2c9948// "01C1E5AA-2C99-486F-B0F6-357F64A3894B"
0x4899e4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4899e9  ldstr    a6232017// "6/23/2017"
0x4899ee  ldstr    aSupportswebfla// "SupportsWebFlags2"
0x4899f3  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x4899f8  brtrue.s loc_489A27
0x4899fa  ldloc.s  6
0x4899fc  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489a01  ldsfld   string [mscorlib]System.String::Empty
0x489a06  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x489a0b  ldnull
0x489a0c  ldarg.0
0x489a0d  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489a12  callvirt instance bool Microsoft.SharePoint.SPWeb::get_HorizontalQuickLaunch()
0x489a17  box      [mscorlib]System.Boolean
0x489a1c  ldc.i4.0
0x489a1d  box      [mscorlib]System.Boolean
0x489a22  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x489a27  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::HasPendingWebTemplateExtensionKillSwitchId
0x489a2c  ldstr    a6282017// "6/28/2017"
0x489a31  ldstr    aHaspendingwebt// "HasPendingWebTemplateExtension"
0x489a36  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x489a3b  brtrue.s loc_489A6A
0x489a3d  ldloc.s  6
0x489a3f  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489a44  ldsfld   string [mscorlib]System.String::Empty
0x489a49  ldstr    aHaspendingwebt// "HasPendingWebTemplateExtension"
0x489a4e  ldnull
0x489a4f  ldarg.0
0x489a50  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489a55  callvirt instance bool Microsoft.SharePoint.SPWeb::get_HasPendingWebTemplateExtension()
0x489a5a  box      [mscorlib]System.Boolean
0x489a5f  ldc.i4.0
0x489a60  box      [mscorlib]System.Boolean
0x489a65  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttributeIfNotDefault(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue, object defaultValue)
0x489a6a  ldloc.s  6
0x489a6c  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489a71  ldsfld   string [mscorlib]System.String::Empty
0x489a76  ldstr    aDisableappview// "DisableAppViews"
0x489a7b  ldnull
0x489a7c  ldarg.0
0x489a7d  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489a82  callvirt instance bool Microsoft.SharePoint.SPWeb::get_InternalDisableAppViews()
0x489a87  box      [mscorlib]System.Boolean
0x489a8c  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489a91  ldloc.s  6
0x489a93  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489a98  ldsfld   string [mscorlib]System.String::Empty
0x489a9d  ldstr    aDisableflows// "DisableFlows"
0x489aa2  ldnull
0x489aa3  ldarg.0
0x489aa4  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489aa9  callvirt instance bool Microsoft.SharePoint.SPWeb::get_InternalDisableFlows()
0x489aae  box      [mscorlib]System.Boolean
0x489ab3  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489ab8  ldloc.s  6
0x489aba  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489abf  ldsfld   string [mscorlib]System.String::Empty
0x489ac4  ldstr    aExcludefromoff// "ExcludeFromOfflineClient"
0x489ac9  ldnull
0x489aca  ldarg.0
0x489acb  ldfld    class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSolutionExporter::web
0x489ad0  callvirt instance bool Microsoft.SharePoint.SPWeb::get_ExcludeFromOfflineClient()
0x489ad5  box      [mscorlib]System.Boolean
0x489ada  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489adf  ldloc.s  6
0x489ae1  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489ae6  ldsfld   string [mscorlib]System.String::Empty
0x489aeb  ldstr    aLocale_0// "Locale"
0x489af0  ldnull
0x489af1  ldloc.s  9
0x489af3  callvirt instance unsigned int32 Microsoft.SharePoint.SPRegionalSettings::get_LocaleId()
0x489af8  box      [mscorlib]System.UInt32
0x489afd  call     void Microsoft.SharePoint.SPSolutionExporter::WriteXmlAttribute(class [System.Xml]System.Xml.XmlWriter xmlWriter, string prefix, string localName, string ns, object unencodedAttributeValue)
0x489b02  ldloc.s  6
0x489b04  callvirt instance var<u1> class Microsoft.SharePoint.ScopedObject`1<class [System.Xml]System.Xml.XmlWriter>::get_Value()
0x489b09  ldsfld   string [mscorlib]System.String::Empty
0x489b0e  ldstr    aName_0// "Name"
0x489b13  ldnull
0x489b14  ldarg.0
0x489b15  ldfld    string Microsoft.SharePoint.SPSolutionExporter::solutionName
0x489b1a  ldsfld   string [mscorlib]System.String::Empty
  ... truncated ...
```
