# Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateSingleEventsCore

- ea: `0xa81d90`
- end: `0xa8214c`
- name: `Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateSingleEventsCore`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa81b40`

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
- `0x79f530`
- `0xa81d90`
- `0xa82eb0`
- `0xa82f60`
- `0xa830c0`
- `0xa83f40`
- `0xae8dd0`
- `0xae8e00`

## string_xrefs

- `0xa8201a`: `Created`
- `0xa81f4c`: `WorkspaceLink`
- `0xa82069`: `WorkspaceLink`
- `0xa82076`: `WorkspaceLink`
- `0xa81f20`: `XMLTZone`
- `0xa81f96`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa81fdd`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa8202a`: `urn:schemas-microsoft-com:office:office#Editor`
- `0xa82040`: `urn:schemas-microsoft-com:office:office#Modified`
- `0xa81e05`: `urn:schemas-microsoft-com:office:office#Title`
- `0xa81e1b`: `urn:schemas-microsoft-com:office:office#ParticipantsPicker`
- `0xa81e31`: `urn:schemas-microsoft-com:office:office#Facilities`
- `0xa81e47`: `urn:schemas-microsoft-com:office:office#EventDate`
- `0xa81e5d`: `urn:schemas-microsoft-com:office:office#EndDate`
- `0xa81e73`: `urn:schemas-microsoft-com:office:office#fAllDayEvent`
- `0xa81e96`: `urn:schemas-microsoft-com:office:office#fRecurrence`
- `0xa81eac`: `urn:schemas-microsoft-com:office:office#Location`
- `0xa81ec2`: `urn:schemas-microsoft-com:office:office#Category`
- `0xa81ed8`: `urn:schemas-microsoft-com:office:office#Description`
- `0xa81eee`: `urn:schemas-microsoft-com:office:office#EventType`
- `0xa81f04`: `urn:schemas-microsoft-com:office:office#TimeZone`
- `0xa81f1a`: `urn:schemas-microsoft-com:office:office#XMLTZone`
- `0xa81f30`: `urn:schemas-microsoft-com:office:office#Duration`
- `0xa81f46`: `urn:schemas-microsoft-com:office:office#WorkspaceLink`
- `0xa81f5c`: `urn:schemas-microsoft-com:office:office#Workspace`
- `0xa81f84`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa81fcb`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa81ffe`: `urn:schemas-microsoft-com:office:office#Author`
- `0xa82014`: `urn:schemas-microsoft-com:office:office#Created`

## pseudocode

```c

```

## disassembly

