# System.Web.Security.ActiveDirectoryMembershipProvider::Initialize

- ea: `0x1117c0`
- end: `0x112109`
- name: `System.Web.Security.ActiveDirectoryMembershipProvider::Initialize`
- size: `2377`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18990`
- `0x24280`
- `0x29e60`
- `0x34f20`
- `0x34fa0`
- `0x58390`
- `0x586c0`
- `0x58700`
- `0x587d0`
- `0x587f0`
- `0x58d50`
- `0x1117c0`
- `0x115340`
- `0x115390`
- `0x115600`
- `0x115690`
- `0x1159d0`
- `0x1161d0`
- `0x1161e0`
- `0x116270`
- `0x116330`
- `0x116350`
- `0x116550`
- `0x161c60`

## string_xrefs

- `0x1117e2`: `config`
- `0x1117f5`: `AspNetActiveDirectoryMembershipProvider`
- `0x111b03`: `DirectoryString`
- `0x111b18`: `DirectoryString`
- `0x111b2d`: `DirectoryString`
- `0x111b42`: `DirectoryString`
- `0x111ba2`: `objectsid`
- `0x111bb3`: `comment`
- `0x111cfc`: `comment`
- `0x111bc4`: `whencreated`
- `0x111be6`: `msds-user-account-control-computed`
- `0x111d44`: `maxInvalidPasswordAttempts`
- `0x112053`: `maxInvalidPasswordAttempts`
- `0x111d58`: `passwordAttemptWindow`
- `0x11205e`: `passwordAttemptWindow`
- `0x111d6d`: `passwordAnswerAttemptLockoutDuration`
- `0x112069`: `passwordAnswerAttemptLockoutDuration`
- `0x111f69`: `passwordCompatMode`
- `0x1120b6`: `passwordCompatMode`

## pseudocode

```c

