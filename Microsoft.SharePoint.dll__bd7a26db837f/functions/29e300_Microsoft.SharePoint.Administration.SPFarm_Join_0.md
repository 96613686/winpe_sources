# Microsoft.SharePoint.Administration.SPFarm::Join_0

- ea: `0x29e300`
- end: `0x29ef86`
- name: `Microsoft.SharePoint.Administration.SPFarm::Join_0`
- size: `3206`
- prototype: ``
- caller_count: `1`
- callee_count: `129`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x29e2f0`

## callees

- `0x36f30`
- `0x1c8480`
- `0x1c8530`
- `0x1c8540`
- `0x1c8630`
- `0x1c8640`
- `0x1c87b0`
- `0x1c8800`
- `0x1c8810`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8ee0`
- `0x1f6b80`
- `0x1f7780`
- `0x223100`
- `0x2236e0`
- `0x223950`
- `0x223ad0`
- `0x223ae0`
- `0x227310`
- `0x232050`
- `0x232440`
- `0x2325b0`
- `0x23da20`
- `0x23ddb0`
- `0x2413a0`
- `0x2413e0`
- `0x241710`
- `0x249550`
- `0x249820`
- `0x249920`
- `0x24e520`
- `0x251b10`
- `0x285d90`
- `0x285e10`
- `0x286530`
- `0x2866d0`
- `0x2939a0`
- `0x2940d0`
- `0x29d020`
- `0x29d0f0`
- `0x29d1c0`
- `0x29d1e0`
- `0x29d230`
- `0x29d250`
- `0x29d2f0`
- `0x29d420`
- `0x29d9f0`
- `0x29db00`
- `0x29e0f0`

## string_xrefs

- `0x29e35b`: `nullChildScopeReferencesDuringJoinKillSwitch`
- `0x29e381`: `FarmNotCreatedYet`
- `0x29e3bc`: `An exception occurred while unjoining an old farm before joining to a new one.  SharePoint will attempt to continue joining the new farm.  Exception message: `
- `0x29e43c`: `An exception occurred while ensuring sprequestfilteringmodule is added to ApplicationHost.config. SharePoint will attempt to continue joining the new farm.  Exception message: `
- `0x29e496`: `SPFarm.Join : ConfigurationDatabase Id is {0}`
- `0x29e654`: `Ensuring certificate authority`
- `0x29e687`: `Ensuring trusted root authority manager`
- `0x29e7ca`: `An error occured while setting the IIS static file Etag seed.  Static files may be not be cached by the browser correctly if there is more than one web front end in the farm. The error contained the following message: {0}`
- `0x29e85f`: `Ensuring UserCodeServiceInstance.`
- `0x29e884`: `Ensured UserCodeServiceInstance.`
- `0x29e8fa`: `SecurityTokenService`
- `0x29e9c3`: `Skipping Help Collection Installation timer job creation. We found a registry key that disables Help Collection Install timer job creation during setup ({0} has value '0')`
- `0x29e9d8`: `\WSS\CreateHelpCollectionJobDuringSetup`
- `0x29ea1f`: `Farm.Join: Checking ConfigDb Server id.`
- `0x29ea7d`: `ConfigurationDatabase is null`
- `0x29ea99`: `ConfigurationDatabase.Server is null`
- `0x29eaac`: `SPFarm.Join: Exception when try to fetch information of ConfigurationDatabase. {0}`
- `0x29eb4b`: `Provision web service application pools`
- `0x29eb80`: `A failure occurred while provisioning a SharePoint web service application pool: {0}`
- `0x29ebca`: `Creating SPDistributedCacheServiceInstance.`
- `0x29ebe7`: `\WindowsPowerShell\v1.0\powershell.exe.config`
- `0x29ebfc`: `\wsmprovhost.exe.config`
- `0x29ec9e`: `Successfully created and configured SPDistributedCacheServiceInstance.`
- `0x29ecb8`: `A failure occurred while creating and configuring SPDistributedCacheServiceInstance. Exception {0}.`
- `0x29ecf3`: `WARNING AppFabric 1.1 for Windows Server is not installed. Please install the AppFabric 1.1 for Windows Server and rerun the psconfig.`
- `0x29ecfd`: `Creating SPRequestManagementServiceInstance.`
- `0x29ed15`: `Creating SPRequestManagementServiceInstance.`
- `0x29ed7c`: `Installing Service Application Proxies`
- `0x29ede6`: `Creating service application proxies took: {0} sec, {1} CPU ticks, {2} SQL queries, {3} SQL duration.`
- `0x29ee4b`: `Administration.Farm.ConfigurationDatabase.New`
- `0x29eef9`: `Inner exception information for the above exception during farm.join: Exception type: {0}, Exception message {1}, Call stack: {2}`
- `0x29ef72`: `nullChildScopeReferencesDuringJoin`

