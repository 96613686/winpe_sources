# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::TryGetNameFromOutputClaimsIdentity

- ea: `0x1f2b0`
- end: `0x1f376`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::TryGetNameFromOutputClaimsIdentity`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1f2b0`

## string_xrefs

- `0x1f2c4`: `Supplied claimsIdentity was null.`
- `0x1f2e9`: `Supplied claimsIdentity.Name was null or empty. Value: '{0}'.`
- `0x1f31b`: `Got user name from claimsIdentity.Name. Value: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f2b0  ldc.i4.0
0x1f2b1  stloc.0
0x1f2b2  ldarg.2
0x1f2b3  ldnull
0x1f2b4  stind.ref
0x1f2b5  ldarg.1
0x1f2b6  brtrue.s loc_1F2D0
0x1f2b8  ldc.i4   0x7A051C
0x1f2bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f2c2  ldc.i4.s 0xA
0x1f2c4  ldstr    aSuppliedClaims// "Supplied claimsIdentity was null."
0x1f2c9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f2ce  br.s     loc_1F340
0x1f2d0  ldarg.1
0x1f2d1  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1f2d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f2db  brfalse.s loc_1F30F
0x1f2dd  ldc.i4   0x7A051D
0x1f2e2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f2e7  ldc.i4.s 0x64
0x1f2e9  ldstr    aSuppliedClaims_1// "Supplied claimsIdentity.Name was null o"...
0x1f2ee  ldc.i4.1
0x1f2ef  newarr   [mscorlib]System.Object
0x1f2f4  stloc.2
0x1f2f5  ldloc.2
0x1f2f6  ldc.i4.0
0x1f2f7  ldarg.1
0x1f2f8  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1f2fd  dup
0x1f2fe  brtrue.s loc_1F306
0x1f300  pop
0x1f301  ldstr    aNull_0// "Null"
0x1f306  stelem.ref
0x1f307  ldloc.2
0x1f308  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f30d  br.s     loc_1F340
0x1f30f  ldc.i4   0x7A051E
0x1f314  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f319  ldc.i4.s 0x64
0x1f31b  ldstr    aGotUserNameFro// "Got user name from claimsIdentity.Name."...
0x1f320  ldc.i4.1
0x1f321  newarr   [mscorlib]System.Object
0x1f326  stloc.3
0x1f327  ldloc.3
0x1f328  ldc.i4.0
0x1f329  ldarg.1
0x1f32a  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1f32f  stelem.ref
0x1f330  ldloc.3
0x1f331  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f336  ldc.i4.1
0x1f337  stloc.0
0x1f338  ldarg.2
0x1f339  ldarg.1
0x1f33a  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1f33f  stind.ref
0x1f340  leave.s  loc_1F374
0x1f342  stloc.1
0x1f343  ldc.i4.0
0x1f344  stloc.0
0x1f345  ldarg.2
0x1f346  ldnull
0x1f347  stind.ref
0x1f348  ldc.i4   0x7A051F
0x1f34d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f352  ldc.i4.s 0xA
0x1f354  ldstr    aFailedToGetUse// "Failed to get username from output clai"...
0x1f359  ldc.i4.1
0x1f35a  newarr   [mscorlib]System.Object
0x1f35f  stloc.s  4
0x1f361  ldloc.s  4
0x1f363  ldc.i4.0
0x1f364  ldloc.1
0x1f365  callvirt instance string [mscorlib]System.Object::ToString()
0x1f36a  stelem.ref
0x1f36b  ldloc.s  4
0x1f36d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f372  leave.s  loc_1F374
0x1f374  ldloc.0
0x1f375  ret
```
