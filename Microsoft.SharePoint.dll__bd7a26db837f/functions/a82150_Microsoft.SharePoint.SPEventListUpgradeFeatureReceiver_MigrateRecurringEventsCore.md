# Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateRecurringEventsCore

- ea: `0xa82150`
- end: `0xa82595`
- name: `Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::MigrateRecurringEventsCore`
- size: `1093`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa81c60`

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
- `0x79f550`
- `0xa82150`
- `0xa825a0`
- `0xa82eb0`
- `0xa82f60`
- `0xa830c0`
- `0xa83f40`
- `0xae8dd0`
- `0xae8e00`

## string_xrefs

- `0xa823e1`: `Created`
- `0xa82313`: `WorkspaceLink`
- `0xa8244f`: `WorkspaceLink`
- `0xa8245c`: `WorkspaceLink`
- `0xa822e7`: `XMLTZone`
- `0xa8235d`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa823a4`: `urn:schemas-microsoft-com:office:office#ContentTypeId`
- `0xa823f1`: `urn:schemas-microsoft-com:office:office#Editor`
- `0xa82407`: `urn:schemas-microsoft-com:office:office#Modified`
- `0xa821cc`: `urn:schemas-microsoft-com:office:office#Title`
- `0xa821e2`: `urn:schemas-microsoft-com:office:office#ParticipantsPicker`
- `0xa821f8`: `urn:schemas-microsoft-com:office:office#Facilities`
- `0xa8220e`: `urn:schemas-microsoft-com:office:office#EventDate`
- `0xa82224`: `urn:schemas-microsoft-com:office:office#EndDate`
- `0xa8223a`: `urn:schemas-microsoft-com:office:office#fAllDayEvent`
- `0xa82250`: `urn:schemas-microsoft-com:office:office#fRecurrence`
- `0xa82266`: `urn:schemas-microsoft-com:office:office#Location`
- `0xa8227c`: `urn:schemas-microsoft-com:office:office#Category`
- `0xa82292`: `urn:schemas-microsoft-com:office:office#Description`
- `0xa822a8`: `urn:schemas-microsoft-com:office:office#EventType`
- `0xa822cb`: `urn:schemas-microsoft-com:office:office#TimeZone`
- `0xa822e1`: `urn:schemas-microsoft-com:office:office#XMLTZone`
- `0xa822f7`: `urn:schemas-microsoft-com:office:office#Duration`
- `0xa8230d`: `urn:schemas-microsoft-com:office:office#WorkspaceLink`
- `0xa82323`: `urn:schemas-microsoft-com:office:office#Workspace`
- `0xa8234b`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa82392`: `urn:schemas-microsoft-com:office:office#ContentType`
- `0xa823c5`: `urn:schemas-microsoft-com:office:office#Author`
- `0xa823db`: `urn:schemas-microsoft-com:office:office#Created`
- `0xa822be`: `urn:schemas-microsoft-com:office:office#UID`
- `0xa8241d`: `urn:schemas-microsoft-com:office:office#RecurrenceData`

## pseudocode

```c

```

## disassembly

