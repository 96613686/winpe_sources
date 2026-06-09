# Microsoft.SharePoint.SPList::GetSpecialFolderPath

- ea: `0x359bd0`
- end: `0x35a27c`
- name: `Microsoft.SharePoint.SPList::GetSpecialFolderPath`
- size: `1708`
- prototype: ``
- caller_count: `2`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x359bb0`
- `0x359bd0`

## callees

- `0x17f7d0`
- `0x26b8b0`
- `0x26bde0`
- `0x3192a0`
- `0x342e60`
- `0x343930`
- `0x343aa0`
- `0x344c40`
- `0x345950`
- `0x359bd0`
- `0x35a280`
- `0x4a3310`
- `0x4a3560`
- `0x4cd8e0`
- `0x4cddc0`
- `0x4cde40`
- `0x5263f0`
- `0x526540`
- `0x526550`
- `0x5265a0`
- `0x526c70`
- `0x526ec0`
- `0x527080`
- `0x52a140`
- `0x531e00`
- `0x531e20`
- `0x531e40`
- `0x531e60`
- `0x5c10e0`
- `0x5c24f0`
- `0x5c3ce0`
- `0x5c5830`
- `0x5c9dd0`
- `0x5ca510`
- `0x7be4f0`
- `0x7be540`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x957470`
- `0x957bd0`

## string_xrefs

- `0x359c4e`: `Unsupported List Template (ListTemplate = {0}). Only MySiteDocumentLibrary is supported.`
- `0x359c73`: `Unsupported List Template. Only MySiteDocumentLibrary is supported.`
- `0x359e00`: `Folder with UniqueId {0} no longer exists in the List. Need to recreate the Folder.`
- `0x359e35`: `No Folder UniqueId stored in the List. Need to create the Folder.`
- `0x359e4e`: `ForceCreate = {0}. Returning without creating the Folder.`
- `0x359ea4`: `Can't create the {0} Folder in this List right now.`
- `0x359f6e`: `AllowCreationOfSpecialFoldersFromPersonalSiteHost feature is enabled. WebTemplateId is MySiteHost. Current user is site owner. Hence, setting allowCreationFromPersonalSiteHost to true`
- `0x359fa8`: `Current User (UserLoginName = {0}) is not the Site Owner (SiteUrl = {1}, OwnerLoginName = {2}). Only the Site Owner can create the {3} Folder.`
- `0x359ff4`: `Current User is not the Site Owner. Only the Site Owner can create the {0} Folder.`
- `0x35a01e`: `SpecialFolderType is AppRoot and hence we will create the special folder under Apps folder.`
- `0x35a06b`: `SpecialFolderType is {0} and hence we will create the special folder under Photos.`
- `0x35a0c9`: `SpecialFolderType is {0} and hence we will create the special folder under Documents.`
- `0x35a11f`: `SpecialFolderType is not AppRoot and hence we will create the special folder under the list root folder.`
- `0x35a180`: `Created the {0} Folder (FolderName = {1}, FolderServerRelativeUrl = {2}, FolderUniqueId = {3}).`
- `0x35a1c7`: `SaveToOneDriveRecreateAndReturnFolder`
- `0x35a1d4`: `SaveToOneDriveCreateAndReturnFolder`

## pseudocode

```c

```

## disassembly

