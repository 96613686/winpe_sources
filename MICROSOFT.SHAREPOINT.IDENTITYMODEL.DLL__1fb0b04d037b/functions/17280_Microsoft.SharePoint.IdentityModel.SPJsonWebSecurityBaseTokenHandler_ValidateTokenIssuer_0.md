# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_0

- ea: `0x17280`
- end: `0x17372`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_0`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x17070`

## callees

- `0x169c0`
- `0x17280`
- `0x17380`
- `0x17440`

## string_xrefs

- `0x1728f`: `The issuerToken is null.`
- `0x17299`: `issuerToken`
- `0x17367`: `issuerToken`
- `0x172b8`: `The tokenIssuer is null or empty.`
- `0x172c2`: `tokenIssuer`
- `0x172ea`: `Validating json issuer token of type X509SecurityToken. TokenIssuerName: '{0}'.`
- `0x17318`: `Validating json issuer token of type BinarySecretSecurityToken. TokenIssuerName: '{0}'.`
- `0x17343`: `Cannot validate json token issuer as it's unrecognized type. TokenIssuerName: '{0}', IssuerTokenType: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x17280  ldarg.1
0x17281  brtrue.s loc_172A4
0x17283  ldc.i4   0x650400
0x17288  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1728d  ldc.i4.s 0xA
0x1728f  ldstr    aTheIssuertoken// "The issuerToken is null."
0x17294  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17299  ldstr    aIssuertoken// "issuerToken"
0x1729e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x172a3  throw
0x172a4  ldarg.2
0x172a5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x172aa  brfalse.s loc_172CD
0x172ac  ldc.i4   0x650401
0x172b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x172b6  ldc.i4.s 0xA
0x172b8  ldstr    aTheTokenissuer// "The tokenIssuer is null or empty."
0x172bd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x172c2  ldstr    aTokenissuer// "tokenIssuer"
0x172c7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x172cc  throw
0x172cd  ldarg.1
0x172ce  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken
0x172d3  stloc.0
0x172d4  ldarg.1
0x172d5  isinst   [System.IdentityModel]System.ServiceModel.Security.Tokens.BinarySecretSecurityToken
0x172da  stloc.1
0x172db  ldloc.0
0x172dc  brfalse.s loc_17309
0x172de  ldc.i4   0x35F7CF
0x172e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x172e8  ldc.i4.s 0x32
0x172ea  ldstr    aValidatingJson_2// "Validating json issuer token of type X5"...
0x172ef  ldc.i4.1
0x172f0  newarr   [mscorlib]System.Object
0x172f5  stloc.2
0x172f6  ldloc.2
0x172f7  ldc.i4.0
0x172f8  ldarg.2
0x172f9  stelem.ref
0x172fa  ldloc.2
0x172fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17300  ldarg.0
0x17301  ldloc.0
0x17302  ldarg.2
0x17303  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken signingKey, string tokenIssuer)
0x17308  ret
0x17309  ldloc.1
0x1730a  brfalse.s loc_17337
0x1730c  ldc.i4   0x35F7D0
0x17311  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17316  ldc.i4.s 0x32
0x17318  ldstr    aValidatingJson_3// "Validating json issuer token of type Bi"...
0x1731d  ldc.i4.1
0x1731e  newarr   [mscorlib]System.Object
0x17323  stloc.3
0x17324  ldloc.3
0x17325  ldc.i4.0
0x17326  ldarg.2
0x17327  stelem.ref
0x17328  ldloc.3
0x17329  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1732e  ldarg.0
0x1732f  ldloc.1
0x17330  ldarg.2
0x17331  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [System.IdentityModel]System.ServiceModel.Security.Tokens.BinarySecretSecurityToken symmetricSigningKey, string tokenIssuer)
0x17336  ret
0x17337  ldc.i4   0x35F7D1
0x1733c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17341  ldc.i4.s 0x14
0x17343  ldstr    aCannotValidate// "Cannot validate json token issuer as it"...
0x17348  ldc.i4.2
0x17349  newarr   [mscorlib]System.Object
0x1734e  stloc.s  4
0x17350  ldloc.s  4
0x17352  ldc.i4.0
0x17353  ldarg.2
0x17354  stelem.ref
0x17355  ldloc.s  4
0x17357  ldc.i4.1
0x17358  ldarg.1
0x17359  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1735e  stelem.ref
0x1735f  ldloc.s  4
0x17361  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17366  ldnull
0x17367  ldstr    aIssuertoken// "issuerToken"
0x1736c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x17371  throw
```