```asm
0xa82150  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::.ctor()
0xa82155  stloc.0
0xa82156  ldnull
0xa82157  stloc.1
0xa82158  ldc.i4.0
0xa82159  stloc.2
0xa8215a  br       loc_A82575
0xa8215f  ldarg.3
0xa82160  ldarg.s  4
0xa82162  ldloc.2
0xa82163  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0xa82168  callvirt instance class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.SPListItemCollection::get_Item(int32 iIndex)
0xa8216d  stloc.3
0xa8216e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xa82173  stloc.s  4
0xa82175  ldloc.1
0xa82176  brtrue.s loc_A82184
0xa82178  newobj   instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::.ctor()
0xa8217d  stloc.1
0xa8217e  ldloc.1
0xa8217f  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartBatch()
0xa82184  ldloc.1
0xa82185  ldstr    aA_4// "A"
0xa8218a  ldloc.2
0xa8218b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa82190  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa82195  call     string [mscorlib]System.String::Concat(string, string)
0xa8219a  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::StartMethod(string strID)
0xa8219f  ldloc.1
0xa821a0  ldarg.1
0xa821a1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPList::get_ID()
0xa821a6  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetList(valuetype [mscorlib]System.Guid guid)
0xa821ab  ldloc.1
0xa821ac  ldstr    aCmd// "Cmd"
0xa821b1  ldstr    aSave_0// "Save"
0xa821b6  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa821bb  ldloc.1
0xa821bc  ldstr    aId_0// "ID"
0xa821c1  ldstr    aNew// "New"
0xa821c6  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa821cb  ldloc.1
0xa821cc  ldstr    aUrnSchemasMicr_19// "urn:schemas-microsoft-com:office:office"...
0xa821d1  ldloc.3
0xa821d2  ldstr    aTitle_0// "Title"
0xa821d7  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa821dc  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa821e1  ldloc.1
0xa821e2  ldstr    aUrnSchemasMicr_20// "urn:schemas-microsoft-com:office:office"...
0xa821e7  ldloc.3
0xa821e8  ldstr    aParticipantspi// "ParticipantsPicker"
0xa821ed  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa821f2  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa821f7  ldloc.1
0xa821f8  ldstr    aUrnSchemasMicr_21// "urn:schemas-microsoft-com:office:office"...
0xa821fd  ldloc.3
0xa821fe  ldstr    aFacilities// "Facilities"
0xa82203  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82208  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa8220d  ldloc.1
0xa8220e  ldstr    aUrnSchemasMicr_22// "urn:schemas-microsoft-com:office:office"...
0xa82213  ldloc.3
0xa82214  ldstr    aEventdate// "EventDate"
0xa82219  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8221e  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82223  ldloc.1
0xa82224  ldstr    aUrnSchemasMicr_23// "urn:schemas-microsoft-com:office:office"...
0xa82229  ldloc.3
0xa8222a  ldstr    aEnddate_0// "EndDate"
0xa8222f  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82234  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa82239  ldloc.1
0xa8223a  ldstr    aUrnSchemasMicr_24// "urn:schemas-microsoft-com:office:office"...
0xa8223f  ldloc.3
0xa82240  ldstr    aFalldayevent// "fAllDayEvent"
0xa82245  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8224a  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa8224f  ldloc.1
0xa82250  ldstr    aUrnSchemasMicr_25// "urn:schemas-microsoft-com:office:office"...
0xa82255  ldloc.3
0xa82256  ldstr    aFrecurrence// "fRecurrence"
0xa8225b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82260  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82265  ldloc.1
0xa82266  ldstr    aUrnSchemasMicr_26// "urn:schemas-microsoft-com:office:office"...
0xa8226b  ldloc.3
0xa8226c  ldstr    aLocation// "Location"
0xa82271  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82276  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa8227b  ldloc.1
0xa8227c  ldstr    aUrnSchemasMicr_27// "urn:schemas-microsoft-com:office:office"...
0xa82281  ldloc.3
0xa82282  ldstr    aCategory// "Category"
0xa82287  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8228c  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82291  ldloc.1
0xa82292  ldstr    aUrnSchemasMicr_28// "urn:schemas-microsoft-com:office:office"...
0xa82297  ldloc.3
0xa82298  ldstr    aDescription// "Description"
0xa8229d  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa822a2  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa822a7  ldloc.1
0xa822a8  ldstr    aUrnSchemasMicr_29// "urn:schemas-microsoft-com:office:office"...
0xa822ad  ldloc.3
0xa822ae  ldstr    aEventtype// "EventType"
0xa822b3  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa822b8  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa822bd  ldloc.1
0xa822be  ldstr    aUrnSchemasMicr_38// "urn:schemas-microsoft-com:office:office"...
0xa822c3  ldloc.s  4
0xa822c5  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetGuidVar(string strName, valuetype [mscorlib]System.Guid guidValue)
0xa822ca  ldloc.1
0xa822cb  ldstr    aUrnSchemasMicr_30// "urn:schemas-microsoft-com:office:office"...
0xa822d0  ldloc.3
0xa822d1  ldstr    aTimezone_1// "TimeZone"
0xa822d6  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa822db  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa822e0  ldloc.1
0xa822e1  ldstr    aUrnSchemasMicr_31// "urn:schemas-microsoft-com:office:office"...
0xa822e6  ldloc.3
0xa822e7  ldstr    aXmltzone// "XMLTZone"
0xa822ec  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa822f1  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa822f6  ldloc.1
0xa822f7  ldstr    aUrnSchemasMicr_32// "urn:schemas-microsoft-com:office:office"...
0xa822fc  ldloc.3
0xa822fd  ldstr    aDuration// "Duration"
0xa82302  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82307  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetIntObjVar(string strName, object objValue)
0xa8230c  ldloc.1
0xa8230d  ldstr    aUrnSchemasMicr_33// "urn:schemas-microsoft-com:office:office"...
0xa82312  ldloc.3
0xa82313  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82318  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8231d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetBoolObjVar(string strName, object objValue)
0xa82322  ldloc.1
0xa82323  ldstr    aUrnSchemasMicr_34// "urn:schemas-microsoft-com:office:office"...
0xa82328  ldloc.3
0xa82329  ldstr    aWorkspace// "Workspace"
0xa8232e  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82333  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82338  ldloc.3
0xa82339  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa8233e  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82343  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsSchedule(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa82348  brfalse.s loc_A8237F
0xa8234a  ldloc.1
0xa8234b  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa82350  ldarg.s  5
0xa82352  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa82357  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa8235c  ldloc.1
0xa8235d  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa82362  ldarg.s  5
0xa82364  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa82369  stloc.s  9
0xa8236b  ldloca.s 9
0xa8236d  constrained. Microsoft.SharePoint.SPContentTypeId
0xa82373  callvirt instance string [mscorlib]System.Object::ToString()
0xa82378  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa8237d  br.s     loc_A823C4
0xa8237f  ldloc.3
0xa82380  callvirt instance class Microsoft.SharePoint.SPContentType Microsoft.SharePoint.SPListItem::get_ContentType()
0xa82385  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa8238a  call     bool Microsoft.SharePoint.Applications.GroupBoard.Utilities.GroupBoardUtility::IsReservation(valuetype Microsoft.SharePoint.SPContentTypeId id)
0xa8238f  brfalse.s loc_A823C4
0xa82391  ldloc.1
0xa82392  ldstr    aUrnSchemasMicr_35// "urn:schemas-microsoft-com:office:office"...
0xa82397  ldarg.s  6
0xa82399  callvirt instance string Microsoft.SharePoint.SPContentType::get_Name()
0xa8239e  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa823a3  ldloc.1
0xa823a4  ldstr    aUrnSchemasMicr_9// "urn:schemas-microsoft-com:office:office"...
0xa823a9  ldarg.s  6
0xa823ab  callvirt instance valuetype Microsoft.SharePoint.SPContentTypeId Microsoft.SharePoint.SPContentType::get_Id()
0xa823b0  stloc.s  0xA
0xa823b2  ldloca.s 0xA
0xa823b4  constrained. Microsoft.SharePoint.SPContentTypeId
0xa823ba  callvirt instance string [mscorlib]System.Object::ToString()
0xa823bf  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetVar(string strName, string strValue)
0xa823c4  ldloc.1
0xa823c5  ldstr    aUrnSchemasMicr_36// "urn:schemas-microsoft-com:office:office"...
0xa823ca  ldloc.3
0xa823cb  ldstr    aAuthor_0// "Author"
0xa823d0  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa823d5  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa823da  ldloc.1
0xa823db  ldstr    aUrnSchemasMicr_37// "urn:schemas-microsoft-com:office:office"...
0xa823e0  ldloc.3
0xa823e1  ldstr    aCreated_0// "Created"
0xa823e6  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa823eb  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa823f0  ldloc.1
0xa823f1  ldstr    aUrnSchemasMicr_14// "urn:schemas-microsoft-com:office:office"...
0xa823f6  ldloc.3
0xa823f7  ldstr    aEditor// "Editor"
0xa823fc  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82401  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82406  ldloc.1
0xa82407  ldstr    aUrnSchemasMicr_15// "urn:schemas-microsoft-com:office:office"...
0xa8240c  ldloc.3
0xa8240d  ldstr    aModified// "Modified"
0xa82412  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82417  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetDateTimeObjVar(string strName, object objValue)
0xa8241c  ldloc.1
0xa8241d  ldstr    aUrnSchemasMicr_39// "urn:schemas-microsoft-com:office:office"...
0xa82422  ldloc.3
0xa82423  ldstr    aRecurrencedata// "RecurrenceData"
0xa82428  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8242d  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::SetStrObjVar(string strName, object objValue)
0xa82432  ldloc.1
0xa82433  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndMethod()
0xa82438  ldloc.3
0xa82439  callvirt instance int32 Microsoft.SharePoint.SPItem::get_ID()
0xa8243e  newobj   instance void ItemMap::.ctor(int32 scheduleItemId)
0xa82443  stloc.s  5
0xa82445  ldloc.s  5
0xa82447  ldloc.s  4
0xa82449  stfld    valuetype [mscorlib]System.Guid ItemMap::Uid
0xa8244e  ldloc.3
0xa8244f  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82454  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82459  brfalse.s loc_A82484
0xa8245b  ldloc.3
0xa8245c  ldstr    aWorkspacelink// "WorkspaceLink"
0xa82461  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa82466  unbox.any [mscorlib]System.Boolean
0xa8246b  brfalse.s loc_A82484
0xa8246d  ldloc.s  5
0xa8246f  ldloc.3
0xa82470  ldstr    aWorkspace// "Workspace"
0xa82475  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0xa8247a  castclass [mscorlib]System.String
0xa8247f  stfld    string ItemMap::MwsUrl
0xa82484  ldloc.3
0xa82485  callvirt instance class Microsoft.SharePoint.SPAttachmentCollection Microsoft.SharePoint.SPListItem::get_Attachments()
0xa8248a  callvirt instance int32 Microsoft.SharePoint.SPAttachmentCollection::get_Count()
0xa8248f  ldc.i4.0
0xa82490  ble.s    loc_A8249A
0xa82492  ldloc.s  5
0xa82494  ldc.i4.1
0xa82495  stfld    bool ItemMap::HasAttachments
0xa8249a  ldloc.0
0xa8249b  ldstr    aA_4// "A"
0xa824a0  ldloc.2
0xa824a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa824a6  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xa824ab  call     string [mscorlib]System.String::Concat(string, string)
0xa824b0  ldloc.s  5
0xa824b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::Add(var<u1>, !!T0)
0xa824b7  ldloc.2
0xa824b8  brfalse.s loc_A824C0
0xa824ba  ldloc.2
0xa824bb  ldc.i4.s 0x64
0xa824bd  rem
0xa824be  brfalse.s loc_A824CF
0xa824c0  ldloc.2
0xa824c1  ldc.i4.1
0xa824c2  add
0xa824c3  ldarg.s  4
0xa824c5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0xa824ca  bne.un   loc_A82571
0xa824cf  ldloc.1
0xa824d0  callvirt instance void Microsoft.SharePoint.Utilities.SPBatchXmlWriter::EndBatch()
0xa824d5  ldarg.1
0xa824d6  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xa824db  ldloc.1
0xa824dc  callvirt instance string [mscorlib]System.Object::ToString()
0xa824e1  callvirt instance string Microsoft.SharePoint.SPWeb::ProcessBatchData(string strBatchData)
0xa824e6  stloc.s  6
0xa824e8  ldarg.0
0xa824e9  ldloc.0
0xa824ea  ldloc.s  6
0xa824ec  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpdateItemMap(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap, string strResults)
0xa824f1  ldarg.0
0xa824f2  ldarg.2
0xa824f3  ldarg.1
0xa824f4  ldloc.0
0xa824f5  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeAttachments(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa824fa  ldarg.0
0xa824fb  ldarg.2
0xa824fc  ldarg.1
0xa824fd  ldloc.0
0xa824fe  call     instance void Microsoft.SharePoint.SPEventListUpgradeFeatureReceiver::UpgradeMWS(class Microsoft.SharePoint.SPList scheduleList, class Microsoft.SharePoint.SPList newEventList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap> dicItemMap)
0xa82503  ldloc.0
0xa82504  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ItemMap>::GetEnumerator()
0xa82509  stloc.s  0xB
0xa8250b  br.s     loc_A8254A
0xa8250d  ldloca.s 0xB
0xa8250f  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class ItemMap>::get_Current()
0xa82514  stloc.s  7
0xa82516  ldloca.s 7
0xa82518  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class ItemMap>::get_Value()
0xa8251d  stloc.s  8
0xa8251f  ldloc.s  8
0xa82521  ldfld    int32 ItemMap::EventItemId
0xa82526  ldc.i4.0
0xa82527  ble.s    loc_A8254A
0xa82529  ldarg.0
0xa8252a  ldarg.1
0xa8252b  ldarg.2
  ... truncated ...
```
