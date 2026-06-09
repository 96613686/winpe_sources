# Microsoft.SharePoint.SPSharedWithHelper::UpdatePrincipalsToSharedWithField_1

- ea: `0x74dbf0`
- end: `0x74e348`
- name: `Microsoft.SharePoint.SPSharedWithHelper::UpdatePrincipalsToSharedWithField_1`
- size: `1880`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x74d8a0`
- `0x74dbd0`

## callees

- `0x342e60`
- `0x3e99e0`
- `0x3e99f0`
- `0x509400`
- `0x50a5f0`
- `0x50a600`
- `0x52a050`
- `0x52a110`
- `0x52a120`
- `0x52a140`
- `0x53be00`
- `0x542e40`
- `0x5b37e0`
- `0x5c3ce0`
- `0x74d8d0`
- `0x74db90`
- `0x74dbf0`
- `0x74e350`
- `0x74e370`
- `0x74e390`
- `0x74e510`
- `0x74e710`
- `0x74e740`
- `0x7af2f0`
- `0x7be4d0`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x957b70`

## string_xrefs

- `0x74dc55`: `UpdatePrincipalsToSharedWithField`
- `0x74dcc5`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: List doesn't support SharedWith column so nothing to update`
- `0x74dd0b`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Attempt {0} to update principals`
- `0x74ddb5`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharedWith' column for list item '{0}' under site '{1}' because the 'SharedWith' column is invalid.`
- `0x74de7b`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Attempting to add to the 'SharedWith' column for list item '{0}' under site '{1}'. SPPrincipleType='{2}'. LoginName=<name>'{3}'</name>`
- `0x74df37`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Attempting to remove from the 'SharedWith' column for list item '{0}' under site '{1}'. SPPrincipleType='{2}.'`
- `0x74e011`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Finished configuring changes for SharedWith column`
- `0x74e01d`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharedWith' column for list item '{0}' under site '{1}' because the 'SharedWith' column could not be added to the list.`
- `0x74e0c8`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharedWithDetails' and 'LastSharedBy*' columns for list item '{0}' under site '{1}' because of an unexpected exception. Details: {2}`
- `0x74e141`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharingHintHash' column for list item '{0}' under site '{1}' because of an unexpected exception. Details: {2}`
- `0x74e195`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Successfully updated the 'SharedWith' column for list item '{0}' under site '{1}'. The SharedWith user count went from '{2}' to '{3}' users.`
- `0x74e21b`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: [Attempt {0} of {1}]: Failed to update SharedWithMe column for list item because of a COMException. Details: {2}.`
- `0x74e26e`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: COMException when trying to update SharedWithMeColumn`
- `0x74e28d`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharedWith' column for list item because of an SPConcurrencyException exception. Details: {0}`
- `0x74e2c8`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: SPConcurrencyException when trying to update SharedWithMeColumn`
- `0x74e2e2`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Cannot update the 'SharedWith' column for list item because of an unexpected exception. Details: {0}`
- `0x74e31d`: `SPSharedWithHelper.AddPrincipalsToSharedWithField: Exception when trying to update SharedWithMeColumn`

## pseudocode

```c

```

## disassembly

