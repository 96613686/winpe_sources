# Microsoft.SharePoint.Sharing.SPSecurableObjectExtensions::ShareLink

- ea: `0x73d130`
- end: `0x73ddaf`
- name: `Microsoft.SharePoint.Sharing.SPSecurableObjectExtensions::ShareLink`
- size: `3199`
- prototype: ``
- caller_count: `0`
- callee_count: `67`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1b7f20`
- `0x26dc40`
- `0x53e000`
- `0x58ad70`
- `0x59b480`
- `0x59b560`
- `0x5c10e0`
- `0x5c24f0`
- `0x5d31f0`
- `0x6c9890`
- `0x721f40`
- `0x7258c0`
- `0x7266a0`
- `0x72bb10`
- `0x72cc00`
- `0x72cc20`
- `0x72cc40`
- `0x72cc60`
- `0x72cc80`
- `0x72cca0`
- `0x72ccf0`
- `0x72cd00`
- `0x72cd40`
- `0x72cd90`
- `0x72cdb0`
- `0x72cdd0`
- `0x72cdf0`
- `0x72ce10`
- `0x72ce30`
- `0x72ce50`
- `0x72ce70`
- `0x72ce90`
- `0x733050`
- `0x7334c0`
- `0x739070`
- `0x73d130`
- `0x73f170`
- `0x748f10`
- `0x748f60`
- `0x749040`
- `0x749690`
- `0x7496c0`
- `0x749730`
- `0x749750`
- `0x749760`
- `0x749770`
- `0x749790`
- `0x7497e0`
- `0x7497f0`
- `0x749810`

## string_xrefs

- `0x73d79a`: `ForceCheckoutEditLink`
- `0x73d7b6`: `ShareByLink Disabled`
- `0x73d8a6`: `AnonymousEditLinkNotAllowedByTenant`
- `0x73d170`: `ShareLink: Called in a site with CompatibilityLevel 14.`
- `0x73d17a`: `Sharing links can only be created for 15 mode or higher site collections`
- `0x73d1b4`: `ShareLink: Called with LinkKind = [{0}].`
- `0x73d1ed`: `ShareLink: Called with LinkKind = [{0}].`
- `0x73d1d2`: `LinkKind cannot be Direct or Uninitialized`
- `0x73d20b`: `LinkKind cannot be flexible`
- `0x73d279`: `linkKind`
- `0x73d2f8`: `SPSecurableObjectExtensions.ShareLink`
- `0x73d325`: `Start-ShareLink`
- `0x73d346`: `Checkpoint-ShareLink-AfterOSC`
- `0x73d380`: `Checkpoint-ShareLink-AfterValidatePeoplePickerInput`
- `0x73d50e`: `ShareLink: Settings is missing or has incorrect role for Flexible share.`
- `0x73d585`: `ShareLink: Only Flexible shares support RestrictShareMembership.`
- `0x73d58f`: `Only Flexible shares can enforce access restrictions`
- `0x73d5af`: `ShareLink: AllowAnonymousAccess and RestrictShareMembership are not compatible with each other.`
- `0x73d5b9`: `AllowAnonymousAccess and RestrictShareMembership are not compatible with each other`
- `0x73d6bc`: `ShareLink`
- `0x73d6c1`: `d:\dbs\el\zlt\dev\sts\stsom\Sharing\SPSecurableObjectExtensions.cs`
- `0x73d6eb`: `SPSecurableObjectExtensions.ShareLink: Invalid Operation Exception  LinkKind: [{0}]. CreateLink: [{1}]. Exception: [{2}].`
- `0x73dac8`: `SPSecurableObjectExtensions.ShareLink: SPException while sharing a link. LinkKind: [{0}]. CreateLink: [{1}]. SPException: [{2}] [{3}].`
- `0x73dbf5`: `Share by link is not enabled.`
- `0x73dcd2`: `SPSecurableObjectExtensions.ShareLink: UnauthorizedAccessException while sharing a link. LinkKind: [{0}]. CreateLink: [{1}]. Exception: [{2}].`
- `0x73dd32`: `SPSecurableObjectExtensions.ShareLink: Exception while sharing a link. LinkKind: [{0}]. CreateLink: [{1}]. Exception: [{2}].`
- `0x73dda3`: `End-ShareLink`

## pseudocode

```c

