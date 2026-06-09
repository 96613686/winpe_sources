# Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateRecurrenceExceptions

- ea: `0xa826a0`
- end: `0xa82a95`
- name: `Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateRecurrenceExceptions`
- size: `1013`
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
- `0xa826a0`
- `0xa82eb0`
- `0xa82f60`
- `0xa830c0`
- `0xa83f40`
- `0xae8dd0`
- `0xae8e00`

## string_xrefs

- `0xa8291d`: `Created`
- `0xa8284f`: `WorkspaceLink`
- `0xa829b2`: `WorkspaceLink`
- `0xa829bf`: `WorkspaceLink`
- `0xa82823`: `XMLTZone`
- `0xa82899`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa828e0`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa8292d`: `urn:schemas-microsoft-com:office:office#Editor`
- `0xa82943`: `urn:schemas-microsoft-com:office:office#Modified`
- `0xa82715`: `urn:schemas-microsoft-com:office:office#Title`
- `0xa8272b`: `urn:schemas-microsoft-com:office:office#ParticipantsPicker`
- `0xa82741`: `urn:schemas-microsoft-com:office:office#Facilities`
- `0xa82757`: `urn:schemas-microsoft-com:office:office#EventDate`
- `0xa8276d`: `urn:schemas-microsoft-com:office:office#EndDate`
- `0xa82783`: `urn:schemas-microsoft-com:office:office#fAllDayEvent`
- `0xa82799`: `urn:schemas-microsoft-com:office:office#fRecurrence`
- `0xa827af`: `urn:schemas-microsoft-com:office:office#Location`
- `0xa827c5`: `urn:schemas-microsoft-com:office:office#Category`
- `0xa827db`: `urn:schemas-microsoft-com:office:office#Description`
- `0xa827f1`: `urn:schemas-microsoft-com:office:office#EventType`
- `0xa82807`: `urn:schemas-microsoft-com:office:office#TimeZone`
- `0xa8281d`: `urn:schemas-microsoft-com:office:office#XMLTZone`
- `0xa82833`: `urn:schemas-microsoft-com:office:office#Duration`
- `0xa82849`: `urn:schemas-microsoft-com:office:office#WorkspaceLink`
- `0xa8285f`: `urn:schemas-microsoft-com:office:office#Workspace`
- `0xa82887`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa828ce`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa82901`: `urn:schemas-microsoft-com:office:office#Author`
- `0xa82917`: `urn:schemas-microsoft-com:office:office#Created`
- `0xa82959`: `urn:schemas-microsoft-com:office:office#UID`
- `0xa82989`: `urn:schemas-microsoft-com:office:office#RecurrenceData`
- `0xa82966`: `urn:schemas-microsoft-com:office:office#RecurrenceID`
- `0xa8297c`: `urn:schemas-microsoft-com:office:office#MasterSeriesItemID`

## pseudocode

```c

```

## disassembly

