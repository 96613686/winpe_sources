# Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateAudienceConditions

- ea: `0x1bca0`
- end: `0x1be3d`
- name: `Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateAudienceConditions`
- size: `413`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1be40`
- `0x1bef0`

## callees

- `0x8830`
- `0x8960`
- `0x1bc70`
- `0x1bca0`

## string_xrefs

- `0x1bd9d`: `Audience validation failed for saml token request. RequestUri: '{0}', TokenAudienceURIs: '{1}'.`
- `0x1bdd5`: `Audience validation succeeded for saml token request. RequestUri: '{0}'.`
- `0x1be01`: `Audience validator failed to initialize, swallowing the exception and failing validation for saml token.`
- `0x1be1d`: `Exeption validating audience, swallowing the exception and failing validation for saml token. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1bca0  ldc.i4.0
0x1bca1  stloc.0
0x1bca2  ldc.i4.1
0x1bca3  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x1bca8  stloc.1
0x1bca9  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1bcae  stloc.2
0x1bcaf  ldarg.0
0x1bcb0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System.IdentityModel]System.IdentityModel.Tokens.SamlCondition> [System.IdentityModel]System.IdentityModel.Tokens.SamlConditions::get_Conditions()
0x1bcb5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Tokens.SamlCondition>::GetEnumerator()
0x1bcba  stloc.s  8
0x1bcbc  br       loc_1BD47
0x1bcc1  ldloc.s  8
0x1bcc3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.IdentityModel]System.IdentityModel.Tokens.SamlCondition>::get_Current()
0x1bcc8  stloc.3
0x1bcc9  ldloc.3
0x1bcca  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SamlAudienceRestrictionCondition
0x1bccf  stloc.s  4
0x1bcd1  ldloc.s  4
0x1bcd3  brfalse.s loc_1BD47
0x1bcd5  ldloc.s  4
0x1bcd7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Tokens.SamlAudienceRestrictionCondition::get_Audiences()
0x1bcdc  brfalse.s loc_1BD47
0x1bcde  ldloc.1
0x1bcdf  ldloc.s  4
0x1bce1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Tokens.SamlAudienceRestrictionCondition::get_Audiences()
0x1bce6  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudiences(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri> audienceUris)
0x1bceb  brfalse.s loc_1BCF1
0x1bced  ldc.i4.1
0x1bcee  stloc.0
0x1bcef  br.s     loc_1BD53
0x1bcf1  ldloc.s  4
0x1bcf3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> [System.IdentityModel]System.IdentityModel.Tokens.SamlAudienceRestrictionCondition::get_Audiences()
0x1bcf8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0x1bcfd  stloc.s  9
0x1bcff  br.s     loc_1BD30
0x1bd01  ldloc.s  9
0x1bd03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x1bd08  stloc.s  5
0x1bd0a  ldloc.2
0x1bd0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bd10  ldstr    a0_1// "'{0}', "
0x1bd15  ldc.i4.1
0x1bd16  newarr   [mscorlib]System.Object
0x1bd1b  stloc.s  0xA
0x1bd1d  ldloc.s  0xA
0x1bd1f  ldc.i4.0
0x1bd20  ldloc.s  5
0x1bd22  callvirt instance string [System]System.Uri::get_OriginalString()
0x1bd27  stelem.ref
0x1bd28  ldloc.s  0xA
0x1bd2a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1bd2f  pop
0x1bd30  ldloc.s  9
0x1bd32  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bd37  brtrue.s loc_1BD01
0x1bd39  leave.s  loc_1BD47
0x1bd3b  ldloc.s  9
0x1bd3d  brfalse.s loc_1BD46
0x1bd3f  ldloc.s  9
0x1bd41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bd46  endfinally
0x1bd47  ldloc.s  8
0x1bd49  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bd4e  brtrue   loc_1BCC1
0x1bd53  leave.s  loc_1BD61
0x1bd55  ldloc.s  8
0x1bd57  brfalse.s loc_1BD60
0x1bd59  ldloc.s  8
0x1bd5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bd60  endfinally
0x1bd61  ldloc.0
0x1bd62  brtrue.s loc_1BDC6
0x1bd64  ldloc.2
0x1bd65  callvirt instance string [mscorlib]System.Object::ToString()
0x1bd6a  stloc.s  6
0x1bd6c  ldloc.s  6
0x1bd6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bd73  brtrue.s loc_1BD91
0x1bd75  ldloc.s  6
0x1bd77  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1bd7c  brfalse.s loc_1BD91
0x1bd7e  ldloc.s  6
0x1bd80  ldc.i4.0
0x1bd81  ldloc.s  6
0x1bd83  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1bd88  ldc.i4.1
0x1bd89  sub
0x1bd8a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1bd8f  stloc.s  6
0x1bd91  ldc.i4   0x15D612
0x1bd96  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1bd9b  ldc.i4.s 0xA
0x1bd9d  ldstr    aAudienceValida_5// "Audience validation failed for saml tok"...
0x1bda2  ldc.i4.2
0x1bda3  newarr   [mscorlib]System.Object
0x1bda8  stloc.s  0xB
0x1bdaa  ldloc.s  0xB
0x1bdac  ldc.i4.0
0x1bdad  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x1bdb2  stelem.ref
0x1bdb3  ldloc.s  0xB
0x1bdb5  ldc.i4.1
0x1bdb6  ldloc.2
0x1bdb7  callvirt instance string [mscorlib]System.Object::ToString()
0x1bdbc  stelem.ref
0x1bdbd  ldloc.s  0xB
0x1bdbf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1bdc4  br.s     loc_1BDF2
0x1bdc6  ldc.i4   0x15D613
0x1bdcb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1bdd0  ldc.i4   0xC8
0x1bdd5  ldstr    aAudienceValida_6// "Audience validation succeeded for saml "...
0x1bdda  ldc.i4.1
0x1bddb  newarr   [mscorlib]System.Object
0x1bde0  stloc.s  0xC
0x1bde2  ldloc.s  0xC
0x1bde4  ldc.i4.0
0x1bde5  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x1bdea  stelem.ref
0x1bdeb  ldloc.s  0xC
0x1bded  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1bdf2  leave.s  loc_1BE3B
0x1bdf4  pop
0x1bdf5  ldc.i4   0xCB2E0
0x1bdfa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1bdff  ldc.i4.s 0xA
0x1be01  ldstr    aAudienceValida_7// "Audience validator failed to initialize"...
0x1be06  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1be0b  ldc.i4.0
0x1be0c  stloc.0
0x1be0d  leave.s  loc_1BE3B
0x1be0f  stloc.s  7
0x1be11  ldc.i4   0x7CC190
0x1be16  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1be1b  ldc.i4.s 0xA
0x1be1d  ldstr    aExeptionValida// "Exeption validating audience, swallowin"...
0x1be22  ldc.i4.1
0x1be23  newarr   [mscorlib]System.Object
0x1be28  stloc.s  0xD
0x1be2a  ldloc.s  0xD
0x1be2c  ldc.i4.0
0x1be2d  ldloc.s  7
0x1be2f  stelem.ref
0x1be30  ldloc.s  0xD
0x1be32  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1be37  ldc.i4.0
0x1be38  stloc.0
0x1be39  leave.s  loc_1BE3B
0x1be3b  ldloc.0
0x1be3c  ret
```
