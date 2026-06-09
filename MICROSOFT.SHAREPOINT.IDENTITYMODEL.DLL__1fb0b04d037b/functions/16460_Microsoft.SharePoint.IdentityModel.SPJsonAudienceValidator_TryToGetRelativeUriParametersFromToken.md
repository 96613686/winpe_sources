# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetRelativeUriParametersFromToken

- ea: `0x16460`
- end: `0x1650a`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetRelativeUriParametersFromToken`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16770`

## callees

- `0x97b0`
- `0x98c0`
- `0x16460`

## string_xrefs

- `0x1646f`: `The token is null.`
- `0x164a1`: `The token audience is not a relative URI.`
- `0x164cd`: `The token has a relative audience uri.`

## pseudocode

```c

```

## disassembly

```asm
0x16460  ldarg.1
0x16461  brtrue.s loc_1647E
0x16463  ldc.i4   0x121140A
0x16468  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1646d  ldc.i4.s 0xA
0x1646f  ldstr    aTheTokenIsNull// "The token is null."
0x16474  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16479  ldarg.2
0x1647a  ldnull
0x1647b  stind.ref
0x1647c  ldc.i4.0
0x1647d  ret
0x1647e  ldc.i4.0
0x1647f  stloc.0
0x16480  ldarg.2
0x16481  ldnull
0x16482  stind.ref
0x16483  ldnull
0x16484  stloc.1
0x16485  ldarg.1
0x16486  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x1648b  ldc.i4.2
0x1648c  ldloca.s 1
0x1648e  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x16493  brtrue.s loc_164AF
0x16495  ldc.i4   0x121140B
0x1649a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1649f  ldc.i4.s 0x32
0x164a1  ldstr    aTheTokenAudien// "The token audience is not a relative UR"...
0x164a6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x164ab  ldc.i4.0
0x164ac  stloc.0
0x164ad  br.s     loc_164D7
0x164af  ldarg.2
0x164b0  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::.ctor()
0x164b5  stloc.2
0x164b6  ldloc.2
0x164b7  ldloc.1
0x164b8  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_AudienceUri(class [System]System.Uri value)
0x164bd  ldloc.2
0x164be  stind.ref
0x164bf  ldc.i4.1
0x164c0  stloc.0
0x164c1  ldc.i4   0x121140C
0x164c6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x164cb  ldc.i4.s 0x64
0x164cd  ldstr    aTheTokenHasARe// "The token has a relative audience uri."
0x164d2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x164d7  leave.s  loc_16508
0x164d9  stloc.3
0x164da  ldc.i4   0x121140D
0x164df  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x164e4  ldc.i4.s 0xA
0x164e6  ldstr    aExceptionBuild// "Exception building audience paramters. "...
0x164eb  ldc.i4.1
0x164ec  newarr   [mscorlib]System.Object
0x164f1  stloc.s  4
0x164f3  ldloc.s  4
0x164f5  ldc.i4.0
0x164f6  ldloc.3
0x164f7  callvirt instance string [mscorlib]System.Object::ToString()
0x164fc  stelem.ref
0x164fd  ldloc.s  4
0x164ff  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16504  ldc.i4.0
0x16505  stloc.0
0x16506  leave.s  loc_16508
0x16508  ldloc.0
0x16509  ret
```
