# Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::.cctor

- ea: `0x4be3e0`
- end: `0x4be9ea`
- name: `Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::.cctor`
- size: `1546`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4bdf80`
- `0x4be3e0`

## string_xrefs

- `0x4be50d`: `DefaultSharingLinkType`
- `0x4be516`: `DefaultSharingLinkType`
- `0x4be559`: `FolderAnonymousLinkPermission`
- `0x4be562`: `FolderAnonymousLinkPermission`
- `0x4be533`: `FileAnonymousLinkPermission`
- `0x4be53c`: `FileAnonymousLinkPermission`
- `0x4be90b`: `DefaultLinkPermission`
- `0x4be914`: `DefaultLinkPermission`
- `0x4be4a4`: `RequireAnonymousLinksExpireInDays`
- `0x4be4ac`: `RequireAnonymousLinksExpireInDays`
- `0x4be803`: `SPO-BlockAccessOnUnmanagedDevices`
- `0x4be80f`: `SPO-BlockAccessOnUnmanagedDevices`
- `0x4be834`: `SPO-LimitedAccessOnUnmanagedDevices`
- `0x4be840`: `SPO-LimitedAccessOnUnmanagedDevices`
- `0x4be865`: `SPO-BlockAccessPolicy`
- `0x4be871`: `SPO-BlockAccessPolicy`
- `0x4be88c`: `SPO-BlockAccessFromNativeAppPolicy`
- `0x4be898`: `SPO-BlockAccessFromNativeAppPolicy`
- `0x4be993`: `AllowedSecurityGroupsForODBList`
- `0x4be99c`: `AllowedSecurityGroupsForODBList`
- `0x4be9b3`: `SPO-LimitedAccessBlockClientSidePreviewers`
- `0x4be9bf`: `SPO-LimitedAccessBlockClientSidePreviewers`

## pseudocode

```c

