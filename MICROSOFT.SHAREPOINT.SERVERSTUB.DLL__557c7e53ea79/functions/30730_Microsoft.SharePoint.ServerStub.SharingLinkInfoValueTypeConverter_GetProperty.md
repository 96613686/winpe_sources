# Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter::GetProperty

- ea: `0x30730`
- end: `0x30994`
- name: `Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter::GetProperty`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x30730`

## string_xrefs

- `0x30793`: `Created`
- `0x307e7`: `IsFormsLink`
- `0x307f3`: `IsReviewLink`
- `0x30827`: `LinkKind`
- `0x30787`: `AllowsAnonymousAccess`
- `0x3079f`: `CreatedBy`
- `0x307db`: `IsEditLink`

## pseudocode

```c

```

## disassembly

```asm
0x30730  ldarg.3
0x30731  brtrue.s loc_3073E
0x30733  ldstr    aProxycontext// "proxyContext"
0x30738  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3073d  throw
0x3073e  ldarg.1
0x3073f  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo
0x30744  stloc.0
0x30745  ldloc.0
0x30746  brtrue.s loc_30753
0x30748  ldstr    aTarget// "target"
0x3074d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30752  throw
0x30753  ldarg.2
0x30754  brtrue.s loc_30761
0x30756  ldstr    aPropname// "propName"
0x3075b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30760  throw
0x30761  ldarg.0
0x30762  ldarg.2
0x30763  ldarg.3
0x30764  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30769  starg.s  2
0x3076b  ldarg.2
0x3076c  dup
0x3076d  stloc.1
0x3076e  brfalse  loc_3098A
0x30773  volatile.
0x30775  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600091e-1
0x3077a  brtrue   loc_3086E
0x3077f  ldc.i4.s 0x12
0x30781  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x30786  dup
0x30787  ldstr    aAllowsanonymou// "AllowsAnonymousAccess"
0x3078c  ldc.i4.0
0x3078d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30792  dup
0x30793  ldstr    aCreated// "Created"
0x30798  ldc.i4.1
0x30799  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3079e  dup
0x3079f  ldstr    aCreatedby// "CreatedBy"
0x307a4  ldc.i4.2
0x307a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307aa  dup
0x307ab  ldstr    aExpiration// "Expiration"
0x307b0  ldc.i4.3
0x307b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307b6  dup
0x307b7  ldstr    aHasexternalgue// "HasExternalGuestInvitees"
0x307bc  ldc.i4.4
0x307bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307c2  dup
0x307c3  ldstr    aInvitations// "Invitations"
0x307c8  ldc.i4.5
0x307c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307ce  dup
0x307cf  ldstr    aIsactive// "IsActive"
0x307d4  ldc.i4.6
0x307d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307da  dup
0x307db  ldstr    aIseditlink// "IsEditLink"
0x307e0  ldc.i4.7
0x307e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307e6  dup
0x307e7  ldstr    aIsformslink// "IsFormsLink"
0x307ec  ldc.i4.8
0x307ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307f2  dup
0x307f3  ldstr    aIsreviewlink// "IsReviewLink"
0x307f8  ldc.i4.s 9
0x307fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x307ff  dup
0x30800  ldstr    aIsunhealthy// "IsUnhealthy"
0x30805  ldc.i4.s 0xA
0x30807  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3080c  dup
0x3080d  ldstr    aLastmodified// "LastModified"
0x30812  ldc.i4.s 0xB
0x30814  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30819  dup
0x3081a  ldstr    aLastmodifiedby// "LastModifiedBy"
0x3081f  ldc.i4.s 0xC
0x30821  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30826  dup
0x30827  ldstr    aLinkkind// "LinkKind"
0x3082c  ldc.i4.s 0xD
0x3082e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30833  dup
0x30834  ldstr    aRequirespasswo// "RequiresPassword"
0x30839  ldc.i4.s 0xE
0x3083b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30840  dup
0x30841  ldstr    aRestrictedshar// "RestrictedShareMembership"
0x30846  ldc.i4.s 0xF
0x30848  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3084d  dup
0x3084e  ldstr    aShareid// "ShareId"
0x30853  ldc.i4.s 0x10
0x30855  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3085a  dup
0x3085b  ldstr    aUrl// "Url"
0x30860  ldc.i4.s 0x11
0x30862  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x30867  volatile.
0x30869  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600091e-1
0x3086e  volatile.
0x30870  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600091e-1
0x30875  ldloc.1
0x30876  ldloca.s 2
0x30878  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3087d  brfalse  loc_3098A
0x30882  ldloc.2
0x30883  switch   loc_308D5, loc_308E1, loc_308E8, loc_308EF, loc_308F6, loc_30902, loc_30909, loc_30915, loc_30921, loc_3092D, loc_30939, loc_30945, loc_3094C, loc_30953, loc_3095F, loc_3096B, loc_30977, loc_30983
0x308d0  br       loc_3098A
0x308d5  ldloc.0
0x308d6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_AllowsAnonymousAccess()
0x308db  box      [mscorlib]System.Boolean
0x308e0  ret
0x308e1  ldloc.0
0x308e2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Created()
0x308e7  ret
0x308e8  ldloc.0
0x308e9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_CreatedBy()
0x308ee  ret
0x308ef  ldloc.0
0x308f0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Expiration()
0x308f5  ret
0x308f6  ldloc.0
0x308f7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_HasExternalGuestInvitees()
0x308fc  box      [mscorlib]System.Boolean
0x30901  ret
0x30902  ldloc.0
0x30903  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.LinkInvitation> [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Invitations()
0x30908  ret
0x30909  ldloc.0
0x3090a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsActive()
0x3090f  box      [mscorlib]System.Boolean
0x30914  ret
0x30915  ldloc.0
0x30916  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsEditLink()
0x3091b  box      [mscorlib]System.Boolean
0x30920  ret
0x30921  ldloc.0
0x30922  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsFormsLink()
0x30927  box      [mscorlib]System.Boolean
0x3092c  ret
0x3092d  ldloc.0
0x3092e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsReviewLink()
0x30933  box      [mscorlib]System.Boolean
0x30938  ret
0x30939  ldloc.0
0x3093a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsUnhealthy()
0x3093f  box      [mscorlib]System.Boolean
0x30944  ret
0x30945  ldloc.0
0x30946  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LastModified()
0x3094b  ret
0x3094c  ldloc.0
0x3094d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LastModifiedBy()
0x30952  ret
0x30953  ldloc.0
0x30954  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LinkKind()
0x30959  box      [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x3095e  ret
0x3095f  ldloc.0
0x30960  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_RequiresPassword()
0x30965  box      [mscorlib]System.Boolean
0x3096a  ret
0x3096b  ldloc.0
0x3096c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_RestrictedShareMembership()
0x30971  box      [mscorlib]System.Boolean
0x30976  ret
0x30977  ldloc.0
0x30978  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_ShareId()
0x3097d  box      [mscorlib]System.Guid
0x30982  ret
0x30983  ldloc.0
0x30984  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Url()
0x30989  ret
0x3098a  ldarg.0
0x3098b  ldarg.1
0x3098c  ldarg.2
0x3098d  ldarg.3
0x3098e  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30993  ret
```
