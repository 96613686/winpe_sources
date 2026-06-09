# Microsoft.SharePoint.IdentityModel.SPClaimsUtility::TryGetSiteSubscriptionIdFromContextUri

- ea: `0x28d60`
- end: `0x28f00`
- name: `Microsoft.SharePoint.IdentityModel.SPClaimsUtility::TryGetSiteSubscriptionIdFromContextUri`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x28af0`

## callees

- `0x22ae0`
- `0x22c40`
- `0x28d60`
- `0x28f00`

## string_xrefs

- `0x28d80`: `TryGetSiteSubscriptionIdFromContextUri. Uri argument is null, returning false.`
- `0x28da5`: `Found the site subscription id in the special list. Uri: '{0}'. Id: '{1}'.`
- `0x28de3`: `Getting current site subscription id using context uri: '{0}'.`
- `0x28e2c`: `Found site subscription id using context uri: '{0}'. Id: '{1}'.`
- `0x28e74`: `Failed getting current site subscription id using context uri: '{0}'.`
- `0x28ea3`: `Failed to grab current site subscription id using context uri: '{0}'. Exception: '{1}'.`
- `0x28ede`: `Get site subscription id: Exception encountered while trying to get site subscription id using ContextUri. Ex: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x28d60  ldarg.1
0x28d61  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28d66  stobj    [mscorlib]System.Guid
0x28d6b  ldarg.0
0x28d6c  ldnull
0x28d6d  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x28d72  brfalse.s loc_28D8C
0x28d74  ldc.i4   0x12078C7
0x28d79  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28d7e  ldc.i4.s 0x32
0x28d80  ldstr    aTrygetsitesubs_2// "TryGetSiteSubscriptionIdFromContextUri."...
0x28d85  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x28d8a  ldc.i4.0
0x28d8b  ret
0x28d8c  ldc.i4.0
0x28d8d  stloc.0
0x28d8e  ldarg.0
0x28d8f  ldarg.1
0x28d90  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::TryGetSpecialCaseSiteSubscriptionId(class [System]System.Uri targetUri, [out] valuetype [mscorlib]System.Guid& siteSubscriptionId)
0x28d95  brfalse.s loc_28DD7
0x28d97  ldc.i4.1
0x28d98  stloc.0
0x28d99  ldc.i4   0x12078C8
0x28d9e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28da3  ldc.i4.s 0x64
0x28da5  ldstr    aFoundTheSiteSu// "Found the site subscription id in the s"...
0x28daa  ldc.i4.2
0x28dab  newarr   [mscorlib]System.Object
0x28db0  stloc.s  4
0x28db2  ldloc.s  4
0x28db4  ldc.i4.0
0x28db5  ldarg.0
0x28db6  callvirt instance string [System]System.Uri::get_OriginalString()
0x28dbb  stelem.ref
0x28dbc  ldloc.s  4
0x28dbe  ldc.i4.1
0x28dbf  ldarg.1
0x28dc0  ldobj    [mscorlib]System.Guid
0x28dc5  box      [mscorlib]System.Guid
0x28dca  stelem.ref
0x28dcb  ldloc.s  4
0x28dcd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28dd2  br       loc_28ECD
0x28dd7  ldc.i4   0x12078C9
0x28ddc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28de1  ldc.i4.s 0x14
0x28de3  ldstr    aGettingCurrent// "Getting current site subscription id us"...
0x28de8  ldc.i4.1
0x28de9  newarr   [mscorlib]System.Object
0x28dee  stloc.s  5
0x28df0  ldloc.s  5
0x28df2  ldc.i4.0
0x28df3  ldarg.0
0x28df4  callvirt instance string [System]System.Uri::get_OriginalString()
0x28df9  stelem.ref
0x28dfa  ldloc.s  5
0x28dfc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28e01  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x28e06  ldarg.0
0x28e07  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri(class [System]System.Uri context)
0x28e0c  stloc.1
0x28e0d  ldloc.1
0x28e0e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28e13  brtrue.s loc_28E5B
0x28e15  ldloc.1
0x28e16  ldarg.1
0x28e17  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x28e1c  brfalse.s loc_28E5B
0x28e1e  ldc.i4.1
0x28e1f  stloc.0
0x28e20  ldc.i4   0x12078CA
0x28e25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28e2a  ldc.i4.s 0x64
0x28e2c  ldstr    aFoundSiteSubsc// "Found site subscription id using contex"...
0x28e31  ldc.i4.2
0x28e32  newarr   [mscorlib]System.Object
0x28e37  stloc.s  6
0x28e39  ldloc.s  6
0x28e3b  ldc.i4.0
0x28e3c  ldarg.0
0x28e3d  callvirt instance string [System]System.Uri::get_OriginalString()
0x28e42  stelem.ref
0x28e43  ldloc.s  6
0x28e45  ldc.i4.1
0x28e46  ldarg.1
0x28e47  ldobj    [mscorlib]System.Guid
0x28e4c  box      [mscorlib]System.Guid
0x28e51  stelem.ref
0x28e52  ldloc.s  6
0x28e54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28e59  br.s     loc_28E92
0x28e5b  ldarg.1
0x28e5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28e61  stobj    [mscorlib]System.Guid
0x28e66  ldc.i4.0
0x28e67  stloc.0
0x28e68  ldc.i4   0x12078CB
0x28e6d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28e72  ldc.i4.s 0x14
0x28e74  ldstr    aFailedGettingC// "Failed getting current site subscriptio"...
0x28e79  ldc.i4.1
0x28e7a  newarr   [mscorlib]System.Object
0x28e7f  stloc.s  7
0x28e81  ldloc.s  7
0x28e83  ldc.i4.0
0x28e84  ldarg.0
0x28e85  callvirt instance string [System]System.Uri::get_OriginalString()
0x28e8a  stelem.ref
0x28e8b  ldloc.s  7
0x28e8d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28e92  leave.s  loc_28ECD
0x28e94  stloc.2
0x28e95  ldc.i4.0
0x28e96  stloc.0
0x28e97  ldc.i4   0x12078CC
0x28e9c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x28ea1  ldc.i4.s 0xA
0x28ea3  ldstr    aFailedToGrabCu// "Failed to grab current site subscriptio"...
0x28ea8  ldc.i4.2
0x28ea9  newarr   [mscorlib]System.Object
0x28eae  stloc.s  8
0x28eb0  ldloc.s  8
0x28eb2  ldc.i4.0
0x28eb3  ldarg.0
0x28eb4  callvirt instance string [System]System.Uri::get_OriginalString()
0x28eb9  stelem.ref
0x28eba  ldloc.s  8
0x28ebc  ldc.i4.1
0x28ebd  ldloc.2
0x28ebe  callvirt instance string [mscorlib]System.Object::ToString()
0x28ec3  stelem.ref
0x28ec4  ldloc.s  8
0x28ec6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28ecb  leave.s  loc_28ECD
0x28ecd  leave.s  loc_28EFE
0x28ecf  stloc.3
0x28ed0  ldc.i4.0
0x28ed1  stloc.0
0x28ed2  ldc.i4   0x12078CD
0x28ed7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x28edc  ldc.i4.s 0xA
0x28ede  ldstr    aGetSiteSubscri_5// "Get site subscription id: Exception enc"...
0x28ee3  ldc.i4.1
0x28ee4  newarr   [mscorlib]System.Object
0x28ee9  stloc.s  9
0x28eeb  ldloc.s  9
0x28eed  ldc.i4.0
0x28eee  ldloc.3
0x28eef  callvirt instance string [mscorlib]System.Object::ToString()
0x28ef4  stelem.ref
0x28ef5  ldloc.s  9
0x28ef7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28efc  leave.s  loc_28EFE
0x28efe  ldloc.0
0x28eff  ret
```