```asm
0xa826a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::.ctor()
0xa826a5  stloc.0
0xa826a6  ldnull
0xa826a7  stloc.1
0xa826a8  ldc.i4.0
0xa826a9  stloc.2
0xa826aa  br       loc_A82A75
0xa826af  ldarg.3
0xa826b0  ldarg.s  4
0xa826b2  ldloc.2
0xa826b3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0xa826b8  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::get_Item(int32 iIndex)
0xa826bd  stloc.3
0xa826be  ldloc.1
0xa826bf  brtrue.s loc_A826CD
0xa826c1  newobj   instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::.ctor()
0xa826c6  stloc.1
0xa826c7  ldloc.1
0xa826c8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartBatch()
0xa826cd  ldloc.1
0xa826ce  ldstr    aA_4// "A"
0xa826d3  ldloc.2
0xa826d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa826d9  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa826de  call     string [mscorlib]System.String::Concat(string, string)
0xa826e3  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartMethod(string strID)
0xa826e8  ldloc.1
0xa826e9  ldarg.1
0xa826ea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa826ef  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetList(valuetype [mscorlib]System.Guid guid)
0xa826f4  ldloc.1
0xa826f5  ldstr    aCmd// "Cmd"
0xa826fa  ldstr    aSave_0// "Save"
0xa826ff  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82704  ldloc.1
0xa82705  ldstr    aId_0// "ID"
0xa8270a  ldstr    aNew// "New"
0xa8270f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82714  ldloc.1
0xa82715  ldstr    aUrnSchemasMicr_19// "urn:schemas-microsoft-com:office:office"...
0xa8271a  ldloc.3
0xa8271b  ldstr    aTitle_0// "Title"
0xa82720  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82725  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa8272a  ldloc.1
0xa8272b  ldstr    aUrnSchemasMicr_20// "urn:schemas-microsoft-com:office:office"...
0xa82730  ldloc.3
0xa82731  ldstr    aParticipantspi// "ParticipantsPicker"
0xa82736  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8273b  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82740  ldloc.1
0xa82741  ldstr    aUrnSchemasMicr_21// "urn:schemas-microsoft-com:office:office"...
0xa82746  ldloc.3
0xa82747  ldstr    aFacilities// "Facilities"
0xa8274c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82751  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82756  ldloc.1
0xa82757  ldstr    aUrnSchemasMicr_22// "urn:schemas-microsoft-com:office:office"...
0xa8275c  ldloc.3
0xa8275d  ldstr    aEventdate// "EventDate"
0xa82762  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82767  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa8276c  ldloc.1
0xa8276d  ldstr    aUrnSchemasMicr_23// "urn:schemas-microsoft-com:office:office"...
0xa82772  ldloc.3
0xa82773  ldstr    aEnddate_0// "EndDate"
0xa82778  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8277d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82782  ldloc.1
0xa82783  ldstr    aUrnSchemasMicr_24// "urn:schemas-microsoft-com:office:office"...
0xa82788  ldloc.3
0xa82789  ldstr    aFalldayevent// "fAllDayEvent"
0xa8278e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82793  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82798  ldloc.1
0xa82799  ldstr    aUrnSchemasMicr_25// "urn:schemas-microsoft-com:office:office"...
0xa8279e  ldloc.3
0xa8279f  ldstr    aFrecurrence// "fRecurrence"
0xa827a4  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa827a9  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa827ae  ldloc.1
0xa827af  ldstr    aUrnSchemasMicr_26// "urn:schemas-microsoft-com:office:office"...
0xa827b4  ldloc.3
0xa827b5  ldstr    aLocation// "Location"
0xa827ba  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa827bf  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa827c4  ldloc.1
0xa827c5  ldstr    aUrnSchemasMicr_27// "urn:schemas-microsoft-com:office:office"...
0xa827ca  ldloc.3
0xa827cb  ldstr    aCategory// "Category"
0xa827d0  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa827d5  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa827da  ldloc.1
0xa827db  ldstr    aUrnSchemasMicr_28// "urn:schemas-microsoft-com:office:office"...
0xa827e0  ldloc.3
0xa827e1  ldstr    aDescription// "Description"
0xa827e6  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa827eb  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa827f0  ldloc.1
0xa827f1  ldstr    aUrnSchemasMicr_29// "urn:schemas-microsoft-com:office:office"...
0xa827f6  ldloc.3
0xa827f7  ldstr    aEventtype// "EventType"
0xa827fc  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82801  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa82806  ldloc.1
0xa82807  ldstr    aUrnSchemasMicr_30// "urn:schemas-microsoft-com:office:office"...
0xa8280c  ldloc.3
0xa8280d  ldstr    aTimezone_1// "TimeZone"
0xa82812  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82817  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa8281c  ldloc.1
0xa8281d  ldstr    aUrnSchemasMicr_31// "urn:schemas-microsoft-com:office:office"...
0xa82822  ldloc.3
0xa82823  ldstr    aXmltzone// "XMLTZone"
0xa82828  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8282d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82832  ldloc.1
0xa82833  ldstr    aUrnSchemasMicr_32// "urn:schemas-microsoft-com:office:office"...
0xa82838  ldloc.3
0xa82839  ldstr    aDuration// "Duration"
0xa8283e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82843  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa82848  ldloc.1
0xa82849  ldstr    aUrnSchemasMicr_33// "urn:schemas-microsoft-com:office:office"...
0xa8284e  ldloc.3
0xa8284f  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82854  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82859  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa8285e  ldloc.1
0xa8285f  ldstr    aUrnSchemasMicr_34// "urn:schemas-microsoft-com:office:office"...
0xa82864  ldloc.3
0xa82865  ldstr    aWorkspace// "Workspace"
0xa8286a  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8286f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82874  ldloc.3
0xa82875  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa8287a  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa8287f  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsSchedule(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa82884  brfalse.s loc_A828BB
0xa82886  ldloc.1
0xa82887  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa8288c  ldarg.s  7
0xa8288e  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa82893  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82898  ldloc.1
0xa82899  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa8289e  ldarg.s  7
0xa828a0  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa828a5  stloc.s  6
0xa828a7  ldloca.s 6
0xa828a9  constrained. Microsoft.SharePoint.SPContentTypeId
0xa828af  callvirt instance string [mscorlib]System.Object::ToString()
0xa828b4  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa828b9  br.s     loc_A82900
0xa828bb  ldloc.3
0xa828bc  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa828c1  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa828c6  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsReservation(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa828cb  brfalse.s loc_A82900
0xa828cd  ldloc.1
0xa828ce  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa828d3  ldarg.s  8
0xa828d5  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa828da  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa828df  ldloc.1
0xa828e0  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa828e5  ldarg.s  8
0xa828e7  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa828ec  stloc.s  7
0xa828ee  ldloca.s 7
0xa828f0  constrained. Microsoft.SharePoint.SPContentTypeId
0xa828f6  callvirt instance string [mscorlib]System.Object::ToString()
0xa828fb  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa82900  ldloc.1
0xa82901  ldstr    aUrnSchemasMicr_36// "urn:schemas-microsoft-com:office:office"...
0xa82906  ldloc.3
0xa82907  ldstr    aAuthor_0// "Author"
0xa8290c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82911  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82916  ldloc.1
0xa82917  ldstr    aUrnSchemasMicr_37// "urn:schemas-microsoft-com:office:office"...
0xa8291c  ldloc.3
0xa8291d  ldstr    aCreated_0// "Created"
0xa82922  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82927  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa8292c  ldloc.1
0xa8292d  ldstr    aUrnSchemasMicr_14// "urn:schemas-microsoft-com:office:office"...
0xa82932  ldloc.3
0xa82933  ldstr    aEditor// "Editor"
0xa82938  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8293d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82942  ldloc.1
0xa82943  ldstr    aUrnSchemasMicr_15// "urn:schemas-microsoft-com:office:office"...
0xa82948  ldloc.3
0xa82949  ldstr    aModified// "Modified"
0xa8294e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82953  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82958  ldloc.1
0xa82959  ldstr    aUrnSchemasMicr_38// "urn:schemas-microsoft-com:office:office"...
0xa8295e  ldarg.s  5
0xa82960  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetGuidVar(string strName, valuetype [mscorlib]System.Guid guidValue)
0xa82965  ldloc.1
0xa82966  ldstr    aUrnSchemasMicr_40// "urn:schemas-microsoft-com:office:office"...
0xa8296b  ldloc.3
0xa8296c  ldstr    aRecurrenceid_1// "RecurrenceID"
0xa82971  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82976  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa8297b  ldloc.1
0xa8297c  ldstr    aUrnSchemasMicr_41// "urn:schemas-microsoft-com:office:office"...
0xa82981  ldarg.s  6
0xa82983  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntVar(string strName, int32 intValue)
0xa82988  ldloc.1
0xa82989  ldstr    aUrnSchemasMicr_39// "urn:schemas-microsoft-com:office:office"...
0xa8298e  ldloc.3
0xa8298f  ldstr    aRecurrencedata// "RecurrenceData"
0xa82994  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82999  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa8299e  ldloc.1
0xa8299f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndMethod()
0xa829a4  ldloc.3
0xa829a5  callvirt instance int32 Microsoft.SharePoint.SPItem::get_ID()
0xa829aa  newobj   instance void ItemMap::.ctor(int32 scheduleItemId)
0xa829af  stloc.s  4
0xa829b1  ldloc.3
0xa829b2  ldstr    aWorkspacelink// "WorkspaceLink"
0xa829b7  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa829bc  brfalse.s loc_A829E7
0xa829be  ldloc.3
0xa829bf  ldstr    aWorkspacelink// "WorkspaceLink"
0xa829c4  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa829c9  unbox.any [mscorlib]System.Boolean
0xa829ce  brfalse.s loc_A829E7
0xa829d0  ldloc.s  4
0xa829d2  ldloc.3
0xa829d3  ldstr    aWorkspace// "Workspace"
0xa829d8  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa829dd  castclass [mscorlib]System.String
0xa829e2  stfld    string ItemMap::MwsUrl
0xa829e7  ldloc.3
0xa829e8  callvirt instance class Microsoft.SharePoint.SPAttachmentCollection Microsoft.SharePoint.SPListItem::get_Attachments()
0xa829ed  callvirt instance int32 Microsoft.SharePoint.SPAttachmentCollection::get_Count()
0xa829f2  ldc.i4.0
0xa829f3  ble.s    loc_A829FD
0xa829f5  ldloc.s  4
0xa829f7  ldc.i4.1
0xa829f8  stfld    bool ItemMap::HasAttachments
0xa829fd  ldloc.0
0xa829fe  ldstr    aA_4// "A"
0xa82a03  ldloc.2
0xa82a04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa82a09  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa82a0e  call     string [mscorlib]System.String::Concat(string, string)
0xa82a13  ldloc.s  4
0xa82a15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Add(var<u1>, !!T0)
0xa82a1a  ldloc.2
0xa82a1b  brfalse.s loc_A82A23
0xa82a1d  ldloc.2
0xa82a1e  ldc.i4.s 0x64
0xa82a20  rem
0xa82a21  brfalse.s loc_A82A2F
0xa82a23  ldloc.2
0xa82a24  ldc.i4.1
0xa82a25  add
0xa82a26  ldarg.s  4
0xa82a28  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xa82a2d  bne.un.s loc_A82A71
0xa82a2f  ldloc.1
0xa82a30  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndBatch()
0xa82a35  ldarg.1
0xa82a36  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xa82a3b  ldloc.1
0xa82a3c  callvirt instance string [mscorlib]System.Object::ToString()
0xa82a41  callvirt instance string Microsoft.SharePoint.SPWeb::ProcessBatchData(string strBatchData)
0xa82a46  stloc.s  5
0xa82a48  ldarg.0
0xa82a49  ldloc.0
0xa82a4a  ldloc.s  5
0xa82a4c  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpdateItemMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap, string strResults)
0xa82a51  ldarg.0
0xa82a52  ldarg.2
0xa82a53  ldarg.1
0xa82a54  ldloc.0
0xa82a55  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeAttachments(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82a5a  ldarg.0
0xa82a5b  ldarg.2
0xa82a5c  ldarg.1
0xa82a5d  ldloc.0
0xa82a5e  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeMWS(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82a63  ldloc.0
0xa82a64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Clear()
0xa82a69  ldloc.1
0xa82a6a  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::Dispose()
0xa82a6f  ldnull
0xa82a70  stloc.1
0xa82a71  ldloc.2
0xa82a72  ldc.i4.1
0xa82a73  add
0xa82a74  stloc.2
0xa82a75  ldloc.2
0xa82a76  ldarg.s  4
  ... truncated ...
```
