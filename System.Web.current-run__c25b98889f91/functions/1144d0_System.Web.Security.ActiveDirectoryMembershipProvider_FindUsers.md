# System.Web.Security.ActiveDirectoryMembershipProvider::FindUsers

- ea: `0x1144d0`
- end: `0x114709`
- name: `System.Web.Security.ActiveDirectoryMembershipProvider::FindUsers`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x113e70`
- `0x113f90`

## callees

- `0x534d0`
- `0x1144d0`
- `0x114a30`
- `0x1161d0`
- `0x116200`
- `0x116210`
- `0x116220`

## string_xrefs

- `0x1145a2`: `comment`
- `0x11457f`: `objectSid`
- `0x1145b3`: `whenCreated`
- `0x1145d5`: `msDS-User-Account-Control-Computed`

## pseudocode

```c

```

## disassembly

```asm
0x1144d0  newobj   instance void [System.Web.ApplicationServices]System.Web.Security.MembershipUserCollection::.ctor()
0x1144d5  stloc.0
0x1144d6  ldarg.s  4
0x1144d8  ldc.i4.1
0x1144d9  add
0x1144da  ldarg.s  5
0x1144dc  mul
0x1144dd  stloc.1
0x1144de  ldloc.1
0x1144df  ldarg.s  5
0x1144e1  sub
0x1144e2  ldc.i4.1
0x1144e3  add
0x1144e4  stloc.2
0x1144e5  ldarg.1
0x1144e6  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x1144eb  stloc.3
0x1144ec  ldloc.3
0x1144ed  ldc.i4.2
0x1144ee  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x1144f3  ldloc.3
0x1144f4  ldstr    aObjectcategory_0// "(&(objectCategory=person)(objectClass=u"...
0x1144f9  ldarg.2
0x1144fa  ldstr    asc_1B2ECE// ")"
0x1144ff  call     string [mscorlib]System.String::Concat(string, string, string)
0x114504  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x114509  ldarg.0
0x11450a  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11450f  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ClientSearchTimeout()
0x114514  ldc.i4.m1
0x114515  beq.s    loc_114538
0x114517  ldloc.3
0x114518  ldarg.0
0x114519  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11451e  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ClientSearchTimeout()
0x114523  ldarg.0
0x114524  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114529  callvirt instance valuetype System.Web.Util.TimeUnit System.Web.Security.DirectoryInformation::get_TimeoutUnit()
0x11452e  call     valuetype [mscorlib]System.TimeSpan System.Web.Util.DateTimeUtil::GetTimeoutFromTimeUnit(int32 timeoutValue, valuetype System.Web.Util.TimeUnit timeoutUnit)
0x114533  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ClientTimeout(valuetype [mscorlib]System.TimeSpan)
0x114538  ldarg.0
0x114539  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11453e  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ServerSearchTimeout()
0x114543  ldc.i4.m1
0x114544  beq.s    loc_114567
0x114546  ldloc.3
0x114547  ldarg.0
0x114548  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x11454d  callvirt instance int32 System.Web.Security.DirectoryInformation::get_ServerSearchTimeout()
0x114552  ldarg.0
0x114553  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114558  callvirt instance valuetype System.Web.Util.TimeUnit System.Web.Security.DirectoryInformation::get_TimeoutUnit()
0x11455d  call     valuetype [mscorlib]System.TimeSpan System.Web.Util.DateTimeUtil::GetTimeoutFromTimeUnit(int32 timeoutValue, valuetype System.Web.Util.TimeUnit timeoutUnit)
0x114562  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ServerPageTimeLimit(valuetype [mscorlib]System.TimeSpan)
0x114567  ldloc.3
0x114568  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11456d  ldarg.0
0x11456e  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapUsername
0x114573  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114578  pop
0x114579  ldloc.3
0x11457a  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11457f  ldstr    aObjectsid_1// "objectSid"
0x114584  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114589  pop
0x11458a  ldloc.3
0x11458b  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114590  ldarg.0
0x114591  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapEmail
0x114596  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11459b  pop
0x11459c  ldloc.3
0x11459d  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145a2  ldstr    aComment// "comment"
0x1145a7  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1145ac  pop
0x1145ad  ldloc.3
0x1145ae  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145b3  ldstr    aWhencreated_0// "whenCreated"
0x1145b8  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1145bd  pop
0x1145be  ldloc.3
0x1145bf  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145c4  ldstr    aPwdlastset_0// "pwdLastSet"
0x1145c9  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1145ce  pop
0x1145cf  ldloc.3
0x1145d0  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145d5  ldstr    aMsdsUserAccoun_0// "msDS-User-Account-Control-Computed"
0x1145da  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1145df  pop
0x1145e0  ldloc.3
0x1145e1  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145e6  ldstr    aLockouttime_0// "lockoutTime"
0x1145eb  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1145f0  pop
0x1145f1  ldarg.0
0x1145f2  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x1145f7  brfalse.s loc_11460B
0x1145f9  ldloc.3
0x1145fa  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1145ff  ldarg.0
0x114600  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapPasswordQuestion
0x114605  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11460a  pop
0x11460b  ldarg.0
0x11460c  ldfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x114611  callvirt instance valuetype System.Web.Security.DirectoryType System.Web.Security.DirectoryInformation::get_DirectoryType()
0x114616  brtrue.s loc_11462B
0x114618  ldloc.3
0x114619  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11461e  ldstr    aUseraccountcon_0// "userAccountControl"
0x114623  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114628  pop
0x114629  br.s     loc_11463C
0x11462b  ldloc.3
0x11462c  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x114631  ldstr    aMsdsUseraccoun_0// "msDS-UserAccountDisabled"
0x114636  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x11463b  pop
0x11463c  ldarg.0
0x11463d  callvirt instance bool [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_EnablePasswordReset()
0x114642  brfalse.s loc_11467A
0x114644  ldloc.3
0x114645  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11464a  ldarg.0
0x11464b  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerCount
0x114650  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114655  pop
0x114656  ldloc.3
0x114657  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11465c  ldarg.0
0x11465d  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerTime
0x114662  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114667  pop
0x114668  ldloc.3
0x114669  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x11466e  ldarg.0
0x11466f  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::attributeMapFailedPasswordAnswerLockoutTime
0x114674  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x114679  pop
0x11467a  ldloc.3
0x11467b  ldc.i4   0x200
0x114680  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_PageSize(int32)
0x114685  ldloc.3
0x114686  ldarg.3
0x114687  ldc.i4.0
0x114688  newobj   instance void [System.DirectoryServices]System.DirectoryServices.SortOption::.ctor(string, valuetype [System.DirectoryServices]System.DirectoryServices.SortDirection)
0x11468d  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Sort(class [System.DirectoryServices]System.DirectoryServices.SortOption)
0x114692  ldloc.3
0x114693  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResultCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindAll()
0x114698  stloc.s  4
0x11469a  ldc.i4.0
0x11469b  stloc.s  5
0x11469d  ldarg.s  6
0x11469f  ldc.i4.0
0x1146a0  stind.i4
0x1146a1  ldloc.s  4
0x1146a3  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::GetEnumerator()
0x1146a8  stloc.s  6
0x1146aa  br.s     loc_1146D8
0x1146ac  ldloc.s  6
0x1146ae  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1146b3  castclass [System.DirectoryServices]System.DirectoryServices.SearchResult
0x1146b8  stloc.s  7
0x1146ba  ldloc.s  5
0x1146bc  ldc.i4.1
0x1146bd  add
0x1146be  stloc.s  5
0x1146c0  ldloc.s  5
0x1146c2  ldloc.2
0x1146c3  blt.s    loc_1146D8
0x1146c5  ldloc.s  5
0x1146c7  ldloc.1
0x1146c8  bgt.s    loc_1146D8
0x1146ca  ldloc.0
0x1146cb  ldarg.0
0x1146cc  ldloc.s  7
0x1146ce  call     instance class [System.Web.ApplicationServices]System.Web.Security.MembershipUser System.Web.Security.ActiveDirectoryMembershipProvider::GetMembershipUserFromSearchResult(class [System.DirectoryServices]System.DirectoryServices.SearchResult res)
0x1146d3  callvirt instance void [System.Web.ApplicationServices]System.Web.Security.MembershipUserCollection::Add(class [System.Web.ApplicationServices]System.Web.Security.MembershipUser)
0x1146d8  ldloc.s  6
0x1146da  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1146df  brtrue.s loc_1146AC
0x1146e1  leave.s  loc_1146F8
0x1146e3  ldloc.s  6
0x1146e5  isinst   [mscorlib]System.IDisposable
0x1146ea  stloc.s  8
0x1146ec  ldloc.s  8
0x1146ee  brfalse.s loc_1146F7
0x1146f0  ldloc.s  8
0x1146f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1146f7  endfinally
0x1146f8  ldarg.s  6
0x1146fa  ldloc.s  5
0x1146fc  stind.i4
0x1146fd  leave.s  loc_114707
0x1146ff  ldloc.s  4
0x114701  callvirt instance void [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::Dispose()
0x114706  endfinally
0x114707  ldloc.0
0x114708  ret
```
