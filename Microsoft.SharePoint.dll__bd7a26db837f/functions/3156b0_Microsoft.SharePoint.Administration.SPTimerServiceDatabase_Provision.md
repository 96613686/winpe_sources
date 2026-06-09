# Microsoft.SharePoint.Administration.SPTimerServiceDatabase::Provision

- ea: `0x3156b0`
- end: `0x315978`
- name: `Microsoft.SharePoint.Administration.SPTimerServiceDatabase::Provision`
- size: `712`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a2260`
- `0x1c8480`
- `0x1c8640`
- `0x1c8a20`
- `0x1c91b0`
- `0x1dbdd0`
- `0x1dbe80`
- `0x1dbf10`
- `0x1dc040`
- `0x1dc630`
- `0x2413a0`
- `0x241710`
- `0x241cc0`
- `0x241fa0`
- `0x242300`
- `0x243220`
- `0x244050`
- `0x247e60`
- `0x252a10`
- `0x254e00`
- `0x2eb6c0`
- `0x3156b0`
- `0x315a20`
- `0x315a70`
- `0x93dab0`
- `0x93dae0`
- `0x957530`
- `0xa4f6d0`
- `0xa4f9a0`

## string_xrefs

- `0x3156bc`: `Entering SPTimerServiceDatabase::Provision()`
- `0x3156de`: `Provisioning Timer Service Database with Connection String '{0}'`
- `0x315717`: `Provisioning Timer Service Database with SQL script at '{0}'`
- `0x315727`: `Template\sql\TimerServicedb.sql`
- `0x3157a0`: `Template\sql\TimerServicedb.sql`
- `0x31578b`: `SPTimerService Database does not exist or exist but is empty, provisioning the database.`
- `0x3157be`: `SPTimerService Database has been provisioned.`
- `0x31580d`: `SPTimerService Database contains valid schema, invalidating.`
- `0x315829`: `Upgrading SPTimerService database to present schema.`
- `0x31584f`: `SPTimerService Database upgraded to present schema.`
- `0x315868`: `Upgrade of SPTimerService Database '{0}' failed during DB attach.`
- `0x31588d`: `Database {0} at Server {1} is at invalid state and cannot be used for SPTimerService database.`
- `0x3158d2`: `Ensure that timer service has access to SPTimerService database.`
- `0x3158ee`: `Ensure that application pool account has access to SPTimerService database.`
- `0x31591e`: `Ensure SQL roles on objects of SPTimerService database '{0}' failed.`
- `0x31594a`: `Set SPTimerService database status to Online.`
- `0x31596d`: `Exiting SPTimerServiceDatabase::Provision()`

## pseudocode

```c

