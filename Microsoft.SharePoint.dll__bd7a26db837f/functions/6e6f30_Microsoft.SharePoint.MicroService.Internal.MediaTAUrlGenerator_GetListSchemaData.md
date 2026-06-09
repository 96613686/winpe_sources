# Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::GetListSchemaData

- ea: `0x6e6f30`
- end: `0x6e72f8`
- name: `Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::GetListSchemaData`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3501f0`

## callees

- `0x5c3eb0`
- `0x6c9890`
- `0x6e5a60`
- `0x6e5a70`
- `0x6e6d80`
- `0x6e6f30`
- `0x6e7780`
- `0x6e8fc0`
- `0x6ea0b0`
- `0x790ee0`
- `0x792b20`
- `0x792cb0`
- `0x93d460`
- `0x93dae0`
- `0x958050`

## string_xrefs

- `0x6e7058`: `access_token`
- `0x6e7091`: `access_token`
- `0x6e70fb`: `access_token`
- `0x6e7143`: `access_token`
- `0x6e7295`: `videomanifest`
- `0x6e7013`: `{0}: Setting mediaTA drive hashed token for the Url {1}`
- `0x6e70b7`: `{0}: Setting mediaTA drive token for the Url {1}`
- `0x6e710a`: `prooftoken`
- `0x6e7152`: `prooftoken`
- `0x6e7170`: `.driveAccessToken`
- `0x6e7193`: `Adds Vroom version 2.1 drive URL and access token`
- `0x6e71a1`: `.driveAccessTokenV21`
- `0x6e71d6`: `ODWeb_AddMediaTAServiceHostUrlSecondary`
- `0x6e728b`: `.videoManifestUrl`

## pseudocode

```c

