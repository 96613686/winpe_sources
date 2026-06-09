# Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateDeletedInstances

- ea: `0xa82aa0`
- end: `0xa82eab`
- name: `Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateDeletedInstances`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa825a0`

## callees

- `0x342e60`
- `0x343930`
- `0x3e99a0`
- `0x3e99e0`
- `0x4a90f0`
- `0x4c01f0`
- `0x4c02c0`
- `0x53e320`
- `0x542ef0`
- `0x54cae0`
- `0x5cc430`
- `0x79f320`
- `0x79f350`
- `0x79f380`
- `0x79f3b0`
- `0x79f3c0`
- `0x79f3f0`
- `0x79f400`
- `0x79f440`
- `0x79f480`
- `0x79f4b0`
- `0x79f4f0`
- `0x79f510`
- `0x79f530`
- `0x79f550`
- `0xa82aa0`
- `0xa82eb0`
- `0xa82f60`
- `0xa830c0`
- `0xa83f40`
- `0xae8dd0`
- `0xae8e00`

## string_xrefs

- `0xa82d1d`: `Created`
- `0xa82c4f`: `WorkspaceLink`
- `0xa82dc8`: `WorkspaceLink`
- `0xa82dd5`: `WorkspaceLink`
- `0xa82c23`: `XMLTZone`
- `0xa82c99`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa82ce0`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa82d2d`: `urn:schemas-microsoft-com:office:office#Editor`
- `0xa82d43`: `urn:schemas-microsoft-com:office:office#Modified`
- `0xa82b15`: `urn:schemas-microsoft-com:office:office#Title`
- `0xa82b2b`: `urn:schemas-microsoft-com:office:office#ParticipantsPicker`
- `0xa82b41`: `urn:schemas-microsoft-com:office:office#Facilities`
- `0xa82b57`: `urn:schemas-microsoft-com:office:office#EventDate`
- `0xa82b6d`: `urn:schemas-microsoft-com:office:office#EndDate`
- `0xa82b83`: `urn:schemas-microsoft-com:office:office#fAllDayEvent`
- `0xa82b99`: `urn:schemas-microsoft-com:office:office#fRecurrence`
- `0xa82baf`: `urn:schemas-microsoft-com:office:office#Location`
- `0xa82bc5`: `urn:schemas-microsoft-com:office:office#Category`
- `0xa82bdb`: `urn:schemas-microsoft-com:office:office#Description`
- `0xa82bf1`: `urn:schemas-microsoft-com:office:office#EventType`
- `0xa82c07`: `urn:schemas-microsoft-com:office:office#TimeZone`
- `0xa82c1d`: `urn:schemas-microsoft-com:office:office#XMLTZone`
- `0xa82c33`: `urn:schemas-microsoft-com:office:office#Duration`
- `0xa82c49`: `urn:schemas-microsoft-com:office:office#WorkspaceLink`
- `0xa82c5f`: `urn:schemas-microsoft-com:office:office#Workspace`
- `0xa82c87`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa82cce`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa82d01`: `urn:schemas-microsoft-com:office:office#Author`
- `0xa82d17`: `urn:schemas-microsoft-com:office:office#Created`
- `0xa82d59`: `urn:schemas-microsoft-com:office:office#UID`
- `0xa82d9f`: `urn:schemas-microsoft-com:office:office#RecurrenceData`
- `0xa82d66`: `urn:schemas-microsoft-com:office:office#RecurrenceID`
- `0xa82d92`: `urn:schemas-microsoft-com:office:office#MasterSeriesItemID`
- `0xa82d7c`: `urn:schemas-microsoft-com:office:office#EventCanceled`

## pseudocode

```c

```

## disassembly

