# Microsoft.SharePoint.Administration.Claims.SPClaimsAuthRoleProvider::GetTokenGroupsForUser

- ea: `0x717d20`
- end: `0x718069`
- name: `Microsoft.SharePoint.Administration.Claims.SPClaimsAuthRoleProvider::GetTokenGroupsForUser`
- size: `841`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x717360`
- `0xbdb9c0`

## callees

- `0x687c60`
- `0x697e90`
- `0x6982d0`
- `0x69af00`
- `0x69c6c0`
- `0x717d20`
- `0x93dab0`
- `0x93dae0`
- `0x9577b0`

## string_xrefs

- `0x717d8c`: `tokenGroups`
- `0x717d2f`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() null argument: principalContext`
- `0x717d53`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() null argument: entity`
- `0x717d77`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() null argument: result`
- `0x717d9e`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() attempting to retrieve UserPrinicpal from principalContext. User: {0}`
- `0x717dd9`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() Retrieve UserPrinicpal from principalContext for user {0}: Failure.`
- `0x717e08`: `SPCLaimsAuthRoleProvider.GetTokenGroupsForUser() Retrieve UserPrinicpal from principalContext for user {0}: Success.`
- `0x717e41`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() Retrieve DirectoryEntry from UserPrincipal for user {0}: Failure.`
- `0x717e70`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() Retrieve DirectoryEntry from UserPrincipal for user {0}: Success.`
- `0x717eaf`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() loaded {0} values for user {1}.`
- `0x717f29`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser: Unable to obtain GroupPrincipal object for group. SID: '{0}'.`
- `0x717f56`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser: Adding group '{0}' with SID '{1}'. `
- `0x717fb3`: `SPClaimsAuthRoleProvider.GetTokenGroupsForUser() Exception trying to obtain GroupPrincipal object for group SID {0}. Exception: {1}`
- `0x71804a`: `Exception encountered in GetTokenGroupsForUser(). Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x717d20  ldarg.0
0x717d21  brtrue.s loc_717D44
0x717d23  ldc.i4   0x754305
0x717d28  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717d2d  ldc.i4.s 0xA
0x717d2f  ldstr    aSpclaimsauthro_3// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717d34  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x717d39  ldstr    aPrincipalconte// "principalContext"
0x717d3e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x717d43  throw
0x717d44  ldarg.1
0x717d45  brtrue.s loc_717D68
0x717d47  ldc.i4   0x754306
0x717d4c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717d51  ldc.i4.s 0xA
0x717d53  ldstr    aSpclaimsauthro_4// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717d58  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x717d5d  ldstr    aEntity_0// "entity"
0x717d62  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x717d67  throw
0x717d68  ldarg.2
0x717d69  brtrue.s loc_717D8C
0x717d6b  ldc.i4   0x754307
0x717d70  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717d75  ldc.i4.s 0xA
0x717d77  ldstr    aSpclaimsauthro_5// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717d7c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x717d81  ldstr    aResult_0// "result"
0x717d86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x717d8b  throw
0x717d8c  ldstr    aTokengroups// "tokenGroups"
0x717d91  stloc.0
0x717d92  ldc.i4   0x754308
0x717d97  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717d9c  ldc.i4.s 0x64
0x717d9e  ldstr    aSpclaimsauthro_6// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717da3  ldc.i4.1
0x717da4  newarr   [mscorlib]System.Object
0x717da9  stloc.s  8
0x717dab  ldloc.s  8
0x717dad  ldc.i4.0
0x717dae  ldarg.1
0x717daf  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717db4  stelem.ref
0x717db5  ldloc.s  8
0x717db7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717dbc  ldarg.0
0x717dbd  ldc.i4.0
0x717dbe  ldarg.1
0x717dbf  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717dc4  call     class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal::FindByIdentity(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext, valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.IdentityType, string)
0x717dc9  stloc.1
0x717dca  ldloc.1
0x717dcb  brtrue.s loc_717DFC
0x717dcd  ldc.i4   0x754309
0x717dd2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717dd7  ldc.i4.s 0xA
0x717dd9  ldstr    aSpclaimsauthro_7// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717dde  ldc.i4.1
0x717ddf  newarr   [mscorlib]System.Object
0x717de4  stloc.s  9
0x717de6  ldloc.s  9
0x717de8  ldc.i4.0
0x717de9  ldarg.1
0x717dea  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717def  stelem.ref
0x717df0  ldloc.s  9
0x717df2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717df7  br       loc_717FFD
0x717dfc  ldc.i4   0x75430A
0x717e01  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717e06  ldc.i4.s 0x64
0x717e08  ldstr    aSpclaimsauthro_8// "SPCLaimsAuthRoleProvider.GetTokenGroups"...
0x717e0d  ldc.i4.1
0x717e0e  newarr   [mscorlib]System.Object
0x717e13  stloc.s  0xA
0x717e15  ldloc.s  0xA
0x717e17  ldc.i4.0
0x717e18  ldarg.1
0x717e19  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717e1e  stelem.ref
0x717e1f  ldloc.s  0xA
0x717e21  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717e26  ldloc.1
0x717e27  callvirt instance object [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::GetUnderlyingObject()
0x717e2c  isinst   [System.DirectoryServices]System.DirectoryServices.DirectoryEntry
0x717e31  stloc.2
0x717e32  ldloc.2
0x717e33  brtrue.s loc_717E64
0x717e35  ldc.i4   0x75430B
0x717e3a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717e3f  ldc.i4.s 0xA
0x717e41  ldstr    aSpclaimsauthro_9// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717e46  ldc.i4.1
0x717e47  newarr   [mscorlib]System.Object
0x717e4c  stloc.s  0xB
0x717e4e  ldloc.s  0xB
0x717e50  ldc.i4.0
0x717e51  ldarg.1
0x717e52  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717e57  stelem.ref
0x717e58  ldloc.s  0xB
0x717e5a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717e5f  br       loc_717FFD
0x717e64  ldc.i4   0x75430C
0x717e69  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717e6e  ldc.i4.s 0x64
0x717e70  ldstr    aSpclaimsauthro_10// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717e75  ldc.i4.1
0x717e76  newarr   [mscorlib]System.Object
0x717e7b  stloc.s  0xC
0x717e7d  ldloc.s  0xC
0x717e7f  ldc.i4.0
0x717e80  ldarg.1
0x717e81  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717e86  stelem.ref
0x717e87  ldloc.s  0xC
0x717e89  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717e8e  ldloc.2
0x717e8f  ldc.i4.1
0x717e90  newarr   [mscorlib]System.String
0x717e95  stloc.s  0xD
0x717e97  ldloc.s  0xD
0x717e99  ldc.i4.0
0x717e9a  ldloc.0
0x717e9b  stelem.ref
0x717e9c  ldloc.s  0xD
0x717e9e  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::RefreshCache(string[])
0x717ea3  ldc.i4   0x75430D
0x717ea8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717ead  ldc.i4.s 0x64
0x717eaf  ldstr    aSpclaimsauthro_11// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717eb4  ldc.i4.2
0x717eb5  newarr   [mscorlib]System.Object
0x717eba  stloc.s  0xE
0x717ebc  ldloc.s  0xE
0x717ebe  ldc.i4.0
0x717ebf  ldloc.0
0x717ec0  stelem.ref
0x717ec1  ldloc.s  0xE
0x717ec3  ldc.i4.1
0x717ec4  ldarg.1
0x717ec5  callvirt instance string Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x717eca  stelem.ref
0x717ecb  ldloc.s  0xE
0x717ecd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717ed2  ldloc.2
0x717ed3  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyCollection [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Properties()
0x717ed8  ldloc.0
0x717ed9  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection [System.DirectoryServices]System.DirectoryServices.PropertyCollection::get_Item(string)
0x717ede  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x717ee3  stloc.s  0xF
0x717ee5  br       loc_717FDA
0x717eea  ldloc.s  0xF
0x717eec  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x717ef1  castclass unsigned int8[]
0x717ef6  stloc.3
0x717ef7  ldloc.3
0x717ef8  ldc.i4.0
0x717ef9  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x717efe  stloc.s  4
0x717f00  ldloc.s  4
0x717f02  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x717f07  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x717f0c  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x717f11  stloc.s  5
0x717f13  ldloc.s  5
0x717f15  ldnull
0x717f16  call     bool [mscorlib]System.Security.Principal.IdentityReference::op_Equality(class [mscorlib]System.Security.Principal.IdentityReference, class [mscorlib]System.Security.Principal.IdentityReference)
0x717f1b  brfalse.s loc_717F4A
0x717f1d  ldc.i4   0x75430E
0x717f22  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717f27  ldc.i4.s 0xA
0x717f29  ldstr    aSpclaimsauthro_12// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717f2e  ldc.i4.1
0x717f2f  newarr   [mscorlib]System.Object
0x717f34  stloc.s  0x10
0x717f36  ldloc.s  0x10
0x717f38  ldc.i4.0
0x717f39  ldloc.s  4
0x717f3b  callvirt instance string [mscorlib]System.Object::ToString()
0x717f40  stelem.ref
0x717f41  ldloc.s  0x10
0x717f43  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717f48  br.s     loc_717FA3
0x717f4a  ldc.i4   0x75430F
0x717f4f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717f54  ldc.i4.s 0x64
0x717f56  ldstr    aSpclaimsauthro_13// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717f5b  ldc.i4.2
0x717f5c  newarr   [mscorlib]System.Object
0x717f61  stloc.s  0x11
0x717f63  ldloc.s  0x11
0x717f65  ldc.i4.0
0x717f66  ldloc.s  5
0x717f68  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x717f6d  stelem.ref
0x717f6e  ldloc.s  0x11
0x717f70  ldc.i4.1
0x717f71  ldloc.s  4
0x717f73  callvirt instance string [mscorlib]System.Object::ToString()
0x717f78  stelem.ref
0x717f79  ldloc.s  0x11
0x717f7b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717f80  ldarg.2
0x717f81  call     string Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_GroupSid()
0x717f86  ldloc.s  4
0x717f88  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x717f8d  call     string Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x717f92  ldc.i4.s 0x77
0x717f94  call     string Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::Format(valuetype Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType type)
0x717f99  call     string Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::EncodeClaimIntoFormsSuffix(string claimType, string claimValue, string claimValueType, string claimOriginalIssuer)
0x717f9e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x717fa3  leave.s  loc_717FDA
0x717fa5  stloc.s  6
0x717fa7  ldc.i4   0x754310
0x717fac  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x717fb1  ldc.i4.s 0xA
0x717fb3  ldstr    aSpclaimsauthro_14// "SPClaimsAuthRoleProvider.GetTokenGroups"...
0x717fb8  ldc.i4.2
0x717fb9  newarr   [mscorlib]System.Object
0x717fbe  stloc.s  0x12
0x717fc0  ldloc.s  0x12
0x717fc2  ldc.i4.0
0x717fc3  ldloc.s  4
0x717fc5  callvirt instance string [mscorlib]System.Object::ToString()
0x717fca  stelem.ref
0x717fcb  ldloc.s  0x12
0x717fcd  ldc.i4.1
0x717fce  ldloc.s  6
0x717fd0  stelem.ref
0x717fd1  ldloc.s  0x12
0x717fd3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x717fd8  leave.s  loc_717FDA
0x717fda  ldloc.s  0xF
0x717fdc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x717fe1  brtrue   loc_717EEA
0x717fe6  leave.s  loc_717FFD
0x717fe8  ldloc.s  0xF
0x717fea  isinst   [mscorlib]System.IDisposable
0x717fef  stloc.s  0x13
0x717ff1  ldloc.s  0x13
0x717ff3  brfalse.s loc_717FFC
0x717ff5  ldloc.s  0x13
0x717ff7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x717ffc  endfinally
0x717ffd  leave.s  loc_718009
0x717fff  ldloc.1
0x718000  brfalse.s loc_718008
0x718002  ldloc.1
0x718003  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x718008  endfinally
0x718009  leave.s  loc_718068
0x71800b  stloc.s  7
0x71800d  ldloc.s  7
0x71800f  isinst   [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.MultipleMatchesException
0x718014  brfalse.s loc_71803E
0x718016  ldc.i4   0x754311
0x71801b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x718020  ldc.i4.s 0x32
0x718022  ldstr    aEncounteredAMu// "Encountered a MultiplMatchesException w"...
0x718027  ldc.i4.1
0x718028  newarr   [mscorlib]System.Object
0x71802d  stloc.s  0x14
0x71802f  ldloc.s  0x14
0x718031  ldc.i4.0
0x718032  ldloc.s  7
0x718034  stelem.ref
0x718035  ldloc.s  0x14
0x718037  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x71803c  br.s     loc_718066
0x71803e  ldc.i4   0x754312
0x718043  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x718048  ldc.i4.s 0x32
0x71804a  ldstr    aExceptionEncou_8// "Exception encountered in GetTokenGroups"...
0x71804f  ldc.i4.1
0x718050  newarr   [mscorlib]System.Object
0x718055  stloc.s  0x15
0x718057  ldloc.s  0x15
0x718059  ldc.i4.0
0x71805a  ldloc.s  7
0x71805c  stelem.ref
0x71805d  ldloc.s  0x15
0x71805f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x718064  rethrow
0x718066  leave.s  loc_718068
0x718068  ret
```
