# System.Web.Security.SqlMembershipProvider::Initialize

- ea: `0x1202e0`
- end: `0x120692`
- name: `System.Web.Security.SqlMembershipProvider::Initialize`
- size: `946`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18990`
- `0x24280`
- `0x34f20`
- `0x34fa0`
- `0x58390`
- `0x583f0`
- `0x586c0`
- `0x58700`
- `0x587f0`
- `0x1202e0`

## string_xrefs

- `0x1202f2`: `config`
- `0x12047d`: `commandTimeout`
- `0x120604`: `commandTimeout`
- `0x120397`: `maxInvalidPasswordAttempts`
- `0x1205ee`: `maxInvalidPasswordAttempts`
- `0x1203ab`: `passwordAttemptWindow`
- `0x1205f9`: `passwordAttemptWindow`
- `0x120572`: `passwordCompatMode`
- `0x120646`: `passwordCompatMode`

## pseudocode

```c

```

## disassembly

```asm
0x1202e0  ldc.i4   0x12C
0x1202e5  ldstr    aFeatureNotSupp// "Feature_not_supported_at_this_level"
0x1202ea  call     void System.Web.HttpRuntime::CheckAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level, string errorMessageId)
0x1202ef  ldarg.2
0x1202f0  brtrue.s loc_1202FD
0x1202f2  ldstr    aConfig// "config"
0x1202f7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1202fc  throw
0x1202fd  ldarg.1
0x1202fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x120303  brfalse.s loc_12030C
0x120305  ldstr    aSqlmembershipp// "SqlMembershipProvider"
0x12030a  starg.s  1
0x12030c  ldarg.2
0x12030d  ldstr    aDescription// "description"
0x120312  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x120317  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12031c  brfalse.s loc_12033E
0x12031e  ldarg.2
0x12031f  ldstr    aDescription// "description"
0x120324  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120329  ldarg.2
0x12032a  ldstr    aDescription// "description"
0x12032f  ldstr    aMembershipsqlp// "MembershipSqlProvider_description"
0x120334  call     string System.Web.SR::GetString(string name)
0x120339  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x12033e  ldarg.0
0x12033f  ldarg.1
0x120340  ldarg.2
0x120341  call     instance void [System.Configuration]System.Configuration.Provider.ProviderBase::Initialize(string, class [System]System.Collections.Specialized.NameValueCollection)
0x120346  ldarg.0
0x120347  ldc.i4.0
0x120348  stfld    int32 System.Web.Security.SqlMembershipProvider::_SchemaVersionCheck
0x12034d  ldarg.0
0x12034e  ldarg.2
0x12034f  ldstr    aEnablepassword_0// "enablePasswordRetrieval"
0x120354  ldc.i4.0
0x120355  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x12035a  stfld    bool System.Web.Security.SqlMembershipProvider::_EnablePasswordRetrieval
0x12035f  ldarg.0
0x120360  ldarg.2
0x120361  ldstr    aEnablepassword// "enablePasswordReset"
0x120366  ldc.i4.1
0x120367  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x12036c  stfld    bool System.Web.Security.SqlMembershipProvider::_EnablePasswordReset
0x120371  ldarg.0
0x120372  ldarg.2
0x120373  ldstr    aRequiresquesti// "requiresQuestionAndAnswer"
0x120378  ldc.i4.1
0x120379  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x12037e  stfld    bool System.Web.Security.SqlMembershipProvider::_RequiresQuestionAndAnswer
0x120383  ldarg.0
0x120384  ldarg.2
0x120385  ldstr    aRequiresunique// "requiresUniqueEmail"
0x12038a  ldc.i4.1
0x12038b  call     bool System.Web.Util.SecUtility::GetBooleanValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, bool defaultValue)
0x120390  stfld    bool System.Web.Security.SqlMembershipProvider::_RequiresUniqueEmail
0x120395  ldarg.0
0x120396  ldarg.2
0x120397  ldstr    aMaxinvalidpass// "maxInvalidPasswordAttempts"
0x12039c  ldc.i4.5
0x12039d  ldc.i4.0
0x12039e  ldc.i4.0
0x12039f  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1203a4  stfld    int32 System.Web.Security.SqlMembershipProvider::_MaxInvalidPasswordAttempts
0x1203a9  ldarg.0
0x1203aa  ldarg.2
0x1203ab  ldstr    aPasswordattemp// "passwordAttemptWindow"
0x1203b0  ldc.i4.s 0xA
0x1203b2  ldc.i4.0
0x1203b3  ldc.i4.0
0x1203b4  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1203b9  stfld    int32 System.Web.Security.SqlMembershipProvider::_PasswordAttemptWindow
0x1203be  ldarg.0
0x1203bf  ldarg.2
0x1203c0  ldstr    aMinrequiredpas// "minRequiredPasswordLength"
0x1203c5  ldc.i4.7
0x1203c6  ldc.i4.0
0x1203c7  ldc.i4   0x80
0x1203cc  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1203d1  stfld    int32 System.Web.Security.SqlMembershipProvider::_MinRequiredPasswordLength
0x1203d6  ldarg.0
0x1203d7  ldarg.2
0x1203d8  ldstr    aMinrequirednon// "minRequiredNonalphanumericCharacters"
0x1203dd  ldc.i4.1
0x1203de  ldc.i4.1
0x1203df  ldc.i4   0x80
0x1203e4  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x1203e9  stfld    int32 System.Web.Security.SqlMembershipProvider::_MinRequiredNonalphanumericCharacters
0x1203ee  ldarg.0
0x1203ef  ldarg.2
0x1203f0  ldstr    aPasswordstreng_0// "passwordStrengthRegexTimeout"
0x1203f5  call     valuetype [mscorlib]System.Nullable`1<int32> System.Web.Util.SecUtility::GetNullableIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName)
0x1203fa  stfld    valuetype [mscorlib]System.Nullable`1<int32> System.Web.Security.SqlMembershipProvider::_passwordStrengthRegexTimeout
0x1203ff  ldarg.0
0x120400  ldarg.2
0x120401  ldstr    aPasswordstreng_1// "passwordStrengthRegularExpression"
0x120406  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12040b  stfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x120410  ldarg.0
0x120411  ldfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x120416  brfalse.s loc_120452
0x120418  ldarg.0
0x120419  ldarg.0
0x12041a  ldfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x12041f  callvirt instance string [mscorlib]System.String::Trim()
0x120424  stfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x120429  ldarg.0
0x12042a  ldfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x12042f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x120434  brfalse.s loc_12045D
0x120436  ldarg.0
0x120437  ldfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x12043c  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x120441  stloc.2
0x120442  leave.s  loc_12045D
0x120444  stloc.3
0x120445  ldloc.3
0x120446  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12044b  ldloc.3
0x12044c  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string, class [mscorlib]System.Exception)
0x120451  throw
0x120452  ldarg.0
0x120453  ldsfld   string [mscorlib]System.String::Empty
0x120458  stfld    string System.Web.Security.SqlMembershipProvider::_PasswordStrengthRegularExpression
0x12045d  ldarg.0
0x12045e  ldfld    int32 System.Web.Security.SqlMembershipProvider::_MinRequiredNonalphanumericCharacters
0x120463  ldarg.0
0x120464  ldfld    int32 System.Web.Security.SqlMembershipProvider::_MinRequiredPasswordLength
0x120469  ble.s    loc_12047B
0x12046b  ldstr    aMinrequirednon_0// "MinRequiredNonalphanumericCharacters_ca"...
0x120470  call     string System.Web.SR::GetString(string name)
0x120475  newobj   instance void System.Web.HttpException::.ctor(string message)
0x12047a  throw
0x12047b  ldarg.0
0x12047c  ldarg.2
0x12047d  ldstr    aCommandtimeout// "commandTimeout"
0x120482  ldc.i4.s 0x1E
0x120484  ldc.i4.1
0x120485  ldc.i4.0
0x120486  call     int32 System.Web.Util.SecUtility::GetIntValue(class [System]System.Collections.Specialized.NameValueCollection config, string valueName, int32 defaultValue, bool zeroAllowed, int32 maxValueAllowed)
0x12048b  stfld    int32 System.Web.Security.SqlMembershipProvider::_CommandTimeout
0x120490  ldarg.0
0x120491  ldarg.2
0x120492  ldstr    aApplicationnam// "applicationName"
0x120497  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12049c  stfld    string System.Web.Security.SqlMembershipProvider::_AppName
0x1204a1  ldarg.0
0x1204a2  ldfld    string System.Web.Security.SqlMembershipProvider::_AppName
0x1204a7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1204ac  brfalse.s loc_1204B9
0x1204ae  ldarg.0
0x1204af  call     string System.Web.Util.SecUtility::GetDefaultAppName()
0x1204b4  stfld    string System.Web.Security.SqlMembershipProvider::_AppName
0x1204b9  ldarg.0
0x1204ba  ldfld    string System.Web.Security.SqlMembershipProvider::_AppName
0x1204bf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1204c4  ldc.i4   0x100
0x1204c9  ble.s    loc_1204DB
0x1204cb  ldstr    aProviderApplic// "Provider_application_name_too_long"
0x1204d0  call     string System.Web.SR::GetString(string name)
0x1204d5  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x1204da  throw
0x1204db  ldarg.2
0x1204dc  ldstr    aPasswordformat// "passwordFormat"
0x1204e1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1204e6  stloc.0
0x1204e7  ldloc.0
0x1204e8  brtrue.s loc_1204F0
0x1204ea  ldstr    aHashed// "Hashed"
0x1204ef  stloc.0
0x1204f0  ldloc.0
0x1204f1  ldstr    aClear_0// "Clear"
0x1204f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1204fb  brtrue.s loc_120519
0x1204fd  ldloc.0
0x1204fe  ldstr    aEncrypted// "Encrypted"
0x120503  call     bool [mscorlib]System.String::op_Equality(string, string)
0x120508  brtrue.s loc_120522
0x12050a  ldloc.0
0x12050b  ldstr    aHashed// "Hashed"
0x120510  call     bool [mscorlib]System.String::op_Equality(string, string)
0x120515  brtrue.s loc_12052B
0x120517  br.s     loc_120534
0x120519  ldarg.0
0x12051a  ldc.i4.0
0x12051b  stfld    valuetype [System.Web.ApplicationServices]System.Web.Security.MembershipPasswordFormat System.Web.Security.SqlMembershipProvider::_PasswordFormat
0x120520  br.s     loc_120544
0x120522  ldarg.0
0x120523  ldc.i4.2
0x120524  stfld    valuetype [System.Web.ApplicationServices]System.Web.Security.MembershipPasswordFormat System.Web.Security.SqlMembershipProvider::_PasswordFormat
0x120529  br.s     loc_120544
0x12052b  ldarg.0
0x12052c  ldc.i4.1
0x12052d  stfld    valuetype [System.Web.ApplicationServices]System.Web.Security.MembershipPasswordFormat System.Web.Security.SqlMembershipProvider::_PasswordFormat
0x120532  br.s     loc_120544
0x120534  ldstr    aProviderBadPas// "Provider_bad_password_format"
0x120539  call     string System.Web.SR::GetString(string name)
0x12053e  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x120543  throw
0x120544  ldarg.0
0x120545  callvirt instance valuetype [System.Web.ApplicationServices]System.Web.Security.MembershipPasswordFormat [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_PasswordFormat()
0x12054a  ldc.i4.1
0x12054b  bne.un.s loc_120565
0x12054d  ldarg.0
0x12054e  callvirt instance bool [System.Web.ApplicationServices]System.Web.Security.MembershipProvider::get_EnablePasswordRetrieval()
0x120553  brfalse.s loc_120565
0x120555  ldstr    aProviderCanNot_0// "Provider_can_not_retrieve_hashed_passwo"...
0x12055a  call     string System.Web.SR::GetString(string name)
0x12055f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x120564  throw
0x120565  ldarg.0
0x120566  ldarg.2
0x120567  call     string System.Web.Util.SecUtility::GetConnectionString(class [System]System.Collections.Specialized.NameValueCollection config)
0x12056c  stfld    string System.Web.Security.SqlMembershipProvider::_sqlConnectionString
0x120571  ldarg.2
0x120572  ldstr    aPasswordcompat// "passwordCompatMode"
0x120577  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12057c  stloc.1
0x12057d  ldloc.1
0x12057e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x120583  brtrue.s loc_1205A0
0x120585  ldarg.0
0x120586  ldtoken  [System.Web.ApplicationServices]System.Web.Configuration.MembershipPasswordCompatibilityMode
0x12058b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x120590  ldloc.1
0x120591  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x120596  unbox.any [System.Web.ApplicationServices]System.Web.Configuration.MembershipPasswordCompatibilityMode
0x12059b  stfld    valuetype [System.Web.ApplicationServices]System.Web.Configuration.MembershipPasswordCompatibilityMode System.Web.Security.SqlMembershipProvider::_LegacyPasswordCompatibilityMode
0x1205a0  ldarg.2
0x1205a1  ldstr    aConnectionstri// "connectionStringName"
0x1205a6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205ab  ldarg.2
0x1205ac  ldstr    aConnectionstri_0// "connectionString"
0x1205b1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205b6  ldarg.2
0x1205b7  ldstr    aEnablepassword_0// "enablePasswordRetrieval"
0x1205bc  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205c1  ldarg.2
0x1205c2  ldstr    aEnablepassword// "enablePasswordReset"
0x1205c7  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205cc  ldarg.2
0x1205cd  ldstr    aRequiresquesti// "requiresQuestionAndAnswer"
0x1205d2  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205d7  ldarg.2
0x1205d8  ldstr    aApplicationnam// "applicationName"
0x1205dd  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205e2  ldarg.2
0x1205e3  ldstr    aRequiresunique// "requiresUniqueEmail"
0x1205e8  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205ed  ldarg.2
0x1205ee  ldstr    aMaxinvalidpass// "maxInvalidPasswordAttempts"
0x1205f3  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x1205f8  ldarg.2
0x1205f9  ldstr    aPasswordattemp// "passwordAttemptWindow"
0x1205fe  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120603  ldarg.2
0x120604  ldstr    aCommandtimeout// "commandTimeout"
0x120609  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x12060e  ldarg.2
0x12060f  ldstr    aPasswordformat// "passwordFormat"
0x120614  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120619  ldarg.2
0x12061a  ldstr    aName// "name"
0x12061f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120624  ldarg.2
0x120625  ldstr    aMinrequiredpas// "minRequiredPasswordLength"
0x12062a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x12062f  ldarg.2
0x120630  ldstr    aMinrequirednon// "minRequiredNonalphanumericCharacters"
0x120635  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x12063a  ldarg.2
0x12063b  ldstr    aPasswordstreng_1// "passwordStrengthRegularExpression"
0x120640  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120645  ldarg.2
0x120646  ldstr    aPasswordcompat// "passwordCompatMode"
0x12064b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x120650  ldarg.2
0x120651  ldstr    aPasswordstreng_0// "passwordStrengthRegexTimeout"
0x120656  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x12065b  ldarg.2
0x12065c  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x120661  ldc.i4.0
0x120662  ble.s    loc_120691
0x120664  ldarg.2
0x120665  ldc.i4.0
0x120666  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::GetKey(int32)
0x12066b  stloc.s  4
0x12066d  ldloc.s  4
0x12066f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x120674  brtrue.s loc_120691
0x120676  ldstr    aProviderUnreco// "Provider_unrecognized_attribute"
0x12067b  ldc.i4.1
0x12067c  newarr   [mscorlib]System.Object
0x120681  dup
0x120682  ldc.i4.0
0x120683  ldloc.s  4
0x120685  stelem.ref
0x120686  call     string System.Web.SR::GetString(string name, object[] args)
0x12068b  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
  ... truncated ...
```
