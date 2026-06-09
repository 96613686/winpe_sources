# Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::Create

- ea: `0xf7f0`
- end: `0xf88a`
- name: `Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::Create`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xf6a0`

## callees

- `0xf770`
- `0xf790`
- `0xf7b0`
- `0xf7d0`
- `0xf7e0`
- `0xf7f0`

## string_xrefs

- `0xf7f8`: `proofTokenValue`
- `0xf806`: `securityKey`
- `0xf82a`: `SPIdentityProofTokenManager: Expiry date is less than current time. Expiry:{0} CurrentDateTime:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xf7f0  ldarg.0
0xf7f1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xf7f6  brfalse.s loc_F803
0xf7f8  ldstr    aProoftokenvalu// "proofTokenValue"
0xf7fd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf802  throw
0xf803  ldarg.1
0xf804  brtrue.s loc_F811
0xf806  ldstr    aSecuritykey// "securityKey"
0xf80b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf810  throw
0xf811  ldarg.2
0xf812  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xf817  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xf81c  brfalse.s loc_F862
0xf81e  ldc.i4   0x114701A
0xf823  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xf828  ldc.i4.s 0x32
0xf82a  ldstr    aSpidentityproo_2// "SPIdentityProofTokenManager: Expiry dat"...
0xf82f  ldc.i4.2
0xf830  newarr   [mscorlib]System.Object
0xf835  stloc.1
0xf836  ldloc.1
0xf837  ldc.i4.0
0xf838  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xf83d  stloc.2
0xf83e  ldloca.s 2
0xf840  constrained. [mscorlib]System.DateTime
0xf846  callvirt instance string [mscorlib]System.Object::ToString()
0xf84b  stelem.ref
0xf84c  ldloc.1
0xf84d  ldc.i4.1
0xf84e  ldarga.s 2
0xf850  constrained. [mscorlib]System.DateTime
0xf856  callvirt instance string [mscorlib]System.Object::ToString()
0xf85b  stelem.ref
0xf85c  ldloc.1
0xf85d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf862  newobj   instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::.ctor()
0xf867  stloc.0
0xf868  ldloc.0
0xf869  ldarg.0
0xf86a  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::set_ProofTokenString(string value)
0xf86f  ldloc.0
0xf870  ldarg.1
0xf871  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::set_SecurityKey(class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey value)
0xf876  ldloc.0
0xf877  ldarg.2
0xf878  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::set_Expiry(valuetype [mscorlib]System.DateTime value)
0xf87d  ldloc.0
0xf87e  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::CorrelationGetVisibleID()
0xf883  callvirt instance void Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::set_IssuanceCorrelationId(valuetype [mscorlib]System.Guid value)
0xf888  ldloc.0
0xf889  ret
```