```

## disassembly

```asm
0x3156b0  ldc.i4   0x17D8383
0x3156b5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3156ba  ldc.i4.s 0x14
0x3156bc  ldstr    aEnteringSptime// "Entering SPTimerServiceDatabase::Provis"...
0x3156c1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3156c6  ldarg.0
0x3156c7  ldc.i4.4
0x3156c8  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype Microsoft.SharePoint.Administration.SPObjectStatus value)
0x3156cd  ldc.i4   0x17D8384
0x3156d2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3156d7  ldc.i4.s 0x14
0x3156d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3156de  ldstr    aProvisioningTi// "Provisioning Timer Service Database wit"...
0x3156e3  ldc.i4.1
0x3156e4  newarr   [mscorlib]System.Object
0x3156e9  stloc.s  6
0x3156eb  ldloc.s  6
0x3156ed  ldc.i4.0
0x3156ee  ldarg.0
0x3156ef  call     instance string Microsoft.SharePoint.Administration.SPDatabase::get_DatabaseConnectionString()
0x3156f4  call     string Microsoft.SharePoint.Utilities.SqlSession::GetConnectionStringForLogging(string connectionString)
0x3156f9  stelem.ref
0x3156fa  ldloc.s  6
0x3156fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x315701  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315706  ldc.i4   0x17D8385
0x31570b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x315710  ldc.i4.s 0x14
0x315712  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x315717  ldstr    aProvisioningTi_0// "Provisioning Timer Service Database wit"...
0x31571c  ldc.i4.1
0x31571d  newarr   [mscorlib]System.Object
0x315722  stloc.s  7
0x315724  ldloc.s  7
0x315726  ldc.i4.0
0x315727  ldstr    aTemplateSqlTim// "Template\\sql\\TimerServicedb.sql"
0x31572c  ldc.i4.s 0xF
0x31572e  call     string Microsoft.SharePoint.Utilities.SPUtility::GetVersionedGenericSetupPath(string strSubdir, int32 desiredPathVersion)
0x315733  stelem.ref
0x315734  ldloc.s  7
0x315736  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31573b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315740  ldc.i4.0
0x315741  stloc.0
0x315742  ldarg.0
0x315743  call     instance bool Microsoft.SharePoint.Administration.SPDatabase::get_Exists()
0x315748  stloc.1
0x315749  ldc.i4.0
0x31574a  stloc.2
0x31574b  ldloc.1
0x31574c  brfalse.s loc_315761
0x31574e  ldarg.0
0x31574f  call     instance bool Microsoft.SharePoint.Administration.SPDatabase::IsEmpty()
0x315754  stloc.2
0x315755  ldarg.0
0x315756  ldstr    aTimerjobhistor// "TimerJobHistory"
0x31575b  call     instance bool Microsoft.SharePoint.Administration.SPDatabase::TableExists(string name)
0x315760  stloc.0
0x315761  ldloc.1
0x315762  brfalse.s loc_31576A
0x315764  ldloc.1
0x315765  brfalse.s loc_3157D4
0x315767  ldloc.2
0x315768  brfalse.s loc_3157D4
0x31576a  ldarg.0
0x31576b  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x315770  ldc.i4.1
0x315771  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype DatabaseOptions, bool>::.ctor(int32)
0x315776  stloc.3
0x315777  ldloc.3
0x315778  ldc.i4.2
0x315779  ldc.i4.0
0x31577a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype DatabaseOptions, bool>::Add(var<u1>, !!T0)
0x31577f  ldc.i4   0x17D8386
0x315784  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x315789  ldc.i4.s 0x14
0x31578b  ldstr    aSptimerservice// "SPTimerService Database does not exist "...
0x315790  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315795  ldarg.0
0x315796  call     instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_AdminSqlSession()
0x31579b  callvirt instance string Microsoft.SharePoint.Utilities.SqlSession::get_ConnectionString()
0x3157a0  ldstr    aTemplateSqlTim// "Template\\sql\\TimerServicedb.sql"
0x3157a5  ldc.i4.s 0xF
0x3157a7  call     string Microsoft.SharePoint.Utilities.SPUtility::GetVersionedGenericSetupPath(string strSubdir, int32 desiredPathVersion)
0x3157ac  ldloc.3
0x3157ad  call     void Microsoft.SharePoint.Administration.SPDatabase::Provision(string connectionString, string provisioningScriptPath, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype DatabaseOptions, bool> options)
0x3157b2  ldc.i4   0x17D8387
0x3157b7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3157bc  ldc.i4.s 0x14
0x3157be  ldstr    aSptimerservice_0// "SPTimerService Database has been provis"...
0x3157c3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3157c8  ldarg.0
0x3157c9  ldc.i4.0
0x3157ca  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::set_NeedsUpgrade(bool value)
0x3157cf  br       loc_3158C0
0x3157d4  ldloc.0
0x3157d5  brfalse  loc_315888
0x3157da  ldarg.0
0x3157db  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::UpdateWithNoObjectCallbackCheck()
0x3157e0  ldarg.0
0x3157e1  callvirt instance bool Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::get_NeedsUpgrade()
0x3157e6  brfalse  loc_3158C0
0x3157eb  ldarg.0
0x3157ec  call     instance bool Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::get_ShouldDeferUpgradeActions()
0x3157f1  brtrue   loc_3158C0
0x3157f6  ldarg.0
0x3157f7  callvirt instance valuetype Microsoft.SharePoint.TriState Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::get_IsBackwardsCompatible()
0x3157fc  brtrue   loc_3158C0
0x315801  ldc.i4   0x17D8388
0x315806  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31580b  ldc.i4.s 0x14
0x31580d  ldstr    aSptimerservice_1// "SPTimerService Database contains valid "...
0x315812  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315817  ldarg.0
0x315818  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedUpgradableObject::Invalidate()
0x31581d  ldc.i4   0x17D8389
0x315822  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x315827  ldc.i4.s 0x14
0x315829  ldstr    aUpgradingSptim// "Upgrading SPTimerService database to pr"...
0x31582e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315833  call     class Microsoft.SharePoint.Upgrade.SPManager Microsoft.SharePoint.Upgrade.SPManager::get_Instance()
0x315838  stloc.s  4
0x31583a  ldloc.s  4
0x31583c  ldarg.0
0x31583d  ldc.i4.1
0x31583e  callvirt instance void Microsoft.SharePoint.Upgrade.SPManager::RunUpgradeSession(class Microsoft.SharePoint.Administration.IUpgradable iup, bool bRecursive)
0x315843  ldc.i4   0x17D838A
0x315848  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31584d  ldc.i4.s 0x14
0x31584f  ldstr    aSptimerservice_2// "SPTimerService Database upgraded to pre"...
0x315854  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315859  leave.s  loc_3158C0
0x31585b  pop
0x31585c  ldc.i4   0x17D838B
0x315861  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x315866  ldc.i4.s 0xA
0x315868  ldstr    aUpgradeOfSptim// "Upgrade of SPTimerService Database '{0}"...
0x31586d  ldc.i4.1
0x31586e  newarr   [mscorlib]System.Object
0x315873  stloc.s  8
0x315875  ldloc.s  8
0x315877  ldc.i4.0
0x315878  ldarg.0
0x315879  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x31587e  stelem.ref
0x31587f  ldloc.s  8
0x315881  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x315886  rethrow
0x315888  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31588d  ldstr    aDatabase0AtSer_0// "Database {0} at Server {1} is at invali"...
0x315892  ldc.i4.2
0x315893  newarr   [mscorlib]System.Object
0x315898  stloc.s  9
0x31589a  ldloc.s  9
0x31589c  ldc.i4.0
0x31589d  ldarg.0
0x31589e  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3158a3  stelem.ref
0x3158a4  ldloc.s  9
0x3158a6  ldc.i4.1
0x3158a7  ldarg.0
0x3158a8  call     instance class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPDatabase::get_Server()
0x3158ad  callvirt instance string Microsoft.SharePoint.Administration.SPServer::get_Address()
0x3158b2  stelem.ref
0x3158b3  ldloc.s  9
0x3158b5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3158ba  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3158bf  throw
0x3158c0  ldarg.0
0x3158c1  call     instance void Microsoft.SharePoint.Administration.SPDatabase::GrantOwnerAccessToDatabaseAccount()
0x3158c6  ldc.i4   0x17D838C
0x3158cb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3158d0  ldc.i4.s 0x14
0x3158d2  ldstr    aEnsureThatTime// "Ensure that timer service has access to"...
0x3158d7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3158dc  ldarg.0
0x3158dd  call     instance void Microsoft.SharePoint.Administration.SPTimerServiceDatabase::EnsureTimerServiceAccess()
0x3158e2  ldc.i4   0x17D838D
0x3158e7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3158ec  ldc.i4.s 0x14
0x3158ee  ldstr    aEnsureThatAppl// "Ensure that application pool account ha"...
0x3158f3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3158f8  ldarg.0
0x3158f9  call     instance void Microsoft.SharePoint.Administration.SPTimerServiceDatabase::EnsureApplicationPoolAccess()
0x3158fe  leave.s  loc_31593E
0x315900  stloc.s  5
0x315902  ldloc.s  5
0x315904  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x315909  ldc.i4   0xF42
0x31590e  beq.s    loc_315912
0x315910  rethrow
0x315912  ldc.i4   0x17D838E
0x315917  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31591c  ldc.i4.s 0xA
0x31591e  ldstr    aEnsureSqlRoles_0// "Ensure SQL roles on objects of SPTimerS"...
0x315923  ldc.i4.1
0x315924  newarr   [mscorlib]System.Object
0x315929  stloc.s  0xA
0x31592b  ldloc.s  0xA
0x31592d  ldc.i4.0
0x31592e  ldarg.0
0x31592f  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x315934  stelem.ref
0x315935  ldloc.s  0xA
0x315937  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x31593c  leave.s  loc_31593E
0x31593e  ldc.i4   0x17D838F
0x315943  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x315948  ldc.i4.s 0x14
0x31594a  ldstr    aSetSptimerserv// "Set SPTimerService database status to O"...
0x31594f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315954  ldarg.0
0x315955  ldc.i4.0
0x315956  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::set_Status(valuetype Microsoft.SharePoint.Administration.SPObjectStatus value)
0x31595b  ldarg.0
0x31595c  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x315961  ldc.i4   0x17D8390
0x315966  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x31596b  ldc.i4.s 0x14
0x31596d  ldstr    aExitingSptimer_2// "Exiting SPTimerServiceDatabase::Provisi"...
0x315972  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x315977  ret
```
