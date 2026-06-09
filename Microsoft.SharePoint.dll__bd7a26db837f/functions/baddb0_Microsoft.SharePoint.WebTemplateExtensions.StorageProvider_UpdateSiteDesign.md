# Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::UpdateSiteDesign

- ea: `0xbaddb0`
- end: `0xbae092`
- name: `Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::UpdateSiteDesign`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3e99e0`
- `0x3e99f0`
- `0x3e9a20`
- `0x7be4d0`
- `0x7be510`
- `0x7be550`
- `0x7be580`
- `0x7beb40`
- `0x7fccd0`
- `0x7fccf0`
- `0x7fcd10`
- `0x7fcd30`
- `0x7fcd50`
- `0x7fcd70`
- `0x7fcd90`
- `0x7fcf10`
- `0x7fcf30`
- `0x93dae0`
- `0xbada10`
- `0xbaddb0`
- `0xbae0a0`
- `0xbae250`
- `0xbae3c0`
- `0xbae500`
- `0xbae640`

## string_xrefs

- `0xbadde0`: `updateInfo`
- `0xbade0e`: `updateInfo.Title`
- `0xbade6a`: `updateInfo.Id`
- `0xbadee1`: `FormulaWebTemplate`
- `0xbadf95`: `FormulaWebTemplate`
- `0xbaddb0`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign`
- `0xbaddd5`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign: updateInfo is null`
- `0xbade03`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign: updateInfo.Title is empty`
- `0xbade31`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign: updateInfo.WebTemplate is empty`
- `0xbade3c`: `updateInfo.WebTemplate`
- `0xbade5f`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign: updateInfo.Id is empty`
- `0xbadeaa`: `StorageProvider.UpdateSiteDesign: Failed to retrieve list item`
- `0xbadfdf`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign failed restore Default to item: {0}`
- `0xbae020`: `StorageProvider.UpdateSiteDesign: Failed to retrieve list item after update`
- `0xbae04f`: `WebTemplateExtensions.StorageProvider.UpdateSiteDesign: table could not be retrieved`

## pseudocode

```c

