# Microsoft.SharePoint.Utilities.SPWOPIHost::GetAppPlusUserTokenForWopi

- ea: `0x7d7b60`
- end: `0x7d80df`
- name: `Microsoft.SharePoint.Utilities.SPWOPIHost::GetAppPlusUserTokenForWopi`
- size: `1407`
- prototype: ``
- caller_count: `3`
- callee_count: `48`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x7d7b50`
- `0x7dab20`
- `0x7dac20`

## callees

- `0x1a6fd0`
- `0x1b7de0`
- `0x26bdd0`
- `0x26f690`
- `0x2b5c50`
- `0x2b5dc0`
- `0x4a2700`
- `0x4a3310`
- `0x4cd8e0`
- `0x50c4d0`
- `0x50d810`
- `0x50d860`
- `0x50db50`
- `0x50e4f0`
- `0x594c60`
- `0x5966c0`
- `0x596780`
- `0x5c10e0`
- `0x5c24f0`
- `0x678580`
- `0x6785e0`
- `0x6c9890`
- `0x6f6140`
- `0x7d71b0`
- `0x7d71d0`
- `0x7d71e0`
- `0x7d7230`
- `0x7d7240`
- `0x7d7250`
- `0x7d7260`
- `0x7d7270`
- `0x7d7280`
- `0x7d72d0`
- `0x7d72e0`
- `0x7d72f0`
- `0x7d79f0`
- `0x7d7a60`
- `0x7d7b60`
- `0x7d82c0`
- `0x7d8410`
- `0x7d85b0`
- `0x7dcc30`
- `0x7ddab0`
- `0x7ddaf0`
- `0x7e1b70`
- `0x93dab0`
- `0x93dae0`
- `0x957b10`

## string_xrefs

- `0x7d7b98`: `OldExtensionForWebEmbed feature is enabled`
- `0x7d7bb7`: `NoAuth tokens are not supported for this file {0}`
- `0x7d7bd5`: `NoAuth tokens are not supported for this file.`
- `0x7d7bf4`: `NoAuth tokens are not supported for this filetype {0}`
- `0x7d7c12`: `NoAuth tokens are not supported for this filetype.`
- `0x7d7c3c`: `GetNoAuthTokenForWopi can only be called when there is a valid app context {0}`
- `0x7d7c5a`: `GetNoAuthTokenForWopi can only be called when there is a valid app context`
- `0x7d7c80`: `No read permissions for document: {0}`
- `0x7d7d48`: `tid claim not present in incoming evosts token`
- `0x7d7d52`: `tid claim not present in incoming evosts token`
- `0x7d7d76`: `wopi_ap claim not present in incoming evosts token`
- `0x7d7d80`: `wopi_ap claim not present in incoming evosts token`
- `0x7d7e52`: `The fileId of the incoming preauth token does not match the file id of the requested token's file: {0}, {1}`
- `0x7d7f13`: `The tid of the incoming preauth token does not match the current tenancy: {0} fileId: {1}`
- `0x7d7f73`: `Preauth tokens are only supported for wopi  [embed]edit and [embed]view actions.  Action requested: {0}`
- `0x7d7fbf`: `WopiAction.[Embed]Edit requested but authed app+user has no write permissions for document: {0}`
- `0x7d7ff6`: `Preauth tokens are only supported for wopi edit and view actions.  Action requested: {0}`
- `0x7d8037`: `WopiAction.Edit requested but authed app+user has no write permissions for document: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7d7b60  ldarg.3
0x7d7b61  ldc.i4.0
0x7d7b62  conv.i8
0x7d7b63  stind.i8
0x7d7b64  ldarg.0
0x7d7b65  brtrue.s loc_7D7B72
0x7d7b67  ldstr    aFile_0// "file"
0x7d7b6c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7d7b71  throw
0x7d7b72  ldarg.0
0x7d7b73  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7b78  brtrue.s loc_7D7B80
0x7d7b7a  ldsfld   string [mscorlib]System.String::Empty
0x7d7b7f  ret
0x7d7b80  ldc.i4   0x2A1A
0x7d7b85  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x7d7b8a  brfalse.s loc_7D7BE0
0x7d7b8c  ldc.i4   0x12121A0
0x7d7b91  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7b96  ldc.i4.s 0x32
0x7d7b98  ldstr    aOldextensionfo// "OldExtensionForWebEmbed feature is enab"...
0x7d7b9d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7d7ba2  ldarg.0
0x7d7ba3  ldarg.2
0x7d7ba4  call     bool Microsoft.SharePoint.Utilities.SPWOPIHost::IsWOPIEnabled(class Microsoft.SharePoint.SPFile file, valuetype Microsoft.SharePoint.Utilities.SPWOPIAction spWopiAction)
0x7d7ba9  brtrue.s loc_7D7C1D
0x7d7bab  ldc.i4   0x12121A1
0x7d7bb0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7bb5  ldc.i4.s 0x14
0x7d7bb7  ldstr    aNoauthTokensAr_0// "NoAuth tokens are not supported for thi"...
0x7d7bbc  ldc.i4.1
0x7d7bbd  newarr   [mscorlib]System.Object
0x7d7bc2  stloc.s  9
0x7d7bc4  ldloc.s  9
0x7d7bc6  ldc.i4.0
0x7d7bc7  ldarg.0
0x7d7bc8  callvirt instance string Microsoft.SharePoint.SPFile::get_Url()
0x7d7bcd  stelem.ref
0x7d7bce  ldloc.s  9
0x7d7bd0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7bd5  ldstr    aNoauthTokensAr_1// "NoAuth tokens are not supported for thi"...
0x7d7bda  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7d7bdf  throw
0x7d7be0  ldarg.0
0x7d7be1  call     bool Microsoft.SharePoint.Utilities.SPWOPIHost::FileSupportsNoAuthEmbed(class Microsoft.SharePoint.SPFile file)
0x7d7be6  brtrue.s loc_7D7C1D
0x7d7be8  ldc.i4   0x1001851
0x7d7bed  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7bf2  ldc.i4.s 0x14
0x7d7bf4  ldstr    aNoauthTokensAr_2// "NoAuth tokens are not supported for thi"...
0x7d7bf9  ldc.i4.1
0x7d7bfa  newarr   [mscorlib]System.Object
0x7d7bff  stloc.s  0xA
0x7d7c01  ldloc.s  0xA
0x7d7c03  ldc.i4.0
0x7d7c04  ldarg.0
0x7d7c05  callvirt instance string Microsoft.SharePoint.SPFile::get_Url()
0x7d7c0a  stelem.ref
0x7d7c0b  ldloc.s  0xA
0x7d7c0d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7c12  ldstr    aNoauthTokensAr_3// "NoAuth tokens are not supported for thi"...
0x7d7c17  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7d7c1c  throw
0x7d7c1d  call     class Microsoft.SharePoint.SPAppRequestContext Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x7d7c22  brfalse.s loc_7D7C30
0x7d7c24  call     class Microsoft.SharePoint.SPAppRequestContext Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x7d7c29  callvirt instance string Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0x7d7c2e  brtrue.s loc_7D7C65
0x7d7c30  ldc.i4   0x1001852
0x7d7c35  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7c3a  ldc.i4.s 0x14
0x7d7c3c  ldstr    aGetnoauthtoken// "GetNoAuthTokenForWopi can only be calle"...
0x7d7c41  ldc.i4.1
0x7d7c42  newarr   [mscorlib]System.Object
0x7d7c47  stloc.s  0xB
0x7d7c49  ldloc.s  0xB
0x7d7c4b  ldc.i4.0
0x7d7c4c  ldarg.0
0x7d7c4d  callvirt instance string Microsoft.SharePoint.SPFile::get_Url()
0x7d7c52  stelem.ref
0x7d7c53  ldloc.s  0xB
0x7d7c55  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7c5a  ldstr    aGetnoauthtoken_0// "GetNoAuthTokenForWopi can only be calle"...
0x7d7c5f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x7d7c64  throw
0x7d7c65  ldarg.0
0x7d7c66  callvirt instance valuetype Microsoft.SharePoint.SPBasePermissions Microsoft.SharePoint.SPFile::get_EffectiveRawPermissions()
0x7d7c6b  stloc.0
0x7d7c6c  ldloc.0
0x7d7c6d  call     bool Microsoft.SharePoint.Utilities.SPWOPIHost::PermsValidForRead(valuetype Microsoft.SharePoint.SPBasePermissions perms)
0x7d7c72  brtrue.s loc_7D7CA4
0x7d7c74  ldc.i4   0x1001853
0x7d7c79  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7c7e  ldc.i4.s 0x32
0x7d7c80  ldstr    aNoReadPermissi// "No read permissions for document: {0}"
0x7d7c85  ldc.i4.1
0x7d7c86  newarr   [mscorlib]System.Object
0x7d7c8b  stloc.s  0xC
0x7d7c8d  ldloc.s  0xC
0x7d7c8f  ldc.i4.0
0x7d7c90  ldarg.0
0x7d7c91  callvirt instance string Microsoft.SharePoint.SPFile::get_Url()
0x7d7c96  stelem.ref
0x7d7c97  ldloc.s  0xC
0x7d7c99  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7c9e  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor()
0x7d7ca3  throw
0x7d7ca4  newobj   instance void Microsoft.SharePoint.Utilities.WopiTokenContext::.ctor()
0x7d7ca9  stloc.1
0x7d7caa  ldarg.0
0x7d7cab  callvirt instance string Microsoft.SharePoint.SPFile::get_Name()
0x7d7cb0  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x7d7cb5  stloc.2
0x7d7cb6  ldloc.1
0x7d7cb7  call     class Microsoft.SharePoint.Administration.SPFileUrlRedirectManager Microsoft.SharePoint.Administration.SPFileUrlRedirectManager::get_Local()
0x7d7cbc  ldloc.2
0x7d7cbd  call     string Microsoft.Office.OpenWebApplication.WopiOM::FixupExtension(string ext)
0x7d7cc2  callvirt instance string Microsoft.SharePoint.Administration.SPFileUrlRedirectManager::GetProofKeyIdForFile(string fileExtension)
0x7d7cc7  callvirt instance void Microsoft.SharePoint.Utilities.WopiTokenContext::set_ProofKeyId(string value)
0x7d7ccc  ldloc.1
0x7d7ccd  ldarg.0
0x7d7cce  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7cd3  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7d7cd8  callvirt instance valuetype Microsoft.SharePoint.Administration.SPUrlZone Microsoft.SharePoint.SPSite::get_Zone()
0x7d7cdd  callvirt instance void Microsoft.SharePoint.Utilities.WopiTokenContext::set_Zone(valuetype Microsoft.SharePoint.Administration.SPUrlZone value)
0x7d7ce2  ldloc.1
0x7d7ce3  ldloc.0
0x7d7ce4  call     bool Microsoft.SharePoint.Utilities.SPWOPIHost::PermsValidForWrite(valuetype Microsoft.SharePoint.SPBasePermissions perms)
0x7d7ce9  callvirt instance void Microsoft.SharePoint.Utilities.WopiTokenContext::set_HasEditLicense(bool value)
0x7d7cee  ldloc.1
0x7d7cef  ldnull
0x7d7cf0  callvirt instance void Microsoft.SharePoint.Utilities.WopiTokenContext::set_Restriction(string value)
0x7d7cf5  ldloc.1
0x7d7cf6  call     class Microsoft.SharePoint.SPAppRequestContext Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x7d7cfb  callvirt instance string Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0x7d7d00  callvirt instance void Microsoft.SharePoint.Utilities.WopiTokenContext::set_ApplicationId(string value)
0x7d7d05  call     T0x2B000451
0x7d7d0a  stloc.3
0x7d7d0b  ldloc.3
0x7d7d0c  brtrue.s loc_7D7D2F
0x7d7d0e  ldc.i4   0x1001854
0x7d7d13  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7d18  ldc.i4.s 0xA
0x7d7d1a  ldstr    aNoSpsharedrequ// "No SPSharedRequestContext set."
0x7d7d1f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7d7d24  ldstr    aNoSpsharedrequ// "No SPSharedRequestContext set."
0x7d7d29  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x7d7d2e  throw
0x7d7d2f  ldloc.3
0x7d7d30  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x7d7d35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d7d3a  brfalse.s loc_7D7D5D
0x7d7d3c  ldc.i4   0x1001855
0x7d7d41  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7d46  ldc.i4.s 0xA
0x7d7d48  ldstr    aTidClaimNotPre// "tid claim not present in incoming evost"...
0x7d7d4d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7d7d52  ldstr    aTidClaimNotPre// "tid claim not present in incoming evost"...
0x7d7d57  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x7d7d5c  throw
0x7d7d5d  ldloc.3
0x7d7d5e  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x7d7d63  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d7d68  brfalse.s loc_7D7D8B
0x7d7d6a  ldc.i4   0x1001856
0x7d7d6f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7d74  ldc.i4.s 0xA
0x7d7d76  ldstr    aWopiApClaimNot// "wopi_ap claim not present in incoming e"...
0x7d7d7b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7d7d80  ldstr    aWopiApClaimNot// "wopi_ap claim not present in incoming e"...
0x7d7d85  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x7d7d8a  throw
0x7d7d8b  ldloc.3
0x7d7d8c  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x7d7d91  ldloca.s 4
0x7d7d93  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x7d7d98  brtrue.s loc_7D7DDE
0x7d7d9a  ldc.i4   0x1001857
0x7d7d9f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7da4  ldc.i4.s 0xA
0x7d7da6  ldstr    aTidClaimIsNotA// "tid claim is not a well-formed guid: {0"...
0x7d7dab  ldc.i4.1
0x7d7dac  newarr   [mscorlib]System.Object
0x7d7db1  stloc.s  0xD
0x7d7db3  ldloc.s  0xD
0x7d7db5  ldc.i4.0
0x7d7db6  ldloc.3
0x7d7db7  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x7d7dbc  brfalse.s loc_7D7DC6
0x7d7dbe  ldloc.3
0x7d7dbf  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x7d7dc4  br.s     loc_7D7DCB
0x7d7dc6  ldstr    aNull_2// "null"
0x7d7dcb  stelem.ref
0x7d7dcc  ldloc.s  0xD
0x7d7dce  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7dd3  ldstr    aTidClaimIsNotA_0// "tid claim is not a well-formed guid"
0x7d7dd8  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x7d7ddd  throw
0x7d7dde  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x7d7de3  ldc.i4   0x2AFB
0x7d7de8  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x7d7ded  brfalse  loc_7D805B
0x7d7df2  call     bool Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiRequest()
0x7d7df7  brfalse  loc_7D805B
0x7d7dfc  ldc.i4   0x181A7DF
0x7d7e01  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7e06  ldc.i4.s 0x32
0x7d7e08  ldstr    aDoingAdditiona// "Doing additional PreAuthWopiChecks"
0x7d7e0d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x7d7e12  ldloc.3
0x7d7e13  ldfld    string Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppCtxClaim
0x7d7e18  call     class Microsoft.SharePoint.Utilities.WopiTokenContext Microsoft.SharePoint.Utilities.SPWOPIHost::ParseApplicationContext(string applicationContext)
0x7d7e1d  stloc.s  5
0x7d7e1f  ldarg.0
0x7d7e20  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPFile::get_UniqueId()
0x7d7e25  stloc.s  0xE
0x7d7e27  ldloca.s 0xE
0x7d7e29  ldstr    aN// "N"
0x7d7e2e  call     instance string [mscorlib]System.Guid::ToString(string)
0x7d7e33  stloc.s  6
0x7d7e35  ldloc.s  6
0x7d7e37  ldloc.s  5
0x7d7e39  callvirt instance string Microsoft.SharePoint.Utilities.WopiTokenContext::get_ItemUniqueId()
0x7d7e3e  ldc.i4.5
0x7d7e3f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7d7e44  brtrue.s loc_7D7E7D
0x7d7e46  ldc.i4   0x181A7E0
0x7d7e4b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7e50  ldc.i4.s 0x32
0x7d7e52  ldstr    aTheFileidOfThe// "The fileId of the incoming preauth toke"...
0x7d7e57  ldc.i4.2
0x7d7e58  newarr   [mscorlib]System.Object
0x7d7e5d  stloc.s  0xF
0x7d7e5f  ldloc.s  0xF
0x7d7e61  ldc.i4.0
0x7d7e62  ldloc.s  5
0x7d7e64  callvirt instance string Microsoft.SharePoint.Utilities.WopiTokenContext::get_ItemUniqueId()
0x7d7e69  stelem.ref
0x7d7e6a  ldloc.s  0xF
0x7d7e6c  ldc.i4.1
0x7d7e6d  ldloc.s  6
0x7d7e6f  stelem.ref
0x7d7e70  ldloc.s  0xF
0x7d7e72  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7d7e77  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor()
0x7d7e7c  throw
0x7d7e7d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPWOPIHost::DoNotCheckTenantIdKillSwitch
0x7d7e82  ldstr    a3302018// "3/30/2018"
0x7d7e87  ldstr    aDonotchecktena// "DoNotCheckTenantIdKillSwitch"
0x7d7e8c  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x7d7e91  brfalse  loc_7D7F3E
0x7d7e96  ldarg.0
0x7d7e97  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7e9c  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7d7ea1  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x7d7ea6  brfalse.s loc_7D7F07
0x7d7ea8  ldarg.0
0x7d7ea9  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7eae  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7d7eb3  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x7d7eb8  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x7d7ebd  ldnull
0x7d7ebe  call     bool Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Equality(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier siteSubscriptionIdentifierA, class Microsoft.SharePoint.SPSiteSubscriptionIdentifier siteSubscriptionIdentifierB)
0x7d7ec3  brtrue.s loc_7D7F07
0x7d7ec5  ldarg.0
0x7d7ec6  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7ecb  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7d7ed0  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x7d7ed5  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x7d7eda  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::get_Id()
0x7d7edf  pop
0x7d7ee0  ldarg.0
0x7d7ee1  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPFile::get_Web()
0x7d7ee6  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x7d7eeb  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x7d7ef0  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPSiteSubscription::get_Id()
0x7d7ef5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::get_Id()
0x7d7efa  stloc.s  0x10
0x7d7efc  ldloca.s 0x10
0x7d7efe  ldloc.s  4
0x7d7f00  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7d7f05  brtrue.s loc_7D7F3E
0x7d7f07  ldc.i4   0x181A7E1
0x7d7f0c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7d7f11  ldc.i4.s 0x32
0x7d7f13  ldstr    aTheTidOfTheInc// "The tid of the incoming preauth token d"...
0x7d7f18  ldc.i4.2
0x7d7f19  newarr   [mscorlib]System.Object
0x7d7f1e  stloc.s  0x11
0x7d7f20  ldloc.s  0x11
0x7d7f22  ldc.i4.0
0x7d7f23  ldloc.s  4
0x7d7f25  box      [mscorlib]System.Guid
0x7d7f2a  stelem.ref
0x7d7f2b  ldloc.s  0x11
0x7d7f2d  ldc.i4.1
0x7d7f2e  ldloc.s  6
0x7d7f30  stelem.ref
0x7d7f31  ldloc.s  0x11
  ... truncated ...
```