```asm
0xa82aa0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::.ctor()
0xa82aa5  stloc.0
0xa82aa6  ldnull
0xa82aa7  stloc.1
0xa82aa8  ldc.i4.0
0xa82aa9  stloc.2
0xa82aaa  br       loc_A82E8B
0xa82aaf  ldarg.3
0xa82ab0  ldarg.s  4
0xa82ab2  ldloc.2
0xa82ab3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0xa82ab8  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::get_Item(int32 iIndex)
0xa82abd  stloc.3
0xa82abe  ldloc.1
0xa82abf  brtrue.s loc_A82ACD
0xa82ac1  newobj   instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::.ctor()
0xa82ac6  stloc.1
0xa82ac7  ldloc.1
0xa82ac8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartBatch()
0xa82acd  ldloc.1
0xa82ace  ldstr    aA_4// "A"
0xa82ad3  ldloc.2
0xa82ad4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa82ad9  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa82ade  call     string [mscorlib]System.String::Concat(string, string)
0xa82ae3  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartMethod(string strID)
0xa82ae8  ldloc.1
0xa82ae9  ldarg.1
0xa82aea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa82aef  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetList(valuetype [mscorlib]System.Guid guid)
0xa82af4  ldloc.1
0xa82af5  ldstr    aCmd// "Cmd"
0xa82afa  ldstr    aSave_0// "Save"
0xa82aff  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82b04  ldloc.1
0xa82b05  ldstr    aId_0// "ID"
0xa82b0a  ldstr    aNew// "New"
0xa82b0f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82b14  ldloc.1
0xa82b15  ldstr    aUrnSchemasMicr_19// "urn:schemas-microsoft-com:office:office"...
0xa82b1a  ldloc.3
0xa82b1b  ldstr    aTitle_0// "Title"
0xa82b20  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b25  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82b2a  ldloc.1
0xa82b2b  ldstr    aUrnSchemasMicr_20// "urn:schemas-microsoft-com:office:office"...
0xa82b30  ldloc.3
0xa82b31  ldstr    aParticipantspi// "ParticipantsPicker"
0xa82b36  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b3b  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82b40  ldloc.1
0xa82b41  ldstr    aUrnSchemasMicr_21// "urn:schemas-microsoft-com:office:office"...
0xa82b46  ldloc.3
0xa82b47  ldstr    aFacilities// "Facilities"
0xa82b4c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b51  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82b56  ldloc.1
0xa82b57  ldstr    aUrnSchemasMicr_22// "urn:schemas-microsoft-com:office:office"...
0xa82b5c  ldloc.3
0xa82b5d  ldstr    aEventdate// "EventDate"
0xa82b62  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b67  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82b6c  ldloc.1
0xa82b6d  ldstr    aUrnSchemasMicr_23// "urn:schemas-microsoft-com:office:office"...
0xa82b72  ldloc.3
0xa82b73  ldstr    aEnddate_0// "EndDate"
0xa82b78  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b7d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82b82  ldloc.1
0xa82b83  ldstr    aUrnSchemasMicr_24// "urn:schemas-microsoft-com:office:office"...
0xa82b88  ldloc.3
0xa82b89  ldstr    aFalldayevent// "fAllDayEvent"
0xa82b8e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82b93  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82b98  ldloc.1
0xa82b99  ldstr    aUrnSchemasMicr_25// "urn:schemas-microsoft-com:office:office"...
0xa82b9e  ldloc.3
0xa82b9f  ldstr    aFrecurrence// "fRecurrence"
0xa82ba4  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82ba9  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82bae  ldloc.1
0xa82baf  ldstr    aUrnSchemasMicr_26// "urn:schemas-microsoft-com:office:office"...
0xa82bb4  ldloc.3
0xa82bb5  ldstr    aLocation// "Location"
0xa82bba  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82bbf  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82bc4  ldloc.1
0xa82bc5  ldstr    aUrnSchemasMicr_27// "urn:schemas-microsoft-com:office:office"...
0xa82bca  ldloc.3
0xa82bcb  ldstr    aCategory// "Category"
0xa82bd0  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82bd5  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82bda  ldloc.1
0xa82bdb  ldstr    aUrnSchemasMicr_28// "urn:schemas-microsoft-com:office:office"...
0xa82be0  ldloc.3
0xa82be1  ldstr    aDescription// "Description"
0xa82be6  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82beb  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82bf0  ldloc.1
0xa82bf1  ldstr    aUrnSchemasMicr_29// "urn:schemas-microsoft-com:office:office"...
0xa82bf6  ldloc.3
0xa82bf7  ldstr    aEventtype// "EventType"
0xa82bfc  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c01  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa82c06  ldloc.1
0xa82c07  ldstr    aUrnSchemasMicr_30// "urn:schemas-microsoft-com:office:office"...
0xa82c0c  ldloc.3
0xa82c0d  ldstr    aTimezone_1// "TimeZone"
0xa82c12  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c17  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa82c1c  ldloc.1
0xa82c1d  ldstr    aUrnSchemasMicr_31// "urn:schemas-microsoft-com:office:office"...
0xa82c22  ldloc.3
0xa82c23  ldstr    aXmltzone// "XMLTZone"
0xa82c28  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c2d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82c32  ldloc.1
0xa82c33  ldstr    aUrnSchemasMicr_32// "urn:schemas-microsoft-com:office:office"...
0xa82c38  ldloc.3
0xa82c39  ldstr    aDuration// "Duration"
0xa82c3e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c43  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa82c48  ldloc.1
0xa82c49  ldstr    aUrnSchemasMicr_33// "urn:schemas-microsoft-com:office:office"...
0xa82c4e  ldloc.3
0xa82c4f  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82c54  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c59  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82c5e  ldloc.1
0xa82c5f  ldstr    aUrnSchemasMicr_34// "urn:schemas-microsoft-com:office:office"...
0xa82c64  ldloc.3
0xa82c65  ldstr    aWorkspace// "Workspace"
0xa82c6a  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82c6f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82c74  ldloc.3
0xa82c75  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa82c7a  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82c7f  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsSchedule(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa82c84  brfalse.s loc_A82CBB
0xa82c86  ldloc.1
0xa82c87  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa82c8c  ldarg.s  7
0xa82c8e  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa82c93  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82c98  ldloc.1
0xa82c99  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa82c9e  ldarg.s  7
0xa82ca0  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82ca5  stloc.s  6
0xa82ca7  ldloca.s 6
0xa82ca9  constrained. Microsoft.SharePoint.SPContentTypeId
0xa82caf  callvirt instance string [mscorlib]System.Object::ToString()
0xa82cb4  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82cb9  br.s     loc_A82D00
0xa82cbb  ldloc.3
0xa82cbc  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa82cc1  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82cc6  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsReservation(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa82ccb  brfalse.s loc_A82D00
0xa82ccd  ldloc.1
0xa82cce  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa82cd3  ldarg.s  8
0xa82cd5  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa82cda  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82cdf  ldloc.1
0xa82ce0  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa82ce5  ldarg.s  8
0xa82ce7  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82cec  stloc.s  7
0xa82cee  ldloca.s 7
0xa82cf0  constrained. Microsoft.SharePoint.SPContentTypeId
0xa82cf6  callvirt instance string [mscorlib]System.Object::ToString()
0xa82cfb  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82d00  ldloc.1
0xa82d01  ldstr    aUrnSchemasMicr_36// "urn:schemas-microsoft-com:office:office"...
0xa82d06  ldloc.3
0xa82d07  ldstr    aAuthor_0// "Author"
0xa82d0c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d11  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82d16  ldloc.1
0xa82d17  ldstr    aUrnSchemasMicr_37// "urn:schemas-microsoft-com:office:office"...
0xa82d1c  ldloc.3
0xa82d1d  ldstr    aCreated_0// "Created"
0xa82d22  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d27  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82d2c  ldloc.1
0xa82d2d  ldstr    aUrnSchemasMicr_14// "urn:schemas-microsoft-com:office:office"...
0xa82d32  ldloc.3
0xa82d33  ldstr    aEditor// "Editor"
0xa82d38  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d3d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82d42  ldloc.1
0xa82d43  ldstr    aUrnSchemasMicr_15// "urn:schemas-microsoft-com:office:office"...
0xa82d48  ldloc.3
0xa82d49  ldstr    aModified// "Modified"
0xa82d4e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d53  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82d58  ldloc.1
0xa82d59  ldstr    aUrnSchemasMicr_38// "urn:schemas-microsoft-com:office:office"...
0xa82d5e  ldarg.s  5
0xa82d60  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetGuidVar(string strName, valuetype [mscorlib]System.Guid guidValue)
0xa82d65  ldloc.1
0xa82d66  ldstr    aUrnSchemasMicr_40// "urn:schemas-microsoft-com:office:office"...
0xa82d6b  ldloc.3
0xa82d6c  ldstr    aRecurrenceid_1// "RecurrenceID"
0xa82d71  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d76  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82d7b  ldloc.1
0xa82d7c  ldstr    aUrnSchemasMicr_42// "urn:schemas-microsoft-com:office:office"...
0xa82d81  ldloc.3
0xa82d82  ldstr    aEventcanceled// "EventCanceled"
0xa82d87  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82d8c  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82d91  ldloc.1
0xa82d92  ldstr    aUrnSchemasMicr_41// "urn:schemas-microsoft-com:office:office"...
0xa82d97  ldarg.s  6
0xa82d99  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntVar(string strName, int32 intValue)
0xa82d9e  ldloc.1
0xa82d9f  ldstr    aUrnSchemasMicr_39// "urn:schemas-microsoft-com:office:office"...
0xa82da4  ldloc.3
0xa82da5  ldstr    aRecurrencedata// "RecurrenceData"
0xa82daa  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82daf  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82db4  ldloc.1
0xa82db5  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndMethod()
0xa82dba  ldloc.3
0xa82dbb  callvirt instance int32 Microsoft.SharePoint.SPItem::get_ID()
0xa82dc0  newobj   instance void ItemMap::.ctor(int32 scheduleItemId)
0xa82dc5  stloc.s  4
0xa82dc7  ldloc.3
0xa82dc8  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82dcd  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82dd2  brfalse.s loc_A82DFD
0xa82dd4  ldloc.3
0xa82dd5  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82dda  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82ddf  unbox.any [mscorlib]System.Boolean
0xa82de4  brfalse.s loc_A82DFD
0xa82de6  ldloc.s  4
0xa82de8  ldloc.3
0xa82de9  ldstr    aWorkspace// "Workspace"
0xa82dee  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82df3  castclass [mscorlib]System.String
0xa82df8  stfld    string ItemMap::MwsUrl
0xa82dfd  ldloc.3
0xa82dfe  callvirt instance class Microsoft.SharePoint.SPAttachmentCollection Microsoft.SharePoint.SPListItem::get_Attachments()
0xa82e03  callvirt instance int32 Microsoft.SharePoint.SPAttachmentCollection::get_Count()
0xa82e08  ldc.i4.0
0xa82e09  ble.s    loc_A82E13
0xa82e0b  ldloc.s  4
0xa82e0d  ldc.i4.1
0xa82e0e  stfld    bool ItemMap::HasAttachments
0xa82e13  ldloc.0
0xa82e14  ldstr    aA_4// "A"
0xa82e19  ldloc.2
0xa82e1a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa82e1f  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa82e24  call     string [mscorlib]System.String::Concat(string, string)
0xa82e29  ldloc.s  4
0xa82e2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Add(var<u1>, !!T0)
0xa82e30  ldloc.2
0xa82e31  brfalse.s loc_A82E39
0xa82e33  ldloc.2
0xa82e34  ldc.i4.s 0x64
0xa82e36  rem
0xa82e37  brfalse.s loc_A82E45
0xa82e39  ldloc.2
0xa82e3a  ldc.i4.1
0xa82e3b  add
0xa82e3c  ldarg.s  4
0xa82e3e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xa82e43  bne.un.s loc_A82E87
0xa82e45  ldloc.1
0xa82e46  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndBatch()
0xa82e4b  ldarg.1
0xa82e4c  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xa82e51  ldloc.1
0xa82e52  callvirt instance string [mscorlib]System.Object::ToString()
0xa82e57  callvirt instance string Microsoft.SharePoint.SPWeb::ProcessBatchData(string strBatchData)
0xa82e5c  stloc.s  5
0xa82e5e  ldarg.0
0xa82e5f  ldloc.0
0xa82e60  ldloc.s  5
0xa82e62  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpdateItemMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap, string strResults)
0xa82e67  ldarg.0
0xa82e68  ldarg.2
0xa82e69  ldarg.1
0xa82e6a  ldloc.0
0xa82e6b  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeAttachments(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82e70  ldarg.0
0xa82e71  ldarg.2
0xa82e72  ldarg.1
0xa82e73  ldloc.0
0xa82e74  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeMWS(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82e79  ldloc.0
0xa82e7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Clear()
0xa82e7f  ldloc.1
0xa82e80  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::Dispose()
0xa82e85  ldnull
0xa82e86  stloc.1
  ... truncated ...
```
