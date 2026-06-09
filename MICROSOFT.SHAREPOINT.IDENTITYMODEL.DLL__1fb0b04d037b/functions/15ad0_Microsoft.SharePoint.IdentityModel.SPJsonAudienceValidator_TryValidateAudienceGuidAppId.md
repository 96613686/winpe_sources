# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceGuidAppId

- ea: `0x15ad0`
- end: `0x15d57`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceGuidAppId`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15d60`

## callees

- `0x9840`
- `0x15ad0`

## string_xrefs

- `0x15b82`: `Audience Guid matches security token service default client identifier. Audience: '{0}', STS Default Identifier: '{1}', STS ID: '{2}'.`
- `0x15bd9`: `Audience Guid does not match security token service default client identifier. Audience: '{0}', STS Default Identifier: '{1}', STS ID: '{2}'.`
- `0x15c73`: `Audience Guid matches security token service scoped client identifier. Audience: '{0}', STS Identifier: '{1}', STS ID: '{2}'.`
- `0x15cd9`: `Audience Guid does not match security token service. Audience: '{0}', STS ID: '{1}'.`
- `0x15d1a`: `Exception validating audience Guid for security token service. Audience: '{0}', STS ID: '{1}', Exception: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x15ad0  ldarg.1
0x15ad1  brtrue.s loc_15AEB
0x15ad3  ldc.i4   0x809305
0x15ad8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15add  ldc.i4.s 0xA
0x15adf  ldstr    aTheValidationp// "The validationParams is null."
0x15ae4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15ae9  ldc.i4.0
0x15aea  ret
0x15aeb  ldarg.1
0x15aec  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15af1  stloc.s  4
0x15af3  ldloca.s 4
0x15af5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15afa  brtrue.s loc_15B14
0x15afc  ldc.i4   0x809306
0x15b01  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15b06  ldc.i4.s 0xA
0x15b08  ldstr    aTheValidationp_0// "The validationParams's GuidApplicationI"...
0x15b0d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15b12  ldc.i4.0
0x15b13  ret
0x15b14  ldnull
0x15b15  ldarg.2
0x15b16  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x15b1b  brfalse.s loc_15B35
0x15b1d  ldc.i4   0x809307
0x15b22  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15b27  ldc.i4.s 0xA
0x15b29  ldstr    aTheStsIsNull// "The sts is null."
0x15b2e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15b33  ldc.i4.0
0x15b34  ret
0x15b35  ldc.i4.0
0x15b36  stloc.0
0x15b37  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15b3c  stloc.1
0x15b3d  ldarg.2
0x15b3e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_DefaultClientIdentifier()
0x15b43  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x15b48  brtrue.s loc_15BC5
0x15b4a  ldarg.2
0x15b4b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_DefaultClientIdentifier()
0x15b50  ldloca.s 1
0x15b52  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x15b57  brfalse.s loc_15BC5
0x15b59  ldarg.1
0x15b5a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15b5f  stloc.s  5
0x15b61  ldloca.s 5
0x15b63  ldloc.1
0x15b64  box      [mscorlib]System.Guid
0x15b69  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15b6f  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x15b74  brfalse.s loc_15BC5
0x15b76  ldc.i4   0x809308
0x15b7b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15b80  ldc.i4.s 0x32
0x15b82  ldstr    aAudienceGuidMa// "Audience Guid matches security token se"...
0x15b87  ldc.i4.3
0x15b88  newarr   [mscorlib]System.Object
0x15b8d  stloc.s  6
0x15b8f  ldloc.s  6
0x15b91  ldc.i4.0
0x15b92  ldarg.1
0x15b93  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15b98  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15b9d  stelem.ref
0x15b9e  ldloc.s  6
0x15ba0  ldc.i4.1
0x15ba1  ldarg.2
0x15ba2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_DefaultClientIdentifier()
0x15ba7  stelem.ref
0x15ba8  ldloc.s  6
0x15baa  ldc.i4.2
0x15bab  ldarg.2
0x15bac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x15bb1  box      [mscorlib]System.Guid
0x15bb6  stelem.ref
0x15bb7  ldloc.s  6
0x15bb9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15bbe  ldc.i4.1
0x15bbf  stloc.0
0x15bc0  br       loc_15D0B
0x15bc5  ldarg.2
0x15bc6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, string> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_ScopedClientIdentifier()
0x15bcb  brtrue.s loc_15C1C
0x15bcd  ldc.i4   0x809309
0x15bd2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15bd7  ldc.i4.s 0x32
0x15bd9  ldstr    aAudienceGuidDo// "Audience Guid does not match security t"...
0x15bde  ldc.i4.3
0x15bdf  newarr   [mscorlib]System.Object
0x15be4  stloc.s  7
0x15be6  ldloc.s  7
0x15be8  ldc.i4.0
0x15be9  ldarg.1
0x15bea  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15bef  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15bf4  stelem.ref
0x15bf5  ldloc.s  7
0x15bf7  ldc.i4.1
0x15bf8  ldarg.2
0x15bf9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_DefaultClientIdentifier()
0x15bfe  stelem.ref
0x15bff  ldloc.s  7
0x15c01  ldc.i4.2
0x15c02  ldarg.2
0x15c03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x15c08  box      [mscorlib]System.Guid
0x15c0d  stelem.ref
0x15c0e  ldloc.s  7
0x15c10  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15c15  ldc.i4.0
0x15c16  stloc.0
0x15c17  br       loc_15D0B
0x15c1c  ldarg.2
0x15c1d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, string> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_ScopedClientIdentifier()
0x15c22  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, string>::get_Values()
0x15c27  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<class [System]System.Uri, string>::GetEnumerator()
0x15c2c  stloc.s  8
0x15c2e  br.s     loc_15CAE
0x15c30  ldloca.s 8
0x15c32  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>::get_Current()
0x15c37  stloc.2
0x15c38  ldloc.2
0x15c39  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x15c3e  brtrue.s loc_15CAE
0x15c40  ldloc.2
0x15c41  ldloca.s 1
0x15c43  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x15c48  brfalse.s loc_15CAE
0x15c4a  ldarg.1
0x15c4b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15c50  stloc.s  9
0x15c52  ldloca.s 9
0x15c54  ldloc.1
0x15c55  box      [mscorlib]System.Guid
0x15c5a  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15c60  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x15c65  brfalse.s loc_15CAE
0x15c67  ldc.i4   0x80930A
0x15c6c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15c71  ldc.i4.s 0x32
0x15c73  ldstr    aAudienceGuidMa_0// "Audience Guid matches security token se"...
0x15c78  ldc.i4.3
0x15c79  newarr   [mscorlib]System.Object
0x15c7e  stloc.s  0xA
0x15c80  ldloc.s  0xA
0x15c82  ldc.i4.0
0x15c83  ldarg.1
0x15c84  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15c89  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15c8e  stelem.ref
0x15c8f  ldloc.s  0xA
0x15c91  ldc.i4.1
0x15c92  ldloc.2
0x15c93  stelem.ref
0x15c94  ldloc.s  0xA
0x15c96  ldc.i4.2
0x15c97  ldarg.2
0x15c98  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x15c9d  box      [mscorlib]System.Guid
0x15ca2  stelem.ref
0x15ca3  ldloc.s  0xA
0x15ca5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15caa  ldc.i4.1
0x15cab  stloc.0
0x15cac  br.s     loc_15CBA
0x15cae  ldloca.s 8
0x15cb0  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>::MoveNext()
0x15cb5  brtrue   loc_15C30
0x15cba  leave.s  loc_15CCA
0x15cbc  ldloca.s 8
0x15cbe  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, string>
0x15cc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15cc9  endfinally
0x15cca  ldloc.0
0x15ccb  brtrue.s loc_15D0B
0x15ccd  ldc.i4   0x80930B
0x15cd2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15cd7  ldc.i4.s 0x64
0x15cd9  ldstr    aAudienceGuidDo_0// "Audience Guid does not match security t"...
0x15cde  ldc.i4.2
0x15cdf  newarr   [mscorlib]System.Object
0x15ce4  stloc.s  0xB
0x15ce6  ldloc.s  0xB
0x15ce8  ldc.i4.0
0x15ce9  ldarg.1
0x15cea  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15cef  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15cf4  stelem.ref
0x15cf5  ldloc.s  0xB
0x15cf7  ldc.i4.1
0x15cf8  ldarg.2
0x15cf9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x15cfe  box      [mscorlib]System.Guid
0x15d03  stelem.ref
0x15d04  ldloc.s  0xB
0x15d06  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15d0b  leave.s  loc_15D55
0x15d0d  stloc.3
0x15d0e  ldc.i4   0x80930C
0x15d13  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15d18  ldc.i4.s 0xA
0x15d1a  ldstr    aExceptionValid// "Exception validating audience Guid for "...
0x15d1f  ldc.i4.3
0x15d20  newarr   [mscorlib]System.Object
0x15d25  stloc.s  0xC
0x15d27  ldloc.s  0xC
0x15d29  ldc.i4.0
0x15d2a  ldarg.1
0x15d2b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_GuidApplicationId()
0x15d30  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x15d35  stelem.ref
0x15d36  ldloc.s  0xC
0x15d38  ldc.i4.1
0x15d39  ldarg.2
0x15d3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x15d3f  box      [mscorlib]System.Guid
0x15d44  stelem.ref
0x15d45  ldloc.s  0xC
0x15d47  ldc.i4.2
0x15d48  ldloc.3
0x15d49  stelem.ref
0x15d4a  ldloc.s  0xC
0x15d4c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15d51  ldc.i4.0
0x15d52  stloc.0
0x15d53  leave.s  loc_15D55
0x15d55  ldloc.0
0x15d56  ret
```