```

## disassembly

```asm
0x4be3e0  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate3
0x4be3e5  brtrue.s loc_4BE3F8
0x4be3e7  ldnull
0x4be3e8  ldftn    string Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::<.cctor>b__1(string value)
0x4be3ee  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x4be3f3  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate3
0x4be3f8  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate3
0x4be3fd  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be402  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x4be407  brtrue.s loc_4BE41A
0x4be409  ldnull
0x4be40a  ldftn    string Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::<.cctor>b__2(string value)
0x4be410  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x4be415  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x4be41a  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::CS$<>9__CachedAnonymousMethodDelegate4
0x4be41f  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::FlippedBoolPolicyDecorator
0x4be424  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::.ctor()
0x4be429  stloc.0
0x4be42a  ldloc.0
0x4be42b  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x4be430  ldc.i4.s 0x6E
0x4be432  ldc.i4.6
0x4be433  ldstr    aRequireaccepti// "RequireAcceptingAccountMatchInvitedAcco"...
0x4be438  ldc.i4.0
0x4be439  stloc.1
0x4be43a  ldloca.s 1
0x4be43c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be441  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be446  ldc.i4.0
0x4be447  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be44c  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be451  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be456  ldloc.0
0x4be457  ldstr    aBccexternalsha_0// "BccExternalSharingInvitations"
0x4be45c  ldc.i4.s 0x6E
0x4be45e  ldc.i4.s 0xA
0x4be460  ldstr    aBccexternalsha_0// "BccExternalSharingInvitations"
0x4be465  ldc.i4.0
0x4be466  stloc.2
0x4be467  ldloca.s 2
0x4be469  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be46e  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be473  ldc.i4.0
0x4be474  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be479  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be47e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be483  ldloc.0
0x4be484  ldstr    aBccexternalsha_1// "BccExternalSharingInvitationsList"
0x4be489  ldc.i4.s 0x6E
0x4be48b  ldc.i4.s 0xB
0x4be48d  ldstr    aBccexternalsha_1// "BccExternalSharingInvitationsList"
0x4be492  ldsfld   string [mscorlib]System.String::Empty
0x4be497  ldc.i4.0
0x4be498  ldnull
0x4be499  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be49e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be4a3  ldloc.0
0x4be4a4  ldstr    aRequireanonymo// "RequireAnonymousLinksExpireInDays"
0x4be4a9  ldc.i4.s 0x6E
0x4be4ab  ldc.i4.5
0x4be4ac  ldstr    aRequireanonymo// "RequireAnonymousLinksExpireInDays"
0x4be4b1  ldstr    a0// "0"
0x4be4b6  ldc.i4.0
0x4be4b7  ldnull
0x4be4b8  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be4bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be4c2  ldloc.0
0x4be4c3  ldstr    aCollaborationt// "CollaborationTypeKey"
0x4be4c8  ldc.i4.s 0x6E
0x4be4ca  ldc.i4.1
0x4be4cb  ldstr    aCollaborationt// "CollaborationTypeKey"
0x4be4d0  ldc.i4.1
0x4be4d1  box      Microsoft.SharePoint.SPCollaborationTypes
0x4be4d6  callvirt instance string [mscorlib]System.Object::ToString()
0x4be4db  ldc.i4.1
0x4be4dc  ldnull
0x4be4dd  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be4e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be4e7  ldloc.0
0x4be4e8  ldstr    aDomainrestrict// "DomainRestrictionModeProp"
0x4be4ed  ldc.i4.s 0x6E
0x4be4ef  ldc.i4.7
0x4be4f0  ldstr    aDomainrestrict// "DomainRestrictionModeProp"
0x4be4f5  ldc.i4.0
0x4be4f6  box      Microsoft.SharePoint.Sharing.SharingDomainRestrictionMode
0x4be4fb  callvirt instance string [mscorlib]System.Object::ToString()
0x4be500  ldc.i4.0
0x4be501  ldnull
0x4be502  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be507  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be50c  ldloc.0
0x4be50d  ldstr    aDefaultsharing// "DefaultSharingLinkType"
0x4be512  ldc.i4.s 0x6E
0x4be514  ldc.i4.s 0xC
0x4be516  ldstr    aDefaultsharing// "DefaultSharingLinkType"
0x4be51b  ldc.i4.0
0x4be51c  box      Microsoft.SharePoint.SharingLinkKind
0x4be521  callvirt instance string [mscorlib]System.Object::ToString()
0x4be526  ldc.i4.0
0x4be527  ldnull
0x4be528  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be52d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be532  ldloc.0
0x4be533  ldstr    aFileanonymousl// "FileAnonymousLinkPermission"
0x4be538  ldc.i4.s 0x6E
0x4be53a  ldc.i4.s 0xD
0x4be53c  ldstr    aFileanonymousl// "FileAnonymousLinkPermission"
0x4be541  ldc.i4.0
0x4be542  box      Microsoft.SharePoint.SharingLinkKind
0x4be547  callvirt instance string [mscorlib]System.Object::ToString()
0x4be54c  ldc.i4.0
0x4be54d  ldnull
0x4be54e  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be553  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be558  ldloc.0
0x4be559  ldstr    aFolderanonymou// "FolderAnonymousLinkPermission"
0x4be55e  ldc.i4.s 0x6E
0x4be560  ldc.i4.s 0xE
0x4be562  ldstr    aFolderanonymou// "FolderAnonymousLinkPermission"
0x4be567  ldc.i4.0
0x4be568  box      Microsoft.SharePoint.SharingLinkKind
0x4be56d  callvirt instance string [mscorlib]System.Object::ToString()
0x4be572  ldc.i4.0
0x4be573  ldnull
0x4be574  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be579  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be57e  ldloc.0
0x4be57f  ldstr    aOwnernotificat// "OwnerNotificationReshare"
0x4be584  ldc.i4.s 0x6E
0x4be586  ldc.i4.s 0xF
0x4be588  ldstr    aOwnernotificat// "OwnerNotificationReshare"
0x4be58d  ldc.i4.1
0x4be58e  stloc.3
0x4be58f  ldloca.s 3
0x4be591  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be596  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be59b  ldc.i4.0
0x4be59c  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be5a1  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be5a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be5ab  ldloc.0
0x4be5ac  ldstr    aOwnernotificat_0// "OwnerNotificationAccept"
0x4be5b1  ldc.i4.s 0x6E
0x4be5b3  ldc.i4.s 0x10
0x4be5b5  ldstr    aOwnernotificat_0// "OwnerNotificationAccept"
0x4be5ba  ldc.i4.1
0x4be5bb  stloc.s  4
0x4be5bd  ldloca.s 4
0x4be5bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be5c4  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be5c9  ldc.i4.0
0x4be5ca  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be5cf  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be5d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be5d9  ldloc.0
0x4be5da  ldstr    aOwnernotificat_1// "OwnerNotificationAnonymous"
0x4be5df  ldc.i4.s 0x6E
0x4be5e1  ldc.i4.s 0x13
0x4be5e3  ldstr    aOwnernotificat_1// "OwnerNotificationAnonymous"
0x4be5e8  ldc.i4.1
0x4be5e9  stloc.s  5
0x4be5eb  ldloca.s 5
0x4be5ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be5f2  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be5f7  ldc.i4.0
0x4be5f8  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be5fd  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be602  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be607  ldloc.0
0x4be608  ldstr    aWhocanshareall_0// "WhoCanShareAllowList"
0x4be60d  ldc.i4.s 0x6E
0x4be60f  ldc.i4.s 0x11
0x4be611  ldstr    aWhocanshareall_0// "WhoCanShareAllowList"
0x4be616  ldsfld   string [mscorlib]System.String::Empty
0x4be61b  ldc.i4.0
0x4be61c  ldnull
0x4be61d  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be622  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be627  ldloc.0
0x4be628  ldstr    aGuestsharinggr_0// "GuestSharingGroupAllowList"
0x4be62d  ldc.i4.s 0x6E
0x4be62f  ldc.i4.s 0x1A
0x4be631  ldstr    aGuestsharinggr_0// "GuestSharingGroupAllowList"
0x4be636  ldsfld   string [mscorlib]System.String::Empty
0x4be63b  ldc.i4.0
0x4be63c  ldnull
0x4be63d  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be642  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be647  ldloc.0
0x4be648  ldstr    aPreventexterna// "PreventExternalUsersFromResharing"
0x4be64d  ldc.i4.s 0x6E
0x4be64f  ldc.i4.s 0x12
0x4be651  ldstr    aPreventexterna// "PreventExternalUsersFromResharing"
0x4be656  ldc.i4.1
0x4be657  stloc.s  6
0x4be659  ldloca.s 6
0x4be65b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be660  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be665  ldc.i4.0
0x4be666  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be66b  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be670  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be675  ldloc.0
0x4be676  ldstr    aGeneratemobile// "GenerateMobileFriendlyUrls"
0x4be67b  ldc.i4.s 0x6E
0x4be67d  ldc.i4.s 0x14
0x4be67f  ldstr    aGeneratemobile// "GenerateMobileFriendlyUrls"
0x4be684  ldc.i4.1
0x4be685  stloc.s  7
0x4be687  ldloca.s 7
0x4be689  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be68e  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be693  ldc.i4.0
0x4be694  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be699  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be69e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be6a3  ldloc.0
0x4be6a4  ldstr    aEmailattestati// "EmailAttestationRequired"
0x4be6a9  ldc.i4.s 0x6E
0x4be6ab  ldc.i4.s 0x1E
0x4be6ad  ldstr    aEmailattestati// "EmailAttestationRequired"
0x4be6b2  ldc.i4.0
0x4be6b3  stloc.s  8
0x4be6b5  ldloca.s 8
0x4be6b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be6bc  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be6c1  ldc.i4.0
0x4be6c2  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be6c7  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be6cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be6d1  ldloc.0
0x4be6d2  ldstr    aEmailattestati_0// "EmailAttestationReAuthTime"
0x4be6d7  ldc.i4.s 0x6E
0x4be6d9  ldc.i4.s 0x1F
0x4be6db  ldstr    aEmailattestati_0// "EmailAttestationReAuthTime"
0x4be6e0  ldsfld   string Microsoft.SharePoint.SPCollaborationTypesHelper::DefaultEmailAttestationTimeSpan
0x4be6e5  ldc.i4.0
0x4be6e6  ldnull
0x4be6e7  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be6ec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be6f1  ldloc.0
0x4be6f2  ldstr    aEmailauthguest// "EmailAuthGuestsDisabled"
0x4be6f7  ldc.i4.s 0x6E
0x4be6f9  ldc.i4.s 0x29
0x4be6fb  ldstr    aEmailauthguest// "EmailAuthGuestsDisabled"
0x4be700  ldc.i4.0
0x4be701  stloc.s  9
0x4be703  ldloca.s 9
0x4be705  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be70a  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be70f  ldc.i4.0
0x4be710  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be715  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be71a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be71f  ldloc.0
0x4be720  ldstr    aIpaddressenfor// "IPAddressEnforcement"
0x4be725  ldc.i4   0x94
0x4be72a  ldc.i4.s 0x15
0x4be72c  ldstr    aIpaddressenfor// "IPAddressEnforcement"
0x4be731  ldc.i4.0
0x4be732  stloc.s  0xA
0x4be734  ldloca.s 0xA
0x4be736  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be73b  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be740  ldc.i4.0
0x4be741  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.SPSiteSubscriptionAuditHelper::BoolPolicyDecorator
0x4be746  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be74b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be750  ldloc.0
0x4be751  ldstr    aIpaddressallow// "IPAddressAllowList"
0x4be756  ldc.i4   0x94
0x4be75b  ldc.i4.s 0x16
0x4be75d  ldstr    aIpaddressallow// "IPAddressAllowList"
0x4be762  ldsfld   string [mscorlib]System.String::Empty
0x4be767  ldc.i4.0
0x4be768  ldnull
0x4be769  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be76e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be773  ldloc.0
0x4be774  ldstr    aSpoIdlesession// "SPO-IdleSessionSignOutForUnmanagedDevic"...
0x4be779  ldc.i4   0x93
0x4be77e  ldc.i4.s 0x17
0x4be780  ldstr    aSpoIdlesession// "SPO-IdleSessionSignOutForUnmanagedDevic"...
0x4be785  ldc.i4.0
0x4be786  stloc.s  0xB
0x4be788  ldloca.s 0xB
0x4be78a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be78f  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x4be794  ldc.i4.0
0x4be795  ldnull
0x4be796  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionAuditContext::.ctor(valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation auditEvent, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SPAuditPolicy impactedPolicy, string propertyName, string defaultValue, [opt] bool customEvent, [opt] class [mscorlib]System.Func`2<string, string> decorator)
0x4be79b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.SPSiteSubscriptionAuditContext>::Add(var<u1>, !!T0)
0x4be7a0  ldloc.0
0x4be7a1  ldstr    aSpoBlockdownlo// "SPO-BlockDownloadOfViewableFilesOnUnman"...
0x4be7a6  ldc.i4   0x93
0x4be7ab  ldc.i4.s 0x18
0x4be7ad  ldstr    aSpoBlockdownlo// "SPO-BlockDownloadOfViewableFilesOnUnman"...
0x4be7b2  ldc.i4.0
0x4be7b3  stloc.s  0xC
0x4be7b5  ldloca.s 0xC
  ... truncated ...
```
