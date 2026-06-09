# Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::GetProperty

- ea: `0xe700`
- end: `0xeb5c`
- name: `Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::GetProperty`
- size: `1116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10230`

## callees

- `0xe700`

## string_xrefs

- `0xe76f`: `CommentsDisabled`
- `0xe954`: `CommentsDisabled`
- `0xe787`: `CreatedBy`
- `0xe97f`: `CreatedBy`
- `0xe7ea`: `IsWebWelcomePage`
- `0xea2b`: `IsWebWelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0xe700  ldarg.2
0xe701  brtrue.s loc_E70E
0xe703  ldstr    aPropname// "propName"
0xe708  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe70d  throw
0xe70e  ldarg.3
0xe70f  brtrue.s loc_E71C
0xe711  ldstr    aProxycontext// "proxyContext"
0xe716  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe71b  throw
0xe71c  ldarg.1
0xe71d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata
0xe722  stloc.0
0xe723  ldloc.0
0xe724  brtrue.s loc_E731
0xe726  ldstr    aTarget// "target"
0xe72b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe730  throw
0xe731  ldarg.0
0xe732  ldarg.2
0xe733  ldarg.3
0xe734  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe739  starg.s  2
0xe73b  ldarg.2
0xe73c  dup
0xe73d  stloc.1
0xe73e  brfalse  loc_EB52
0xe743  volatile.
0xe745  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a5-1
0xe74a  brtrue   loc_E8A6
0xe74f  ldc.i4.s 0x1A
0xe751  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xe756  dup
0xe757  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xe75c  ldc.i4.0
0xe75d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe762  dup
0xe763  ldstr    aBannerimageurl// "BannerImageUrl"
0xe768  ldc.i4.1
0xe769  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe76e  dup
0xe76f  ldstr    aCommentsdisabl// "CommentsDisabled"
0xe774  ldc.i4.2
0xe775  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe77a  dup
0xe77b  ldstr    aContenttypeid// "ContentTypeId"
0xe780  ldc.i4.3
0xe781  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe786  dup
0xe787  ldstr    aCreatedby// "CreatedBy"
0xe78c  ldc.i4.4
0xe78d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe792  dup
0xe793  ldstr    aDescription// "Description"
0xe798  ldc.i4.5
0xe799  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe79e  dup
0xe79f  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xe7a4  ldc.i4.6
0xe7a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7aa  dup
0xe7ab  ldstr    aFilename// "FileName"
0xe7b0  ldc.i4.7
0xe7b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7b6  dup
0xe7b7  ldstr    aFirstpublished// "FirstPublished"
0xe7bc  ldc.i4.8
0xe7bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7c2  dup
0xe7c3  ldstr    aFirstpublished_0// "FirstPublishedRelativeTime"
0xe7c8  ldc.i4.s 9
0xe7ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7cf  dup
0xe7d0  ldstr    aId// "Id"
0xe7d5  ldc.i4.s 0xA
0xe7d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7dc  dup
0xe7dd  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xe7e2  ldc.i4.s 0xB
0xe7e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7e9  dup
0xe7ea  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xe7ef  ldc.i4.s 0xC
0xe7f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe7f6  dup
0xe7f7  ldstr    aLastmodifiedby// "LastModifiedBy"
0xe7fc  ldc.i4.s 0xD
0xe7fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe803  dup
0xe804  ldstr    aListid// "ListId"
0xe809  ldc.i4.s 0xE
0xe80b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe810  dup
0xe811  ldstr    aModified// "Modified"
0xe816  ldc.i4.s 0xF
0xe818  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe81d  dup
0xe81e  ldstr    aModifiedrelati// "ModifiedRelativeTime"
0xe823  ldc.i4.s 0x10
0xe825  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe82a  dup
0xe82b  ldstr    aPagelayouttype// "PageLayoutType"
0xe830  ldc.i4.s 0x11
0xe832  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe837  dup
0xe838  ldstr    aPath_0// "Path"
0xe83d  ldc.i4.s 0x12
0xe83f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe844  dup
0xe845  ldstr    aPromotedstate_0// "PromotedState"
0xe84a  ldc.i4.s 0x13
0xe84c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe851  dup
0xe852  ldstr    aSocialbaronsit// "SocialBarOnSitePagesDisabled"
0xe857  ldc.i4.s 0x14
0xe859  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe85e  dup
0xe85f  ldstr    aTitle// "Title"
0xe864  ldc.i4.s 0x15
0xe866  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe86b  dup
0xe86c  ldstr    aUniqueid// "UniqueId"
0xe871  ldc.i4.s 0x16
0xe873  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe878  dup
0xe879  ldstr    aUrl// "Url"
0xe87e  ldc.i4.s 0x17
0xe880  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe885  dup
0xe886  ldstr    aVersion_0// "Version"
0xe88b  ldc.i4.s 0x18
0xe88d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe892  dup
0xe893  ldstr    aVersioninfo// "VersionInfo"
0xe898  ldc.i4.s 0x19
0xe89a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe89f  volatile.
0xe8a1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a5-1
0xe8a6  volatile.
0xe8a8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x60002a5-1
0xe8ad  ldloc.1
0xe8ae  ldloca.s 2
0xe8b0  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xe8b5  brfalse  loc_EB52
0xe8ba  ldloc.2
0xe8bb  switch   loc_E92D, loc_E940, loc_E953, loc_E96B, loc_E97E, loc_E991, loc_E9A4, loc_E9BC, loc_E9CF, loc_E9E7, loc_E9FA, loc_EA12, loc_EA2A, loc_EA42, loc_EA55, loc_EA6D, loc_EA85, loc_EA98, loc_EAAB, loc_EABE, loc_EAD6, loc_EAEE, loc_EB01, loc_EB19, loc_EB2C, loc_EB3F
0xe928  br       loc_EB52
0xe92d  ldarg.0
0xe92e  ldstr    aAbsoluteurl// "AbsoluteUrl"
0xe933  ldarg.3
0xe934  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe939  ldloc.0
0xe93a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_AbsoluteUrl()
0xe93f  ret
0xe940  ldarg.0
0xe941  ldstr    aBannerimageurl// "BannerImageUrl"
0xe946  ldarg.3
0xe947  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe94c  ldloc.0
0xe94d  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_BannerImageUrl()
0xe952  ret
0xe953  ldarg.0
0xe954  ldstr    aCommentsdisabl// "CommentsDisabled"
0xe959  ldarg.3
0xe95a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe95f  ldloc.0
0xe960  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_CommentsDisabled()
0xe965  box      [mscorlib]System.Boolean
0xe96a  ret
0xe96b  ldarg.0
0xe96c  ldstr    aContenttypeid// "ContentTypeId"
0xe971  ldarg.3
0xe972  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe977  ldloc.0
0xe978  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_ContentTypeId()
0xe97d  ret
0xe97e  ldarg.0
0xe97f  ldstr    aCreatedby// "CreatedBy"
0xe984  ldarg.3
0xe985  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe98a  ldloc.0
0xe98b  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_CreatedBy()
0xe990  ret
0xe991  ldarg.0
0xe992  ldstr    aDescription// "Description"
0xe997  ldarg.3
0xe998  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe99d  ldloc.0
0xe99e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Description()
0xe9a3  ret
0xe9a4  ldarg.0
0xe9a5  ldstr    aDoesuserhaveed// "DoesUserHaveEditPermission"
0xe9aa  ldarg.3
0xe9ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe9b0  ldloc.0
0xe9b1  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_DoesUserHaveEditPermission()
0xe9b6  box      [mscorlib]System.Boolean
0xe9bb  ret
0xe9bc  ldarg.0
0xe9bd  ldstr    aFilename// "FileName"
0xe9c2  ldarg.3
0xe9c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe9c8  ldloc.0
0xe9c9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_FileName()
0xe9ce  ret
0xe9cf  ldarg.0
0xe9d0  ldstr    aFirstpublished// "FirstPublished"
0xe9d5  ldarg.3
0xe9d6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe9db  ldloc.0
0xe9dc  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_FirstPublished()
0xe9e1  box      [mscorlib]System.DateTime
0xe9e6  ret
0xe9e7  ldarg.0
0xe9e8  ldstr    aFirstpublished_0// "FirstPublishedRelativeTime"
0xe9ed  ldarg.3
0xe9ee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe9f3  ldloc.0
0xe9f4  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_FirstPublishedRelativeTime()
0xe9f9  ret
0xe9fa  ldarg.0
0xe9fb  ldstr    aId// "Id"
0xea00  ldarg.3
0xea01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea06  ldloc.0
0xea07  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Id()
0xea0c  box      [mscorlib]System.Int32
0xea11  ret
0xea12  ldarg.0
0xea13  ldstr    aIspagecheckedo// "IsPageCheckedOutToCurrentUser"
0xea18  ldarg.3
0xea19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea1e  ldloc.0
0xea1f  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_IsPageCheckedOutToCurrentUser()
0xea24  box      [mscorlib]System.Boolean
0xea29  ret
0xea2a  ldarg.0
0xea2b  ldstr    aIswebwelcomepa// "IsWebWelcomePage"
0xea30  ldarg.3
0xea31  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea36  ldloc.0
0xea37  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_IsWebWelcomePage()
0xea3c  box      [mscorlib]System.Boolean
0xea41  ret
0xea42  ldarg.0
0xea43  ldstr    aLastmodifiedby// "LastModifiedBy"
0xea48  ldarg.3
0xea49  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea4e  ldloc.0
0xea4f  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.UserInfo [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_LastModifiedBy()
0xea54  ret
0xea55  ldarg.0
0xea56  ldstr    aListid// "ListId"
0xea5b  ldarg.3
0xea5c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea61  ldloc.0
0xea62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_ListId()
0xea67  box      [mscorlib]System.Guid
0xea6c  ret
0xea6d  ldarg.0
0xea6e  ldstr    aModified// "Modified"
0xea73  ldarg.3
0xea74  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea79  ldloc.0
0xea7a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Modified()
0xea7f  box      [mscorlib]System.DateTime
0xea84  ret
0xea85  ldarg.0
0xea86  ldstr    aModifiedrelati// "ModifiedRelativeTime"
0xea8b  ldarg.3
0xea8c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xea91  ldloc.0
0xea92  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_ModifiedRelativeTime()
0xea97  ret
0xea98  ldarg.0
0xea99  ldstr    aPagelayouttype// "PageLayoutType"
0xea9e  ldarg.3
0xea9f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xeaa4  ldloc.0
0xeaa5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_PageLayoutType()
0xeaaa  ret
0xeaab  ldarg.0
0xeaac  ldstr    aPath_0// "Path"
0xeab1  ldarg.3
0xeab2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xeab7  ldloc.0
0xeab8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_Path()
0xeabd  ret
0xeabe  ldarg.0
0xeabf  ldstr    aPromotedstate_0// "PromotedState"
0xeac4  ldarg.3
0xeac5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xeaca  ldloc.0
0xeacb  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadata::get_PromotedState()
0xead0  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState
0xead5  ret
0xead6  ldarg.0
0xead7  ldstr    aSocialbaronsit// "SocialBarOnSitePagesDisabled"
0xeadc  ldarg.3
0xeadd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
