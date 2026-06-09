# Microsoft.SharePoint.IdentityModel.SPPassiveIssuerTokenResolver::TryResolveSecurityKeyCore

- ea: `0x18d50`
- end: `0x18e65`
- name: `Microsoft.SharePoint.IdentityModel.SPPassiveIssuerTokenResolver::TryResolveSecurityKeyCore`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18d50`

## string_xrefs

- `0x18dd6`: `Token validation succeeded but is null.`
- `0x18df4`: `Token validation succeeded but security keys are null.`
- `0x18e18`: `The key identifier clause resolved token does not have a single key. Count: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x18d50  ldarg.1
0x18d51  brtrue.s loc_18D5E
0x18d53  ldstr    aKeyidentifierc// "keyIdentifierClause"
0x18d58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18d5d  throw
0x18d5e  ldc.i4.0
0x18d5f  stloc.0
0x18d60  ldnull
0x18d61  stloc.1
0x18d62  ldarg.2
0x18d63  ldnull
0x18d64  stind.ref
0x18d65  ldarg.1
0x18d66  isinst   [System.IdentityModel]System.IdentityModel.Tokens.EncryptedKeyIdentifierClause
0x18d6b  brfalse.s loc_18D86
0x18d6d  ldc.i4.0
0x18d6e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18d73  ldc.i4.s 0xA
0x18d75  ldstr    aTheKeyIdentifi// "The key identifier clause is an encrypt"...
0x18d7a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18d7f  ldc.i4.0
0x18d80  stloc.0
0x18d81  br       loc_18E63
0x18d86  ldarg.0
0x18d87  ldarg.1
0x18d88  ldloca.s 1
0x18d8a  call     instance bool [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver::TryResolveToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken&)
0x18d8f  brtrue.s loc_18DCB
0x18d91  ldarg.1
0x18d92  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause::get_CanCreateKey()
0x18d97  brfalse.s loc_18DB2
0x18d99  ldc.i4.0
0x18d9a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18d9f  ldc.i4.s 0xA
0x18da1  ldstr    aTheKeyIdentifi_0// "The key identifier clause is embeded ke"...
0x18da6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18dab  ldc.i4.0
0x18dac  stloc.0
0x18dad  br       loc_18E63
0x18db2  ldc.i4.0
0x18db3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18db8  ldc.i4.s 0xA
0x18dba  ldstr    aTheKeyIdentifi_1// "The key identifier clause could not be "...
0x18dbf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18dc4  ldc.i4.0
0x18dc5  stloc.0
0x18dc6  br       loc_18E63
0x18dcb  ldloc.1
0x18dcc  brtrue.s loc_18DE4
0x18dce  ldc.i4.0
0x18dcf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18dd4  ldc.i4.s 0xA
0x18dd6  ldstr    aTokenValidatio// "Token validation succeeded but is null."
0x18ddb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18de0  ldc.i4.0
0x18de1  stloc.0
0x18de2  br.s     loc_18E63
0x18de4  ldloc.1
0x18de5  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x18dea  brtrue.s loc_18E02
0x18dec  ldc.i4.0
0x18ded  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18df2  ldc.i4.s 0xA
0x18df4  ldstr    aTokenValidatio_0// "Token validation succeeded but security"...
0x18df9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18dfe  ldc.i4.0
0x18dff  stloc.0
0x18e00  br.s     loc_18E63
0x18e02  ldloc.1
0x18e03  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x18e08  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Count()
0x18e0d  ldc.i4.1
0x18e0e  beq.s    loc_18E41
0x18e10  ldc.i4.0
0x18e11  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18e16  ldc.i4.s 0xA
0x18e18  ldstr    aTheKeyIdentifi_2// "The key identifier clause resolved toke"...
0x18e1d  ldc.i4.1
0x18e1e  newarr   [mscorlib]System.Object
0x18e23  stloc.2
0x18e24  ldloc.2
0x18e25  ldc.i4.0
0x18e26  ldloc.1
0x18e27  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x18e2c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Count()
0x18e31  box      [mscorlib]System.Int32
0x18e36  stelem.ref
0x18e37  ldloc.2
0x18e38  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x18e3d  ldc.i4.0
0x18e3e  stloc.0
0x18e3f  br.s     loc_18E63
0x18e41  ldc.i4.0
0x18e42  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x18e47  ldc.i4.s 0x64
0x18e49  ldstr    aTheKeyIdentifi_3// "The key identifier clause resulve succe"...
0x18e4e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18e53  ldarg.2
0x18e54  ldloc.1
0x18e55  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0x18e5a  ldc.i4.0
0x18e5b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Item(!!T0)
0x18e60  stind.ref
0x18e61  ldc.i4.1
0x18e62  stloc.0
0x18e63  ldloc.0
0x18e64  ret
```
