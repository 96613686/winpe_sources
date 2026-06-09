# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsOAuthRequestSubjectToPolicyEnforcement

- ea: `0x6270`
- end: `0x631d`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsOAuthRequestSubjectToPolicyEnforcement`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6270`
- `0x6320`
- `0x2c520`
- `0x2c720`

## string_xrefs

- `0x6299`: `tokenContext`
- `0x62b8`: `IsOAuthRequestSubjectToPolicyEnforcement: Not an OAuth request but on OAuth path.`
- `0x62ec`: `PolicyEnforcement: Incoming OAuth identity/token type not set. IdentityType: '{0}'. TokenType: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x6270  ldc.i4   0x1249397
0x6275  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x627a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_PolicyEnforcement()
0x627f  ldstr    aContext_0// "context"
0x6284  ldarg.0
0x6285  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnInvalid(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, class [System.Web]System.Web.HttpContext value)
0x628a  ldc.i4   0x1249398
0x628f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x6294  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_PolicyEnforcement()
0x6299  ldstr    aTokencontext// "tokenContext"
0x629e  ldarg.1
0x629f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x62a4  ldarg.0
0x62a5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IsOAuthRequest(class [System.Web]System.Web.HttpContext)
0x62aa  brtrue.s loc_62C8
0x62ac  ldc.i4   0x1249399
0x62b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_PolicyEnforcement()
0x62b6  ldc.i4.s 0xA
0x62b8  ldstr    aIsoauthrequest// "IsOAuthRequestSubjectToPolicyEnforcemen"...
0x62bd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x62c2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x62c7  throw
0x62c8  ldarg.2
0x62c9  ldarg.0
0x62ca  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IncomingOAuthIdentityType(class [System.Web]System.Web.HttpContext)
0x62cf  stind.i4
0x62d0  ldarg.3
0x62d1  ldarg.0
0x62d2  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIncomingTokenType [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IncomingOAuthTokenType(class [System.Web]System.Web.HttpContext)
0x62d7  stind.i4
0x62d8  ldarg.2
0x62d9  ldind.i4
0x62da  brfalse.s loc_62E0
0x62dc  ldarg.3
0x62dd  ldind.i4
0x62de  brtrue.s loc_6312
0x62e0  ldc.i4   0x124939A
0x62e5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_PolicyEnforcement()
0x62ea  ldc.i4.s 0x32
0x62ec  ldstr    aPolicyenforcem// "PolicyEnforcement: Incoming OAuth ident"...
0x62f1  ldc.i4.2
0x62f2  newarr   [mscorlib]System.Object
0x62f7  stloc.0
0x62f8  ldloc.0
0x62f9  ldc.i4.0
0x62fa  ldarg.2
0x62fb  ldind.i4
0x62fc  box      [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType
0x6301  stelem.ref
0x6302  ldloc.0
0x6303  ldc.i4.1
0x6304  ldarg.3
0x6305  ldind.i4
0x6306  box      [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIncomingTokenType
0x630b  stelem.ref
0x630c  ldloc.0
0x630d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x6312  ldarg.1
0x6313  ldarg.3
0x6314  ldind.i4
0x6315  ldarg.2
0x6316  ldind.i4
0x6317  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsOAuthRequestSubjectToPolicyEnforcement(class Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext tokenContext, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIncomingTokenType incomingOAuthTokenType, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType incomingOAuthIdentityType)
0x631c  ret
```
