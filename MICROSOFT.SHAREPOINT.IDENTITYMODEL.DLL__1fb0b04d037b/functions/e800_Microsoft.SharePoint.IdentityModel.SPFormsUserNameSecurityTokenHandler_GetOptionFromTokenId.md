# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetOptionFromTokenId

- ea: `0xe800`
- end: `0xe971`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetOptionFromTokenId`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xe5f0`

## callees

- `0xd240`
- `0xe800`
- `0x2c520`

## string_xrefs

- `0xe80f`: `token`
- `0xe829`: `token.Id`
- `0xe880`: `Could not find the first separator in the token ID.`
- `0xe8b3`: `The first separator in the token ID ends the string.`
- `0xe8da`: `Could not find the second separator in the token ID.`
- `0xe90d`: `The second separator in the token ID ends the string.`

## pseudocode

```c

```

## disassembly

```asm
0xe800  ldc.i4   0x1192319
0xe805  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe80a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe80f  ldstr    aToken// "token"
0xe814  ldarg.0
0xe815  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe81a  ldc.i4   0x119231A
0xe81f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0xe824  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe829  ldstr    aTokenId// "token.Id"
0xe82e  ldarg.0
0xe82f  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe834  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0xe839  ldloca.s 0
0xe83b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe841  ldarg.0
0xe842  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe847  ldstr    asc_3C208// ":"
0xe84c  ldc.i4.5
0xe84d  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xe852  stloc.1
0xe853  ldarg.0
0xe854  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe859  ldstr    asc_3C208// ":"
0xe85e  ldloc.1
0xe85f  ldc.i4.1
0xe860  add
0xe861  ldc.i4.5
0xe862  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0xe867  stloc.2
0xe868  ldloc.1
0xe869  ldc.i4.m1
0xe86a  bne.un.s loc_E88F
0xe86c  ldloca.s 0
0xe86e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe874  ldc.i4   0x119231C
0xe879  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe87e  ldc.i4.s 0xA
0xe880  ldstr    aCouldNotFindTh// "Could not find the first separator in t"...
0xe885  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe88a  br       loc_E96F
0xe88f  ldloc.1
0xe890  ldarg.0
0xe891  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe896  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe89b  ldc.i4.1
0xe89c  sub
0xe89d  bne.un.s loc_E8C2
0xe89f  ldloca.s 0
0xe8a1  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe8a7  ldc.i4   0x119231D
0xe8ac  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe8b1  ldc.i4.s 0xA
0xe8b3  ldstr    aTheFirstSepara// "The first separator in the token ID end"...
0xe8b8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe8bd  br       loc_E96F
0xe8c2  ldloc.2
0xe8c3  ldc.i4.m1
0xe8c4  bne.un.s loc_E8E9
0xe8c6  ldloca.s 0
0xe8c8  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe8ce  ldc.i4   0x119231E
0xe8d3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe8d8  ldc.i4.s 0xA
0xe8da  ldstr    aCouldNotFindTh_0// "Could not find the second separator in "...
0xe8df  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe8e4  br       loc_E96F
0xe8e9  ldloc.2
0xe8ea  ldarg.0
0xe8eb  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe8f0  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe8f5  ldc.i4.1
0xe8f6  sub
0xe8f7  bne.un.s loc_E919
0xe8f9  ldloca.s 0
0xe8fb  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe901  ldc.i4   0x119231F
0xe906  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe90b  ldc.i4.s 0xA
0xe90d  ldstr    aTheSecondSepar// "The second separator in the token ID en"...
0xe912  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xe917  br.s     loc_E96F
0xe919  ldarg.0
0xe91a  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_Id()
0xe91f  ldloc.2
0xe920  ldc.i4.1
0xe921  add
0xe922  callvirt instance string [mscorlib]System.String::Substring(int32)
0xe927  stloc.3
0xe928  ldloc.3
0xe929  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe92e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xe933  stloc.s  4
0xe935  ldloc.s  4
0xe937  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>::.ctor(var<u1>)
0xe93c  stloc.0
0xe93d  leave.s  loc_E96F
0xe93f  pop
0xe940  ldc.i4   0x1192320
0xe945  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xe94a  ldc.i4.s 0xA
0xe94c  ldstr    aCouldNotConver// "Could not convert value into a forms au"...
0xe951  ldc.i4.1
0xe952  newarr   [mscorlib]System.Object
0xe957  stloc.s  5
0xe959  ldloc.s  5
0xe95b  ldc.i4.0
0xe95c  ldloc.3
0xe95d  stelem.ref
0xe95e  ldloc.s  5
0xe960  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xe965  ldloca.s 0
0xe967  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPFormsAuthenticationOption>
0xe96d  leave.s  loc_E96F
0xe96f  ldloc.0
0xe970  ret
```