```

## disassembly

```asm
0x1117c0  call     bool System.Web.Hosting.HostingEnvironment::get_IsHosted()
0x1117c5  brfalse.s loc_1117D6
0x1117c7  ldc.i4   0x12C
0x1117cc  ldstr    aFeatureNotSupp// "Feature_not_supported_at_this_level"
0x1117d1  call     void System.Web.HttpRuntime::CheckAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level, string errorMessageId)
0x1117d6  ldarg.0
0x1117d7  ldfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::initialized
0x1117dc  brfalse.s loc_1117DF
0x1117de  ret
0x1117df  ldarg.2
0x1117e0  brtrue.s loc_1117ED
0x1117e2  ldstr    aConfig// "config"
0x1117e7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1117ec  throw
0x1117ed  ldarg.1
0x1117ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1117f3  brfalse.s loc_1117FC
0x1117f5  ldstr    aAspnetactivedi// "AspNetActiveDirectoryMembershipProvider"
0x1117fa  starg.s  1
0x1117fc  ldarg.2
0x1117fd  ldstr    aDescription// "description"
0x111802  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x111807  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11180c  brfalse.s loc_11182E
0x11180e  ldarg.2
0x11180f  ldstr    aDescription// "description"
0x111814  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x111819  ldarg.2
0x11181a  ldstr    aDescription// "description"
0x11181f  ldstr    aAdmembershipDe// "ADMembership_Description"
0x111824  call     string System.Web.SR::GetString(string name)
0x111829  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x11182e  ldarg.0
0x11182f  ldarg.1
0x111830  ldarg.2
0x111831  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x111836  ldarg.0
0x111837  ldarg.2
0x111838  ldstr    aApplicationnam// "applicationName"
0x11183d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x111842  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::appName
0x111847  ldarg.0
0x111848  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::appName
0x11184d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x111852  brfalse.s loc_11185F
0x111854  ldarg.0
0x111855  call     string System.Web.Util.SecUtility::GetDefaultAppName()
0x11185a  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::appName
0x11185f  ldarg.0
0x111860  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::appName
0x111865  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11186a  ldc.i4   0x100
0x11186f  ble.s    loc_111881
0x111871  ldstr    aProviderApplic// "Provider_application_name_too_long"
0x111876  call     string System.Web.SR::GetString(string name)
0x11187b  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x111880  throw
0x111881  ldarg.2
0x111882  ldstr    aConnectionstri// "connectionStringName"
0x111887  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11188c  stloc.0
0x11188d  ldloc.0
0x11188e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x111893  brfalse.s loc_1118A5
0x111895  ldstr    aConnectionName// "Connection_name_not_specified"
0x11189a  call     string System.Web.SR::GetString(string name)
0x11189f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1118a4  throw
0x1118a5  ldarg.0
0x1118a6  ldarg.0
0x1118a7  ldloc.0
0x1118a8  ldc.i4.1
0x1118a9  call     instance string System.Web.Security.ActiveDirectoryMembershipProvider::GetConnectionString(string connectionStringName, bool appLevel)
0x1118ae  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::adConnectionString
0x1118b3  ldarg.0
0x1118b4  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::adConnectionString
0x1118b9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1118be  brfalse.s loc_1118DA
0x1118c0  ldstr    aConnectionStri// "Connection_string_not_found"
0x1118c5  ldc.i4.1
0x1118c6  newarr   [mscorlib]System.Object
0x1118cb  dup
0x1118cc  ldc.i4.0
0x1118cd  ldloc.0
0x1118ce  stelem.ref
0x1118cf  call     string System.Web.SR::GetString(string name, object[] args)
0x1118d4  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1118d9  throw
0x1118da  ldarg.2
0x1118db  ldstr    aConnectionprot// "connectionProtection"
0x1118e0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1118e5  stloc.1
0x1118e6  ldloc.1
0x1118e7  brtrue.s loc_1118F1
0x1118e9  ldstr    aSecure// "Secure"
0x1118ee  stloc.1
0x1118ef  br.s     loc_111927
0x1118f1  ldloc.1
0x1118f2  ldstr    aSecure// "Secure"
0x1118f7  ldc.i4.4
0x1118f8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1118fd  brfalse.s loc_111927
0x1118ff  ldloc.1
0x111900  ldstr    aNone_0// "None"
0x111905  ldc.i4.4
0x111906  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x11190b  brfalse.s loc_111927
0x11190d  ldstr    aAdmembershipIn// "ADMembership_InvalidConnectionProtectio"...
0x111912  ldc.i4.1
0x111913  newarr   [mscorlib]System.Object
0x111918  dup
0x111919  ldc.i4.0
0x11191a  ldloc.1
0x11191b  stelem.ref
0x11191c  call     string System.Web.SR::GetString(string name, object[] args)
0x111921  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x111926  throw
0x111927  ldarg.2
0x111928  ldstr    aConnectionuser// "connectionUsername"
0x11192d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x111932  stloc.2
0x111933  ldloc.2
0x111934  brfalse.s loc_11194E
0x111936  ldloc.2
0x111937  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11193c  brtrue.s loc_11194E
0x11193e  ldstr    aAdmembershipCo// "ADMembership_Connection_username_must_n"...
0x111943  call     string System.Web.SR::GetString(string name)
0x111948  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x11194d  throw
0x11194e  ldarg.2
0x11194f  ldstr    aConnectionpass// "connectionPassword"
0x111954  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x111959  stloc.3
0x11195a  ldloc.3
0x11195b  brfalse.s loc_111975
0x11195d  ldloc.3
0x11195e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x111963  brtrue.s loc_111975
0x111965  ldstr    aAdmembershipCo_0// "ADMembership_Connection_password_must_n"...
0x11196a  call     string System.Web.SR::GetString(string name)
0x11196f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x111974  throw
0x111975  ldloc.2
0x111976  brfalse.s loc_11197B
0x111978  ldloc.3
0x111979  brfalse.s loc_111981
0x11197b  ldloc.3
0x11197c  brfalse.s loc_111991
0x11197e  ldloc.2
0x11197f  brtrue.s loc_111991
0x111981  ldstr    aAdmembershipUs// "ADMembership_Username_and_password_reqd"
0x111986  call     string System.Web.SR::GetString(string name)
0x11198b  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x111990  throw
0x111991  ldloc.2
0x111992  ldloc.3
0x111993  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string)
0x111998  stloc.s  4
0x11199a  ldarg.2
0x11199b  ldstr    aClientsearchti// "clientSearchTimeout"
0x1119a0  ldc.i4.m1
0x1119a1  ldc.i4.0
0x1119a2  ldc.i4.0
0x1119a3  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1119a8  stloc.s  5
0x1119aa  ldarg.2
0x1119ab  ldstr    aServersearchti// "serverSearchTimeout"
0x1119b0  ldc.i4.m1
0x1119b1  ldc.i4.0
0x1119b2  ldc.i4.0
0x1119b3  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1119b8  stloc.s  6
0x1119ba  ldarg.2
0x1119bb  ldstr    aTimeoutunit// "timeoutUnit"
0x1119c0  ldc.i4.3
0x1119c1  call     valuetype System.Web.Util.TimeUnit System.Web.Util.SecUtility::GetTimeoutUnit(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, valuetype System.Web.Util.TimeUnit defaultValue)
0x1119c6  stloc.s  7
0x1119c8  ldarg.0
0x1119c9  ldarg.2
0x1119ca  ldstr    aPasswordstreng_0// "passwordStrengthRegexTimeout"
0x1119cf  call     valuetype [mscorlib]System.Nullable`1<int32> System.Web.Util.SecUtility::GetNullableIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName)
0x1119d4  stfld    valuetype [mscorlib]System.Nullable`1<int32> System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegexTimeout
0x1119d9  ldarg.0
0x1119da  ldarg.2
0x1119db  ldstr    aEnablesearchme// "enableSearchMethods"
0x1119e0  ldc.i4.0
0x1119e1  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x1119e6  stfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::enableSearchMethods
0x1119eb  ldarg.0
0x1119ec  ldarg.2
0x1119ed  ldstr    aRequiresunique// "requiresUniqueEmail"
0x1119f2  ldc.i4.0
0x1119f3  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x1119f8  stfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::requiresUniqueEmail
0x1119fd  ldarg.0
0x1119fe  ldarg.2
0x1119ff  ldstr    aEnablepassword// "enablePasswordReset"
0x111a04  ldc.i4.0
0x111a05  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x111a0a  stfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::enablePasswordReset
0x111a0f  ldarg.0
0x111a10  ldarg.2
0x111a11  ldstr    aRequiresquesti// "requiresQuestionAndAnswer"
0x111a16  ldc.i4.0
0x111a17  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x111a1c  stfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::requiresQuestionAndAnswer
0x111a21  ldarg.0
0x111a22  ldarg.2
0x111a23  ldstr    aMinrequiredpas// "minRequiredPasswordLength"
0x111a28  ldc.i4.7
0x111a29  ldc.i4.0
0x111a2a  ldc.i4   0x80
0x111a2f  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x111a34  stfld    int32 System.Web.Security.ActiveDirectoryMembershipProvider::minRequiredPasswordLength
0x111a39  ldarg.0
0x111a3a  ldarg.2
0x111a3b  ldstr    aMinrequirednon// "minRequiredNonalphanumericCharacters"
0x111a40  ldc.i4.1
0x111a41  ldc.i4.1
0x111a42  ldc.i4   0x80
0x111a47  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x111a4c  stfld    int32 System.Web.Security.ActiveDirectoryMembershipProvider::minRequiredNonalphanumericCharacters
0x111a51  ldarg.0
0x111a52  ldarg.2
0x111a53  ldstr    aPasswordstreng_1// "passwordStrengthRegularExpression"
0x111a58  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x111a5d  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a62  ldarg.0
0x111a63  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a68  brfalse.s loc_111AA8
0x111a6a  ldarg.0
0x111a6b  ldarg.0
0x111a6c  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a71  callvirt instance string [mscorlib]System.String::Trim()
0x111a76  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a7b  ldarg.0
0x111a7c  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a81  callvirt instance int32 [mscorlib]System.String::get_Length()
0x111a86  brfalse.s loc_111AB3
0x111a88  ldarg.0
0x111a89  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111a8e  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x111a93  stloc.s  8
0x111a95  leave.s  loc_111AB3
0x111a97  stloc.s  9
0x111a99  ldloc.s  9
0x111a9b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x111aa0  ldloc.s  9
0x111aa2  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string, class [mscorlib]System.Exception)
0x111aa7  throw
0x111aa8  ldarg.0
0x111aa9  ldsfld   string [mscorlib]System.String::Empty
0x111aae  stfld    string System.Web.Security.ActiveDirectoryMembershipProvider::passwordStrengthRegularExpression
0x111ab3  ldarg.0
0x111ab4  ldfld    int32 System.Web.Security.ActiveDirectoryMembershipProvider::minRequiredNonalphanumericCharacters
0x111ab9  ldarg.0
0x111aba  ldfld    int32 System.Web.Security.ActiveDirectoryMembershipProvider::minRequiredPasswordLength
0x111abf  ble.s    loc_111AD1
0x111ac1  ldstr    aMinrequirednon_0// "MinRequiredNonalphanumericCharacters_ca"...
0x111ac6  call     string System.Web.SR::GetString(string name)
0x111acb  newobj   instance void System.Web.HttpException::.ctor(string message)
0x111ad0  throw
0x111ad1  newobj   instance void System.Web.ApplicationImpersonationContext::.ctor()
0x111ad6  stloc.s  0xA
0x111ad8  ldarg.0
0x111ad9  ldarg.0
0x111ada  ldfld    string System.Web.Security.ActiveDirectoryMembershipProvider::adConnectionString
0x111adf  ldloc.s  4
0x111ae1  ldloc.1
0x111ae2  ldloc.s  5
0x111ae4  ldloc.s  6
0x111ae6  ldarg.0
0x111ae7  ldfld    bool System.Web.Security.ActiveDirectoryMembershipProvider::enablePasswordReset
0x111aec  ldloc.s  7
0x111aee  newobj   instance void System.Web.Security.DirectoryInformation::.ctor(string adspath, class [System]System.Net.NetworkCredential credentials, string connProtection, int32 clientSearchTimeout, int32 serverSearchTimeout, bool enablePasswordReset, valuetype System.Web.Util.TimeUnit timeUnit)
0x111af3  stfld    class System.Web.Security.DirectoryInformation System.Web.Security.ActiveDirectoryMembershipProvider::directoryInfo
0x111af8  ldarg.0
0x111af9  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Security.ActiveDirectoryMembershipProvider::syntaxes
0x111afe  ldstr    aAttributemapus// "attributeMapUsername"
0x111b03  ldstr    aDirectorystrin// "DirectoryString"
0x111b08  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x111b0d  ldarg.0
0x111b0e  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Security.ActiveDirectoryMembershipProvider::syntaxes
0x111b13  ldstr    aAttributemapem// "attributeMapEmail"
0x111b18  ldstr    aDirectorystrin// "DirectoryString"
0x111b1d  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x111b22  ldarg.0
0x111b23  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Security.ActiveDirectoryMembershipProvider::syntaxes
0x111b28  ldstr    aAttributemappa// "attributeMapPasswordQuestion"
0x111b2d  ldstr    aDirectorystrin// "DirectoryString"
0x111b32  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x111b37  ldarg.0
0x111b38  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Security.ActiveDirectoryMembershipProvider::syntaxes
0x111b3d  ldstr    aAttributemappa_0// "attributeMapPasswordAnswer"
0x111b42  ldstr    aDirectorystrin// "DirectoryString"
0x111b47  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x111b4c  ldarg.0
0x111b4d  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Security.ActiveDirectoryMembershipProvider::syntaxes
0x111b52  ldstr    aAttributemapfa// "attributeMapFailedPasswordAnswerCount"
  ... truncated ...
```
