# Microsoft.SharePoint.Deployment.ListSerializer::GetListMetaDataFromDataSet

- ea: `0x5ede30`
- end: `0x5eea71`
- name: `Microsoft.SharePoint.Deployment.ListSerializer::GetListMetaDataFromDataSet`
- size: `3137`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5edbd0`

## callees

- `0x1d8a0`
- `0x25cc60`
- `0x25d3e0`
- `0x25d8b0`
- `0x26f6c0`
- `0x5c12c0`
- `0x5c24f0`
- `0x5c3ce0`
- `0x5c3da0`
- `0x5e7e70`
- `0x5e7fe0`
- `0x5e7ff0`
- `0x5e8090`
- `0x5ec1a0`
- `0x5ec250`
- `0x5ec280`
- `0x5ede30`
- `0x5f3230`
- `0x5f32d0`
- `0x5f3cc0`
- `0x5f3d20`
- `0x5f4320`
- `0x60cef0`
- `0x612010`
- `0x615a70`
- `0x615a80`
- `0x615aa0`
- `0x618d00`
- `0x619370`

## string_xrefs

- `0x5ee5b5`: `DefaultItemOpen`
- `0x5ee59a`: `DefaultItemOpenUseListSetting`
- `0x5ee3a9`: `ReadSecurity`
- `0x5ee3bd`: `WriteSecurity`
- `0x5ee2cd`: `NeedUpdateSiteClientTag`
- `0x5ee87e`: `ReadOnlyUI`
- `0x5ee89c`: `RestrictUserUpdates`
- `0x5ee425`: `Created`
- `0x5ee008`: `BaseTemplate`
- `0x5ee1fc`: `RequestAccessEnabled`
- `0x5ee9d5`: `ListDefaultComplianceTag`
- `0x5ee9f8`: `ListDefaultComplianceFlags`
- `0x5eea1b`: `ListDefaultComplianceTagUserId`
- `0x5eea3e`: `ListDefaultComplianceTagWrittenTime`
- `0x5ee023`: `TemplateFeatureId`
- `0x5ee037`: `DocumentTemplateId`
- `0x5ee246`: `ExcludeFromTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5ede30  ldnull
0x5ede31  stloc.0
0x5ede32  ldarg.0
0x5ede33  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5ede38  ldstr    aId_2// "Id"
0x5ede3d  ldarg.1
0x5ede3e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ede43  box      [mscorlib]System.Guid
0x5ede48  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, object entryValue)
0x5ede4d  ldarg.0
0x5ede4e  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5ede53  ldstr    aRootfolderurl_0// "RootFolderUrl"
0x5ede58  ldarg.1
0x5ede59  callvirt instance string Microsoft.SharePoint.Deployment.DeploymentObject::get_Url()
0x5ede5e  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, object entryValue)
0x5ede63  ldarg.0
0x5ede64  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5ede69  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> Microsoft.SharePoint.Deployment.ExportObjectManager::get_ListToRootFolderMap()
0x5ede6e  ldarg.1
0x5ede6f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ede74  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::ContainsKey(var<u1>)
0x5ede79  brtrue.s loc_5EDE97
0x5ede7b  ldarg.0
0x5ede7c  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5ede81  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> Microsoft.SharePoint.Deployment.ExportObjectManager::get_ListToRootFolderMap()
0x5ede86  ldarg.1
0x5ede87  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ede8c  ldarg.1
0x5ede8d  callvirt instance string Microsoft.SharePoint.Deployment.DeploymentObject::get_Url()
0x5ede92  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::Add(var<u1>, !!T0)
0x5ede97  ldarg.0
0x5ede98  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5ede9d  ldstr    aParentwebid_0// "ParentWebId"
0x5edea2  ldarg.1
0x5edea3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_ParentWebId()
0x5edea8  box      [mscorlib]System.Guid
0x5edead  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, object entryValue)
0x5edeb2  ldarg.0
0x5edeb3  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5edeb8  ldarg.1
0x5edeb9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_ParentWebId()
0x5edebe  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Deployment.ObjectManager::GetWeb(valuetype [mscorlib]System.Guid webId)
0x5edec3  stloc.0
0x5edec4  ldarg.0
0x5edec5  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edeca  ldstr    aParentweburl// "ParentWebUrl"
0x5edecf  ldloc.0
0x5eded0  callvirt instance string Microsoft.SharePoint.SPWeb::get_ServerRelativeUrl()
0x5eded5  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, object entryValue)
0x5ededa  ldarg.0
0x5ededb  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edee0  ldstr    aRootfolderid_0// "RootFolderId"
0x5edee5  ldc.i4.s 0xB
0x5edee7  ldarg.2
0x5edee8  ldc.i4.0
0x5edee9  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edeee  ldarg.0
0x5edeef  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edef4  ldstr    aTitle_0// "Title"
0x5edef9  ldc.i4.3
0x5edefa  ldarg.2
0x5edefb  ldc.i4.0
0x5edefc  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edf01  ldarg.0
0x5edf02  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edf07  ldstr    aDescription// "Description"
0x5edf0c  ldc.i4.4
0x5edf0d  ldarg.2
0x5edf0e  ldc.i4.1
0x5edf0f  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edf14  ldarg.2
0x5edf15  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5edf1a  ldc.i4.s 0x10
0x5edf1c  ldelem.ref
0x5edf1d  isinst   [mscorlib]System.DBNull
0x5edf22  brtrue.s loc_5EDF7F
0x5edf24  ldarg.2
0x5edf25  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5edf2a  ldc.i4.s 0x10
0x5edf2c  ldelem.ref
0x5edf2d  unbox.any [mscorlib]System.Int32
0x5edf32  stloc.1
0x5edf33  ldloc.1
0x5edf34  stloc.s  0x1C
0x5edf36  ldloc.s  0x1C
0x5edf38  switch   loc_5EDF4B, loc_5EDF5D, loc_5EDF6F
0x5edf49  br.s     loc_5EDF7F
0x5edf4b  ldarg.3
0x5edf4c  ldstr    aDirection_0// "Direction"
0x5edf51  ldstr    aNone// "none"
0x5edf56  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x5edf5b  br.s     loc_5EDF7F
0x5edf5d  ldarg.3
0x5edf5e  ldstr    aDirection_0// "Direction"
0x5edf63  ldstr    aLtr// "ltr"
0x5edf68  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x5edf6d  br.s     loc_5EDF7F
0x5edf6f  ldarg.3
0x5edf70  ldstr    aDirection_0// "Direction"
0x5edf75  ldstr    aRtl// "rtl"
0x5edf7a  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x5edf7f  ldarg.2
0x5edf80  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5edf85  ldc.i4.8
0x5edf86  ldelem.ref
0x5edf87  unbox.any Microsoft.SharePoint.SPBaseType
0x5edf8c  stloc.2
0x5edf8d  ldarg.0
0x5edf8e  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edf93  ldstr    aBasetype_1// "BaseType"
0x5edf98  ldloc.2
0x5edf99  box      Microsoft.SharePoint.SPBaseType
0x5edf9e  callvirt instance string [mscorlib]System.Object::ToString()
0x5edfa3  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, object entryValue)
0x5edfa8  ldarg.0
0x5edfa9  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edfae  ldstr    aImageurl_0// "ImageUrl"
0x5edfb3  ldc.i4.s 0x15
0x5edfb5  ldarg.2
0x5edfb6  ldc.i4.0
0x5edfb7  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edfbc  ldarg.0
0x5edfbd  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edfc2  ldstr    aEventsinkassem_0// "EventSinkAssembly"
0x5edfc7  ldc.i4.s 0x17
0x5edfc9  ldarg.2
0x5edfca  ldc.i4.1
0x5edfcb  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edfd0  ldarg.0
0x5edfd1  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edfd6  ldstr    aEventsinkclass_0// "EventSinkClass"
0x5edfdb  ldc.i4.s 0x18
0x5edfdd  ldarg.2
0x5edfde  ldc.i4.1
0x5edfdf  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edfe4  ldarg.0
0x5edfe5  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5edfea  ldstr    aEventsinkdata_0// "EventSinkData"
0x5edfef  ldc.i4.s 0x19
0x5edff1  ldarg.2
0x5edff2  ldc.i4.1
0x5edff3  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5edff8  ldarg.2
0x5edff9  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5edffe  ldc.i4.s 0xA
0x5ee000  ldelem.ref
0x5ee001  unbox.any Microsoft.SharePoint.SPListTemplateType
0x5ee006  stloc.3
0x5ee007  ldarg.3
0x5ee008  ldstr    aBasetemplate// "BaseTemplate"
0x5ee00d  ldloc.3
0x5ee00e  box      Microsoft.SharePoint.SPListTemplateType
0x5ee013  callvirt instance string [mscorlib]System.Object::ToString()
0x5ee018  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x5ee01d  ldarg.0
0x5ee01e  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5ee023  ldstr    aTemplatefeatur// "TemplateFeatureId"
0x5ee028  ldc.i4.s 9
0x5ee02a  ldarg.2
0x5ee02b  ldc.i4.1
0x5ee02c  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5ee031  ldarg.0
0x5ee032  call     instance class Microsoft.SharePoint.Deployment.SerializationInfoHelper Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_InfoHelper()
0x5ee037  ldstr    aDocumenttempla_5// "DocumentTemplateId"
0x5ee03c  ldc.i4.s 0xC
0x5ee03e  ldarg.2
0x5ee03f  ldc.i4.1
0x5ee040  callvirt instance void Microsoft.SharePoint.Deployment.SerializationInfoHelper::AddValue(string entryName, int32 column, class [System.Data]System.Data.DataRow row, bool nullable)
0x5ee045  ldarg.2
0x5ee046  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5ee04b  ldc.i4.s 0x27
0x5ee04d  ldelem.ref
0x5ee04e  unbox.any [mscorlib]System.Guid
0x5ee053  stloc.s  4
0x5ee055  ldloc.0
0x5ee056  ldloc.s  4
0x5ee058  ldarg.0
0x5ee059  call     instance class Microsoft.SharePoint.Deployment.SPExportSettings Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportSettings()
0x5ee05e  ldarg.3
0x5ee05f  call     void Microsoft.SharePoint.Deployment.SecurityObjectSerializer::ExportListSecurityAttributes(class Microsoft.SharePoint.SPWeb web, valuetype [mscorlib]System.Guid scopeId, class Microsoft.SharePoint.Deployment.SPExportSettings settings, class [mscorlib]System.Runtime.Serialization.SerializationInfo info)
0x5ee064  ldarg.2
0x5ee065  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5ee06a  ldc.i4.s 0x11
0x5ee06c  ldelem.ref
0x5ee06d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ee072  call     int64 [mscorlib]System.Convert::ToInt64(object, class [mscorlib]System.IFormatProvider)
0x5ee077  stloc.s  5
0x5ee079  ldc.i4.0
0x5ee07a  conv.i8
0x5ee07b  stloc.s  6
0x5ee07d  ldloc.0
0x5ee07e  brfalse.s loc_5EE0A7
0x5ee080  ldloc.0
0x5ee081  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x5ee086  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x5ee08b  callvirt instance bool Microsoft.SharePoint.Administration.SPContentDatabase::get_SupportsAllListsFlags2()
0x5ee090  brfalse.s loc_5EE0A7
0x5ee092  ldarg.2
0x5ee093  callvirt instance object[] [System.Data]System.Data.DataRow::get_ItemArray()
0x5ee098  ldc.i4.s 0x29
0x5ee09a  ldelem.ref
0x5ee09b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ee0a0  call     int64 [mscorlib]System.Convert::ToInt64(object, class [mscorlib]System.IFormatProvider)
0x5ee0a5  stloc.s  6
0x5ee0a7  ldarg.3
0x5ee0a8  ldstr    aFlags_1// "Flags"
0x5ee0ad  ldloc.s  5
0x5ee0af  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, int64)
0x5ee0b4  ldarg.3
0x5ee0b5  ldstr    aFlags2_0// "Flags2"
0x5ee0ba  ldloc.s  6
0x5ee0bc  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, int64)
0x5ee0c1  ldloc.s  5
0x5ee0c3  ldc.i4   0x4000
0x5ee0c8  conv.i8
0x5ee0c9  and
0x5ee0ca  ldc.i4.0
0x5ee0cb  conv.i8
0x5ee0cc  beq.s    loc_5EE0E5
0x5ee0ce  ldarg.0
0x5ee0cf  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5ee0d4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.SharePoint.Deployment.ObjectManager::get_RootWebOnlyList()
0x5ee0d9  ldarg.1
0x5ee0da  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ee0df  ldc.i4.1
0x5ee0e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0x5ee0e5  ldarg.3
0x5ee0e6  ldstr    aAllowdeletion// "AllowDeletion"
0x5ee0eb  ldloc.s  5
0x5ee0ed  ldc.i4.4
0x5ee0ee  conv.i8
0x5ee0ef  and
0x5ee0f0  ldc.i4.0
0x5ee0f1  conv.i8
0x5ee0f2  ceq
0x5ee0f4  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, bool)
0x5ee0f9  ldarg.3
0x5ee0fa  ldstr    aAllowmultiresp// "AllowMultiResponses"
0x5ee0ff  ldloc.s  5
0x5ee101  ldc.i4   0x800
0x5ee106  conv.i8
0x5ee107  and
0x5ee108  ldc.i4.0
0x5ee109  conv.i8
0x5ee10a  ceq
0x5ee10c  ldc.i4.0
0x5ee10d  ceq
0x5ee10f  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, bool)
0x5ee114  ldloc.2
0x5ee115  ldc.i4.1
0x5ee116  beq.s    loc_5EE130
0x5ee118  ldloc.2
0x5ee119  ldc.i4.4
0x5ee11a  beq.s    loc_5EE130
0x5ee11c  ldarg.3
0x5ee11d  ldstr    aEnableattachme_0// "EnableAttachments"
0x5ee122  ldloc.s  5
0x5ee124  ldc.i4.8
0x5ee125  conv.i8
0x5ee126  and
0x5ee127  ldc.i4.0
0x5ee128  conv.i8
0x5ee129  ceq
0x5ee12b  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, bool)
0x5ee130  ldloc.s  5
0x5ee132  ldc.i4   0x400
0x5ee137  conv.i8
0x5ee138  and
0x5ee139  ldc.i4.0
0x5ee13a  conv.i8
0x5ee13b  ceq
0x5ee13d  ldc.i4.0
0x5ee13e  ceq
0x5ee140  stloc.s  7
0x5ee142  ldarg.3
0x5ee143  ldstr    aEnablemoderati// "EnableModeration"
0x5ee148  ldloc.s  7
0x5ee14a  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, bool)
0x5ee14f  ldarg.0
0x5ee150  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5ee155  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.SharePoint.Deployment.ExportObjectManager::get_NonDocLibListWithModeration()
0x5ee15a  ldarg.1
0x5ee15b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ee160  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x5ee165  brtrue.s loc_5EE186
0x5ee167  ldarg.0
0x5ee168  call     instance class Microsoft.SharePoint.Deployment.ExportObjectManager Microsoft.SharePoint.Deployment.DeploymentSerializationSurrogate::get_ExportObjectManager()
0x5ee16d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.SharePoint.Deployment.ExportObjectManager::get_NonDocLibListWithModeration()
0x5ee172  ldarg.1
0x5ee173  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Deployment.DeploymentObject::get_Id()
0x5ee178  ldloc.2
0x5ee179  ldc.i4.1
0x5ee17a  beq.s    loc_5EE180
0x5ee17c  ldloc.s  7
0x5ee17e  br.s     loc_5EE181
0x5ee180  ldc.i4.0
0x5ee181  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0x5ee186  ldarg.3
0x5ee187  ldstr    aEnableversioni// "EnableVersioning"
0x5ee18c  ldloc.s  5
  ... truncated ...
```