## pseudocode

```c

```

## disassembly

```asm
0x29e300  ldc.i4   0x7D869C
0x29e305  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x29e30a  ldc.i4.s 0x32
0x29e30c  ldstr    aJoiningTheFarm// "Joining the farm."
0x29e311  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x29e316  ldsfld   class [mscorlib]System.Threading.Mutex Microsoft.SharePoint.Administration.SPFarm::s_FarmJoinMutex
0x29e31b  brtrue.s loc_29E32D
0x29e31d  ldc.i4.0
0x29e31e  ldstr    aGlobalSpfarmjo// "Global\\SPFarmJoinLock"
0x29e323  newobj   instance void [mscorlib]System.Threading.Mutex::.ctor(bool, string)
0x29e328  stsfld   class [mscorlib]System.Threading.Mutex Microsoft.SharePoint.Administration.SPFarm::s_FarmJoinMutex
0x29e32d  ldsfld   class [mscorlib]System.Threading.Mutex Microsoft.SharePoint.Administration.SPFarm::s_FarmJoinMutex
0x29e332  ldc.i4.0
0x29e333  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32)
0x29e338  brtrue.s loc_29E345
0x29e33a  ldstr    aThereIsAnother_0// "There is another SPFarm.Join in process"...
0x29e33f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x29e344  throw
0x29e345  ldarg.0
0x29e346  call     void Microsoft.SharePoint.Administration.SPUnattendFarmJoinHandler::Initialize(class Microsoft.SharePoint.Administration.SPFarm farm)
0x29e34b  ldarg.0
0x29e34c  call     instance void Microsoft.SharePoint.Administration.SPFarm::OnPreFarmJoin()
0x29e351  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPFarm::s_SPEED_SPFarm_nullChildScopeReferencesDuringJoinKillSwitch
0x29e356  ldstr    a20160623// "2016/06/23"
0x29e35b  ldstr    aNullchildscope// "nullChildScopeReferencesDuringJoinKillS"...
0x29e360  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x29e365  brtrue.s loc_29E36D
0x29e367  ldc.i4.1
0x29e368  call     void Microsoft.SharePoint.Utilities.SPMonitoredScope::SetNullChildrenReferencesOnDispose(bool flag)
0x29e36d  ldstr    aSpfarmJoin// "SPFarm.Join"
0x29e372  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x29e377  stloc.s  0x2C
0x29e379  ldarg.0
0x29e37a  callvirt instance valuetype Microsoft.SharePoint.Administration.SPObjectStatus Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0x29e37f  brfalse.s loc_29E397
0x29e381  ldstr    aFarmnotcreated// "FarmNotCreatedYet"
0x29e386  ldc.i4.0
0x29e387  newarr   [mscorlib]System.Object
0x29e38c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x29e391  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x29e396  throw
0x29e397  call     void Microsoft.SharePoint.Administration.SPTracingServiceInstance::StaticStart()
0x29e39c  call     bool Microsoft.SharePoint.Administration.SPFarm::get_Joined()
0x29e3a1  brfalse.s loc_29E3AD
0x29e3a3  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x29e3a8  callvirt instance void Microsoft.SharePoint.Administration.SPFarm::Unjoin()
0x29e3ad  leave.s  loc_29E3D3
0x29e3af  stloc.0
0x29e3b0  ldc.i4   0x38386165
0x29e3b5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x29e3ba  ldc.i4.s 0x32
0x29e3bc  ldstr    aAnExceptionOcc_4// "An exception occurred while unjoining a"...
0x29e3c1  ldloc.0
0x29e3c2  callvirt instance string [mscorlib]System.Object::ToString()
0x29e3c7  call     string [mscorlib]System.String::Concat(string, string)
0x29e3cc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x29e3d1  leave.s  loc_29E3D3
0x29e3d3  call     void Microsoft.SharePoint.Administration.SPServer::EnsureLocalSecurityGroups()
0x29e3d8  ldarg.0
0x29e3d9  call     instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x29e3de  call     void Microsoft.SharePoint.Administration.SPServer::StaticProvision(class Microsoft.SharePoint.Administration.SPConfigurationDatabase configurationDatabase)
0x29e3e3  ldarg.0
0x29e3e4  call     instance void Microsoft.SharePoint.Administration.SPFarm::EnsureCurrentServerProductsMatchFarmProducts()
0x29e3e9  leave.s  loc_29E427
0x29e3eb  stloc.1
0x29e3ec  ldstr    aMismatchedprod// "MismatchedProductsOnFarmJoin"
0x29e3f1  ldc.i4.0
0x29e3f2  newarr   [mscorlib]System.Object
0x29e3f7  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x29e3fc  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x29e401  stloc.2
0x29e402  ldloc.2
0x29e403  ldstr    asc_D5CC9C// "\n\n"
0x29e408  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29e40d  pop
0x29e40e  ldloc.2
0x29e40f  ldloc.1
0x29e410  callvirt instance string [mscorlib]System.Exception::get_Message()
0x29e415  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x29e41a  pop
0x29e41b  ldloc.2
0x29e41c  callvirt instance string [mscorlib]System.Object::ToString()
0x29e421  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x29e426  throw
0x29e427  call     class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement Microsoft.SharePoint.Administration.AntimalwareScanFeatureReceiver::EnsureGlobalConfiguration()
0x29e42c  pop
0x29e42d  leave.s  loc_29E453
0x29e42f  stloc.3
0x29e430  ldc.i4   0x1E39A5DE
0x29e435  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x29e43a  ldc.i4.s 0x32
0x29e43c  ldstr    aAnExceptionOcc_5// "An exception occurred while ensuring sp"...
0x29e441  ldloc.3
0x29e442  callvirt instance string [mscorlib]System.Object::ToString()
0x29e447  call     string [mscorlib]System.String::Concat(string, string)
0x29e44c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x29e451  leave.s  loc_29E453
0x29e453  ldarg.0
0x29e454  ldarg.2
0x29e455  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Administration.SPServerRole> Microsoft.SharePoint.Administration.SPFarm::ValidateAndEnforceServerRole(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Administration.SPServerRole> serverRole)
0x29e45a  starg.s  2
0x29e45c  ldarg.0
0x29e45d  call     instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x29e462  callvirt instance string Microsoft.SharePoint.Administration.SPDatabase::get_DatabaseConnectionString()
0x29e467  call     void Microsoft.SharePoint.Administration.SPConfigurationDatabase::set_RegistryConnectionString(string value)
0x29e46c  ldarg.0
0x29e46d  call     instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x29e472  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x29e477  call     void Microsoft.SharePoint.Administration.SPConfigurationDatabase::set_RegistryId(valuetype [mscorlib]System.Guid value)
0x29e47c  ldarg.0
0x29e47d  call     instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x29e482  ldnull
0x29e483  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x29e488  brfalse.s loc_29E4BE
0x29e48a  ldc.i4   0x7D869D
0x29e48f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x29e494  ldc.i4.s 0x32
0x29e496  ldstr    aSpfarmJoinConf// "SPFarm.Join : ConfigurationDatabase Id "...
0x29e49b  ldc.i4.1
0x29e49c  newarr   [mscorlib]System.Object
0x29e4a1  stloc.s  0x2D
0x29e4a3  ldloc.s  0x2D
0x29e4a5  ldc.i4.0
0x29e4a6  ldarg.0
0x29e4a7  call     instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x29e4ac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x29e4b1  box      [mscorlib]System.Guid
0x29e4b6  stelem.ref
0x29e4b7  ldloc.s  0x2D
0x29e4b9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x29e4be  ldarg.0
0x29e4bf  call     instance unsigned int16 Microsoft.SharePoint.Administration.SPFarm::get_EncodedFarmId()
0x29e4c4  call     void Microsoft.SharePoint.Administration.SPFarm::set_RegistryEncodedFarmId(unsigned int16 value)
0x29e4c9  ldnull
0x29e4ca  stloc.s  4
0x29e4cc  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPServer::get_RegistryServerId()
0x29e4d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29e4d6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29e4db  brtrue.s loc_29E4FB
0x29e4dd  ldarg.0
0x29e4de  call     instance class Microsoft.SharePoint.Administration.SPServerCollection Microsoft.SharePoint.Administration.SPFarm::get_Servers()
0x29e4e3  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPServer::get_RegistryServerId()
0x29e4e8  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServer>::get_Item(!!T0)
0x29e4ed  dup
0x29e4ee  stloc.s  4
0x29e4f0  ldnull
0x29e4f1  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x29e4f6  brfalse  loc_29E591
0x29e4fb  ldarg.0
0x29e4fc  call     instance class Microsoft.SharePoint.Administration.SPServerCollection Microsoft.SharePoint.Administration.SPFarm::get_Servers()
0x29e501  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServer>::GetEnumerator()
0x29e506  stloc.s  0x2E
0x29e508  br.s     loc_29E528
0x29e50a  ldloc.s  0x2E
0x29e50c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServer>::get_Current()
0x29e511  stloc.s  5
0x29e513  ldloc.s  5
0x29e515  callvirt instance string Microsoft.SharePoint.Administration.SPServer::get_Address()
0x29e51a  ldc.i4.1
0x29e51b  call     bool Microsoft.SharePoint.Administration.SPServer::IsLocalAddress(string address, [opt] bool tryDnsLookup)
0x29e520  brfalse.s loc_29E528
0x29e522  ldloc.s  5
0x29e524  stloc.s  4
0x29e526  br.s     loc_29E531
0x29e528  ldloc.s  0x2E
0x29e52a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x29e52f  brtrue.s loc_29E50A
0x29e531  leave.s  loc_29E53F
0x29e533  ldloc.s  0x2E
0x29e535  brfalse.s loc_29E53E
0x29e537  ldloc.s  0x2E
0x29e539  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29e53e  endfinally
0x29e53f  ldloc.s  4
0x29e541  ldnull
0x29e542  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x29e547  brfalse.s loc_29E55F
0x29e549  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x29e54e  stloc.s  6
0x29e550  call     string [mscorlib]System.Environment::get_MachineName()
0x29e555  ldarg.0
0x29e556  ldloc.s  6
0x29e558  newobj   instance void Microsoft.SharePoint.Administration.SPServer::.ctor(string address, class Microsoft.SharePoint.Administration.SPFarm farm, valuetype [mscorlib]System.Guid id)
0x29e55d  stloc.s  4
0x29e55f  ldloc.s  4
0x29e561  newobj   instance void Microsoft.SharePoint.Administration.SPServerRoleManager::.ctor(class Microsoft.SharePoint.Administration.SPServer server)
0x29e566  stloc.s  7
0x29e568  ldloc.s  7
0x29e56a  ldarga.s 2
0x29e56c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Administration.SPServerRole>::get_Value()
0x29e571  ldc.i4.1
0x29e572  callvirt instance void Microsoft.SharePoint.Administration.SPServerRoleManager::EnsureServerRole(valuetype Microsoft.SharePoint.Administration.SPServerRole serverRole, bool forceUpdate)
0x29e577  ldloc.s  4
0x29e579  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x29e57e  call     void Microsoft.SharePoint.Administration.SPServer::set_RegistryServerId(valuetype [mscorlib]System.Guid value)
0x29e583  ldloc.s  4
0x29e585  callvirt instance int32 Microsoft.SharePoint.Administration.SPServer::get_EncodedServerId()
0x29e58a  call     void Microsoft.SharePoint.Administration.SPServer::set_RegistryEncodedServerId(int32 value)
0x29e58f  br.s     loc_29E5A9
0x29e591  ldloc.s  4
0x29e593  newobj   instance void Microsoft.SharePoint.Administration.SPServerRoleManager::.ctor(class Microsoft.SharePoint.Administration.SPServer server)
0x29e598  stloc.s  8
0x29e59a  ldloc.s  8
0x29e59c  ldarga.s 2
0x29e59e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.Administration.SPServerRole>::get_Value()
0x29e5a3  ldc.i4.0
0x29e5a4  callvirt instance void Microsoft.SharePoint.Administration.SPServerRoleManager::EnsureServerRole(valuetype Microsoft.SharePoint.Administration.SPServerRole serverRole, bool forceUpdate)
0x29e5a9  ldarg.0
0x29e5aa  call     instance class Microsoft.SharePoint.Administration.SPTimerService Microsoft.SharePoint.Administration.SPFarm::get_TimerService()
0x29e5af  callvirt instance class Microsoft.SharePoint.Administration.SPProcessIdentity Microsoft.SharePoint.Administration.SPWindowsService::get_ProcessIdentity()
0x29e5b4  stloc.s  9
0x29e5b6  ldarg.0
0x29e5b7  call     instance bool Microsoft.SharePoint.Administration.SPFarm::get_ExistingPassphraseKeyIsValid()
0x29e5bc  brtrue.s loc_29E5FF
0x29e5be  ldarg.0
0x29e5bf  ldfld    unsigned int8[] Microsoft.SharePoint.Administration.SPFarm::m_rgbMasterKey
0x29e5c4  brfalse.s loc_29E5D8
0x29e5c6  call     void Microsoft.SharePoint.Administration.SPCredentialManager::CleanupMasterKey()
0x29e5cb  ldarg.0
0x29e5cc  ldfld    unsigned int8[] Microsoft.SharePoint.Administration.SPFarm::m_rgbMasterKey
0x29e5d1  call     void Microsoft.SharePoint.Administration.SPCredentialManager::SetMasterKey(unsigned int8[] rgbMasterKey)
0x29e5d6  br.s     loc_29E5FF
0x29e5d8  ldarg.0
0x29e5d9  ldfld    class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Administration.SPFarm::m_SecureStringPassphrase
0x29e5de  brtrue.s loc_29E5E7
0x29e5e0  call     unsigned int8[] Microsoft.SharePoint.Administration.SPCredentialManager::get_MasterKey()
0x29e5e5  brtrue.s loc_29E5F9
0x29e5e7  call     void Microsoft.SharePoint.Administration.SPCredentialManager::CleanupMasterKey()
0x29e5ec  ldc.i4.1
0x29e5ed  ldarg.0
0x29e5ee  ldfld    class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Administration.SPFarm::m_SecureStringPassphrase
0x29e5f3  call     unsigned int8[] Microsoft.SharePoint.Administration.SPCredentialManager::CreateMasterKey(bool generateKeyIfNeeded, class [mscorlib]System.Security.SecureString sstrPassphrase)
0x29e5f8  pop
0x29e5f9  ldarg.0
0x29e5fa  call     instance void Microsoft.SharePoint.Administration.SPFarm::OnMasterPassphraseUpdate()
0x29e5ff  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_TrustDerivedCollectionCacheRefresh()
0x29e604  brfalse.s loc_29E635
0x29e606  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x29e60b  ldnull
0x29e60c  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x29e611  brfalse.s loc_29E635
0x29e613  ldarg.0
0x29e614  call     instance class Microsoft.SharePoint.Administration.ISPPersistedStoreProvider Microsoft.SharePoint.Administration.SPPersistedObject::get_PersistedStoreProvider()
0x29e619  callvirt instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.ISPPersistedStoreProvider::get_ConfigurationDatabase()
0x29e61e  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x29e623  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x29e628  brfalse.s loc_29E635
0x29e62a  ldarg.0
0x29e62b  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x29e630  call     instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_PersistedStoreProvider(class Microsoft.SharePoint.Administration.ISPPersistedStoreProvider value)
0x29e635  ldstr    aClearingSharep// "Clearing SharePoint certificate store"
0x29e63a  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x29e63f  stloc.s  0x2F
0x29e641  call     void Microsoft.SharePoint.Administration.SPCertificateAuthority::ClearSharePointCertificateStore()
0x29e646  leave.s  loc_29E654
0x29e648  ldloc.s  0x2F
0x29e64a  brfalse.s loc_29E653
0x29e64c  ldloc.s  0x2F
0x29e64e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29e653  endfinally
0x29e654  ldstr    aEnsuringCertif// "Ensuring certificate authority"
0x29e659  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x29e65e  stloc.s  0x30
0x29e660  ldarg.0
0x29e661  call     class Microsoft.SharePoint.Administration.SPCertificateAuthority Microsoft.SharePoint.Administration.SPCertificateAuthority::EnsureLocal(class Microsoft.SharePoint.Administration.SPFarm farm)
0x29e666  stloc.s  0xA
0x29e668  ldc.i4.1
0x29e669  ldloc.s  0xA
0x29e66b  callvirt instance valuetype Microsoft.SharePoint.Administration.SPObjectStatus Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0x29e670  bne.un.s loc_29E679
0x29e672  ldloc.s  0xA
0x29e674  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x29e679  leave.s  loc_29E687
0x29e67b  ldloc.s  0x30
0x29e67d  brfalse.s loc_29E686
0x29e67f  ldloc.s  0x30
0x29e681  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29e686  endfinally
0x29e687  ldstr    aEnsuringTruste// "Ensuring trusted root authority manager"
0x29e68c  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x29e691  stloc.s  0x31
0x29e693  ldarg.0
0x29e694  call     class Microsoft.SharePoint.Administration.SPTrustedRootAuthorityManager Microsoft.SharePoint.Administration.SPTrustedRootAuthorityManager::EnsureLocal(class Microsoft.SharePoint.Administration.SPFarm farm)
0x29e699  stloc.s  0xB
0x29e69b  ldc.i4.1
0x29e69c  ldloc.s  0xB
0x29e69e  callvirt instance valuetype Microsoft.SharePoint.Administration.SPObjectStatus Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0x29e6a3  bne.un.s loc_29E6AC
0x29e6a5  ldloc.s  0xB
0x29e6a7  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x29e6ac  leave.s  loc_29E6BA
0x29e6ae  ldloc.s  0x31
0x29e6b0  brfalse.s loc_29E6B9
0x29e6b2  ldloc.s  0x31
0x29e6b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29e6b9  endfinally
0x29e6ba  ldarg.0
0x29e6bb  call     void Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::EnsureDefault(class Microsoft.SharePoint.Administration.SPFarm farm)
0x29e6c0  ldsfld   string [mscorlib]System.String::Empty
0x29e6c5  ldloc.s  4
  ... truncated ...
```
