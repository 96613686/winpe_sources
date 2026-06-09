# Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::CreateSiteScript

- ea: `0xbacac0`
- end: `0xbace37`
- name: `Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::CreateSiteScript`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x343aa0`
- `0x344760`
- `0x3e99f0`
- `0x3e9a20`
- `0x4cd8e0`
- `0x4cddc0`
- `0x50c610`
- `0x50e070`
- `0x510900`
- `0x522080`
- `0x526910`
- `0x6c9890`
- `0x7be4d0`
- `0x7be4f0`
- `0x7be510`
- `0x7be550`
- `0x7be580`
- `0x7beb40`
- `0x7fd160`
- `0x7fd180`
- `0x7fd1a0`
- `0x7fd1c0`
- `0x7fd440`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0xbacac0`
- `0xbad160`
- `0xbae250`
- `0xbae640`
- `0xbae670`

## string_xrefs

- `0xbacac0`: `WebTemplateExtensions.StorageProvider.CreateSiteScript`
- `0xbacae5`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Info is null`
- `0xbacb0e`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Info.Title is missing`
- `0xbacb3a`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Info has no content`
- `0xbacb69`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: SPContext.Current or SPContext.Current.Web is null`
- `0xbacbca`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: ContentStream resolved empty`
- `0xbacc2b`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Exceeded site script limit`
- `0xbacc7f`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Failed to convert info.Content to byte array`
- `0xbacd53`: `WebTemplateExtensions.StorageProvider.CreateSiteScript failed to update fields. Attempting to delete file.`
- `0xbacd70`: `WebTemplateExtensions.StorageProvider.CreateSiteScript failed to update fields. File deleted.`
- `0xbacd86`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: File did not exist`
- `0xbacd9f`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: File created was null`
- `0xbacdb8`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Library could not be retrieved`
- `0xbace0e`: `WebTemplateExtensions.StorageProvider.CreateSiteScript: Unexpected exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xbacac0  ldstr    aWebtemplateext_76// "WebTemplateExtensions.StorageProvider.C"...
0xbacac5  ldc.i4   0x160D7DC
0xbacaca  ldc.i4   0x160D7DD
0xbacacf  ldc.i4   0x160D7DE
0xbacad4  ldc.i4.0
0xbacad5  ldnull
0xbacad6  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacadb  stloc.0
0xbacadc  ldarg.1
0xbacadd  brtrue.s loc_BACAFB
0xbacadf  ldloc.0
0xbacae0  ldc.i4   0x160D7DF
0xbacae5  ldstr    aWebtemplateext_77// "WebTemplateExtensions.StorageProvider.C"...
0xbacaea  ldnull
0xbacaeb  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacaf0  ldstr    aInfo// "info"
0xbacaf5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbacafa  throw
0xbacafb  ldarg.1
0xbacafc  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Title()
0xbacb01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbacb06  brfalse.s loc_BACB24
0xbacb08  ldloc.0
0xbacb09  ldc.i4   0x160D7E0
0xbacb0e  ldstr    aWebtemplateext_78// "WebTemplateExtensions.StorageProvider.C"...
0xbacb13  ldnull
0xbacb14  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacb19  ldstr    aInfoTitle// "info.Title"
0xbacb1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbacb23  throw
0xbacb24  ldarg.1
0xbacb25  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_ContentStream()
0xbacb2a  brtrue.s loc_BACB50
0xbacb2c  ldarg.1
0xbacb2d  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Content()
0xbacb32  brtrue.s loc_BACB50
0xbacb34  ldloc.0
0xbacb35  ldc.i4   0x160D7E1
0xbacb3a  ldstr    aWebtemplateext_79// "WebTemplateExtensions.StorageProvider.C"...
0xbacb3f  ldnull
0xbacb40  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacb45  ldstr    aInfoContentstr// "info.ContentStream"
0xbacb4a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbacb4f  throw
0xbacb50  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xbacb55  brfalse.s loc_BACB63
0xbacb57  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0xbacb5c  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0xbacb61  brtrue.s loc_BACB7A
0xbacb63  ldloc.0
0xbacb64  ldc.i4   0x160D7E2
0xbacb69  ldstr    aWebtemplateext_80// "WebTemplateExtensions.StorageProvider.C"...
0xbacb6e  ldnull
0xbacb6f  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacb74  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacb79  throw
0xbacb7a  ldc.i4.0
0xbacb7b  stloc.1
0xbacb7c  ldc.i4.0
0xbacb7d  stloc.2
0xbacb7e  ldarg.1
0xbacb7f  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Content()
0xbacb84  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbacb89  brtrue.s loc_BACB94
0xbacb8b  ldarg.1
0xbacb8c  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Content()
0xbacb91  stloc.3
0xbacb92  br.s     loc_BACBE0
0xbacb94  ldarg.1
0xbacb95  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_ContentStream()
0xbacb9a  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xbacb9f  stloc.s  4
0xbacba1  ldloc.s  4
0xbacba3  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0xbacba8  stloc.3
0xbacba9  leave.s  loc_BACBB7
0xbacbab  ldloc.s  4
0xbacbad  brfalse.s loc_BACBB6
0xbacbaf  ldloc.s  4
0xbacbb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbacbb6  endfinally
0xbacbb7  ldloc.3
0xbacbb8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbacbbd  brfalse.s loc_BACBE0
0xbacbbf  ldloc.0
0xbacbc0  ldc.i4   0x230971E
0xbacbc5  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0xbacbca  ldstr    aWebtemplateext_81// "WebTemplateExtensions.StorageProvider.C"...
0xbacbcf  ldnull
0xbacbd0  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacbd5  ldstr    aInfoContentstr// "info.ContentStream"
0xbacbda  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbacbdf  throw
0xbacbe0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::EnsureSiteScriptContentKillSwitch
0xbacbe5  ldstr    a152018// "1/5/2018"
0xbacbea  ldstr    aEnsuresitescri// "EnsureSiteScriptContent"
0xbacbef  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xbacbf4  brtrue.s loc_BACBFE
0xbacbf6  ldloc.3
0xbacbf7  ldloca.s 1
0xbacbf9  call     void Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::EnsureSiteScriptContent(string content, [out] bool& scriptParseFailure)
0xbacbfe  ldarg.0
0xbacbff  ldc.i4.0
0xbacc00  call     instance class DisposableObject`1<class Microsoft.SharePoint.SPList> Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::TryGetTable(valuetype ItemType itemType)
0xbacc05  stloc.s  5
0xbacc07  ldloc.s  5
0xbacc09  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbacc0e  brfalse  loc_BACDB2
0xbacc13  ldloc.s  5
0xbacc15  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbacc1a  callvirt instance int32 Microsoft.SharePoint.SPList::get_ItemCount()
0xbacc1f  ldc.i4.s 0x64
0xbacc21  blt.s    loc_BACC3C
0xbacc23  ldc.i4.1
0xbacc24  stloc.2
0xbacc25  ldloc.0
0xbacc26  ldc.i4   0x18141C4
0xbacc2b  ldstr    aWebtemplateext_82// "WebTemplateExtensions.StorageProvider.C"...
0xbacc30  ldnull
0xbacc31  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacc36  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor()
0xbacc3b  throw
0xbacc3c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xbacc41  stloc.s  6
0xbacc43  ldloc.s  6
0xbacc45  call     string Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetSiteScriptFileName(valuetype [mscorlib]System.Guid id)
0xbacc4a  stloc.s  7
0xbacc4c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xbacc51  ldloc.3
0xbacc52  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xbacc57  stloc.s  9
0xbacc59  ldloc.s  5
0xbacc5b  callvirt instance var<u1> class DisposableObject`1<class Microsoft.SharePoint.SPList>::get_Object()
0xbacc60  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0xbacc65  callvirt instance class Microsoft.SharePoint.SPFileCollection Microsoft.SharePoint.SPFolder::get_Files()
0xbacc6a  ldloc.s  7
0xbacc6c  ldloc.s  9
0xbacc6e  ldc.i4.1
0xbacc6f  callvirt instance class Microsoft.SharePoint.SPFile Microsoft.SharePoint.SPFileCollection::Add(string urlOfFile, unsigned int8[] file, bool overwrite)
0xbacc74  stloc.s  8
0xbacc76  leave.s  loc_BACC97
0xbacc78  pop
0xbacc79  ldloc.0
0xbacc7a  ldc.i4   0x160D7E3
0xbacc7f  ldstr    aWebtemplateext_83// "WebTemplateExtensions.StorageProvider.C"...
0xbacc84  ldnull
0xbacc85  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacc8a  ldc.i4.1
0xbacc8b  stloc.2
0xbacc8c  ldstr    aInfoContent// "info.Content"
0xbacc91  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbacc96  throw
0xbacc97  ldloc.s  8
0xbacc99  brfalse  loc_BACD99
0xbacc9e  ldloc.s  8
0xbacca0  callvirt instance bool Microsoft.SharePoint.SPFile::get_Exists()
0xbacca5  brfalse  loc_BACD80
0xbaccaa  ldloc.s  8
0xbaccac  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPFile::get_Item()
0xbaccb1  stloc.s  0xA
0xbaccb3  ldloc.s  0xA
0xbaccb5  ldstr    aRecipetitle// "RecipeTitle"
0xbaccba  ldarg.1
0xbaccbb  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Title()
0xbaccc0  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbaccc5  ldloc.s  0xA
0xbaccc7  ldstr    aRecipeguid// "RecipeGuid"
0xbacccc  ldloc.s  6
0xbaccce  box      [mscorlib]System.Guid
0xbaccd3  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbaccd8  ldloc.s  0xA
0xbaccda  ldstr    aRecipeversion// "RecipeVersion"
0xbaccdf  ldc.i4.1
0xbacce0  box      [mscorlib]System.Int32
0xbacce5  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbaccea  ldloc.s  0xA
0xbaccec  ldstr    aRecipedescript// "RecipeDescription"
0xbaccf1  ldarg.1
0xbaccf2  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Description()
0xbaccf7  brfalse.s loc_BACD01
0xbaccf9  ldarg.1
0xbaccfa  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Description()
0xbaccff  br.s     loc_BACD06
0xbacd01  ldsfld   string [mscorlib]System.String::Empty
0xbacd06  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0xbacd0b  ldloc.s  0xA
0xbacd0d  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0xbacd12  ldloc.0
0xbacd13  ldnull
0xbacd14  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacd19  ldarg.1
0xbacd1a  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Title()
0xbacd1f  ldc.i4.0
0xbacd20  ldarg.1
0xbacd21  callvirt instance string Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptCreationInfo::get_Description()
0xbacd26  ldloc.s  6
0xbacd28  ldnull
0xbacd29  newobj   instance void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata::.ctor(string title, int32 version, string description, valuetype [mscorlib]System.Guid id, [opt] string content)
0xbacd2e  stloc.s  0xD
0xbacd30  leave    loc_BACE34
0xbacd35  stloc.s  0xB
0xbacd37  ldloc.0
0xbacd38  ldc.i4   0x160D800
0xbacd3d  ldloc.s  0xB
0xbacd3f  ldnull
0xbacd40  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacd45  ldc.i4.1
0xbacd46  stloc.2
0xbacd47  ldc.i4   0x230971F
0xbacd4c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetULSCat()
0xbacd51  ldc.i4.s 0x32
0xbacd53  ldstr    aWebtemplateext_84// "WebTemplateExtensions.StorageProvider.C"...
0xbacd58  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xbacd5d  ldloc.s  8
0xbacd5f  callvirt instance void Microsoft.SharePoint.SPFile::Delete()
0xbacd64  ldc.i4   0x2309720
0xbacd69  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetULSCat()
0xbacd6e  ldc.i4.s 0x32
0xbacd70  ldstr    aWebtemplateext_85// "WebTemplateExtensions.StorageProvider.C"...
0xbacd75  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xbacd7a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacd7f  throw
0xbacd80  ldloc.0
0xbacd81  ldc.i4   0x160D803
0xbacd86  ldstr    aWebtemplateext_86// "WebTemplateExtensions.StorageProvider.C"...
0xbacd8b  ldnull
0xbacd8c  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacd91  ldc.i4.1
0xbacd92  stloc.2
0xbacd93  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacd98  throw
0xbacd99  ldloc.0
0xbacd9a  ldc.i4   0x160D804
0xbacd9f  ldstr    aWebtemplateext_87// "WebTemplateExtensions.StorageProvider.C"...
0xbacda4  ldnull
0xbacda5  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacdaa  ldc.i4.1
0xbacdab  stloc.2
0xbacdac  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacdb1  throw
0xbacdb2  ldloc.0
0xbacdb3  ldc.i4   0x160D805
0xbacdb8  ldstr    aWebtemplateext_88// "WebTemplateExtensions.StorageProvider.C"...
0xbacdbd  ldnull
0xbacdbe  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacdc3  ldc.i4.1
0xbacdc4  stloc.2
0xbacdc5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xbacdca  throw
0xbacdcb  ldloc.s  5
0xbacdcd  brfalse.s loc_BACDD6
0xbacdcf  ldloc.s  5
0xbacdd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbacdd6  endfinally
0xbacdd7  stloc.s  0xC
0xbacdd9  ldloc.1
0xbacdda  brfalse.s loc_BACDF1
0xbacddc  ldloc.0
0xbacddd  ldc.i4   0x2309721
0xbacde2  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0xbacde7  ldloc.s  0xC
0xbacde9  ldnull
0xbacdea  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbacdef  br.s     loc_BACE02
0xbacdf1  ldloc.2
0xbacdf2  brtrue.s loc_BACE02
0xbacdf4  ldloc.0
0xbacdf5  ldc.i4   0x160D806
0xbacdfa  ldloc.s  0xC
0xbacdfc  ldnull
0xbacdfd  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xbace02  ldc.i4   0x2309722
0xbace07  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.WebTemplateExtensions.StorageProvider::GetULSCat()
0xbace0c  ldc.i4.s 0x32
0xbace0e  ldstr    aWebtemplateext_89// "WebTemplateExtensions.StorageProvider.C"...
0xbace13  ldc.i4.1
0xbace14  newarr   [mscorlib]System.Object
0xbace19  stloc.s  0xE
0xbace1b  ldloc.s  0xE
0xbace1d  ldc.i4.0
0xbace1e  ldloc.s  0xC
0xbace20  stelem.ref
0xbace21  ldloc.s  0xE
0xbace23  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbace28  rethrow
0xbace2a  ldloc.0
0xbace2b  brfalse.s loc_BACE33
0xbace2d  ldloc.0
0xbace2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbace33  endfinally
0xbace34  ldloc.s  0xD
0xbace36  ret
```
