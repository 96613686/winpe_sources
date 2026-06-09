# Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::UpdateSiteScript

- ea: `0xbace40`
- end: `0xbad155`
- name: `Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::UpdateSiteScript`
- size: `789`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3e99f0`
- `0x3e9a20`
- `0x50c610`
- `0x50f8d0`
- `0x53e830`
- `0x6c9890`
- `0x7be4d0`
- `0x7be4f0`
- `0x7be510`
- `0x7be550`
- `0x7be580`
- `0x7beb40`
- `0x7fd390`
- `0x7fd3b0`
- `0x7fd3d0`
- `0x7fd3f0`
- `0x7fd410`
- `0x8ecdb0`
- `0x93dae0`
- `0xbac9a0`
- `0xbace40`
- `0xbae250`
- `0xbae500`
- `0xbae640`
- `0xbae670`

## string_xrefs

- `0xbace70`: `updateInfo`
- `0xbace40`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript`
- `0xbace65`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: updateInfo is null`
- `0xbace93`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: updateInfo.Title is missing`
- `0xbace9e`: `updateInfo.Title`
- `0xbacec1`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: updateInfo has no content`
- `0xbacecc`: `updateInfo.Content`
- `0xbacff6`: `updateInfo.Content`
- `0xbaceef`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: updateInfo.Id is empty`
- `0xbacefa`: `updateInfo.Id`
- `0xbacf68`: `StorageProvider.UpdateSiteScript: Failed to retrieve recipe list item`
- `0xbacf99`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: File created was null`
- `0xbacfbb`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: File did not exist`
- `0xbacfe9`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: Failed to convert info.Content to byte array`
- `0xbad0d8`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: Library could not be retrieved`
- `0xbad12c`: `WebTemplateExtensions.StorageProvider.UpdateSiteScript: Unexpected exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xbace40  ldstr    aWebtemplateext_90// "WebTemplateExtensions.StorageProvider.U"...
0xbace45  ldc.i4   0x188D898
0xbace4a  ldc.i4   0x188D899
0xbace4f  ldc.i4   0x188D89A
0xbace54  ldc.i4.0
0xbace55  ldnull
0xbace56  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbace5b  stloc.0
0xbace5c  ldarg.1
0xbace5d  brtrue.s loc_BACE7B
0xbace5f  ldloc.0
0xbace60  ldc.i4   0x188D89B
0xbace65  ldstr    aWebtemplateext_91// "WebTemplateExtensions.StorageProvider.U"...
0xbace6a  ldnull
0xbace6b  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbace70  ldstr    aUpdateinfo// "updateInfo"
0xbace75  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbace7a  throw
0xbace7b  ldarg.1
0xbace7c  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Title()
0xbace81  ldsfld   string [mscorlib]System.String::Empty
0xbace86  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbace8b  brfalse.s loc_BACEA9
0xbace8d  ldloc.0
0xbace8e  ldc.i4   0x188D89C
0xbace93  ldstr    aWebtemplateext_92// "WebTemplateExtensions.StorageProvider.U"...
0xbace98  ldnull
0xbace99  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbace9e  ldstr    aUpdateinfoTitl// "updateInfo.Title"
0xbacea3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbacea8  throw
0xbacea9  ldarg.1
0xbaceaa  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Content()
0xbaceaf  ldsfld   string [mscorlib]System.String::Empty
0xbaceb4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbaceb9  brfalse.s loc_BACED7
0xbacebb  ldloc.0
0xbacebc  ldc.i4   0x188D89D
0xbacec1  ldstr    aWebtemplateext_93// "WebTemplateExtensions.StorageProvider.U"...
0xbacec6  ldnull
0xbacec7  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacecc  ldstr    aUpdateinfoCont// "updateInfo.Content"
0xbaced1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbaced6  throw
0xbaced7  ldarg.1
0xbaced8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Id()
0xbacedd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbacee2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbacee7  brfalse.s loc_BACF05
0xbacee9  ldloc.0
0xbaceea  ldc.i4   0x188D89E
0xbaceef  ldstr    aWebtemplateext_94// "WebTemplateExtensions.StorageProvider.U"...
0xbacef4  ldnull
0xbacef5  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacefa  ldstr    aUpdateinfoId// "updateInfo.Id"
0xbaceff  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbacf04  throw
0xbacf05  ldc.i4.0
0xbacf06  stloc.1
0xbacf07  ldc.i4.0
0xbacf08  stloc.2
0xbacf09  ldarg.1
0xbacf0a  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Content()
0xbacf0f  brfalse.s loc_BACF34
0xbacf11  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::EnsureSiteScriptContentKillSwitch
0xbacf16  ldstr    a152018// "1/5/2018"
0xbacf1b  ldstr    aEnsuresitescri// "EnsureSiteScriptContent"
0xbacf20  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xbacf25  brtrue.s loc_BACF34
0xbacf27  ldarg.1
0xbacf28  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Content()
0xbacf2d  ldloca.s 1
0xbacf2f  call     void Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::EnsureSiteScriptContent(string content, [out] bool& scriptParseFailure)
0xbacf34  ldarg.0
0xbacf35  ldc.i4.0
0xbacf36  call     instance class DisposableObject`1<class Microsoft.SharePoint.SPList> Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetTable(valuetype ItemType itemType)
0xbacf3b  stloc.3
0xbacf3c  ldloc.3
0xbacf3d  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbacf42  brfalse  loc_BAD0D2
0xbacf47  ldloc.3
0xbacf48  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbacf4d  ldarg.1
0xbacf4e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Id()
0xbacf53  ldc.i4.0
0xbacf54  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetItemFromList(class Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid itemGuid, valuetype ItemType itemType)
0xbacf59  stloc.s  4
0xbacf5b  ldnull
0xbacf5c  stloc.s  5
0xbacf5e  ldloc.s  4
0xbacf60  brtrue.s loc_BACF7B
0xbacf62  ldloc.0
0xbacf63  ldc.i4   0x188D89F
0xbacf68  ldstr    aStorageprovide_2// "StorageProvider.UpdateSiteScript: Faile"...
0xbacf6d  ldnull
0xbacf6e  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacf73  ldc.i4.1
0xbacf74  stloc.2
0xbacf75  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0xbacf7a  throw
0xbacf7b  ldarg.1
0xbacf7c  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Content()
0xbacf81  brfalse  loc_BAD00A
0xbacf86  ldloc.s  4
0xbacf88  callvirt instance class Microsoft.SharePoint.SPFile Microsoft.SharePoint.SPListItem::get_File()
0xbacf8d  stloc.s  5
0xbacf8f  ldloc.s  5
0xbacf91  brtrue.s loc_BACFAC
0xbacf93  ldloc.0
0xbacf94  ldc.i4   0x188D8A0
0xbacf99  ldstr    aWebtemplateext_95// "WebTemplateExtensions.StorageProvider.U"...
0xbacf9e  ldnull
0xbacf9f  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacfa4  ldc.i4.1
0xbacfa5  stloc.2
0xbacfa6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacfab  throw
0xbacfac  ldloc.s  5
0xbacfae  callvirt instance bool Microsoft.SharePoint.SPFile::get_Exists()
0xbacfb3  brtrue.s loc_BACFCE
0xbacfb5  ldloc.0
0xbacfb6  ldc.i4   0x188D8A1
0xbacfbb  ldstr    aWebtemplateext_96// "WebTemplateExtensions.StorageProvider.U"...
0xbacfc0  ldnull
0xbacfc1  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacfc6  ldc.i4.1
0xbacfc7  stloc.2
0xbacfc8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacfcd  throw
0xbacfce  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xbacfd3  ldarg.1
0xbacfd4  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Content()
0xbacfd9  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xbacfde  stloc.s  6
0xbacfe0  leave.s  loc_BAD001
0xbacfe2  pop
0xbacfe3  ldloc.0
0xbacfe4  ldc.i4   0x188D8A2
0xbacfe9  ldstr    aWebtemplateext_97// "WebTemplateExtensions.StorageProvider.U"...
0xbacfee  ldnull
0xbacfef  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacff4  ldc.i4.1
0xbacff5  stloc.2
0xbacff6  ldstr    aUpdateinfoCont// "updateInfo.Content"
0xbacffb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbad000  throw
0xbad001  ldloc.s  5
0xbad003  ldloc.s  6
0xbad005  callvirt instance void Microsoft.SharePoint.SPFile::SaveBinary(unsigned int8[] file)
0xbad00a  ldarg.1
0xbad00b  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Title()
0xbad010  brtrue.s loc_BAD026
0xbad012  ldarg.1
0xbad013  callvirt instance int32 Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Version()
0xbad018  ldc.i4.0
0xbad019  bgt.s    loc_BAD026
0xbad01b  ldarg.1
0xbad01c  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Description()
0xbad021  brfalse  loc_BAD0B3
0xbad026  ldloc.s  5
0xbad028  brfalse.s loc_BAD03E
0xbad02a  ldloc.3
0xbad02b  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbad030  ldarg.1
0xbad031  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Id()
0xbad036  ldc.i4.0
0xbad037  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetItemFromList(class Microsoft.SharePoint.SPList list, valuetype [mscorlib]System.Guid itemGuid, valuetype ItemType itemType)
0xbad03c  stloc.s  4
0xbad03e  ldarg.1
0xbad03f  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Title()
0xbad044  brfalse.s loc_BAD058
0xbad046  ldloc.s  4
0xbad048  ldstr    aRecipetitle// "RecipeTitle"
0xbad04d  ldarg.1
0xbad04e  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Title()
0xbad053  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbad058  ldarg.1
0xbad059  callvirt instance int32 Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Version()
0xbad05e  ldc.i4.0
0xbad05f  ble.s    loc_BAD078
0xbad061  ldloc.s  4
0xbad063  ldstr    aRecipeversion// "RecipeVersion"
0xbad068  ldarg.1
0xbad069  callvirt instance int32 Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Version()
0xbad06e  box      [mscorlib]System.Int32
0xbad073  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbad078  ldarg.1
0xbad079  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Description()
0xbad07e  brfalse.s loc_BAD092
0xbad080  ldloc.s  4
0xbad082  ldstr    aRecipedescript// "RecipeDescription"
0xbad087  ldarg.1
0xbad088  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Description()
0xbad08d  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbad092  ldloc.s  4
0xbad094  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0xbad099  leave.s  loc_BAD0B3
0xbad09b  stloc.s  7
0xbad09d  ldloc.0
0xbad09e  ldc.i4   0x188D8A3
0xbad0a3  ldloc.s  7
0xbad0a5  ldnull
0xbad0a6  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbad0ab  ldc.i4.1
0xbad0ac  stloc.2
0xbad0ad  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbad0b2  throw
0xbad0b3  ldarg.0
0xbad0b4  ldarg.1
0xbad0b5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::get_Id()
0xbad0ba  ldc.i4.1
0xbad0bb  call     instance class Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::LoadSiteScriptInternal(valuetype [mscorlib]System.Guid id, bool loadContents)
0xbad0c0  stloc.s  8
0xbad0c2  ldloc.0
0xbad0c3  ldnull
0xbad0c4  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbad0c9  ldloc.s  8
0xbad0cb  stloc.s  0xA
0xbad0cd  leave    loc_BAD152
0xbad0d2  ldloc.0
0xbad0d3  ldc.i4   0x188D8C0
0xbad0d8  ldstr    aWebtemplateext_98// "WebTemplateExtensions.StorageProvider.U"...
0xbad0dd  ldnull
0xbad0de  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbad0e3  ldc.i4.1
0xbad0e4  stloc.2
0xbad0e5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbad0ea  throw
0xbad0eb  ldloc.3
0xbad0ec  brfalse.s loc_BAD0F4
0xbad0ee  ldloc.3
0xbad0ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbad0f4  endfinally
0xbad0f5  stloc.s  9
0xbad0f7  ldloc.1
0xbad0f8  brfalse.s loc_BAD10F
0xbad0fa  ldloc.0
0xbad0fb  ldc.i4   0x2309723
0xbad100  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0xbad105  ldloc.s  9
0xbad107  ldnull
0xbad108  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbad10d  br.s     loc_BAD120
0xbad10f  ldloc.2
0xbad110  brtrue.s loc_BAD120
0xbad112  ldloc.0
0xbad113  ldc.i4   0x188D8C1
0xbad118  ldloc.s  9
0xbad11a  ldnull
0xbad11b  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbad120  ldc.i4   0x2309740
0xbad125  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetULSCat()
0xbad12a  ldc.i4.s 0x32
0xbad12c  ldstr    aWebtemplateext_99// "WebTemplateExtensions.StorageProvider.U"...
0xbad131  ldc.i4.1
0xbad132  newarr   [mscorlib]System.Object
0xbad137  stloc.s  0xB
0xbad139  ldloc.s  0xB
0xbad13b  ldc.i4.0
0xbad13c  ldloc.s  9
0xbad13e  stelem.ref
0xbad13f  ldloc.s  0xB
0xbad141  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbad146  rethrow
0xbad148  ldloc.0
0xbad149  brfalse.s loc_BAD151
0xbad14b  ldloc.0
0xbad14c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbad151  endfinally
0xbad152  ldloc.s  0xA
0xbad154  ret
```