```asm
0x359bd0  ldc.i4.3
0x359bd1  stloc.0
0x359bd2  ldstr    aSavetoonedrive// "SaveToOneDrive"
0x359bd7  ldc.i4   0x681657
0x359bdc  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x359be1  ldc.i4   0x681658
0x359be6  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x359beb  ldc.i4   0x681659
0x359bf0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x359bf5  ldc.i4.0
0x359bf6  ldnull
0x359bf7  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x359bfc  stloc.1
0x359bfd  ldarg.1
0x359bfe  ldc.i4.5
0x359bff  bne.un.s loc_359C35
0x359c01  call     class Microsoft.SharePoint.SPAppRequestContext Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x359c06  brtrue.s loc_359C35
0x359c08  ldc.i4   0x10528C0
0x359c0d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359c12  ldc.i4.s 0xF
0x359c14  ldstr    aGetspecialfold// "GetSpecialFolderUrl :: The type is set "...
0x359c19  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x359c1e  ldstr    aSavetoonedrive_0// "SaveToOneDriveReturnEmpty"
0x359c23  ldnull
0x359c24  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x359c29  ldsfld   class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.SPResourcePath::EmptyPath
0x359c2e  stloc.s  0x13
0x359c30  leave    loc_35A279
0x359c35  ldarg.0
0x359c36  call     instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0x359c3b  ldc.i4   0x2BC
0x359c40  beq.s    loc_359C7E
0x359c42  ldc.i4   0x68165A
0x359c47  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359c4c  ldc.i4.s 0xF
0x359c4e  ldstr    aUnsupportedLis// "Unsupported List Template (ListTemplate"...
0x359c53  ldc.i4.1
0x359c54  newarr   [mscorlib]System.Object
0x359c59  stloc.s  0x14
0x359c5b  ldloc.s  0x14
0x359c5d  ldc.i4.0
0x359c5e  ldarg.0
0x359c5f  call     instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0x359c64  box      Microsoft.SharePoint.SPListTemplateType
0x359c69  stelem.ref
0x359c6a  ldloc.s  0x14
0x359c6c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359c71  ldc.i4.1
0x359c72  stloc.0
0x359c73  ldstr    aUnsupportedLis_0// "Unsupported List Template. Only MySiteD"...
0x359c78  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x359c7d  throw
0x359c7e  ldarg.1
0x359c7f  newobj   instance void Microsoft.SharePoint.SpecialFolderTypeInfo::.ctor(valuetype Microsoft.SharePoint.SpecialFolderType type)
0x359c84  stloc.2
0x359c85  ldc.i4   0x68165B
0x359c8a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359c8f  ldc.i4.s 0x32
0x359c91  ldstr    aFetchingThe0Fo// "Fetching the {0} Folder in List [Parent"...
0x359c96  ldc.i4.3
0x359c97  newarr   [mscorlib]System.Object
0x359c9c  stloc.s  0x15
0x359c9e  ldloc.s  0x15
0x359ca0  ldc.i4.0
0x359ca1  ldloc.2
0x359ca2  callvirt instance string Microsoft.SharePoint.SpecialFolderTypeInfo::get_TypeName()
0x359ca7  stelem.ref
0x359ca8  ldloc.s  0x15
0x359caa  ldc.i4.1
0x359cab  ldarg.0
0x359cac  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x359cb1  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x359cb6  callvirt instance string [mscorlib]System.Object::ToString()
0x359cbb  stelem.ref
0x359cbc  ldloc.s  0x15
0x359cbe  ldc.i4.2
0x359cbf  ldarg.0
0x359cc0  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0x359cc5  stloc.s  0x16
0x359cc7  ldloca.s 0x16
0x359cc9  constrained. [mscorlib]System.Guid
0x359ccf  callvirt instance string [mscorlib]System.Object::ToString()
0x359cd4  stelem.ref
0x359cd5  ldloc.s  0x15
0x359cd7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359cdc  ldc.i4.0
0x359cdd  stloc.3
0x359cde  ldarg.0
0x359cdf  call     instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x359ce4  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPFolder::get_Properties()
0x359ce9  ldloc.2
0x359cea  callvirt instance string Microsoft.SharePoint.SpecialFolderTypeInfo::get_FolderGuidPropertyName()
0x359cef  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x359cf4  brtrue.s loc_359CFF
0x359cf6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x359cfb  stloc.s  4
0x359cfd  br.s     loc_359D22
0x359cff  ldarg.0
0x359d00  call     instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPList::get_RootFolder()
0x359d05  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPFolder::get_Properties()
0x359d0a  ldloc.2
0x359d0b  callvirt instance string Microsoft.SharePoint.SpecialFolderTypeInfo::get_FolderGuidPropertyName()
0x359d10  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x359d15  callvirt instance string [mscorlib]System.Object::ToString()
0x359d1a  ldloca.s 4
0x359d1c  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x359d21  pop
0x359d22  ldloc.s  4
0x359d24  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x359d29  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x359d2e  brfalse.s loc_359D40
0x359d30  ldarg.3
0x359d31  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x359d36  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x359d3b  brfalse.s loc_359D40
0x359d3d  ldarg.3
0x359d3e  stloc.s  4
0x359d40  ldloc.s  4
0x359d42  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x359d47  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x359d4c  brfalse  loc_359E29
0x359d51  ldc.i4   0x68165C
0x359d56  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359d5b  ldc.i4.s 0x32
0x359d5d  ldstr    aFolderSUniquei// "Folder's UniqueId retrieved from the Li"...
0x359d62  ldc.i4.1
0x359d63  newarr   [mscorlib]System.Object
0x359d68  stloc.s  0x17
0x359d6a  ldloc.s  0x17
0x359d6c  ldc.i4.0
0x359d6d  ldloca.s 4
0x359d6f  constrained. [mscorlib]System.Guid
0x359d75  callvirt instance string [mscorlib]System.Object::ToString()
0x359d7a  stelem.ref
0x359d7b  ldloc.s  0x17
0x359d7d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359d82  ldarg.0
0x359d83  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x359d88  ldloc.s  4
0x359d8a  callvirt instance class Microsoft.SharePoint.SPFolder Microsoft.SharePoint.SPWeb::GetFolder(valuetype [mscorlib]System.Guid uniqueId)
0x359d8f  stloc.s  5
0x359d91  ldloc.s  5
0x359d93  callvirt instance bool Microsoft.SharePoint.SPFolder::get_Exists()
0x359d98  brfalse.s loc_359DF4
0x359d9a  ldc.i4   0x68165D
0x359d9f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359da4  ldc.i4.s 0x32
0x359da6  ldstr    aFolderWithUniq// "Folder with UniqueId {0} found in the L"...
0x359dab  ldc.i4.2
0x359dac  newarr   [mscorlib]System.Object
0x359db1  stloc.s  0x18
0x359db3  ldloc.s  0x18
0x359db5  ldc.i4.0
0x359db6  ldloca.s 4
0x359db8  constrained. [mscorlib]System.Guid
0x359dbe  callvirt instance string [mscorlib]System.Object::ToString()
0x359dc3  stelem.ref
0x359dc4  ldloc.s  0x18
0x359dc6  ldc.i4.1
0x359dc7  ldloc.s  5
0x359dc9  callvirt instance string Microsoft.SharePoint.SPFolder::get_ServerRelativeUrl()
0x359dce  callvirt instance string [mscorlib]System.Object::ToString()
0x359dd3  stelem.ref
0x359dd4  ldloc.s  0x18
0x359dd6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359ddb  ldstr    aSavetoonedrive_1// "SaveToOneDriveReturnFolder"
0x359de0  ldnull
0x359de1  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x359de6  ldloc.s  5
0x359de8  callvirt instance class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.SPFolder::get_ServerRelativePath()
0x359ded  stloc.s  0x13
0x359def  leave    loc_35A279
0x359df4  ldc.i4   0x68165E
0x359df9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359dfe  ldc.i4.s 0x32
0x359e00  ldstr    aFolderWithUniq_0// "Folder with UniqueId {0} no longer exis"...
0x359e05  ldc.i4.1
0x359e06  newarr   [mscorlib]System.Object
0x359e0b  stloc.s  0x19
0x359e0d  ldloc.s  0x19
0x359e0f  ldc.i4.0
0x359e10  ldloca.s 4
0x359e12  constrained. [mscorlib]System.Guid
0x359e18  callvirt instance string [mscorlib]System.Object::ToString()
0x359e1d  stelem.ref
0x359e1e  ldloc.s  0x19
0x359e20  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359e25  ldc.i4.1
0x359e26  stloc.3
0x359e27  br.s     loc_359E3F
0x359e29  ldc.i4   0x68165F
0x359e2e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359e33  ldc.i4.s 0x32
0x359e35  ldstr    aNoFolderUnique// "No Folder UniqueId stored in the List. "...
0x359e3a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x359e3f  ldarg.2
0x359e40  brtrue.s loc_359E84
0x359e42  ldc.i4   0x681660
0x359e47  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359e4c  ldc.i4.s 0x32
0x359e4e  ldstr    aForcecreate0Re// "ForceCreate = {0}. Returning without cr"...
0x359e53  ldc.i4.1
0x359e54  newarr   [mscorlib]System.Object
0x359e59  stloc.s  0x1A
0x359e5b  ldloc.s  0x1A
0x359e5d  ldc.i4.0
0x359e5e  ldarga.s 2
0x359e60  call     instance string [mscorlib]System.Boolean::ToString()
0x359e65  stelem.ref
0x359e66  ldloc.s  0x1A
0x359e68  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x359e6d  ldstr    aSavetoonedrive_0// "SaveToOneDriveReturnEmpty"
0x359e72  ldnull
0x359e73  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x359e78  ldsfld   class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.SPResourcePath::EmptyPath
0x359e7d  stloc.s  0x13
0x359e7f  leave    loc_35A279
0x359e84  ldarg.0
0x359e85  call     instance bool Microsoft.SharePoint.SPList::get_EnableFolderCreation()
0x359e8a  brtrue.s loc_359EBE
0x359e8c  ldc.i4   0x681661
0x359e91  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x359e96  ldc.i4.s 0xF
0x359e98  ldstr    aFolderCreation// "Folder creation is disabled in the List"...
0x359e9d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x359ea2  ldc.i4.0
0x359ea3  stloc.0
0x359ea4  ldstr    aCanTCreateThe0// "Can't create the {0} Folder in this Lis"...
0x359ea9  ldloc.2
0x359eaa  callvirt instance string Microsoft.SharePoint.SpecialFolderTypeInfo::get_TypeName()
0x359eaf  call     string [mscorlib]System.String::Format(string, object)
0x359eb4  stloc.s  6
0x359eb6  ldloc.s  6
0x359eb8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x359ebd  throw
0x359ebe  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x359ec3  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x359ec8  stloc.s  7
0x359eca  ldloc.s  7
0x359ecc  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPSite::get_Owner()
0x359ed1  stloc.s  8
0x359ed3  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x359ed8  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x359edd  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPWeb::get_CurrentUser()
0x359ee2  stloc.s  9
0x359ee4  call     class Microsoft.SharePoint.SPAppRequestContext Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x359ee9  stloc.s  0xA
0x359eeb  ldloc.s  0xA
0x359eed  brfalse.s loc_359EF8
0x359eef  ldloc.s  0xA
0x359ef1  callvirt instance bool Microsoft.SharePoint.SPAppRequestContext::get_IsAppOnlyRequest()
0x359ef6  br.s     loc_359EF9
0x359ef8  ldc.i4.0
0x359ef9  stloc.s  0xB
0x359efb  ldc.i4.0
0x359efc  stloc.s  0xC
0x359efe  ldc.i4   0x2B3F
0x359f03  ldnull
0x359f04  ldnull
0x359f05  call     bool Microsoft.SharePoint.DarkDeploymentUtility::IsFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId, class Microsoft.SharePoint.SPContext context, [opt] class Microsoft.SharePoint.SPWeb web)
0x359f0a  brfalse.s loc_359F7B
0x359f0c  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x359f11  brfalse.s loc_359F7B
0x359f13  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x359f18  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x359f1d  brfalse.s loc_359F7B
0x359f1f  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x359f24  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x359f29  callvirt instance int32 Microsoft.SharePoint.SPWeb::get_WebTemplateId()
0x359f2e  ldc.i4.s 0x36
0x359f30  bne.un.s loc_359F7B
0x359f32  ldloc.s  9
0x359f34  brfalse.s loc_359F7B
0x359f36  ldloc.s  9
0x359f38  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x359f3d  brfalse.s loc_359F7B
0x359f3f  ldloc.s  9
0x359f41  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x359f46  ldarg.0
0x359f47  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x359f4c  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x359f51  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPSite::get_Owner()
0x359f56  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x359f5b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x359f60  brfalse.s loc_359F7B
0x359f62  ldc.i4   0x104761B
0x359f67  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_RESTfulListData()
0x359f6c  ldc.i4.s 0x32
0x359f6e  ldstr    aAllowcreationo// "AllowCreationOfSpecialFoldersFromPerson"...
0x359f73  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x359f78  ldc.i4.1
0x359f79  stloc.s  0xC
0x359f7b  ldloc.s  9
0x359f7d  brfalse.s loc_359F9C
0x359f7f  ldloc.s  9
0x359f81  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x359f86  ldloc.s  8
0x359f88  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x359f8d  callvirt instance bool [mscorlib]System.String::Equals(string)
  ... truncated ...
```
