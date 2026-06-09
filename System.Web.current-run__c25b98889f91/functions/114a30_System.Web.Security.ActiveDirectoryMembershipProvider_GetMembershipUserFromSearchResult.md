# System.Web.Security.ActiveDirectoryMembershipProvider::GetMembershipUserFromSearchResult

- ea: `0x114a30`
- end: `0x114d37`
- name: `System.Web.Security.ActiveDirectoryMembershipProvider::GetMembershipUserFromSearchResult`
- size: `775`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1142b0`
- `0x1144d0`

## callees

- `0x111740`
- `0x114a30`
- `0x1161d0`
- `0x116240`
- `0x116cc0`
- `0x116f30`

## string_xrefs

- `0x114ac5`: `comment`
- `0x114ada`: `comment`
- `0x114a43`: `objectSid`
- `0x114cd5`: `whenCreated`
- `0x114b2a`: `msDS-User-Account-Control-Computed`
- `0x114b37`: `msDS-User-Account-Control-Computed`
- `0x114bd9`: `msDS-User-Account-Control-Computed`

## pseudocode

```c

```

## disassembly

```asm
0x114a30  ldarg.1
0x114a31  ldarg.0
0x114a32  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapUsername
0x114a37  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114a3c  castclass [mscorlib]System.String
0x114a41  stloc.0
0x114a42  ldarg.1
0x114a43  ldstr    aObjectsid_1// "objectSid"
0x114a48  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114a4d  castclass unsigned int8[]
0x114a52  stloc.1
0x114a53  ldloc.1
0x114a54  ldc.i4.0
0x114a55  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x114a5a  stloc.2
0x114a5b  ldarg.1
0x114a5c  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114a61  ldarg.0
0x114a62  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapEmail
0x114a67  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114a6c  brtrue.s loc_114A71
0x114a6e  ldnull
0x114a6f  br.s     loc_114A8D
0x114a71  ldarg.1
0x114a72  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114a77  ldarg.0
0x114a78  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapEmail
0x114a7d  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x114a82  ldc.i4.0
0x114a83  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x114a88  castclass [mscorlib]System.String
0x114a8d  stloc.3
0x114a8e  ldnull
0x114a8f  stloc.s  4
0x114a91  ldarg.0
0x114a92  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x114a97  brfalse.s loc_114ABF
0x114a99  ldarg.1
0x114a9a  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114a9f  ldarg.0
0x114aa0  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x114aa5  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114aaa  brfalse.s loc_114ABF
0x114aac  ldarg.1
0x114aad  ldarg.0
0x114aae  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x114ab3  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114ab8  castclass [mscorlib]System.String
0x114abd  stloc.s  4
0x114abf  ldarg.1
0x114ac0  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114ac5  ldstr    aComment// "comment"
0x114aca  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114acf  brtrue.s loc_114AD4
0x114ad1  ldnull
0x114ad2  br.s     loc_114AEF
0x114ad4  ldarg.1
0x114ad5  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114ada  ldstr    aComment// "comment"
0x114adf  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x114ae4  ldc.i4.0
0x114ae5  callvirt instance object [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection::get_Item(int32)
0x114aea  castclass [mscorlib]System.String
0x114aef  stloc.s  5
0x114af1  ldc.i4.0
0x114af2  stloc.s  7
0x114af4  ldarg.0
0x114af5  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114afa  callvirt instance valuetype System.Web.Security.DirectoryType System.Web.Security.DirectoryInformation::get_DirectoryType()
0x114aff  brtrue   loc_114BAE
0x114b04  ldarg.1
0x114b05  ldstr    aUseraccountcon_0// "userAccountControl"
0x114b0a  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114b0f  unbox.any [mscorlib]System.Int32
0x114b14  stloc.s  0xD
0x114b16  ldloc.s  0xD
0x114b18  ldc.i4.2
0x114b19  and
0x114b1a  brtrue.s loc_114B21
0x114b1c  ldc.i4.1
0x114b1d  stloc.s  6
0x114b1f  br.s     loc_114B24
0x114b21  ldc.i4.0
0x114b22  stloc.s  6
0x114b24  ldarg.1
0x114b25  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114b2a  ldstr    aMsdsUserAccoun_0// "msDS-User-Account-Control-Computed"
0x114b2f  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114b34  brfalse.s loc_114B5A
0x114b36  ldarg.1
0x114b37  ldstr    aMsdsUserAccoun_0// "msDS-User-Account-Control-Computed"
0x114b3c  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114b41  unbox.any [mscorlib]System.Int32
0x114b46  stloc.s  0xE
0x114b48  ldloc.s  0xE
0x114b4a  ldc.i4.s 0x10
0x114b4c  and
0x114b4d  brfalse  loc_114BF4
0x114b52  ldc.i4.1
0x114b53  stloc.s  7
0x114b55  br       loc_114BF4
0x114b5a  ldarg.1
0x114b5b  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114b60  ldstr    aLockouttime_0// "lockoutTime"
0x114b65  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114b6a  brfalse  loc_114BF4
0x114b6f  ldarg.1
0x114b70  ldstr    aLockouttime_0// "lockoutTime"
0x114b75  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114b7a  unbox.any [mscorlib]System.Int64
0x114b7f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTimeUtc(int64)
0x114b84  stloc.s  0xF
0x114b86  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x114b8b  stloc.s  0x10
0x114b8d  ldloca.s 0x10
0x114b8f  ldloc.s  0xF
0x114b91  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x114b96  stloc.s  0x11
0x114b98  ldloc.s  0x11
0x114b9a  ldarg.0
0x114b9b  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114ba0  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.Security.DirectoryInformation::get_ADLockoutDuration()
0x114ba5  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x114baa  stloc.s  7
0x114bac  br.s     loc_114BF4
0x114bae  ldc.i4.1
0x114baf  stloc.s  6
0x114bb1  ldarg.1
0x114bb2  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114bb7  ldstr    aMsdsUseraccoun_0// "msDS-UserAccountDisabled"
0x114bbc  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114bc1  brfalse.s loc_114BD8
0x114bc3  ldarg.1
0x114bc4  ldstr    aMsdsUseraccoun_0// "msDS-UserAccountDisabled"
0x114bc9  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114bce  unbox.any [mscorlib]System.Boolean
0x114bd3  ldc.i4.0
0x114bd4  ceq
0x114bd6  stloc.s  6
0x114bd8  ldarg.1
0x114bd9  ldstr    aMsdsUserAccoun_0// "msDS-User-Account-Control-Computed"
0x114bde  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114be3  unbox.any [mscorlib]System.Int32
0x114be8  stloc.s  0x12
0x114bea  ldloc.s  0x12
0x114bec  ldc.i4.s 0x10
0x114bee  and
0x114bef  brfalse.s loc_114BF4
0x114bf1  ldc.i4.1
0x114bf2  stloc.s  7
0x114bf4  ldarg.0
0x114bf5  ldfld    valuetype [mscorlib]System.DateTime System.Web.Security.ActiveDirectoryMembershipProvider::DefaultLastLockoutDate
0x114bfa  stloc.s  8
0x114bfc  ldloc.s  7
0x114bfe  brfalse.s loc_114C17
0x114c00  ldarg.1
0x114c01  ldstr    aLockouttime_0// "lockoutTime"
0x114c06  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114c0b  unbox.any [mscorlib]System.Int64
0x114c10  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTime(int64)
0x114c15  stloc.s  8
0x114c17  ldarg.0
0x114c18  callvirt instance bool [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_EnablePasswordReset()
0x114c1d  brfalse  loc_114CD4
0x114c22  ldarg.1
0x114c23  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x114c28  ldarg.0
0x114c29  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114c2e  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x114c33  brfalse  loc_114CD4
0x114c38  ldarg.1
0x114c39  ldarg.0
0x114c3a  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114c3f  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114c44  unbox.any [mscorlib]System.Int64
0x114c49  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTimeUtc(int64)
0x114c4e  stloc.s  0x13
0x114c50  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x114c55  stloc.s  0x14
0x114c57  ldloca.s 0x14
0x114c59  ldloc.s  0x13
0x114c5b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x114c60  stloc.s  0x15
0x114c62  ldloc.s  0x15
0x114c64  ldc.i4.0
0x114c65  ldarg.0
0x114c66  call     instance int32 System.Web.Security.ActiveDirectoryMembershipProvider::get_PasswordAnswerAttemptLockoutDuration()
0x114c6b  ldc.i4.0
0x114c6c  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x114c71  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x114c76  stloc.s  0x16
0x114c78  ldloc.s  0x16
0x114c7a  brfalse.s loc_114CD4
0x114c7c  ldloc.s  7
0x114c7e  brfalse.s loc_114CB9
0x114c80  ldloc.s  0x13
0x114c82  ldarg.1
0x114c83  ldstr    aLockouttime_0// "lockoutTime"
0x114c88  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114c8d  unbox.any [mscorlib]System.Int64
0x114c92  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTimeUtc(int64)
0x114c97  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x114c9c  ldc.i4.0
0x114c9d  ble.s    loc_114CD4
0x114c9f  ldarg.1
0x114ca0  ldarg.0
0x114ca1  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114ca6  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114cab  unbox.any [mscorlib]System.Int64
0x114cb0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTime(int64)
0x114cb5  stloc.s  8
0x114cb7  br.s     loc_114CD4
0x114cb9  ldc.i4.1
0x114cba  stloc.s  7
0x114cbc  ldarg.1
0x114cbd  ldarg.0
0x114cbe  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114cc3  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114cc8  unbox.any [mscorlib]System.Int64
0x114ccd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTime(int64)
0x114cd2  stloc.s  8
0x114cd4  ldarg.1
0x114cd5  ldstr    aWhencreated_0// "whenCreated"
0x114cda  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114cdf  unbox.any [mscorlib]System.DateTime
0x114ce4  stloc.s  0x17
0x114ce6  ldloca.s 0x17
0x114ce8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x114ced  stloc.s  9
0x114cef  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x114cf4  stloc.s  0xA
0x114cf6  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x114cfb  stloc.s  0xB
0x114cfd  ldarg.1
0x114cfe  ldstr    aPwdlastset_0// "pwdLastSet"
0x114d03  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114d08  unbox.any [mscorlib]System.Int64
0x114d0d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTime(int64)
0x114d12  stloc.s  0xC
0x114d14  ldarg.0
0x114d15  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x114d1a  ldloc.0
0x114d1b  ldloc.1
0x114d1c  ldloc.2
0x114d1d  ldloc.3
0x114d1e  ldloc.s  4
0x114d20  ldloc.s  5
0x114d22  ldloc.s  6
0x114d24  ldloc.s  7
0x114d26  ldloc.s  9
0x114d28  ldloc.s  0xA
0x114d2a  ldloc.s  0xB
0x114d2c  ldloc.s  0xC
0x114d2e  ldloc.s  8
0x114d30  ldc.i4.1
0x114d31  newobj   instance void System.Web.Security.ActiveDirectoryMembershipUser::.ctor(string providerName, string name, unsigned int8[] sidBinaryForm, object providerUserKey, string email, string passwordQuestion, string comment, bool isApproved, bool isLockedOut, valuetype [mscorlib]System.DateTime creationDate, valuetype [mscorlib]System.DateTime lastLoginDate, valuetype [mscorlib]System.DateTime lastActivityDate, valuetype [mscorlib]System.DateTime lastPasswordChangedDate, valuetype [mscorlib]System.DateTime lastLockoutDate, bool valuesAreUpdated)
0x114d36  ret
```