```

## disassembly

```asm
0x6e6f30  ldarg.0
0x6e6f31  brtrue.s loc_6E6F3E
0x6e6f33  ldstr    aSpweb// "spWeb"
0x6e6f38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6e6f3d  throw
0x6e6f3e  ldarg.1
0x6e6f3f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e6f44  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e6f49  brfalse.s loc_6E6F56
0x6e6f4b  ldstr    aSiteid// "siteId"
0x6e6f50  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6e6f55  throw
0x6e6f56  ldarg.2
0x6e6f57  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e6f5c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e6f61  brfalse.s loc_6E6F6E
0x6e6f63  ldstr    aListid_4// "listId"
0x6e6f68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6e6f6d  throw
0x6e6f6e  ldarg.3
0x6e6f6f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e6f74  brfalse.s loc_6E6F81
0x6e6f76  ldstr    aSpserverhostur// "spServerHostUrl"
0x6e6f7b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6e6f80  throw
0x6e6f81  ldarg.0
0x6e6f82  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPWeb::get_ID()
0x6e6f87  stloc.0
0x6e6f88  ldarg.3
0x6e6f89  ldarg.1
0x6e6f8a  ldloc.0
0x6e6f8b  ldarg.2
0x6e6f8c  ldloca.s 0x12
0x6e6f8e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6e6f94  ldloc.s  0x12
0x6e6f96  ldc.i4.0
0x6e6f97  call     string Microsoft.SharePoint.Utilities.FileServiceHelper::GenerateFileAccessUrl(string spHostUrl, valuetype [mscorlib]System.Guid siteId, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> uniqueItemId, [opt] bool version21)
0x6e6f9c  stloc.1
0x6e6f9d  ldloc.1
0x6e6f9e  newobj   instance void [System]System.Uri::.ctor(string)
0x6e6fa3  stloc.2
0x6e6fa4  ldloc.2
0x6e6fa5  ldc.i4.1
0x6e6fa6  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x6e6fab  newobj   instance void [System]System.Uri::.ctor(string)
0x6e6fb0  stloc.3
0x6e6fb1  ldarg.3
0x6e6fb2  ldarg.1
0x6e6fb3  ldloc.0
0x6e6fb4  ldarg.2
0x6e6fb5  ldloca.s 0x13
0x6e6fb7  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6e6fbd  ldloc.s  0x13
0x6e6fbf  ldc.i4.1
0x6e6fc0  call     string Microsoft.SharePoint.Utilities.FileServiceHelper::GenerateFileAccessUrl(string spHostUrl, valuetype [mscorlib]System.Guid siteId, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> uniqueItemId, [opt] bool version21)
0x6e6fc5  stloc.s  5
0x6e6fc7  ldloc.s  5
0x6e6fc9  newobj   instance void [System]System.Uri::.ctor(string)
0x6e6fce  stloc.s  6
0x6e6fd0  ldloc.s  6
0x6e6fd2  ldc.i4.1
0x6e6fd3  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x6e6fd8  newobj   instance void [System]System.Uri::.ctor(string)
0x6e6fdd  stloc.s  7
0x6e6fdf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6e6fe4  stloc.s  0x14
0x6e6fe6  ldloca.s 0x14
0x6e6fe8  ldc.r8   6.0
0x6e6ff1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x6e6ff6  stloc.s  9
0x6e6ff8  ldc.i4   0x339B
0x6e6ffd  call     bool Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::IsExpFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x6e7002  brfalse  loc_6E70AB
0x6e7007  ldc.i4   0x16C32D1
0x6e700c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_MicroServices()
0x6e7011  ldc.i4.s 0x32
0x6e7013  ldstr    a0SettingMediat// "{0}: Setting mediaTA drive hashed token"...
0x6e7018  ldc.i4.2
0x6e7019  newarr   [mscorlib]System.Object
0x6e701e  stloc.s  0x15
0x6e7020  ldloc.s  0x15
0x6e7022  ldc.i4.0
0x6e7023  ldstr    aMediataurlgene// "MediaTAUrlGenerator:GetListSchemaData"
0x6e7028  stelem.ref
0x6e7029  ldloc.s  0x15
0x6e702b  ldc.i4.1
0x6e702c  ldloc.1
0x6e702d  stelem.ref
0x6e702e  ldloc.s  0x15
0x6e7030  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x6e7035  ldarg.0
0x6e7036  ldloc.2
0x6e7037  ldloc.s  9
0x6e7039  ldc.i4.1
0x6e703a  ldc.i4.0
0x6e703b  ldc.i4.0
0x6e703c  call     string Microsoft.SharePoint.Utilities.ProofTokenUtility::GetHashedProofToken(class Microsoft.SharePoint.SPWeb signingWeb, class [System]System.Uri targetUri, valuetype [mscorlib]System.DateTime expirationDateTime, [opt] bool bypassWebUrlValidation, [opt] bool forSigningWebUser, [opt] bool readonlyProofToken)
0x6e7041  stloc.s  0xA
0x6e7043  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e7048  ldstr    a01_30// "{0}={1}"
0x6e704d  ldc.i4.2
0x6e704e  newarr   [mscorlib]System.Object
0x6e7053  stloc.s  0x16
0x6e7055  ldloc.s  0x16
0x6e7057  ldc.i4.0
0x6e7058  ldstr    aAccessToken// "access_token"
0x6e705d  stelem.ref
0x6e705e  ldloc.s  0x16
0x6e7060  ldc.i4.1
0x6e7061  ldloc.s  0xA
0x6e7063  stelem.ref
0x6e7064  ldloc.s  0x16
0x6e7066  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e706b  stloc.s  4
0x6e706d  ldarg.0
0x6e706e  ldloc.s  6
0x6e7070  ldloc.s  9
0x6e7072  ldc.i4.1
0x6e7073  ldc.i4.0
0x6e7074  ldc.i4.0
0x6e7075  call     string Microsoft.SharePoint.Utilities.ProofTokenUtility::GetHashedProofToken(class Microsoft.SharePoint.SPWeb signingWeb, class [System]System.Uri targetUri, valuetype [mscorlib]System.DateTime expirationDateTime, [opt] bool bypassWebUrlValidation, [opt] bool forSigningWebUser, [opt] bool readonlyProofToken)
0x6e707a  stloc.s  0xB
0x6e707c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e7081  ldstr    a01_30// "{0}={1}"
0x6e7086  ldc.i4.2
0x6e7087  newarr   [mscorlib]System.Object
0x6e708c  stloc.s  0x17
0x6e708e  ldloc.s  0x17
0x6e7090  ldc.i4.0
0x6e7091  ldstr    aAccessToken// "access_token"
0x6e7096  stelem.ref
0x6e7097  ldloc.s  0x17
0x6e7099  ldc.i4.1
0x6e709a  ldloc.s  0xB
0x6e709c  stelem.ref
0x6e709d  ldloc.s  0x17
0x6e709f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e70a4  stloc.s  8
0x6e70a6  br       loc_6E7167
0x6e70ab  ldc.i4   0x12E11C6
0x6e70b0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_MicroServices()
0x6e70b5  ldc.i4.s 0x64
0x6e70b7  ldstr    a0SettingMediat_0// "{0}: Setting mediaTA drive token for th"...
0x6e70bc  ldc.i4.2
0x6e70bd  newarr   [mscorlib]System.Object
0x6e70c2  stloc.s  0x18
0x6e70c4  ldloc.s  0x18
0x6e70c6  ldc.i4.0
0x6e70c7  ldstr    aMediataurlgene// "MediaTAUrlGenerator:GetListSchemaData"
0x6e70cc  stelem.ref
0x6e70cd  ldloc.s  0x18
0x6e70cf  ldc.i4.1
0x6e70d0  ldloc.1
0x6e70d1  stelem.ref
0x6e70d2  ldloc.s  0x18
0x6e70d4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x6e70d9  ldloc.2
0x6e70da  ldloc.3
0x6e70db  ldloc.s  9
0x6e70dd  ldloca.s 0xD
0x6e70df  ldloca.s 0xC
0x6e70e1  call     void Microsoft.SharePoint.Utilities.ProofTokenUtility::GetAccessProofToken(class [System]System.Uri spResourceUri, class [System]System.Uri rootUri, valuetype [mscorlib]System.DateTime expirationDateTime, [out] string& proofToken, [out] string& accessToken)
0x6e70e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e70eb  ldstr    a0123_6// "{0}={1}&{2}={3}"
0x6e70f0  ldc.i4.4
0x6e70f1  newarr   [mscorlib]System.Object
0x6e70f6  stloc.s  0x19
0x6e70f8  ldloc.s  0x19
0x6e70fa  ldc.i4.0
0x6e70fb  ldstr    aAccessToken// "access_token"
0x6e7100  stelem.ref
0x6e7101  ldloc.s  0x19
0x6e7103  ldc.i4.1
0x6e7104  ldloc.s  0xC
0x6e7106  stelem.ref
0x6e7107  ldloc.s  0x19
0x6e7109  ldc.i4.2
0x6e710a  ldstr    aProoftoken_0// "prooftoken"
0x6e710f  stelem.ref
0x6e7110  ldloc.s  0x19
0x6e7112  ldc.i4.3
0x6e7113  ldloc.s  0xD
0x6e7115  stelem.ref
0x6e7116  ldloc.s  0x19
0x6e7118  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e711d  stloc.s  4
0x6e711f  ldloc.s  6
0x6e7121  ldloc.s  7
0x6e7123  ldloc.s  9
0x6e7125  ldloca.s 0xF
0x6e7127  ldloca.s 0xE
0x6e7129  call     void Microsoft.SharePoint.Utilities.ProofTokenUtility::GetAccessProofToken(class [System]System.Uri spResourceUri, class [System]System.Uri rootUri, valuetype [mscorlib]System.DateTime expirationDateTime, [out] string& proofToken, [out] string& accessToken)
0x6e712e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e7133  ldstr    a0123_6// "{0}={1}&{2}={3}"
0x6e7138  ldc.i4.4
0x6e7139  newarr   [mscorlib]System.Object
0x6e713e  stloc.s  0x1A
0x6e7140  ldloc.s  0x1A
0x6e7142  ldc.i4.0
0x6e7143  ldstr    aAccessToken// "access_token"
0x6e7148  stelem.ref
0x6e7149  ldloc.s  0x1A
0x6e714b  ldc.i4.1
0x6e714c  ldloc.s  0xE
0x6e714e  stelem.ref
0x6e714f  ldloc.s  0x1A
0x6e7151  ldc.i4.2
0x6e7152  ldstr    aProoftoken_0// "prooftoken"
0x6e7157  stelem.ref
0x6e7158  ldloc.s  0x1A
0x6e715a  ldc.i4.3
0x6e715b  ldloc.s  0xF
0x6e715d  stelem.ref
0x6e715e  ldloc.s  0x1A
0x6e7160  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e7165  stloc.s  8
0x6e7167  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6e716c  stloc.s  0x10
0x6e716e  ldloc.s  0x10
0x6e7170  ldstr    aDriveaccesstok_1// ".driveAccessToken"
0x6e7175  ldloc.s  4
0x6e7177  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e717c  ldloc.s  0x10
0x6e717e  ldstr    aDriveurl// ".driveUrl"
0x6e7183  ldloc.1
0x6e7184  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e7189  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::KillSwitchId_Version21DriveUrls
0x6e718e  ldstr    a05112017// "05/11/2017"
0x6e7193  ldstr    aAddsVroomVersi// "Adds Vroom version 2.1 drive URL and ac"...
0x6e7198  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x6e719d  brtrue.s loc_6E71BB
0x6e719f  ldloc.s  0x10
0x6e71a1  ldstr    aDriveaccesstok_2// ".driveAccessTokenV21"
0x6e71a6  ldloc.s  8
0x6e71a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e71ad  ldloc.s  0x10
0x6e71af  ldstr    aDriveurlv21// ".driveUrlV21"
0x6e71b4  ldloc.s  5
0x6e71b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e71bb  ldloc.s  0x10
0x6e71bd  ldstr    aMediabaseurl_0// ".mediaBaseUrl"
0x6e71c2  call     string Microsoft.SharePoint.MicroService.Internal.MediaTAServiceManager::get_MediaTAServiceHostUrl()
0x6e71c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e71cc  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::KillSwitchId_AddMediaTAServiceUrlSecondary
0x6e71d1  ldstr    a11182017// "11/18/2017"
0x6e71d6  ldstr    aOdwebAddmediat// "ODWeb_AddMediaTAServiceHostUrlSecondary"
0x6e71db  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x6e71e0  brtrue.s loc_6E71F3
0x6e71e2  ldloc.s  0x10
0x6e71e4  ldstr    aMediabaseurlse// ".mediaBaseUrlSecondary"
0x6e71e9  call     string Microsoft.SharePoint.MicroService.Internal.MediaTAServiceManager::get_MediaTAServiceHostUrlSecondary()
0x6e71ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e71f3  ldloc.s  0x10
0x6e71f5  ldstr    aPushchannelbas// ".pushChannelBaseUrl"
0x6e71fa  call     string Microsoft.SharePoint.MicroService.PushChannelManager::get_ServiceHostUrl()
0x6e71ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e7204  ldloc.s  0x10
0x6e7206  ldstr    aCallerstack_0// ".callerStack"
0x6e720b  call     string Microsoft.SharePoint.MicroService.MicroServiceUtilities::GetCallerStack()
0x6e7210  dup
0x6e7211  brtrue.s loc_6E7219
0x6e7213  pop
0x6e7214  ldsfld   string [mscorlib]System.String::Empty
0x6e7219  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e721e  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Diagnostics.ULS::CorrelationGetVisibleID()
0x6e7223  stloc.s  0x11
0x6e7225  ldloc.s  0x10
0x6e7227  ldstr    aCorrelationid_5// ".correlationId"
0x6e722c  ldloc.s  0x11
0x6e722e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e7233  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e7238  brtrue.s loc_6E7241
0x6e723a  ldsfld   string [mscorlib]System.String::Empty
0x6e723f  br.s     loc_6E724E
0x6e7241  ldloca.s 0x11
0x6e7243  constrained. [mscorlib]System.Guid
0x6e7249  callvirt instance string [mscorlib]System.Object::ToString()
0x6e724e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e7253  ldloc.s  0x10
0x6e7255  ldstr    aTransformurl// ".transformUrl"
0x6e725a  ldstr    aTransform// "transform"
0x6e725f  ldsfld   string [mscorlib]System.String::Empty
0x6e7264  call     string Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::GenerateMediaTAUrlTemplate(string action, string method)
0x6e7269  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e726e  ldloc.s  0x10
0x6e7270  ldstr    aThumbnailurl_0// ".thumbnailUrl"
0x6e7275  ldstr    aTransform// "transform"
0x6e727a  ldstr    aThumbnail// "thumbnail"
0x6e727f  call     string Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::GenerateMediaTAUrlTemplate(string action, string method)
0x6e7284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e7289  ldloc.s  0x10
0x6e728b  ldstr    aVideomanifestu_1// ".videoManifestUrl"
0x6e7290  ldstr    aTransform// "transform"
0x6e7295  ldstr    aVideomanifest// "videomanifest"
0x6e729a  call     string Microsoft.SharePoint.MicroService.Internal.MediaTAUrlGenerator::GenerateMediaTAUrlTemplate(string action, string method)
0x6e729f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e72a4  ldloc.s  0x10
0x6e72a6  ldstr    aPdfconversionu_1// ".pdfConversionUrl"
0x6e72ab  ldstr    aTransform// "transform"
0x6e72b0  ldstr    aPdf_0// "pdf"
  ... truncated ...
```