```asm
0xa81d90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::.ctor()
0xa81d95  stloc.0
0xa81d96  ldnull
0xa81d97  stloc.1
0xa81d98  ldc.i4.0
0xa81d99  stloc.2
0xa81d9a  br       loc_A8212C
0xa81d9f  ldarg.3
0xa81da0  ldarg.s  4
0xa81da2  ldloc.2
0xa81da3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0xa81da8  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::get_Item(int32 iIndex)
0xa81dad  stloc.3
0xa81dae  ldloc.1
0xa81daf  brtrue.s loc_A81DBD
0xa81db1  newobj   instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::.ctor()
0xa81db6  stloc.1
0xa81db7  ldloc.1
0xa81db8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartBatch()
0xa81dbd  ldloc.1
0xa81dbe  ldstr    aA_4// "A"
0xa81dc3  ldloc.2
0xa81dc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa81dc9  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa81dce  call     string [mscorlib]System.String::Concat(string, string)
0xa81dd3  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartMethod(string strID)
0xa81dd8  ldloc.1
0xa81dd9  ldarg.1
0xa81dda  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa81ddf  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetList(valuetype [mscorlib]System.Guid guid)
0xa81de4  ldloc.1
0xa81de5  ldstr    aCmd// "Cmd"
0xa81dea  ldstr    aSave_0// "Save"
0xa81def  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81df4  ldloc.1
0xa81df5  ldstr    aId_0// "ID"
0xa81dfa  ldstr    aNew// "New"
0xa81dff  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81e04  ldloc.1
0xa81e05  ldstr    aUrnSchemasMicr_19// "urn:schemas-microsoft-com:office:office"...
0xa81e0a  ldloc.3
0xa81e0b  ldstr    aTitle_0// "Title"
0xa81e10  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e15  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81e1a  ldloc.1
0xa81e1b  ldstr    aUrnSchemasMicr_20// "urn:schemas-microsoft-com:office:office"...
0xa81e20  ldloc.3
0xa81e21  ldstr    aParticipantspi// "ParticipantsPicker"
0xa81e26  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e2b  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81e30  ldloc.1
0xa81e31  ldstr    aUrnSchemasMicr_21// "urn:schemas-microsoft-com:office:office"...
0xa81e36  ldloc.3
0xa81e37  ldstr    aFacilities// "Facilities"
0xa81e3c  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e41  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81e46  ldloc.1
0xa81e47  ldstr    aUrnSchemasMicr_22// "urn:schemas-microsoft-com:office:office"...
0xa81e4c  ldloc.3
0xa81e4d  ldstr    aEventdate// "EventDate"
0xa81e52  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e57  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa81e5c  ldloc.1
0xa81e5d  ldstr    aUrnSchemasMicr_23// "urn:schemas-microsoft-com:office:office"...
0xa81e62  ldloc.3
0xa81e63  ldstr    aEnddate_0// "EndDate"
0xa81e68  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e6d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa81e72  ldloc.1
0xa81e73  ldstr    aUrnSchemasMicr_24// "urn:schemas-microsoft-com:office:office"...
0xa81e78  ldloc.3
0xa81e79  ldstr    aFalldayevent// "fAllDayEvent"
0xa81e7e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e83  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa81e88  ldloc.3
0xa81e89  ldstr    aFrecurrence// "fRecurrence"
0xa81e8e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81e93  brfalse.s loc_A81EAB
0xa81e95  ldloc.1
0xa81e96  ldstr    aUrnSchemasMicr_25// "urn:schemas-microsoft-com:office:office"...
0xa81e9b  ldloc.3
0xa81e9c  ldstr    aFrecurrence// "fRecurrence"
0xa81ea1  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81ea6  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa81eab  ldloc.1
0xa81eac  ldstr    aUrnSchemasMicr_26// "urn:schemas-microsoft-com:office:office"...
0xa81eb1  ldloc.3
0xa81eb2  ldstr    aLocation// "Location"
0xa81eb7  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81ebc  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81ec1  ldloc.1
0xa81ec2  ldstr    aUrnSchemasMicr_27// "urn:schemas-microsoft-com:office:office"...
0xa81ec7  ldloc.3
0xa81ec8  ldstr    aCategory// "Category"
0xa81ecd  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81ed2  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81ed7  ldloc.1
0xa81ed8  ldstr    aUrnSchemasMicr_28// "urn:schemas-microsoft-com:office:office"...
0xa81edd  ldloc.3
0xa81ede  ldstr    aDescription// "Description"
0xa81ee3  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81ee8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81eed  ldloc.1
0xa81eee  ldstr    aUrnSchemasMicr_29// "urn:schemas-microsoft-com:office:office"...
0xa81ef3  ldloc.3
0xa81ef4  ldstr    aEventtype// "EventType"
0xa81ef9  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81efe  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa81f03  ldloc.1
0xa81f04  ldstr    aUrnSchemasMicr_30// "urn:schemas-microsoft-com:office:office"...
0xa81f09  ldloc.3
0xa81f0a  ldstr    aTimezone_1// "TimeZone"
0xa81f0f  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81f14  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa81f19  ldloc.1
0xa81f1a  ldstr    aUrnSchemasMicr_31// "urn:schemas-microsoft-com:office:office"...
0xa81f1f  ldloc.3
0xa81f20  ldstr    aXmltzone// "XMLTZone"
0xa81f25  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81f2a  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81f2f  ldloc.1
0xa81f30  ldstr    aUrnSchemasMicr_32// "urn:schemas-microsoft-com:office:office"...
0xa81f35  ldloc.3
0xa81f36  ldstr    aDuration// "Duration"
0xa81f3b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81f40  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa81f45  ldloc.1
0xa81f46  ldstr    aUrnSchemasMicr_33// "urn:schemas-microsoft-com:office:office"...
0xa81f4b  ldloc.3
0xa81f4c  ldstr    aWorkspacelink// "WorkspaceLink"
0xa81f51  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81f56  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa81f5b  ldloc.1
0xa81f5c  ldstr    aUrnSchemasMicr_34// "urn:schemas-microsoft-com:office:office"...
0xa81f61  ldloc.3
0xa81f62  ldstr    aWorkspace// "Workspace"
0xa81f67  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa81f6c  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa81f71  ldloc.3
0xa81f72  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa81f77  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa81f7c  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsSchedule(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa81f81  brfalse.s loc_A81FB8
0xa81f83  ldloc.1
0xa81f84  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa81f89  ldarg.s  5
0xa81f8b  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa81f90  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81f95  ldloc.1
0xa81f96  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa81f9b  ldarg.s  5
0xa81f9d  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa81fa2  stloc.s  6
0xa81fa4  ldloca.s 6
0xa81fa6  constrained. Microsoft.SharePoint.SPContentTypeId
0xa81fac  callvirt instance string [mscorlib]System.Object::ToString()
0xa81fb1  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81fb6  br.s     loc_A81FFD
0xa81fb8  ldloc.3
0xa81fb9  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa81fbe  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa81fc3  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsReservation(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa81fc8  brfalse.s loc_A81FFD
0xa81fca  ldloc.1
0xa81fcb  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa81fd0  ldarg.s  6
0xa81fd2  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa81fd7  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81fdc  ldloc.1
0xa81fdd  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa81fe2  ldarg.s  6
0xa81fe4  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa81fe9  stloc.s  7
0xa81feb  ldloca.s 7
0xa81fed  constrained. Microsoft.SharePoint.SPContentTypeId
0xa81ff3  callvirt instance string [mscorlib]System.Object::ToString()
0xa81ff8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa81ffd  ldloc.1
0xa81ffe  ldstr    aUrnSchemasMicr_36// "urn:schemas-microsoft-com:office:office"...
0xa82003  ldloc.3
0xa82004  ldstr    aAuthor_0// "Author"
0xa82009  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8200e  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82013  ldloc.1
0xa82014  ldstr    aUrnSchemasMicr_37// "urn:schemas-microsoft-com:office:office"...
0xa82019  ldloc.3
0xa8201a  ldstr    aCreated_0// "Created"
0xa8201f  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82024  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82029  ldloc.1
0xa8202a  ldstr    aUrnSchemasMicr_14// "urn:schemas-microsoft-com:office:office"...
0xa8202f  ldloc.3
0xa82030  ldstr    aEditor// "Editor"
0xa82035  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8203a  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa8203f  ldloc.1
0xa82040  ldstr    aUrnSchemasMicr_15// "urn:schemas-microsoft-com:office:office"...
0xa82045  ldloc.3
0xa82046  ldstr    aModified// "Modified"
0xa8204b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82050  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82055  ldloc.1
0xa82056  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndMethod()
0xa8205b  ldloc.3
0xa8205c  callvirt instance int32 Microsoft.SharePoint.SPItem::get_ID()
0xa82061  newobj   instance void ItemMap::.ctor(int32 scheduleItemId)
0xa82066  stloc.s  4
0xa82068  ldloc.3
0xa82069  ldstr    aWorkspacelink// "WorkspaceLink"
0xa8206e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82073  brfalse.s loc_A8209E
0xa82075  ldloc.3
0xa82076  ldstr    aWorkspacelink// "WorkspaceLink"
0xa8207b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82080  unbox.any [mscorlib]System.Boolean
0xa82085  brfalse.s loc_A8209E
0xa82087  ldloc.s  4
0xa82089  ldloc.3
0xa8208a  ldstr    aWorkspace// "Workspace"
0xa8208f  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82094  castclass [mscorlib]System.String
0xa82099  stfld    string ItemMap::MwsUrl
0xa8209e  ldloc.3
0xa8209f  callvirt instance class Microsoft.SharePoint.SPAttachmentCollection Microsoft.SharePoint.SPListItem::get_Attachments()
0xa820a4  callvirt instance int32 Microsoft.SharePoint.SPAttachmentCollection::get_Count()
0xa820a9  ldc.i4.0
0xa820aa  ble.s    loc_A820B4
0xa820ac  ldloc.s  4
0xa820ae  ldc.i4.1
0xa820af  stfld    bool ItemMap::HasAttachments
0xa820b4  ldloc.0
0xa820b5  ldstr    aA_4// "A"
0xa820ba  ldloc.2
0xa820bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa820c0  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa820c5  call     string [mscorlib]System.String::Concat(string, string)
0xa820ca  ldloc.s  4
0xa820cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Add(var<u1>, !!T0)
0xa820d1  ldloc.2
0xa820d2  brfalse.s loc_A820DA
0xa820d4  ldloc.2
0xa820d5  ldc.i4.s 0x64
0xa820d7  rem
0xa820d8  brfalse.s loc_A820E6
0xa820da  ldloc.2
0xa820db  ldc.i4.1
0xa820dc  add
0xa820dd  ldarg.s  4
0xa820df  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xa820e4  bne.un.s loc_A82128
0xa820e6  ldloc.1
0xa820e7  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndBatch()
0xa820ec  ldarg.1
0xa820ed  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xa820f2  ldloc.1
0xa820f3  callvirt instance string [mscorlib]System.Object::ToString()
0xa820f8  callvirt instance string Microsoft.SharePoint.SPWeb::ProcessBatchData(string strBatchData)
0xa820fd  stloc.s  5
0xa820ff  ldarg.0
0xa82100  ldloc.0
0xa82101  ldloc.s  5
0xa82103  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpdateItemMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap, string strResults)
0xa82108  ldarg.0
0xa82109  ldarg.2
0xa8210a  ldarg.1
0xa8210b  ldloc.0
0xa8210c  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeAttachments(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82111  ldarg.0
0xa82112  ldarg.2
0xa82113  ldarg.1
0xa82114  ldloc.0
0xa82115  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeMWS(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa8211a  ldloc.0
0xa8211b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Clear()
0xa82120  ldloc.1
0xa82121  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::Dispose()
0xa82126  ldnull
0xa82127  stloc.1
0xa82128  ldloc.2
0xa82129  ldc.i4.1
0xa8212a  add
0xa8212b  stloc.2
0xa8212c  ldloc.2
0xa8212d  ldarg.s  4
0xa8212f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xa82134  blt      loc_A81D9F
0xa82139  leave.s  loc_A8214B
0xa8213b  ldloc.0
0xa8213c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Clear()
0xa82141  ldloc.1
0xa82142  brfalse.s loc_A8214A
0xa82144  ldloc.1
0xa82145  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::Dispose()
0xa8214a  endfinally
0xa8214b  ret
```