```

## disassembly

```asm
0xbaddb0  ldstr    aWebtemplateext_124// "WebTemplateExtensions.StorageProvider.U"...
0xbaddb5  ldc.i4   0x188D8C3
0xbaddba  ldc.i4   0x188D8C4
0xbaddbf  ldc.i4   0x188D8C5
0xbaddc4  ldc.i4.0
0xbaddc5  ldnull
0xbaddc6  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbaddcb  stloc.0
0xbaddcc  ldarg.1
0xbaddcd  brtrue.s loc_BADDEB
0xbaddcf  ldloc.0
0xbaddd0  ldc.i4   0x188D8C6
0xbaddd5  ldstr    aWebtemplateext_125// "WebTemplateExtensions.StorageProvider.U"...
0xbaddda  ldnull
0xbadddb  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbadde0  ldstr    aUpdateinfo// "updateInfo"
0xbadde5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbaddea  throw
0xbaddeb  ldarg.1
0xbaddec  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_Title()
0xbaddf1  ldsfld   string [mscorlib]System.String::Empty
0xbaddf6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbaddfb  brfalse.s loc_BADE19
0xbaddfd  ldloc.0
0xbaddfe  ldc.i4   0x188D8C7
0xbade03  ldstr    aWebtemplateext_126// "WebTemplateExtensions.StorageProvider.U"...
0xbade08  ldnull
0xbade09  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbade0e  ldstr    aUpdateinfoTitl// "updateInfo.Title"
0xbade13  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbade18  throw
0xbade19  ldarg.1
0xbade1a  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_WebTemplate()
0xbade1f  ldsfld   string [mscorlib]System.String::Empty
0xbade24  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbade29  brfalse.s loc_BADE47
0xbade2b  ldloc.0
0xbade2c  ldc.i4   0x188D8C8
0xbade31  ldstr    aWebtemplateext_127// "WebTemplateExtensions.StorageProvider.U"...
0xbade36  ldnull
0xbade37  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbade3c  ldstr    aUpdateinfoWebt// "updateInfo.WebTemplate"
0xbade41  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbade46  throw
0xbade47  ldarg.1
0xbade48  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Id()
0xbade4d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbade52  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbade57  brfalse.s loc_BADE75
0xbade59  ldloc.0
0xbade5a  ldc.i4   0x188D8C9
0xbade5f  ldstr    aWebtemplateext_128// "WebTemplateExtensions.StorageProvider.U"...
0xbade64  ldnull
0xbade65  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbade6a  ldstr    aUpdateinfoId// "updateInfo.Id"
0xbade6f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbade74  throw
0xbade75  ldnull
0xbade76  stloc.1
0xbade77  ldc.i4.0
0xbade78  stloc.2
0xbade79  ldarg.0
0xbade7a  ldc.i4.1
0xbade7b  call     instance class DisposableObject`1<class Microsoft.SharePoint.SPList> Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetTable(valuetype ItemType itemType)
0xbade80  stloc.3
0xbade81  ldloc.3
0xbade82  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbade87  brfalse  loc_BAE049
0xbade8c  ldloc.3
0xbade8d  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbade92  ldarg.1
0xbade93  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Id()
0xbade98  ldc.i4.1
0xbade99  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetItemFromList(class Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid itemGuid, valuetype ItemType itemType)
0xbade9e  stloc.s  4
0xbadea0  ldloc.s  4
0xbadea2  brtrue.s loc_BADEBD
0xbadea4  ldloc.0
0xbadea5  ldc.i4   0x188D8CA
0xbadeaa  ldstr    aStorageprovide_8// "StorageProvider.UpdateSiteDesign: Faile"...
0xbadeaf  ldnull
0xbadeb0  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbadeb5  ldc.i4.1
0xbadeb6  stloc.2
0xbadeb7  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0xbadebc  throw
0xbadebd  ldarg.1
0xbadebe  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_Title()
0xbadec3  brfalse.s loc_BADED7
0xbadec5  ldloc.s  4
0xbadec7  ldstr    aTitle_0// "Title"
0xbadecc  ldarg.1
0xbadecd  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_Title()
0xbaded2  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbaded7  ldarg.1
0xbaded8  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_WebTemplate()
0xbadedd  brfalse.s loc_BADEF1
0xbadedf  ldloc.s  4
0xbadee1  ldstr    aFormulawebtemp// "FormulaWebTemplate"
0xbadee6  ldarg.1
0xbadee7  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_WebTemplate()
0xbadeec  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadef1  ldarg.1
0xbadef2  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_Description()
0xbadef7  brfalse.s loc_BADF0B
0xbadef9  ldloc.s  4
0xbadefb  ldstr    aFormuladescrip// "FormulaDescription"
0xbadf00  ldarg.1
0xbadf01  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_Description()
0xbadf06  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadf0b  ldarg.1
0xbadf0c  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_SiteScriptIds()
0xbadf11  brfalse.s loc_BADF2A
0xbadf13  ldloc.s  4
0xbadf15  ldstr    aFormularecipeg// "FormulaRecipeGuids"
0xbadf1a  ldarg.1
0xbadf1b  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_SiteScriptIds()
0xbadf20  call     string Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::SerializeGuidArray(valuetype [mscorlib]System.Guid[] guids)
0xbadf25  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadf2a  ldarg.1
0xbadf2b  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_PreviewImageUrl()
0xbadf30  brfalse.s loc_BADF44
0xbadf32  ldloc.s  4
0xbadf34  ldstr    aFormulapreview// "FormulaPreviewImage"
0xbadf39  ldarg.1
0xbadf3a  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_PreviewImageUrl()
0xbadf3f  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadf44  ldarg.1
0xbadf45  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_PreviewImageAltText()
0xbadf4a  brfalse.s loc_BADF5E
0xbadf4c  ldloc.s  4
0xbadf4e  ldstr    aFormulapicture// "FormulaPictureAltText"
0xbadf53  ldarg.1
0xbadf54  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_PreviewImageAltText()
0xbadf59  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadf5e  ldarg.1
0xbadf5f  callvirt instance int32 Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Version()
0xbadf64  ldc.i4.0
0xbadf65  ble.s    loc_BADF7E
0xbadf67  ldloc.s  4
0xbadf69  ldstr    aFormulaversion// "FormulaVersion"
0xbadf6e  ldarg.1
0xbadf6f  callvirt instance int32 Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Version()
0xbadf74  box      [mscorlib]System.Int32
0xbadf79  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadf7e  ldarg.0
0xbadf7f  ldloc.3
0xbadf80  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbadf85  ldloc.s  4
0xbadf87  ldarg.1
0xbadf88  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Id()
0xbadf8d  ldarg.1
0xbadf8e  callvirt instance bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignCreationInfo::get_IsDefault()
0xbadf93  ldloc.s  4
0xbadf95  ldstr    aFormulawebtemp// "FormulaWebTemplate"
0xbadf9a  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xbadf9f  isinst   [mscorlib]System.String
0xbadfa4  ldloca.s 1
0xbadfa6  call     instance void Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::SetSiteDesignIsDefault(class Microsoft.SharePoint.SPList siteDesignsTable, class Microsoft.SharePoint.SPListItem item, valuetype [mscorlib]System.Guid itemId, bool isDefault, string webTemplate, [out] class Microsoft.SharePoint.SPListItem& previousDefault)
0xbadfab  ldloc.s  4
0xbadfad  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0xbadfb2  leave.s  loc_BAE002
0xbadfb4  pop
0xbadfb5  ldloc.1
0xbadfb6  brfalse.s loc_BAE000
0xbadfb8  ldloc.1
0xbadfb9  ldstr    aFormulaisdefau// "FormulaIsDefault"
0xbadfbe  ldc.i4.1
0xbadfbf  box      [mscorlib]System.Boolean
0xbadfc4  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbadfc9  ldloc.1
0xbadfca  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0xbadfcf  leave.s  loc_BAE000
0xbadfd1  stloc.s  5
0xbadfd3  ldc.i4   0x2309749
0xbadfd8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetULSCat()
0xbadfdd  ldc.i4.s 0x32
0xbadfdf  ldstr    aWebtemplateext_129// "WebTemplateExtensions.StorageProvider.U"...
0xbadfe4  ldc.i4.1
0xbadfe5  newarr   [mscorlib]System.Object
0xbadfea  stloc.s  0xA
0xbadfec  ldloc.s  0xA
0xbadfee  ldc.i4.0
0xbadfef  ldloc.s  5
0xbadff1  callvirt instance string [mscorlib]System.Object::ToString()
0xbadff6  stelem.ref
0xbadff7  ldloc.s  0xA
0xbadff9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbadffe  leave.s  loc_BAE000
0xbae000  rethrow
0xbae002  ldloc.3
0xbae003  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbae008  ldarg.1
0xbae009  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata::get_Id()
0xbae00e  ldc.i4.1
0xbae00f  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetItemFromList(class Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid itemGuid, valuetype ItemType itemType)
0xbae014  stloc.s  6
0xbae016  ldloc.s  6
0xbae018  brtrue.s loc_BAE033
0xbae01a  ldloc.0
0xbae01b  ldc.i4   0x188D8CC
0xbae020  ldstr    aStorageprovide_9// "StorageProvider.UpdateSiteDesign: Faile"...
0xbae025  ldnull
0xbae026  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbae02b  ldc.i4.1
0xbae02c  stloc.2
0xbae02d  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0xbae032  throw
0xbae033  ldloc.s  6
0xbae035  call     class Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetSiteDesignMetadataFromItem(class Microsoft.SharePoint.SPListItem item)
0xbae03a  stloc.s  7
0xbae03c  ldloc.0
0xbae03d  ldnull
0xbae03e  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbae043  ldloc.s  7
0xbae045  stloc.s  9
0xbae047  leave.s  loc_BAE08F
0xbae049  ldloc.0
0xbae04a  ldc.i4   0x188D8CD
0xbae04f  ldstr    aWebtemplateext_130// "WebTemplateExtensions.StorageProvider.U"...
0xbae054  ldnull
0xbae055  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbae05a  leave.s  loc_BAE066
0xbae05c  ldloc.3
0xbae05d  brfalse.s loc_BAE065
0xbae05f  ldloc.3
0xbae060  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbae065  endfinally
0xbae066  leave.s  loc_BAE07D
0xbae068  stloc.s  8
0xbae06a  ldloc.2
0xbae06b  brtrue.s loc_BAE07B
0xbae06d  ldloc.0
0xbae06e  ldc.i4   0x188D8CE
0xbae073  ldloc.s  8
0xbae075  ldnull
0xbae076  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbae07b  rethrow
0xbae07d  leave.s  loc_BAE089
0xbae07f  ldloc.0
0xbae080  brfalse.s loc_BAE088
0xbae082  ldloc.0
0xbae083  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbae088  endfinally
0xbae089  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbae08e  throw
0xbae08f  ldloc.s  9
0xbae091  ret
```
