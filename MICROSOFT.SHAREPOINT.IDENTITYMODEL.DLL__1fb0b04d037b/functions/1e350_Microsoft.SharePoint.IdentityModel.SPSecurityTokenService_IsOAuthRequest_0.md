# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::IsOAuthRequest_0

- ea: `0x1e350`
- end: `0x1e3b9`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::IsOAuthRequest_0`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a0d0`
- `0x1e300`

## callees

- `0x1e350`
- `0x2c520`

## string_xrefs

- `0x1e35f`: `requestSecurityToken`
- `0x1e38a`: `requestSecurityToken`
- `0x1e380`: `The requestSecurityToken is not a SPRequestSecurityToken object.`

## pseudocode

```c

```

## disassembly

```asm
0x1e350  ldc.i4   0x1299245
0x1e355  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1e35a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e35f  ldstr    aRequestsecurit// "requestSecurityToken"
0x1e364  ldarg.0
0x1e365  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1e36a  ldarg.0
0x1e36b  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken
0x1e370  stloc.0
0x1e371  ldloc.0
0x1e372  brtrue.s loc_1E395
0x1e374  ldc.i4   0x1299246
0x1e379  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1e37e  ldc.i4.s 0xA
0x1e380  ldstr    aTheRequestsecu// "The requestSecurityToken is not a SPReq"...
0x1e385  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1e38a  ldstr    aRequestsecurit// "requestSecurityToken"
0x1e38f  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1e394  throw
0x1e395  ldc.i4.0
0x1e396  stloc.1
0x1e397  ldloc.0
0x1e398  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1e39d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_IsOAuthRequest()
0x1e3a2  stloc.2
0x1e3a3  ldloca.s 2
0x1e3a5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1e3aa  brfalse.s loc_1E3B7
0x1e3ac  ldloca.s 2
0x1e3ae  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1e3b3  brfalse.s loc_1E3B7
0x1e3b5  ldc.i4.1
0x1e3b6  stloc.1
0x1e3b7  ldloc.1
0x1e3b8  ret
```
