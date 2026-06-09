# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTokenSignature

- ea: `0x17bc0`
- end: `0x17d32`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTokenSignature`
- size: `370`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5b40`
- `0x17bc0`
- `0x1d2c0`

## callees

- `0x169c0`
- `0x17bc0`

## string_xrefs

- `0x17bcf`: `The jwtToken is null.`
- `0x17bd9`: `jwtToken`
- `0x17bf8`: `SPJsonWebSecurityBaseTokenHandler: JsonWebSecurityToken doesn't have a signature.`
- `0x17c07`: `NullBootstrapToken`
- `0x17d1a`: `NullBootstrapToken`
- `0x17d0b`: `SPJsonWebSecurityBaseTokenHandler: BootstrapToken doesn't have a signature.`

## pseudocode

```c

```

## disassembly

```asm
0x17bc0  ldarg.0
0x17bc1  brtrue.s loc_17BE4
0x17bc3  ldc.i4   0x650409
0x17bc8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17bcd  ldc.i4.s 0xA
0x17bcf  ldstr    aTheJwttokenIsN// "The jwtToken is null."
0x17bd4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17bd9  ldstr    aJwttoken// "jwtToken"
0x17bde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17be3  throw
0x17be4  ldarg.0
0x17be5  callvirt instance bool [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_CanWriteSourceData()
0x17bea  brtrue.s loc_17C1D
0x17bec  ldc.i4   0x1C565A
0x17bf1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17bf6  ldc.i4.s 0xA
0x17bf8  ldstr    aSpjsonwebsecur_3// "SPJsonWebSecurityBaseTokenHandler: Json"...
0x17bfd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17c02  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17c07  ldstr    aNullbootstrapt// "NullBootstrapToken"
0x17c0c  ldc.i4.0
0x17c0d  newarr   [mscorlib]System.Object
0x17c12  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x17c17  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17c1c  throw
0x17c1d  ldarg.0
0x17c1e  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::WriteSourceData()
0x17c23  stloc.0
0x17c24  ldloc.0
0x17c25  ldloc.0
0x17c26  ldc.i4.s 0x2E
0x17c28  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x17c2d  ldc.i4.1
0x17c2e  add
0x17c2f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x17c34  stloc.1
0x17c35  ldloc.1
0x17c36  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x17c3b  brfalse  loc_17D30
0x17c40  ldarg.0
0x17c41  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17c46  brfalse  loc_17CFF
0x17c4b  ldarg.0
0x17c4c  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17c51  call     string Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetTokenSignature(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jwtToken)
0x17c56  stloc.1
0x17c57  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x17c5c  stloc.2
0x17c5d  ldloc.2
0x17c5e  ldarg.0
0x17c5f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x17c64  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17c69  pop
0x17c6a  ldloc.2
0x17c6b  ldc.i4.s 0x2C
0x17c6d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x17c72  pop
0x17c73  ldloc.2
0x17c74  ldarg.0
0x17c75  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x17c7a  stloc.s  4
0x17c7c  ldloca.s 4
0x17c7e  call     instance int64 [mscorlib]System.DateTime::ToFileTimeUtc()
0x17c83  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int64)
0x17c88  pop
0x17c89  ldloc.2
0x17c8a  ldc.i4.s 0x2C
0x17c8c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x17c91  pop
0x17c92  ldloc.2
0x17c93  ldarg.0
0x17c94  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x17c99  stloc.s  5
0x17c9b  ldloca.s 5
0x17c9d  call     instance int64 [mscorlib]System.DateTime::ToFileTimeUtc()
0x17ca2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int64)
0x17ca7  pop
0x17ca8  ldloc.2
0x17ca9  ldc.i4.s 0x2C
0x17cab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x17cb0  pop
0x17cb1  ldarg.0
0x17cb2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x17cb7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::GetEnumerator()
0x17cbc  stloc.s  6
0x17cbe  br.s     loc_17CDE
0x17cc0  ldloc.s  6
0x17cc2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::get_Current()
0x17cc7  stloc.3
0x17cc8  ldloc.2
0x17cc9  ldloc.3
0x17cca  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17ccf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17cd4  pop
0x17cd5  ldloc.2
0x17cd6  ldc.i4.s 0x2C
0x17cd8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x17cdd  pop
0x17cde  ldloc.s  6
0x17ce0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17ce5  brtrue.s loc_17CC0
0x17ce7  leave.s  loc_17CF5
0x17ce9  ldloc.s  6
0x17ceb  brfalse.s loc_17CF4
0x17ced  ldloc.s  6
0x17cef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17cf4  endfinally
0x17cf5  ldloc.2
0x17cf6  ldloc.1
0x17cf7  call     string [mscorlib]System.String::Concat(object, object)
0x17cfc  stloc.1
0x17cfd  ldloc.1
0x17cfe  ret
0x17cff  ldc.i4   0x1C565B
0x17d04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17d09  ldc.i4.s 0xA
0x17d0b  ldstr    aSpjsonwebsecur_4// "SPJsonWebSecurityBaseTokenHandler: Boot"...
0x17d10  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17d15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17d1a  ldstr    aNullbootstrapt// "NullBootstrapToken"
0x17d1f  ldc.i4.0
0x17d20  newarr   [mscorlib]System.Object
0x17d25  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x17d2a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x17d2f  throw
0x17d30  ldloc.1
0x17d31  ret
```