```

## disassembly

```asm
0x73d130  ldnull
0x73d131  stloc.0
0x73d132  ldnull
0x73d133  stloc.1
0x73d134  ldarg.0
0x73d135  brtrue.s loc_73D142
0x73d137  ldstr    aListitem// "listItem"
0x73d13c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73d141  throw
0x73d142  ldarg.1
0x73d143  brtrue.s loc_73D150
0x73d145  ldstr    aRequest// "request"
0x73d14a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73d14f  throw
0x73d150  ldarg.0
0x73d151  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPListItem::get_Web()
0x73d156  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x73d15b  callvirt instance int32 Microsoft.SharePoint.SPSite::get_CompatibilityLevel()
0x73d160  ldc.i4.s 0xF
0x73d162  bge.s    loc_73D185
0x73d164  ldc.i4   0x1248609
0x73d169  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x73d16e  ldc.i4.s 0x32
0x73d170  ldstr    aSharelinkCalle_2// "ShareLink: Called in a site with Compat"...
0x73d175  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x73d17a  ldstr    aSharingLinksCa// "Sharing links can only be created for 1"...
0x73d17f  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0x73d184  throw
0x73d185  ldarg.1
0x73d186  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d18b  brtrue.s loc_73D195
0x73d18d  ldarg.1
0x73d18e  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.ShareLinkRequest::get_LinkKind()
0x73d193  br.s     loc_73D1A0
0x73d195  ldarg.1
0x73d196  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d19b  callvirt instance valuetype Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.Sharing.ShareLinkSettings::get_LinkKind()
0x73d1a0  stloc.2
0x73d1a1  ldloc.2
0x73d1a2  ldc.i4.1
0x73d1a3  beq.s    loc_73D1A8
0x73d1a5  ldloc.2
0x73d1a6  brtrue.s loc_73D1DD
0x73d1a8  ldc.i4   0x124860A
0x73d1ad  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x73d1b2  ldc.i4.s 0x32
0x73d1b4  ldstr    aSharelinkCalle_3// "ShareLink: Called with LinkKind = [{0}]"...
0x73d1b9  ldc.i4.1
0x73d1ba  newarr   [mscorlib]System.Object
0x73d1bf  stloc.s  0x1B
0x73d1c1  ldloc.s  0x1B
0x73d1c3  ldc.i4.0
0x73d1c4  ldloc.2
0x73d1c5  box      Microsoft.SharePoint.SharingLinkKind
0x73d1ca  stelem.ref
0x73d1cb  ldloc.s  0x1B
0x73d1cd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x73d1d2  ldstr    aLinkkindCannot// "LinkKind cannot be Direct or Uninitiali"...
0x73d1d7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x73d1dc  throw
0x73d1dd  ldloc.2
0x73d1de  ldc.i4.6
0x73d1df  bne.un.s loc_73D216
0x73d1e1  ldc.i4   0x245E2DA
0x73d1e6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DocumentSharing()
0x73d1eb  ldc.i4.s 0x32
0x73d1ed  ldstr    aSharelinkCalle_3// "ShareLink: Called with LinkKind = [{0}]"...
0x73d1f2  ldc.i4.1
0x73d1f3  newarr   [mscorlib]System.Object
0x73d1f8  stloc.s  0x1C
0x73d1fa  ldloc.s  0x1C
0x73d1fc  ldc.i4.0
0x73d1fd  ldloc.2
0x73d1fe  box      Microsoft.SharePoint.SharingLinkKind
0x73d203  stelem.ref
0x73d204  ldloc.s  0x1C
0x73d206  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x73d20b  ldstr    aLinkkindCannot_0// "LinkKind cannot be flexible"
0x73d210  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x73d215  throw
0x73d216  ldloca.s 3
0x73d218  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x73d21e  ldarg.1
0x73d21f  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d224  brfalse.s loc_73D251
0x73d226  ldarg.1
0x73d227  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d22c  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkSettings::get_Expiration()
0x73d231  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x73d236  brtrue.s loc_73D251
0x73d238  ldloca.s 3
0x73d23a  ldarg.1
0x73d23b  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d240  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkSettings::get_Expiration()
0x73d245  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPSharingUtility::ParseExpirationDate(string expiration)
0x73d24a  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x73d24f  br.s     loc_73D270
0x73d251  ldarg.1
0x73d252  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Expiration()
0x73d257  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x73d25c  brtrue.s loc_73D270
0x73d25e  ldloca.s 3
0x73d260  ldarg.1
0x73d261  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Expiration()
0x73d266  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPSharingUtility::ParseExpirationDate(string expiration)
0x73d26b  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x73d270  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x73d275  stloc.s  0x1A
0x73d277  ldloc.s  0x1A
0x73d279  ldstr    aLinkkind// "linkKind"
0x73d27e  ldloc.2
0x73d27f  box      Microsoft.SharePoint.SharingLinkKind
0x73d284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x73d289  ldloc.s  0x1A
0x73d28b  ldstr    aSendemail_0// "sendEmail"
0x73d290  ldarg.1
0x73d291  callvirt instance class Microsoft.SharePoint.Sharing.EmailData Microsoft.SharePoint.Sharing.ShareLinkRequest::get_EmailData()
0x73d296  ldnull
0x73d297  ceq
0x73d299  ldc.i4.0
0x73d29a  ceq
0x73d29c  box      [mscorlib]System.Boolean
0x73d2a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x73d2a6  ldloc.s  0x1A
0x73d2a8  stloc.s  4
0x73d2aa  ldc.i4.s 0x1E
0x73d2ac  box      Microsoft.SharePoint.GlobalEnums.SPComponentId
0x73d2b1  call     valuetype [Cil.Core]Cil.NullableEnum [Cil.Core]Cil.NullableEnum::op_Implicit(class [mscorlib]System.Enum)
0x73d2b6  stloc.s  0x1D
0x73d2b8  ldloc.2
0x73d2b9  box      Microsoft.SharePoint.SharingLinkKind
0x73d2be  call     valuetype [Cil.Core]Cil.NullableEnum [Cil.Core]Cil.NullableEnum::op_Implicit(class [mscorlib]System.Enum)
0x73d2c3  stloc.s  0x1E
0x73d2c5  ldnull
0x73d2c6  call     valuetype [Cil.Core]Cil.NullableEnum [Cil.Core]Cil.NullableEnum::op_Implicit(class [mscorlib]System.Enum)
0x73d2cb  ldc.i4.1
0x73d2cc  box      Microsoft.SharePoint.GlobalEnums.SPScenarioId
0x73d2d1  call     valuetype [Cil.Core]Cil.NullableEnum [Cil.Core]Cil.NullableEnum::op_Implicit(class [mscorlib]System.Enum)
0x73d2d6  ldloc.s  0x1D
0x73d2d8  ldloc.s  0x1E
0x73d2da  ldc.i4.1
0x73d2db  box      Microsoft.SharePoint.GlobalEnums.SPPropertyId
0x73d2e0  call     valuetype [Cil.Core]Cil.NullableEnum [Cil.Core]Cil.NullableEnum::op_Implicit(class [mscorlib]System.Enum)
0x73d2e5  ldc.i4.1
0x73d2e6  ldnull
0x73d2e7  ldloca.s 0x1F
0x73d2e9  initobj  [mscorlib]System.Guid
0x73d2ef  ldloc.s  0x1F
0x73d2f1  newobj   instance void [Cil.Core]Cil.Events.SharepointOnline.IncomingRequestQosEvent::.ctor(valuetype [Cil.Core]Cil.NullableEnum, valuetype [Cil.Core]Cil.NullableEnum, valuetype [Cil.Core]Cil.NullableEnum, valuetype [Cil.Core]Cil.NullableEnum, valuetype [Cil.Core]Cil.NullableEnum, bool, string, valuetype [mscorlib]System.Guid)
0x73d2f6  stloc.s  5
0x73d2f8  ldstr    aSpsecurableobj_0// "SPSecurableObjectExtensions.ShareLink"
0x73d2fd  ldc.i4   0x124860B
0x73d302  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x73d307  ldc.i4   0x124860C
0x73d30c  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x73d311  ldc.i4   0x124860D
0x73d316  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x73d31b  ldc.i4.0
0x73d31c  ldloc.s  4
0x73d31e  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x73d323  stloc.s  6
0x73d325  ldstr    aStartSharelink// "Start-ShareLink"
0x73d32a  call     void Microsoft.SharePoint.Sharing.SPShareByLinkHelper::LogPerfTimeToULS(string LocationName)
0x73d32f  ldarg.0
0x73d330  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPListItem::get_Web()
0x73d335  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.SPWeb::get_CurrentUser()
0x73d33a  stloc.s  7
0x73d33c  ldarg.0
0x73d33d  ldc.i4.0
0x73d33e  ldc.i4.1
0x73d33f  newobj   instance void Microsoft.SharePoint.ObjectSharingContext::.ctor(class Microsoft.SharePoint.SPSecurableObject securableObject, bool retrieveSharingInformation, [opt] bool useSimplifiedRoles)
0x73d344  stloc.s  8
0x73d346  ldstr    aCheckpointShar// "Checkpoint-ShareLink-AfterOSC"
0x73d34b  call     void Microsoft.SharePoint.Sharing.SPShareByLinkHelper::LogPerfTimeToULS(string LocationName)
0x73d350  ldnull
0x73d351  stloc.s  9
0x73d353  ldarg.1
0x73d354  callvirt instance class Microsoft.SharePoint.Sharing.EmailData Microsoft.SharePoint.Sharing.ShareLinkRequest::get_EmailData()
0x73d359  ldnull
0x73d35a  ceq
0x73d35c  ldc.i4.0
0x73d35d  ceq
0x73d35f  stloc.s  0xA
0x73d361  ldnull
0x73d362  stloc.s  0xB
0x73d364  ldarg.1
0x73d365  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkRequest::get_PeoplePickerInput()
0x73d36a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x73d36f  brtrue.s loc_73D38C
0x73d371  ldarg.1
0x73d372  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkRequest::get_PeoplePickerInput()
0x73d377  ldloc.s  8
0x73d379  call     class [mscorlib]System.Collections.ArrayList Microsoft.SharePoint.SPSharingUtility::ValidatePeoplePickerInput(string peoplePickerInput, class Microsoft.SharePoint.ObjectSharingContext sharingContext)
0x73d37e  stloc.s  9
0x73d380  ldstr    aCheckpointShar_0// "Checkpoint-ShareLink-AfterValidatePeopl"...
0x73d385  call     void Microsoft.SharePoint.Sharing.SPShareByLinkHelper::LogPerfTimeToULS(string LocationName)
0x73d38a  br.s     loc_73D38F
0x73d38c  ldc.i4.0
0x73d38d  stloc.s  0xA
0x73d38f  ldloc.s  0xA
0x73d391  brfalse.s loc_73D3A0
0x73d393  ldarg.1
0x73d394  callvirt instance class Microsoft.SharePoint.Sharing.EmailData Microsoft.SharePoint.Sharing.ShareLinkRequest::get_EmailData()
0x73d399  callvirt instance string Microsoft.SharePoint.Sharing.EmailData::get_Body()
0x73d39e  stloc.s  0xB
0x73d3a0  ldnull
0x73d3a1  stloc.s  0xC
0x73d3a3  ldarg.1
0x73d3a4  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d3a9  brtrue.s loc_73D3CD
0x73d3ab  ldloc.2
0x73d3ac  newobj   instance void Microsoft.SharePoint.Sharing.SPShareSettings::.ctor(valuetype Microsoft.SharePoint.SharingLinkKind shareKind)
0x73d3b1  stloc.s  0xD
0x73d3b3  ldloc.s  0xD
0x73d3b5  ldloc.3
0x73d3b6  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_ExpirationDateTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x73d3bb  ldloc.s  0xD
0x73d3bd  ldloc.s  7
0x73d3bf  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_CurrentUser(class Microsoft.SharePoint.SPUser value)
0x73d3c4  ldloc.s  0xD
0x73d3c6  stloc.s  0xC
0x73d3c8  br       loc_73D5CC
0x73d3cd  ldarg.1
0x73d3ce  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d3d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Sharing.ShareLinkSettings::get_ShareId()
0x73d3d8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x73d3dd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x73d3e2  brtrue.s loc_73D401
0x73d3e4  ldloc.2
0x73d3e5  newobj   instance void Microsoft.SharePoint.Sharing.SPShareSettings::.ctor(valuetype Microsoft.SharePoint.SharingLinkKind shareKind)
0x73d3ea  stloc.s  0x13
0x73d3ec  ldloc.s  0x13
0x73d3ee  ldloc.3
0x73d3ef  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_ExpirationDateTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x73d3f4  ldloc.s  0x13
0x73d3f6  ldloc.s  7
0x73d3f8  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_CurrentUser(class Microsoft.SharePoint.SPUser value)
0x73d3fd  ldloc.s  0x13
0x73d3ff  br.s     loc_73D427
0x73d401  ldloc.2
0x73d402  ldarg.1
0x73d403  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d408  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Sharing.ShareLinkSettings::get_ShareId()
0x73d40d  newobj   instance void Microsoft.SharePoint.Sharing.SPShareSettings::.ctor(valuetype Microsoft.SharePoint.SharingLinkKind shareKind, valuetype [mscorlib]System.Guid shareId)
0x73d412  stloc.s  0x12
0x73d414  ldloc.s  0x12
0x73d416  ldloc.3
0x73d417  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_ExpirationDateTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x73d41c  ldloc.s  0x12
0x73d41e  ldloc.s  7
0x73d420  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_CurrentUser(class Microsoft.SharePoint.SPUser value)
0x73d425  ldloc.s  0x12
0x73d427  stloc.s  0xC
0x73d429  call     bool Microsoft.SharePoint.Sharing.SPShareByLinkHelper::CSLSupportsPasswordsFlightEnabled()
0x73d42e  stloc.s  0xE
0x73d430  ldloc.2
0x73d431  ldc.i4.4
0x73d432  beq.s    loc_73D440
0x73d434  ldloc.2
0x73d435  ldc.i4.5
0x73d436  beq.s    loc_73D440
0x73d438  ldloc.2
0x73d439  ldc.i4.6
0x73d43a  beq.s    loc_73D440
0x73d43c  ldloc.s  0xE
0x73d43e  brfalse.s loc_73D464
0x73d440  ldloc.s  0xC
0x73d442  ldarg.1
0x73d443  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d448  callvirt instance string Microsoft.SharePoint.Sharing.ShareLinkSettings::get_Password()
0x73d44d  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_Password(string value)
0x73d452  ldloc.s  0xC
0x73d454  ldarg.1
0x73d455  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d45a  callvirt instance bool Microsoft.SharePoint.Sharing.ShareLinkSettings::get_UpdatePassword()
0x73d45f  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_UpdatePassword(bool value)
0x73d464  ldloc.2
0x73d465  ldc.i4.6
0x73d466  bne.un   loc_73D5CC
0x73d46b  ldloc.s  0xC
0x73d46d  ldnull
0x73d46e  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_Group(class Microsoft.SharePoint.SPGroup value)
0x73d473  ldc.i8   0x7FFFFFFFFFFFFFFF
0x73d47c  newobj   instance void GrantAdditionalPermissionsInScope::.ctor(valuetype Microsoft.SharePoint.SPBasePermissions permsAdded)
0x73d481  stloc.s  0x20
0x73d483  ldloc.s  8
0x73d485  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SharingBase::get_Web()
0x73d48a  ldc.i4.0
0x73d48b  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPWeb::GetFirstUniqueRoleDefinitionWeb(bool bFetchMetaInfo)
0x73d490  stloc.s  0xF
0x73d492  ldloc.s  0xC
0x73d494  ldloc.s  0xF
0x73d496  ldarg.1
0x73d497  callvirt instance class Microsoft.SharePoint.Sharing.ShareLinkSettings Microsoft.SharePoint.Sharing.ShareLinkRequest::get_Settings()
0x73d49c  callvirt instance valuetype Microsoft.SharePoint.Sharing.Role Microsoft.SharePoint.Sharing.ShareLinkSettings::get_Role()
0x73d4a1  call     class Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.Sharing.SPDocumentSharingManager::GetRoleDefinitionFromWeb(class Microsoft.SharePoint.SPWeb web, valuetype Microsoft.SharePoint.Sharing.Role role)
0x73d4a6  callvirt instance void Microsoft.SharePoint.Sharing.SPShareSettings::set_RoleDefinition(class Microsoft.SharePoint.SPRoleDefinition value)
0x73d4ab  ldloc.s  0xC
0x73d4ad  callvirt instance class Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.Sharing.SPShareSettings::get_RoleDefinition()
0x73d4b2  brtrue.s loc_73D4D9
  ... truncated ...
```