```asm
0x74dbf0  ldnull
0x74dbf1  stloc.0
0x74dbf2  ldarg.s  5
0x74dbf4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x74dbf9  stind.ref
0x74dbfa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x74dbff  stloc.1
0x74dc00  ldarg.s  6
0x74dc02  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x74dc07  stind.ref
0x74dc08  ldarg.3
0x74dc09  brtrue.s loc_74DC33
0x74dc0b  ldarg.s  4
0x74dc0d  brfalse.s loc_74DC33
0x74dc0f  ldc.i4   0x89480D
0x74dc14  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc19  stloc.2
0x74dc1a  ldc.i4   0x89480E
0x74dc1f  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc24  stloc.3
0x74dc25  ldc.i4   0x89480F
0x74dc2a  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc2f  stloc.s  4
0x74dc31  br.s     loc_74DC55
0x74dc33  ldc.i4   0x6C40DE
0x74dc38  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc3d  stloc.2
0x74dc3e  ldc.i4   0x6C4101
0x74dc43  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc48  stloc.3
0x74dc49  ldc.i4   0x88719D
0x74dc4e  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc53  stloc.s  4
0x74dc55  ldstr    aUpdateprincipa_0// "UpdatePrincipalsToSharedWithField"
0x74dc5a  ldloc.2
0x74dc5b  ldloc.3
0x74dc5c  ldloc.s  4
0x74dc5e  ldc.i4.0
0x74dc5f  ldnull
0x74dc60  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x74dc65  stloc.s  5
0x74dc67  ldarg.1
0x74dc68  isinst   Microsoft.SharePoint.SPListItem
0x74dc6d  stloc.s  6
0x74dc6f  ldc.i4.0
0x74dc70  stloc.s  7
0x74dc72  ldloc.s  6
0x74dc74  brtrue.s loc_74DC9E
0x74dc76  ldloc.s  5
0x74dc78  ldarg.3
0x74dc79  ldarg.s  4
0x74dc7b  ldc.i4   0x8C460A
0x74dc80  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc85  ldc.i4   0x8C460B
0x74dc8a  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dc8f  ldstr    aSpsharedwithhe_2// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74dc94  call     void Microsoft.SharePoint.SPSharedWithHelper::LogUpdateActionUnexpectedFailure(class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor, valuetype SharedWithFieldUpdateActions updateAction, bool additivePermissions, unsigned int32 addPrincipalTag, unsigned int32 removePrincipalTag, string failureMessage)
0x74dc99  br       loc_74E338
0x74dc9e  ldloc.s  6
0x74dca0  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x74dca5  call     bool Microsoft.SharePoint.SPSharedWithHelper::DoesListSupportSharedWithColumn(class Microsoft.SharePoint.SPList list)
0x74dcaa  brtrue.s loc_74DCD4
0x74dcac  ldloc.s  5
0x74dcae  ldarg.3
0x74dcaf  ldarg.s  4
0x74dcb1  ldc.i4   0x8C460C
0x74dcb6  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dcbb  ldc.i4   0x8C460D
0x74dcc0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74dcc5  ldstr    aSpsharedwithhe_3// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74dcca  call     void Microsoft.SharePoint.SPSharedWithHelper::LogUpdateActionExpectedFailure(class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor, valuetype SharedWithFieldUpdateActions updateAction, bool additivePermissions, unsigned int32 addPrincipalTag, unsigned int32 removePrincipalTag, string failureMessage)
0x74dccf  br       loc_74E338
0x74dcd4  ldc.i4   0x6C40DF
0x74dcd9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74dcde  ldc.i4.s 0xF
0x74dce0  ldstr    aSpsharedwithhe_4// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74dce5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x74dcea  ldnull
0x74dceb  stloc.s  8
0x74dced  ldc.i4.m1
0x74dcee  stloc.s  9
0x74dcf0  ldc.i4.0
0x74dcf1  stloc.s  0xA
0x74dcf3  ldc.i4.s 0xA
0x74dcf5  stloc.s  0xB
0x74dcf7  br       loc_74E32F
0x74dcfc  ldnull
0x74dcfd  stloc.s  8
0x74dcff  ldc.i4   0x894810
0x74dd04  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74dd09  ldc.i4.s 0x32
0x74dd0b  ldstr    aSpsharedwithhe_5// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74dd10  ldc.i4.1
0x74dd11  newarr   [mscorlib]System.Object
0x74dd16  stloc.s  0x22
0x74dd18  ldloc.s  0x22
0x74dd1a  ldc.i4.0
0x74dd1b  ldloc.s  0xA
0x74dd1d  box      [mscorlib]System.Int32
0x74dd22  stelem.ref
0x74dd23  ldloc.s  0x22
0x74dd25  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x74dd2a  ldloc.s  0xA
0x74dd2c  ldc.i4.0
0x74dd2d  ble.s    loc_74DD39
0x74dd2f  ldarg.0
0x74dd30  ldloc.s  6
0x74dd32  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.Utilities.SPListUtility::RefreshListItem(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPListItem targetListItem)
0x74dd37  stloc.s  6
0x74dd39  ldloc.s  6
0x74dd3b  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x74dd40  ldloca.s 0xC
0x74dd42  ldloca.s 0xD
0x74dd44  ldloca.s 0xE
0x74dd46  ldloca.s 0xF
0x74dd48  ldloca.s 0x10
0x74dd4a  call     bool Microsoft.SharePoint.SPSharedWithHelper::EnsureSharedWithRelatedFieldsOnList(class Microsoft.SharePoint.SPList list, [out] string& sharedWithFieldInternalName, [out] string& sharedWithDetailsFieldInternalName, [out] string& sharingHintHashFieldInternalName, [out] string& lastSharedByUserFieldInternalName, [out] string& lastSharedByTimeFieldInternalName)
0x74dd4f  brfalse.s loc_74DD5B
0x74dd51  ldarg.0
0x74dd52  ldloc.s  6
0x74dd54  call     class Microsoft.SharePoint.SPListItem Microsoft.SharePoint.Utilities.SPListUtility::RefreshListItem(class Microsoft.SharePoint.SPWeb web, class Microsoft.SharePoint.SPListItem targetListItem)
0x74dd59  stloc.s  6
0x74dd5b  ldloc.s  0xC
0x74dd5d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x74dd62  brtrue   loc_74E01D
0x74dd67  ldloc.s  6
0x74dd69  ldloc.s  0xC
0x74dd6b  callvirt instance object Microsoft.SharePoint.SPItem::get_Item(string fieldName)
0x74dd70  stloc.s  0x11
0x74dd72  ldloc.s  0x11
0x74dd74  brtrue.s loc_74DD7D
0x74dd76  newobj   instance void Microsoft.SharePoint.SPFieldUserValueCollection::.ctor()
0x74dd7b  br.s     loc_74DD84
0x74dd7d  ldloc.s  0x11
0x74dd7f  isinst   Microsoft.SharePoint.SPFieldUserValueCollection
0x74dd84  stloc.s  8
0x74dd86  ldloc.s  8
0x74dd88  brtrue.s loc_74DDB1
0x74dd8a  ldloc.s  0x11
0x74dd8c  isinst   [mscorlib]System.String
0x74dd91  stloc.s  0x12
0x74dd93  ldloc.s  0x12
0x74dd95  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x74dd9a  brtrue.s loc_74DDB1
0x74dd9c  ldloc.s  6
0x74dd9e  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPListItem::get_ParentList()
0x74dda3  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0x74dda8  ldloc.s  0x12
0x74ddaa  newobj   instance void Microsoft.SharePoint.SPFieldUserValueCollection::.ctor(class Microsoft.SharePoint.SPWeb web, string fieldValue)
0x74ddaf  stloc.s  8
0x74ddb1  ldloc.s  8
0x74ddb3  brtrue.s loc_74DE11
0x74ddb5  ldstr    aSpsharedwithhe_6// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74ddba  ldloc.s  6
0x74ddbc  callvirt instance string Microsoft.SharePoint.SPListItem::get_Url()
0x74ddc1  ldarg.0
0x74ddc2  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x74ddc7  call     string [mscorlib]System.String::Format(string, object, object)
0x74ddcc  stloc.s  0x13
0x74ddce  ldc.i4   0x6C40E0
0x74ddd3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74ddd8  ldc.i4.s 0xA
0x74ddda  ldloc.s  0x13
0x74dddc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x74dde1  ldloc.s  0xA
0x74dde3  ldloc.s  0xB
0x74dde5  ldc.i4.1
0x74dde6  sub
0x74dde7  bne.un   loc_74E071
0x74ddec  ldloc.s  5
0x74ddee  ldarg.3
0x74ddef  ldarg.s  4
0x74ddf1  ldc.i4   0x894811
0x74ddf6  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74ddfb  ldc.i4   0x88719F
0x74de00  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x74de05  ldloc.s  0x13
0x74de07  call     void Microsoft.SharePoint.SPSharedWithHelper::LogUpdateActionUnexpectedFailure(class Microsoft.SharePoint.Utilities.SPReliabilityMonitor monitor, valuetype SharedWithFieldUpdateActions updateAction, bool additivePermissions, unsigned int32 addPrincipalTag, unsigned int32 removePrincipalTag, string failureMessage)
0x74de0c  br       loc_74E071
0x74de11  ldloc.s  8
0x74de13  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPFieldUserValue>::get_Count()
0x74de18  stloc.s  9
0x74de1a  ldarg.2
0x74de1b  brfalse  loc_74DFF7
0x74de20  ldarg.2
0x74de21  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.SPPrincipal>::GetEnumerator()
0x74de26  stloc.s  0x23
0x74de28  br       loc_74DFDD
0x74de2d  ldloc.s  0x23
0x74de2f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.SPPrincipal>::get_Current()
0x74de34  stloc.s  0x14
0x74de36  ldloc.s  8
0x74de38  ldloc.s  0x14
0x74de3a  call     int32 Microsoft.SharePoint.SPSharedWithHelper::IndexOfPrincipalInUserCollection(class Microsoft.SharePoint.SPFieldUserValueCollection userCollection, class Microsoft.SharePoint.SPPrincipal principal)
0x74de3f  stloc.s  0x15
0x74de41  ldloc.s  0x15
0x74de43  ldc.i4.m1
0x74de44  cgt
0x74de46  stloc.s  0x16
0x74de48  ldc.i4.0
0x74de49  stloc.s  0x17
0x74de4b  ldloc.s  0x14
0x74de4d  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPPrincipalType Microsoft.SharePoint.SPPrincipal::get_PrincipalType()
0x74de52  ldc.i4.1
0x74de53  beq.s    loc_74DE62
0x74de55  ldloc.s  0x14
0x74de57  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPPrincipalType Microsoft.SharePoint.SPPrincipal::get_PrincipalType()
0x74de5c  ldc.i4.4
0x74de5d  bne.un   loc_74DF89
0x74de62  ldloc.s  0x16
0x74de64  brtrue   loc_74DF23
0x74de69  ldarg.3
0x74de6a  brtrue   loc_74DF23
0x74de6f  ldc.i4   0x8C5617
0x74de74  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74de79  ldc.i4.s 0x32
0x74de7b  ldstr    aSpsharedwithhe_7// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74de80  ldc.i4.4
0x74de81  newarr   [mscorlib]System.Object
0x74de86  stloc.s  0x24
0x74de88  ldloc.s  0x24
0x74de8a  ldc.i4.0
0x74de8b  ldloc.s  6
0x74de8d  callvirt instance string Microsoft.SharePoint.SPListItem::get_Url()
0x74de92  stelem.ref
0x74de93  ldloc.s  0x24
0x74de95  ldc.i4.1
0x74de96  ldarg.0
0x74de97  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x74de9c  stelem.ref
0x74de9d  ldloc.s  0x24
0x74de9f  ldc.i4.2
0x74dea0  ldloc.s  0x14
0x74dea2  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPPrincipalType Microsoft.SharePoint.SPPrincipal::get_PrincipalType()
0x74dea7  box      Microsoft.SharePoint.Utilities.SPPrincipalType
0x74deac  stelem.ref
0x74dead  ldloc.s  0x24
0x74deaf  ldc.i4.3
0x74deb0  ldloc.s  0x14
0x74deb2  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x74deb7  stelem.ref
0x74deb8  ldloc.s  0x24
0x74deba  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x74debf  ldloc.s  8
0x74dec1  ldarg.0
0x74dec2  ldloc.s  0x14
0x74dec4  callvirt instance int32 Microsoft.SharePoint.SPMember::get_ID()
0x74dec9  ldloc.s  0x14
0x74decb  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_Name()
0x74ded0  newobj   instance void Microsoft.SharePoint.SPFieldUserValue::.ctor(class Microsoft.SharePoint.SPWeb web, int32 lookupId, string lookupValue)
0x74ded5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPFieldUserValue>::Add(var<u1>)
0x74deda  ldarg.s  5
0x74dedc  ldind.ref
0x74dedd  ldloc.s  0x14
0x74dedf  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x74dee4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x74dee9  ldc.i4.1
0x74deea  stloc.s  0x17
0x74deec  ldloc.s  0x14
0x74deee  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPPrincipalType Microsoft.SharePoint.SPPrincipal::get_PrincipalType()
0x74def3  ldc.i4.1
0x74def4  bne.un   loc_74DF89
0x74def9  ldloc.s  0x14
0x74defb  castclass Microsoft.SharePoint.SPUser
0x74df00  stloc.s  0x18
0x74df02  ldloc.s  0x18
0x74df04  brfalse  loc_74DF89
0x74df09  ldloc.s  0x18
0x74df0b  callvirt instance bool Microsoft.SharePoint.SPUser::get_IsShareByEmailGuestUser()
0x74df10  brfalse.s loc_74DF89
0x74df12  ldarg.s  6
0x74df14  ldind.ref
0x74df15  ldloc.s  0x18
0x74df17  callvirt instance string Microsoft.SharePoint.SPPrincipal::get_LoginName()
0x74df1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x74df21  br.s     loc_74DF89
0x74df23  ldloc.s  0x16
0x74df25  brfalse.s loc_74DF89
0x74df27  ldarg.3
0x74df28  ldc.i4.1
0x74df29  bne.un.s loc_74DF89
0x74df2b  ldc.i4   0x6C40E2
0x74df30  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x74df35  ldc.i4.s 0x32
0x74df37  ldstr    aSpsharedwithhe_8// "SPSharedWithHelper.AddPrincipalsToShare"...
0x74df3c  ldc.i4.3
0x74df3d  newarr   [mscorlib]System.Object
0x74df42  stloc.s  0x25
0x74df44  ldloc.s  0x25
0x74df46  ldc.i4.0
0x74df47  ldloc.s  6
0x74df49  callvirt instance string Microsoft.SharePoint.SPListItem::get_Url()
0x74df4e  stelem.ref
0x74df4f  ldloc.s  0x25
0x74df51  ldc.i4.1
0x74df52  ldarg.0
0x74df53  callvirt instance string Microsoft.SharePoint.SPWeb::get_Url()
0x74df58  stelem.ref
0x74df59  ldloc.s  0x25
0x74df5b  ldc.i4.2
  ... truncated ...
```
