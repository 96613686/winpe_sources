# Microsoft.SharePoint.SPEvaluatorModeProvisioner::Provision

- ea: `0x3af020`
- end: `0x3af4a5`
- name: `Microsoft.SharePoint.SPEvaluatorModeProvisioner::Provision`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x3ae330`

## callees

- `0x190d10`
- `0x1b7de0`
- `0x1c8630`
- `0x1c8640`
- `0x1c89b0`
- `0x1fab70`
- `0x227b70`
- `0x26b410`
- `0x26fa60`
- `0x28d2a0`
- `0x2b81e0`
- `0x2b83f0`
- `0x2eb850`
- `0x2eba00`
- `0x2f3de0`
- `0x31c280`
- `0x31ea50`
- `0x324ec0`
- `0x32cb80`
- `0x32cdb0`
- `0x3aee00`
- `0x3aee60`
- `0x3aee80`
- `0x3aef50`
- `0x3af020`
- `0x3af4b0`
- `0x3af900`
- `0x3af920`
- `0x3af930`
- `0x3af940`
- `0x577060`
- `0x5c0760`

## string_xrefs

- `0x3af17f`: `SomeoneExampleCom`
- `0x3af1b6`: `SPEvaluatorModeProvisioner.Provision failed: SPWebService.ContentService is null.`
- `0x3af1c6`: `SPWebService.ContentService`
- `0x3af1e3`: `SPEvaluatorModeProvisioner.Provision failed: SPWebService.ContentService.DefaultDatabaseInstance is null.`
- `0x3af1f3`: `SPWebService.ContentService.DefaultDatabaseInstance`
- `0x3af216`: `SPEvaluatorModeProvisioner.Provision failed: SPWebService.ContentService.DefaultDatabaseInstance.NormalizedDataSource is null.`
- `0x3af226`: `SPWebService.ContentService.DefaultDatabaseInstance.NormalizedDataSource`
- `0x3af2da`: `SPGlobalAdmin.ExtendVirtualServer() succeeded.  Now, creating the site using the {0} template`
- `0x3af382`: `Successfully created the default content site. Now, creating default SharePoint groups.`
- `0x3af3a2`: `Default sharepoint groups were created.`
- `0x3af3d2`: `A default content site already exists on this server, so we will not re-create it`
- `0x3af3f3`: `This server does not have a content service installed.  This server should have been created when joined to a farm`
- `0x3af42f`: `This content service does not have a content service instance.  One has not been created yet.`
- `0x3af450`: `Status of the content service instance is {0}`
- `0x3af47c`: `Changed status of the content service instance to {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3af020  ldstr    aSpevaluatormod_10// "SPEvaluatorModeProvisioner.Provision"
0x3af025  call     void Microsoft.SharePoint.Tracer::Enter(string function)
0x3af02a  ldarg.0
0x3af02b  call     instance void Microsoft.SharePoint.SPEvaluatorModeProvisioner::ApplyDefaults()
0x3af030  ldarg.0
0x3af031  callvirt instance bool Microsoft.SharePoint.SPEvaluatorModeProvisioner::IsProvisioned()
0x3af036  brtrue   loc_3AF3D2
0x3af03b  ldnull
0x3af03c  stloc.0
0x3af03d  ldnull
0x3af03e  stloc.1
0x3af03f  ldnull
0x3af040  stloc.2
0x3af041  ldnull
0x3af042  stloc.3
0x3af043  newobj   instance void Microsoft.SharePoint.Administration.SPGlobalAdmin::.ctor()
0x3af048  stloc.s  4
0x3af04a  ldnull
0x3af04b  stloc.s  5
0x3af04d  ldstr    aTheDefaultSite// "The default site url is {0}, port {1}"
0x3af052  ldc.i4.2
0x3af053  newarr   [mscorlib]System.Object
0x3af058  stloc.s  0xE
0x3af05a  ldloc.s  0xE
0x3af05c  ldc.i4.0
0x3af05d  ldarg.0
0x3af05e  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af063  callvirt instance string [mscorlib]System.Object::ToString()
0x3af068  stelem.ref
0x3af069  ldloc.s  0xE
0x3af06b  ldc.i4.1
0x3af06c  ldarg.0
0x3af06d  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af072  callvirt instance int32 [System]System.Uri::get_Port()
0x3af077  box      [mscorlib]System.Int32
0x3af07c  stelem.ref
0x3af07d  ldloc.s  0xE
0x3af07f  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af084  ldarg.0
0x3af085  call     instance string Microsoft.SharePoint.SPEvaluatorModeProvisioner::get_SiteOwnerAccount()
0x3af08a  stloc.1
0x3af08b  ldloc.1
0x3af08c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3af091  brfalse.s loc_3AF0AE
0x3af093  ldstr    aTheOwnerAccoun// "The owner account is null or empty."
0x3af098  ldc.i4.0
0x3af099  newarr   [mscorlib]System.Object
0x3af09e  call     void Microsoft.SharePoint.Tracer::TraceLogError(string toTrace, object[] args)
0x3af0a3  ldstr    aOwneraccount// "ownerAccount"
0x3af0a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3af0ad  throw
0x3af0ae  ldstr    aTheOwnerAccoun_0// "The owner account for the default site "...
0x3af0b3  ldc.i4.1
0x3af0b4  newarr   [mscorlib]System.Object
0x3af0b9  stloc.s  0xF
0x3af0bb  ldloc.s  0xF
0x3af0bd  ldc.i4.0
0x3af0be  ldloc.1
0x3af0bf  stelem.ref
0x3af0c0  ldloc.s  0xF
0x3af0c2  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af0c7  ldloc.s  4
0x3af0c9  ldloc.1
0x3af0ca  ldloca.s 3
0x3af0cc  ldloca.s 2
0x3af0ce  call     void Microsoft.SharePoint.Utilities.SPUtility::GetNTFullNameandEmailfromLogin(class Microsoft.SharePoint.Administration.SPGlobalAdmin globalAdmin, string login, [out] string& displayName, [out] string& email)
0x3af0d3  leave    loc_3AF174
0x3af0d8  stloc.s  6
0x3af0da  ldstr    aSputilityGetnt// "SPUtility.GetNTFullNameandEmailfromLogi"...
0x3af0df  ldc.i4.5
0x3af0e0  newarr   [mscorlib]System.Object
0x3af0e5  stloc.s  0x10
0x3af0e7  ldloc.s  0x10
0x3af0e9  ldc.i4.0
0x3af0ea  ldloc.1
0x3af0eb  stelem.ref
0x3af0ec  ldloc.s  0x10
0x3af0ee  ldc.i4.1
0x3af0ef  ldloc.s  6
0x3af0f1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3af0f6  stelem.ref
0x3af0f7  ldloc.s  0x10
0x3af0f9  ldc.i4.2
0x3af0fa  ldloc.s  6
0x3af0fc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3af101  callvirt instance string [mscorlib]System.Object::ToString()
0x3af106  stelem.ref
0x3af107  ldloc.s  0x10
0x3af109  ldc.i4.3
0x3af10a  ldloc.s  6
0x3af10c  callvirt instance string [mscorlib]System.Exception::get_Source()
0x3af111  stelem.ref
0x3af112  ldloc.s  0x10
0x3af114  ldc.i4.4
0x3af115  ldloc.s  6
0x3af117  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3af11c  stelem.ref
0x3af11d  ldloc.s  0x10
0x3af11f  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af124  leave.s  loc_3AF174
0x3af126  stloc.s  7
0x3af128  ldstr    aSputilityGetnt_0// "SPUtility.GetNTFullNameandEmailfromLogi"...
0x3af12d  ldc.i4.5
0x3af12e  newarr   [mscorlib]System.Object
0x3af133  stloc.s  0x11
0x3af135  ldloc.s  0x11
0x3af137  ldc.i4.0
0x3af138  ldloc.1
0x3af139  stelem.ref
0x3af13a  ldloc.s  0x11
0x3af13c  ldc.i4.1
0x3af13d  ldloc.s  7
0x3af13f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3af144  stelem.ref
0x3af145  ldloc.s  0x11
0x3af147  ldc.i4.2
0x3af148  ldloc.s  7
0x3af14a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3af14f  callvirt instance string [mscorlib]System.Object::ToString()
0x3af154  stelem.ref
0x3af155  ldloc.s  0x11
0x3af157  ldc.i4.3
0x3af158  ldloc.s  7
0x3af15a  callvirt instance string [mscorlib]System.Exception::get_Source()
0x3af15f  stelem.ref
0x3af160  ldloc.s  0x11
0x3af162  ldc.i4.4
0x3af163  ldloc.s  7
0x3af165  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3af16a  stelem.ref
0x3af16b  ldloc.s  0x11
0x3af16d  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af172  leave.s  loc_3AF174
0x3af174  ldloc.2
0x3af175  brfalse.s loc_3AF17F
0x3af177  ldloc.2
0x3af178  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3af17d  brtrue.s loc_3AF190
0x3af17f  ldstr    aSomeoneexample// "SomeoneExampleCom"
0x3af184  ldc.i4.0
0x3af185  newarr   [mscorlib]System.Object
0x3af18a  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x3af18f  stloc.2
0x3af190  ldstr    aTheOwnerEmailF// "The owner email for the default site is"...
0x3af195  ldc.i4.1
0x3af196  newarr   [mscorlib]System.Object
0x3af19b  stloc.s  0x12
0x3af19d  ldloc.s  0x12
0x3af19f  ldc.i4.0
0x3af1a0  ldloc.2
0x3af1a1  stelem.ref
0x3af1a2  ldloc.s  0x12
0x3af1a4  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af1a9  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPWebService::get_ContentService()
0x3af1ae  ldnull
0x3af1af  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x3af1b4  brfalse.s loc_3AF1D1
0x3af1b6  ldstr    aSpevaluatormod_11// "SPEvaluatorModeProvisioner.Provision fa"...
0x3af1bb  ldc.i4.0
0x3af1bc  newarr   [mscorlib]System.Object
0x3af1c1  call     void Microsoft.SharePoint.Tracer::TraceLogError(string toTrace, object[] args)
0x3af1c6  ldstr    aSpwebserviceCo_0// "SPWebService.ContentService"
0x3af1cb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3af1d0  throw
0x3af1d1  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPWebService::get_ContentService()
0x3af1d6  callvirt instance class Microsoft.SharePoint.Administration.SPDatabaseServiceInstance Microsoft.SharePoint.Administration.SPWebService::get_DefaultDatabaseInstance()
0x3af1db  ldnull
0x3af1dc  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x3af1e1  brfalse.s loc_3AF1FE
0x3af1e3  ldstr    aSpevaluatormod_12// "SPEvaluatorModeProvisioner.Provision fa"...
0x3af1e8  ldc.i4.0
0x3af1e9  newarr   [mscorlib]System.Object
0x3af1ee  call     void Microsoft.SharePoint.Tracer::TraceLogError(string toTrace, object[] args)
0x3af1f3  ldstr    aSpwebserviceCo_1// "SPWebService.ContentService.DefaultData"...
0x3af1f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3af1fd  throw
0x3af1fe  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPWebService::get_ContentService()
0x3af203  callvirt instance class Microsoft.SharePoint.Administration.SPDatabaseServiceInstance Microsoft.SharePoint.Administration.SPWebService::get_DefaultDatabaseInstance()
0x3af208  callvirt instance string Microsoft.SharePoint.Administration.SPDatabaseServiceInstance::get_NormalizedDataSource()
0x3af20d  stloc.0
0x3af20e  ldloc.0
0x3af20f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3af214  brfalse.s loc_3AF231
0x3af216  ldstr    aSpevaluatormod_13// "SPEvaluatorModeProvisioner.Provision fa"...
0x3af21b  ldc.i4.0
0x3af21c  newarr   [mscorlib]System.Object
0x3af221  call     void Microsoft.SharePoint.Tracer::TraceLogError(string toTrace, object[] args)
0x3af226  ldstr    aSpwebserviceCo_2// "SPWebService.ContentService.DefaultData"...
0x3af22b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3af230  throw
0x3af231  ldstr    aTheDbServerFor// "The db server for the default site is {"...
0x3af236  ldc.i4.1
0x3af237  newarr   [mscorlib]System.Object
0x3af23c  stloc.s  0x13
0x3af23e  ldloc.s  0x13
0x3af240  ldc.i4.0
0x3af241  ldloc.0
0x3af242  stelem.ref
0x3af243  ldloc.s  0x13
0x3af245  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af24a  ldarg.0
0x3af24b  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisioningAssemblyTemplate
0x3af250  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3af255  brtrue.s loc_3AF261
0x3af257  ldarg.0
0x3af258  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisioningAssemblyTemplate
0x3af25d  stloc.s  5
0x3af25f  br.s     loc_3AF269
0x3af261  ldarg.0
0x3af262  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::siteTemplate
0x3af267  stloc.s  5
0x3af269  ldnull
0x3af26a  stloc.s  8
0x3af26c  ldarg.0
0x3af26d  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af272  call     class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPWebApplication::Lookup(class [System]System.Uri requestUri)
0x3af277  stloc.s  9
0x3af279  ldnull
0x3af27a  ldloc.s  9
0x3af27c  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x3af281  brfalse  loc_3AF33C
0x3af286  ldstr    aCallingSpgloba// "Calling SPGlobalAdmin.ExtendVirtualServ"...
0x3af28b  ldc.i4.0
0x3af28c  newarr   [mscorlib]System.Object
0x3af291  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af296  ldloc.s  4
0x3af298  ldc.i4.1
0x3af299  ldc.i4.1
0x3af29a  ldloc.0
0x3af29b  ldnull
0x3af29c  ldnull
0x3af29d  ldnull
0x3af29e  ldarg.0
0x3af29f  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af2a4  ldarg.0
0x3af2a5  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::webSiteName
0x3af2aa  ldc.i4.1
0x3af2ab  ldarg.0
0x3af2ac  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::siteApplicationPoolName
0x3af2b1  ldarg.0
0x3af2b2  call     instance string Microsoft.SharePoint.SPEvaluatorModeProvisioner::get_ApplicationPoolUser()
0x3af2b7  call     valuetype Microsoft.SharePoint.Administration.IdentityType Microsoft.SharePoint.Administration.SPProcessIdentity::GetIdentityType(string username)
0x3af2bc  ldc.i4.3
0x3af2bd  ceq
0x3af2bf  ldarg.0
0x3af2c0  call     instance string Microsoft.SharePoint.SPEvaluatorModeProvisioner::get_ApplicationPoolUser()
0x3af2c5  ldarg.0
0x3af2c6  call     instance class [mscorlib]System.Security.SecureString Microsoft.SharePoint.SPEvaluatorModeProvisioner::get_ApplicationPoolPassword()
0x3af2cb  ldc.i4.0
0x3af2cc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3af2d1  ldc.i4.0
0x3af2d2  ldc.i4.0
0x3af2d3  callvirt instance class Microsoft.SharePoint.Administration.SPVirtualServer Microsoft.SharePoint.Administration.SPGlobalAdmin::ExtendVirtualServerCore(bool bCreateContentDatabase, bool bUseClaimsAuthentication, string strDatabaseServer, string strDatabaseName, string strUserName, string strPassword, class [System]System.Uri uri, string strIisWebSiteName, bool bCreateNewAppPool, string strAppPoolId, bool bConfigurableAppPoolAccount, string strAppPoolUserName, class [mscorlib]System.Security.SecureString sstrAppPoolPassword, bool bAllowAnonymous, valuetype [mscorlib]System.Guid webAppId, bool bEnsureNTLM, bool bindHostHeaderInIis)
0x3af2d8  stloc.s  0xA
0x3af2da  ldstr    aSpglobaladminE// "SPGlobalAdmin.ExtendVirtualServer() suc"...
0x3af2df  ldc.i4.1
0x3af2e0  newarr   [mscorlib]System.Object
0x3af2e5  stloc.s  0x14
0x3af2e7  ldloc.s  0x14
0x3af2e9  ldc.i4.0
0x3af2ea  ldloc.s  5
0x3af2ec  stelem.ref
0x3af2ed  ldloc.s  0x14
0x3af2ef  call     void Microsoft.SharePoint.Tracer::TraceLogInfo(string toTrace, object[] args)
0x3af2f4  ldloc.s  0xA
0x3af2f6  callvirt instance class Microsoft.SharePoint.Administration.SPSiteCollection Microsoft.SharePoint.Administration.SPVirtualServer::get_Sites()
0x3af2fb  ldarg.0
0x3af2fc  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af301  callvirt instance string [System]System.Uri::get_Scheme()
0x3af306  ldarg.0
0x3af307  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af30c  callvirt instance string [System]System.Uri::get_Host()
0x3af311  ldarg.0
0x3af312  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af317  callvirt instance int32 [System]System.Uri::get_Port()
0x3af31c  newobj   instance void [System]System.UriBuilder::.ctor(string, string, int32)
0x3af321  callvirt instance string [mscorlib]System.Object::ToString()
0x3af326  ldarg.0
0x3af327  ldfld    string Microsoft.SharePoint.SPEvaluatorModeProvisioner::siteTitle
0x3af32c  ldnull
0x3af32d  ldc.i4.0
0x3af32e  ldloc.s  5
0x3af330  ldloc.1
0x3af331  ldloc.3
0x3af332  ldloc.2
0x3af333  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.Administration.SPSiteCollection::Add(string siteUrl, string title, string description, unsigned int32 nLCID, string webTemplate, string ownerLogin, string ownerName, string ownerEmail)
0x3af338  stloc.s  8
0x3af33a  br.s     loc_3AF382
0x3af33c  ldloc.s  9
0x3af33e  callvirt instance class Microsoft.SharePoint.Administration.SPSiteCollection Microsoft.SharePoint.Administration.SPWebApplication::get_Sites()
0x3af343  ldarg.0
0x3af344  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af349  callvirt instance string [System]System.Uri::get_Scheme()
0x3af34e  ldarg.0
0x3af34f  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af354  callvirt instance string [System]System.Uri::get_Host()
0x3af359  ldarg.0
0x3af35a  ldfld    class [System]System.Uri Microsoft.SharePoint.SPEvaluatorModeProvisioner::provisionedUri
0x3af35f  callvirt instance int32 [System]System.Uri::get_Port()
0x3af364  newobj   instance void [System]System.UriBuilder::.ctor(string, string, int32)
  ... truncated ...
```
