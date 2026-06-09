# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeSiteSubscription

- ea: `0x22040`
- end: `0x22126`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeSiteSubscription`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x21d60`

## callees

- `0x21c00`
- `0x21c10`
- `0x22040`
- `0x28af0`

## string_xrefs

- `0x22102`: `Token Request Data: Exception intializing SubscriptionId data for request. Exception: '{0}'.`
- `0x22076`: `Token Request Data: Found subscription id in legacy auth mode: '{0}'.`
- `0x220a2`: `Token Request Data: SubscriptionId set to null. LegacyMode: '{0}'.`
- `0x220d5`: `Token Request Data: Successfully initialized SubscriptionId data for request. SubscriptionId: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22040  ldc.i4.0
0x22041  stloc.0
0x22042  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22047  stloc.1
0x22048  ldc.i4.0
0x22049  stloc.2
0x2204a  ldnull
0x2204b  ldloca.s 1
0x2204d  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::TryGetCurrentSiteSubscriptionId(class [System]System.Uri targetUri, [out] valuetype [mscorlib]System.Guid& siteSubscriptionId)
0x22052  brfalse.s loc_22096
0x22054  ldarg.0
0x22055  ldloca.s 1
0x22057  constrained. [mscorlib]System.Guid
0x2205d  callvirt instance string [mscorlib]System.Object::ToString()
0x22062  call     instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_SubscriptionId(string value)
0x22067  ldloc.2
0x22068  brfalse.s loc_220C7
0x2206a  ldc.i4   0x12113E0
0x2206f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22074  ldc.i4.s 0x32
0x22076  ldstr    aTokenRequestDa_18// "Token Request Data: Found subscription "...
0x2207b  ldc.i4.1
0x2207c  newarr   [mscorlib]System.Object
0x22081  stloc.s  4
0x22083  ldloc.s  4
0x22085  ldc.i4.0
0x22086  ldloc.1
0x22087  box      [mscorlib]System.Guid
0x2208c  stelem.ref
0x2208d  ldloc.s  4
0x2208f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22094  br.s     loc_220C7
0x22096  ldc.i4   0x12113E1
0x2209b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x220a0  ldc.i4.s 0x32
0x220a2  ldstr    aTokenRequestDa_19// "Token Request Data: SubscriptionId set "...
0x220a7  ldc.i4.1
0x220a8  newarr   [mscorlib]System.Object
0x220ad  stloc.s  5
0x220af  ldloc.s  5
0x220b1  ldc.i4.0
0x220b2  ldloc.2
0x220b3  box      [mscorlib]System.Boolean
0x220b8  stelem.ref
0x220b9  ldloc.s  5
0x220bb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x220c0  ldarg.0
0x220c1  ldnull
0x220c2  call     instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_SubscriptionId(string value)
0x220c7  ldc.i4.1
0x220c8  stloc.0
0x220c9  ldc.i4   0x120789A
0x220ce  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x220d3  ldc.i4.s 0x32
0x220d5  ldstr    aTokenRequestDa_20// "Token Request Data: Successfully initia"...
0x220da  ldc.i4.1
0x220db  newarr   [mscorlib]System.Object
0x220e0  stloc.s  6
0x220e2  ldloc.s  6
0x220e4  ldc.i4.0
0x220e5  ldarg.0
0x220e6  call     instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_SubscriptionId()
0x220eb  stelem.ref
0x220ec  ldloc.s  6
0x220ee  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x220f3  leave.s  loc_22124
0x220f5  stloc.3
0x220f6  ldc.i4   0x120789B
0x220fb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22100  ldc.i4.s 0xA
0x22102  ldstr    aTokenRequestDa_17// "Token Request Data: Exception intializi"...
0x22107  ldc.i4.1
0x22108  newarr   [mscorlib]System.Object
0x2210d  stloc.s  7
0x2210f  ldloc.s  7
0x22111  ldc.i4.0
0x22112  ldloc.3
0x22113  callvirt instance string [mscorlib]System.Object::ToString()
0x22118  stelem.ref
0x22119  ldloc.s  7
0x2211b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22120  ldc.i4.0
0x22121  stloc.0
0x22122  leave.s  loc_22124
0x22124  ldloc.0
0x22125  ret
```
