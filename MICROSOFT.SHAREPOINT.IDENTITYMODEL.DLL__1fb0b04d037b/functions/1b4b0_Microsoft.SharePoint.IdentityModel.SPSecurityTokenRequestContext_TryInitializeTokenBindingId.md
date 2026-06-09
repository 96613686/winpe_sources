# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryInitializeTokenBindingId

- ea: `0x1b4b0`
- end: `0x1b5ad`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryInitializeTokenBindingId`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1aa80`

## callees

- `0x1b4b0`

## string_xrefs

- `0x1b4d4`: `TryInitializeTokenBindingId: Request object is null.`
- `0x1b4fc`: `TryInitializeTokenBindingId: Request property bag is null.`
- `0x1b526`: `TryInitializeTokenBindingId: Request property bag doesn't have value for TokenBindindId.`
- `0x1b540`: `TryInitializeTokenBindingId: Initializing TokenBindingId from request data: '<name>{0}</name>'.`
- `0x1b58e`: `Failed to parse token binding Id from request properties. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1b4b0  ldc.i4   0x37B0
0x1b4b5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1b4ba  brtrue.s loc_1B4BE
0x1b4bc  ldc.i4.1
0x1b4bd  ret
0x1b4be  ldc.i4.0
0x1b4bf  stloc.0
0x1b4c0  ldarg.0
0x1b4c1  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b4c6  brtrue.s loc_1B4E3
0x1b4c8  ldc.i4   0x230F6C7
0x1b4cd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b4d2  ldc.i4.s 0xA
0x1b4d4  ldstr    aTryinitializet// "TryInitializeTokenBindingId: Request ob"...
0x1b4d9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b4de  br       loc_1B57D
0x1b4e3  ldarg.0
0x1b4e4  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b4e9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b4ee  brtrue.s loc_1B508
0x1b4f0  ldc.i4   0x230F6C8
0x1b4f5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b4fa  ldc.i4.s 0xA
0x1b4fc  ldstr    aTryinitializet_0// "TryInitializeTokenBindingId: Request pr"...
0x1b501  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b506  br.s     loc_1B57D
0x1b508  ldarg.0
0x1b509  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b50e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b513  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_TokenBindingId()
0x1b518  brtrue.s loc_1B534
0x1b51a  ldc.i4   0x230F6C9
0x1b51f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b524  ldc.i4.s 0x32
0x1b526  ldstr    aTryinitializet_1// "TryInitializeTokenBindingId: Request pr"...
0x1b52b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1b530  ldc.i4.1
0x1b531  stloc.0
0x1b532  br.s     loc_1B57D
0x1b534  ldc.i4   0x230F6CA
0x1b539  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b53e  ldc.i4.s 0x32
0x1b540  ldstr    aTryinitializet_2// "TryInitializeTokenBindingId: Initializi"...
0x1b545  ldc.i4.1
0x1b546  newarr   [mscorlib]System.Object
0x1b54b  stloc.2
0x1b54c  ldloc.2
0x1b54d  ldc.i4.0
0x1b54e  ldarg.0
0x1b54f  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b554  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b559  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_TokenBindingId()
0x1b55e  stelem.ref
0x1b55f  ldloc.2
0x1b560  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b565  ldarg.0
0x1b566  ldarg.0
0x1b567  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_Request
0x1b56c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1b571  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_TokenBindingId()
0x1b576  stfld    string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::m_TokenBindingId
0x1b57b  ldc.i4.1
0x1b57c  stloc.0
0x1b57d  leave.s  loc_1B5AB
0x1b57f  stloc.1
0x1b580  ldc.i4.0
0x1b581  stloc.0
0x1b582  ldc.i4   0x230F6CB
0x1b587  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1b58c  ldc.i4.s 0xA
0x1b58e  ldstr    aFailedToParseT// "Failed to parse token binding Id from r"...
0x1b593  ldc.i4.1
0x1b594  newarr   [mscorlib]System.Object
0x1b599  stloc.3
0x1b59a  ldloc.3
0x1b59b  ldc.i4.0
0x1b59c  ldloc.1
0x1b59d  callvirt instance string [mscorlib]System.Object::ToString()
0x1b5a2  stelem.ref
0x1b5a3  ldloc.3
0x1b5a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1b5a9  leave.s  loc_1B5AB
0x1b5ab  ldloc.0
0x1b5ac  ret
```
