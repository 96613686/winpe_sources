# Microsoft.SharePoint.SPAccessRequests::UpdateItem

- ea: `0x4995f0`
- end: `0x4999d2`
- name: `Microsoft.SharePoint.SPAccessRequests::UpdateItem`
- size: `994`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x498b90`
- `0x4992b0`

## callees

- `0x1c18c0`
- `0x342e60`
- `0x3e99f0`
- `0x3e9a20`
- `0x475c60`
- `0x496640`
- `0x4966d0`
- `0x4966f0`
- `0x496710`
- `0x496730`
- `0x496750`
- `0x496800`
- `0x496880`
- `0x496be0`
- `0x496cf0`
- `0x497490`
- `0x4995f0`
- `0x4999e0`
- `0x499a90`
- `0x499cd0`
- `0x49a2d0`
- `0x4cd8e0`
- `0x4cd940`
- `0x52a050`
- `0x5c24f0`
- `0x678580`
- `0x7536d0`
- `0x93dab0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x499654`: `PropagateAcl`
- `0x499664`: `PropagateAcl`
- `0x499691`: `PropagateAcl`
- `0x4996bc`: `PropagateAcl`
- `0x499681`: `UpdateItem: Upgrade Access Request list to update the field {0} has succeeded`
- `0x4996ac`: `UpdateItem: Upgrade Access Request list to add the field {0} has failed`
- `0x499717`: `SPAccessRequests::UpdateItem - Update Access Request conversation start.`
- `0x49980a`: `SPAccessRequests::UpdateItem: we will start ItemUpdating for the list item.`
- `0x49986d`: `ExtendedWelcomeEmailBody`
- `0x4998d7`: `SPAccessRequests::UpdateItem:invitation will be extended.`
- `0x49991f`: `AnonymousLinkType`
- `0x49993a`: `SPAccessRequests::UpdateItem: we set needed properties that will be updated.`
- `0x499957`: `SPAccessRequests::UpdateItem: Successfully finished updating item.`
- `0x499985`: `SPAccessRequests::UpdateItem - Update Access Request conversation success.`
- `0x499991`: `The operation couldn't be completed. Please try again or contact your administrator.`
- `0x4999ac`: `SPAccessRequests::UpdateItem - Update invitation failed with exception {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x4995f0  ldarg.s  8
0x4995f2  newobj   instance void Microsoft.SharePoint.SPCachedItemEventProperties::.ctor(class Microsoft.SharePoint.SPListItem actualItem)
0x4995f7  stloc.0
0x4995f8  ldloc.0
0x4995f9  ldarg.s  7
0x4995fb  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x499600  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x499605  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_Site(class Microsoft.SharePoint.SPSite value)
0x49960a  ldloc.0
0x49960b  ldarg.s  7
0x49960d  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x499612  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_Web(class Microsoft.SharePoint.SPWeb value)
0x499617  ldloc.0
0x499618  ldarg.s  7
0x49961a  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_List(class Microsoft.SharePoint.SPList value)
0x49961f  ldloc.0
0x499620  ldarg.s  0xC
0x499622  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_SendInvitationEmail(bool value)
0x499627  ldloc.0
0x499628  ldarg.s  0xD
0x49962a  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_PropagateAcl(bool value)
0x49962f  ldloc.0
0x499630  ldarg.s  0xF
0x499632  callvirt instance void Microsoft.SharePoint.SPCachedItemEventProperties::set_CanSendReminderIfEnabled(bool value)
0x499637  call     bool Microsoft.SharePoint.SPContext::get_IsCurrentContextInitialized()
0x49963c  brfalse  loc_4996C9
0x499641  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x499646  ldc.i4   0x2BCD
0x49964b  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x499650  brfalse.s loc_4996C9
0x499652  ldarg.s  7
0x499654  ldstr    aPropagateacl_0// "PropagateAcl"
0x499659  call     bool Microsoft.SharePoint.SPSharingEmailHelper::UpgradeAccessRequestList(class Microsoft.SharePoint.SPList accReqList, string fieldInternalName)
0x49965e  stloc.1
0x49965f  ldloc.1
0x499660  brfalse.s loc_4996A0
0x499662  ldarg.s  8
0x499664  ldstr    aPropagateacl_0// "PropagateAcl"
0x499669  ldarg.s  0xD
0x49966b  box      [mscorlib]System.Boolean
0x499670  callvirt instance void Microsoft.SharePoint.SPItem::set_Item(string fieldName, object value)
0x499675  ldc.i4   0x11CD554
0x49967a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x49967f  ldc.i4.s 0x32
0x499681  ldstr    aUpdateitemUpgr// "UpdateItem: Upgrade Access Request list"...
0x499686  ldc.i4.1
0x499687  newarr   [mscorlib]System.Object
0x49968c  stloc.s  6
0x49968e  ldloc.s  6
0x499690  ldc.i4.0
0x499691  ldstr    aPropagateacl_0// "PropagateAcl"
0x499696  stelem.ref
0x499697  ldloc.s  6
0x499699  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x49969e  br.s     loc_4996C9
0x4996a0  ldc.i4   0x11CD555
0x4996a5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4996aa  ldc.i4.s 0x32
0x4996ac  ldstr    aUpdateitemUpgr_0// "UpdateItem: Upgrade Access Request list"...
0x4996b1  ldc.i4.1
0x4996b2  newarr   [mscorlib]System.Object
0x4996b7  stloc.s  7
0x4996b9  ldloc.s  7
0x4996bb  ldc.i4.0
0x4996bc  ldstr    aPropagateacl_0// "PropagateAcl"
0x4996c1  stelem.ref
0x4996c2  ldloc.s  7
0x4996c4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x4996c9  ldarg.s  4
0x4996cb  ldc.i4.0
0x4996cc  ble.s    loc_4996EA
0x4996ce  ldloc.0
0x4996cf  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x4996d4  ldsfld   valuetype [mscorlib]System.Guid FieldIds::PermissionLevelRequested
0x4996d9  ldarga.s 4
0x4996db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4996e0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4996e5  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x4996ea  ldarg.3
0x4996eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4996f0  brtrue.s loc_499703
0x4996f2  ldloc.0
0x4996f3  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x4996f8  ldsfld   valuetype [mscorlib]System.Guid FieldIds::PermissionType
0x4996fd  ldarg.3
0x4996fe  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x499703  ldarg.2
0x499704  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x499709  brtrue.s loc_499732
0x49970b  ldc.i4   0x362897
0x499710  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x499715  ldc.i4.s 0xF
0x499717  ldstr    aSpaccessreques_44// "SPAccessRequests::UpdateItem - Update A"...
0x49971c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x499721  ldloc.0
0x499722  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x499727  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Conversation
0x49972c  ldarg.2
0x49972d  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x499732  ldarg.s  0xE
0x499734  brfalse.s loc_499748
0x499736  ldloc.0
0x499737  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x49973c  ldsfld   valuetype [mscorlib]System.Guid FieldIds::ExtendedWelcomeEmailBody
0x499741  ldarg.s  0xE
0x499743  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x499748  ldarg.0
0x499749  ldc.i4.0
0x49974a  blt.s    loc_499768
0x49974c  ldloc.0
0x49974d  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x499752  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Status
0x499757  ldarga.s 0
0x499759  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49975e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x499763  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x499768  ldarg.1
0x499769  brfalse.s loc_49978F
0x49976b  ldloc.0
0x49976c  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x499771  ldsfld   valuetype [mscorlib]System.Guid FieldIds::RequestedForUserId
0x499776  ldarg.1
0x499777  callvirt instance int32 Microsoft.SharePoint.SPMember::get_ID()
0x49977c  stloc.s  8
0x49977e  ldloca.s 8
0x499780  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x499785  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x49978a  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x49978f  ldarg.s  5
0x499791  brfalse.s loc_4997CC
0x499793  ldloc.0
0x499794  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x499799  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Status
0x49979e  ldc.i4.0
0x49979f  stloc.s  9
0x4997a1  ldloca.s 9
0x4997a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4997a8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4997ad  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x4997b2  ldloc.0
0x4997b3  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x4997b8  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Expires
0x4997bd  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPAccessRequestsUtility::GetExpiryDateForInvitations()
0x4997c2  box      [mscorlib]System.DateTime
0x4997c7  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x4997cc  ldarg.s  6
0x4997ce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4997d3  brtrue.s loc_4997E7
0x4997d5  ldloc.0
0x4997d6  callvirt instance class Microsoft.SharePoint.SPCachedItemProperties Microsoft.SharePoint.SPCachedItemEventProperties::get_AfterProperties()
0x4997db  ldsfld   valuetype [mscorlib]System.Guid FieldIds::AnonymousLinkType
0x4997e0  ldarg.s  6
0x4997e2  callvirt instance void Microsoft.SharePoint.SPCachedItemProperties::set_Item(valuetype [mscorlib]System.Guid fieldId, object value)
0x4997e7  newobj   instance void Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext::.ctor()
0x4997ec  stloc.2
0x4997ed  ldloc.0
0x4997ee  ldarg.s  9
0x4997f0  ldarg.s  0xA
0x4997f2  ldarg.s  0xB
0x4997f4  call     bool Microsoft.SharePoint.SPAccessRequestsOperationHandler::ItemUpdating(class Microsoft.SharePoint.SPCachedItemEventProperties properties, class Microsoft.SharePoint.SPUserCollection users, class Microsoft.SharePoint.SPGroupCollection groups, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.SPRoleDefinition> roleDefs)
0x4997f9  brfalse  loc_499991
0x4997fe  ldc.i4   0x164575C
0x499803  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x499808  ldc.i4.s 0x32
0x49980a  ldstr    aSpaccessreques_45// "SPAccessRequests::UpdateItem: we will s"...
0x49980f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x499814  ldloc.0
0x499815  ldloca.s 3
0x499817  call     bool Microsoft.SharePoint.SPAccessRequestsOperationHandler::IsStatusChanging(class Microsoft.SharePoint.SPCachedItemEventProperties properties, [out] int32& newStatus)
0x49981c  pop
0x49981d  ldc.i4.0
0x49981e  stloc.s  4
0x499820  ldarg.s  4
0x499822  ldc.i4.0
0x499823  ble.s    loc_499848
0x499825  ldarg.s  8
0x499827  ldloc.0
0x499828  ldloc.2
0x499829  ldarg.s  0xA
0x49982b  ldarg.s  0xB
0x49982d  call     bool Microsoft.SharePoint.SPAccessRequests::AuditRequestItemPermissionLevelChange(class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext, class Microsoft.SharePoint.SPGroupCollection groups, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.SPRoleDefinition> roleDefs)
0x499832  stloc.s  4
0x499834  ldsfld   valuetype [mscorlib]System.Guid FieldIds::PermissionLevelRequested
0x499839  ldstr    aPermissionleve// "PermissionLevelRequested"
0x49983e  ldarg.s  8
0x499840  ldloc.0
0x499841  ldnull
0x499842  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x499847  pop
0x499848  ldarg.3
0x499849  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x49984e  brtrue.s loc_499864
0x499850  ldsfld   valuetype [mscorlib]System.Guid FieldIds::PermissionType
0x499855  ldstr    aPermissiontype_0// "PermissionType"
0x49985a  ldarg.s  8
0x49985c  ldloc.0
0x49985d  ldnull
0x49985e  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x499863  pop
0x499864  ldarg.s  0xE
0x499866  brfalse.s loc_49987C
0x499868  ldsfld   valuetype [mscorlib]System.Guid FieldIds::ExtendedWelcomeEmailBody
0x49986d  ldstr    aExtendedwelcom_1// "ExtendedWelcomeEmailBody"
0x499872  ldarg.s  8
0x499874  ldloc.0
0x499875  ldnull
0x499876  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x49987b  pop
0x49987c  ldarg.2
0x49987d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x499882  brtrue.s loc_499898
0x499884  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Conversation
0x499889  ldstr    aConversation// "Conversation"
0x49988e  ldarg.s  8
0x499890  ldloc.0
0x499891  ldnull
0x499892  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x499897  pop
0x499898  ldarg.0
0x499899  ldc.i4.0
0x49989a  blt.s    loc_4998B0
0x49989c  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Status
0x4998a1  ldstr    aStatus_1// "Status"
0x4998a6  ldarg.s  8
0x4998a8  ldloc.0
0x4998a9  ldnull
0x4998aa  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x4998af  pop
0x4998b0  ldarg.1
0x4998b1  brfalse.s loc_4998C7
0x4998b3  ldsfld   valuetype [mscorlib]System.Guid FieldIds::RequestedForUserId
0x4998b8  ldstr    aRequestedforus// "RequestedForUserId"
0x4998bd  ldarg.s  8
0x4998bf  ldloc.0
0x4998c0  ldnull
0x4998c1  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x4998c6  pop
0x4998c7  ldarg.s  5
0x4998c9  brfalse.s loc_499911
0x4998cb  ldc.i4   0x164575D
0x4998d0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4998d5  ldc.i4.s 0x32
0x4998d7  ldstr    aSpaccessreques_46// "SPAccessRequests::UpdateItem:invitation"...
0x4998dc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x4998e1  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Status
0x4998e6  ldstr    aStatus_1// "Status"
0x4998eb  ldarg.s  8
0x4998ed  ldloc.0
0x4998ee  ldnull
0x4998ef  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x4998f4  pop
0x4998f5  ldsfld   valuetype [mscorlib]System.Guid FieldIds::Expires
0x4998fa  ldstr    aExpireDate// "Expire date"
0x4998ff  ldarg.s  8
0x499901  ldloc.0
0x499902  ldloc.2
0x499903  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x499908  brtrue.s loc_49990E
0x49990a  ldloc.s  4
0x49990c  br.s     loc_49990F
0x49990e  ldc.i4.1
0x49990f  stloc.s  4
0x499911  ldarg.s  6
0x499913  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x499918  brtrue.s loc_49992E
0x49991a  ldsfld   valuetype [mscorlib]System.Guid FieldIds::AnonymousLinkType
0x49991f  ldstr    aAnonymouslinkt// "AnonymousLinkType"
0x499924  ldarg.s  8
0x499926  ldloc.0
0x499927  ldnull
0x499928  call     bool Microsoft.SharePoint.SPAccessRequests::UpdateRequestItemProperty(valuetype [mscorlib]System.Guid propertyGuid, string propertyName, class Microsoft.SharePoint.SPListItem requestItem, class Microsoft.SharePoint.SPCachedItemEventProperties newProperties, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext)
0x49992d  pop
0x49992e  ldc.i4   0x164575E
0x499933  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x499938  ldc.i4.s 0x32
0x49993a  ldstr    aSpaccessreques_47// "SPAccessRequests::UpdateItem: we set ne"...
0x49993f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x499944  ldarg.s  8
0x499946  callvirt instance void Microsoft.SharePoint.SPItem::Update()
0x49994b  ldc.i4   0x164575F
0x499950  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x499955  ldc.i4.s 0x32
0x499957  ldstr    aSpaccessreques_48// "SPAccessRequests::UpdateItem: Successfu"...
0x49995c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x499961  ldarg.s  8
0x499963  ldloc.3
0x499964  ldarg.1
0x499965  ldarg.s  0xA
0x499967  ldarg.s  0xB
0x499969  ldloc.2
0x49996a  ldloc.s  4
0x49996c  call     void Microsoft.SharePoint.SPAccessRequests::AuditItemModifiedAction(class Microsoft.SharePoint.SPListItem requestItem, int32 itemStatus, class Microsoft.SharePoint.SPUser affectedUser, class Microsoft.SharePoint.SPGroupCollection groups, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.SPRoleDefinition> roleDefs, class Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditContext auditContext, bool isUpdated)
0x499971  ldarg.2
0x499972  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x499977  brtrue.s loc_49999C
0x499979  ldc.i4   0x362898
0x49997e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x499983  ldc.i4.s 0xF
0x499985  ldstr    aSpaccessreques_49// "SPAccessRequests::UpdateItem - Update A"...
0x49998a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
  ... truncated ...
```
