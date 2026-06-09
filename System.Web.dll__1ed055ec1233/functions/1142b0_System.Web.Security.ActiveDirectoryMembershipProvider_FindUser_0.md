# System.Web.Security.ActiveDirectoryMembershipProvider::FindUser_0

- ea: `0x1142b0`
- end: `0x1144d0`
- name: `System.Web.Security.ActiveDirectoryMembershipProvider::FindUser_0`
- size: `544`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x112110`
- `0x114290`
- `0x1142a0`

## callees

- `0x534d0`
- `0x1142b0`
- `0x114a30`
- `0x1161d0`
- `0x116200`
- `0x116210`
- `0x116220`
- `0x116cc0`

## string_xrefs

- `0x11436f`: `comment`
- `0x11434c`: `objectSid`
- `0x114380`: `whenCreated`
- `0x1143a2`: `msDS-User-Account-Control-Computed`

## pseudocode

```c

```

## disassembly

```asm
0x1142b0  ldnull
0x1142b1  stloc.0
0x1142b2  ldarg.1
0x1142b3  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x1142b8  stloc.1
0x1142b9  ldloc.1
0x1142ba  ldarg.3
0x1142bb  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x1142c0  ldloc.1
0x1142c1  ldstr    aObjectcategory_0// "(&(objectCategory=person)(objectClass=u"...
0x1142c6  ldarg.2
0x1142c7  ldstr    asc_1B2ECE// ")"
0x1142cc  call     string [mscorlib]System.String::Concat(string, string, string)
0x1142d1  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x1142d6  ldarg.0
0x1142d7  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x1142dc  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ClientSearchTimeout()
0x1142e1  ldc.i4.m1
0x1142e2  beq.s    loc_114305
0x1142e4  ldloc.1
0x1142e5  ldarg.0
0x1142e6  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x1142eb  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ClientSearchTimeout()
0x1142f0  ldarg.0
0x1142f1  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x1142f6  callvirt instance valuetype System.Web.Util.TimeUnit System.Web.Security.DirectoryInformation::get_TimeoutUnit()
0x1142fb  call     valuetype [mscorlib]System.TimeSpan System.Web.Util.DateTimeUtil::GetTimeoutFromTimeUnit(int32 timeoutValue, valuetype System.Web.Util.TimeUnit timeoutUnit)
0x114300  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ClientTimeout(valuetype [mscorlib]System.TimeSpan)
0x114305  ldarg.0
0x114306  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11430b  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ServerSearchTimeout()
0x114310  ldc.i4.m1
0x114311  beq.s    loc_114334
0x114313  ldloc.1
0x114314  ldarg.0
0x114315  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11431a  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ServerSearchTimeout()
0x11431f  ldarg.0
0x114320  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114325  callvirt instance valuetype System.Web.Util.TimeUnit System.Web.Security.DirectoryInformation::get_TimeoutUnit()
0x11432a  call     valuetype [mscorlib]System.TimeSpan System.Web.Util.DateTimeUtil::GetTimeoutFromTimeUnit(int32 timeoutValue, valuetype System.Web.Util.TimeUnit timeoutUnit)
0x11432f  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ServerPageTimeLimit(valuetype [mscorlib]System.TimeSpan)
0x114334  ldloc.1
0x114335  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11433a  ldarg.0
0x11433b  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapUsername
0x114340  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114345  pop
0x114346  ldloc.1
0x114347  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11434c  ldstr    aObjectsid_1// "objectSid"
0x114351  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114356  pop
0x114357  ldloc.1
0x114358  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11435d  ldarg.0
0x11435e  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapEmail
0x114363  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114368  pop
0x114369  ldloc.1
0x11436a  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11436f  ldstr    aComment// "comment"
0x114374  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114379  pop
0x11437a  ldloc.1
0x11437b  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114380  ldstr    aWhencreated_0// "whenCreated"
0x114385  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11438a  pop
0x11438b  ldloc.1
0x11438c  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114391  ldstr    aPwdlastset_0// "pwdLastSet"
0x114396  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11439b  pop
0x11439c  ldloc.1
0x11439d  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1143a2  ldstr    aMsdsUserAccoun_0// "msDS-User-Account-Control-Computed"
0x1143a7  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1143ac  pop
0x1143ad  ldloc.1
0x1143ae  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1143b3  ldstr    aLockouttime_0// "lockoutTime"
0x1143b8  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1143bd  pop
0x1143be  ldarg.s  4
0x1143c0  brfalse.s loc_1143D3
0x1143c2  ldloc.1
0x1143c3  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1143c8  ldstr    aSamaccountname// "sAMAccountName"
0x1143cd  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1143d2  pop
0x1143d3  ldarg.0
0x1143d4  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x1143d9  brfalse.s loc_1143ED
0x1143db  ldloc.1
0x1143dc  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1143e1  ldarg.0
0x1143e2  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x1143e7  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1143ec  pop
0x1143ed  ldarg.0
0x1143ee  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x1143f3  callvirt instance valuetype System.Web.Security.DirectoryType System.Web.Security.DirectoryInformation::get_DirectoryType()
0x1143f8  brtrue.s loc_11440D
0x1143fa  ldloc.1
0x1143fb  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114400  ldstr    aUseraccountcon_0// "userAccountControl"
0x114405  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11440a  pop
0x11440b  br.s     loc_11441E
0x11440d  ldloc.1
0x11440e  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114413  ldstr    aMsdsUseraccoun_0// "msDS-UserAccountDisabled"
0x114418  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11441d  pop
0x11441e  ldarg.0
0x11441f  callvirt instance bool [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_EnablePasswordReset()
0x114424  brfalse.s loc_11445C
0x114426  ldloc.1
0x114427  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11442c  ldarg.0
0x11442d  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerCount
0x114432  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114437  pop
0x114438  ldloc.1
0x114439  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11443e  ldarg.0
0x11443f  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerTime
0x114444  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114449  pop
0x11444a  ldloc.1
0x11444b  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114450  ldarg.0
0x114451  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114456  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11445b  pop
0x11445c  ldloc.1
0x11445d  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindOne()
0x114462  stloc.2
0x114463  ldarg.s  6
0x114465  ldc.i4.0
0x114466  stind.i1
0x114467  ldarg.s  7
0x114469  ldnull
0x11446a  stind.ref
0x11446b  ldloc.2
0x11446c  brfalse.s loc_1144CA
0x11446e  ldarg.0
0x11446f  ldloc.2
0x114470  call     instance class [System.Web.ApplicationServices]System.Web.Security.MembershipUser System.Web.Security.ActiveDirectoryMembershipProvider::GetMembershipUserFromSearchResult(class [System.DirectoryServices]System.DirectoryServices.SearchResult res)
0x114475  stloc.0
0x114476  ldarg.s  5
0x114478  ldloc.2
0x114479  callvirt instance class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry [System.DirectoryServices]System.DirectoryServices.SearchResult::GetDirectoryEntry()
0x11447e  stind.ref
0x11447f  ldarg.s  4
0x114481  brfalse.s loc_114496
0x114483  ldarg.s  7
0x114485  ldloc.2
0x114486  ldstr    aSamaccountname// "sAMAccountName"
0x11448b  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x114490  castclass [mscorlib]System.String
0x114495  stind.ref
0x114496  ldarg.0
0x114497  callvirt instance bool [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_EnablePasswordReset()
0x11449c  brfalse.s loc_1144CE
0x11449e  ldloc.2
0x11449f  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x1144a4  ldarg.0
0x1144a5  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerCount
0x1144aa  callvirt instance bool [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::Contains(string)
0x1144af  brfalse.s loc_1144CE
0x1144b1  ldarg.s  6
0x1144b3  ldloc.2
0x1144b4  ldarg.0
0x1144b5  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerCount
0x1144ba  call     object System.Web.Security.PropertyManager::GetSearchResultPropertyValue(class [System.DirectoryServices]System.DirectoryServices.SearchResult res, string propertyName)
0x1144bf  unbox.any [mscorlib]System.Int32
0x1144c4  ldc.i4.0
0x1144c5  cgt
0x1144c7  stind.i1
0x1144c8  br.s     loc_1144CE
0x1144ca  ldarg.s  5
0x1144cc  ldnull
0x1144cd  stind.ref
0x1144ce  ldloc.0
0x1144cf  ret
```
