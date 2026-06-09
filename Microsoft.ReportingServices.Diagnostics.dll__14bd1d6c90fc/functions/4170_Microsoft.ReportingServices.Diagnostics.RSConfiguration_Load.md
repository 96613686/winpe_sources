# Microsoft.ReportingServices.Diagnostics.RSConfiguration::Load

- ea: `0x4170`
- end: `0x4bc2`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::Load`
- size: `2642`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7000`
- `0x7060`
- `0x7160`
- `0x7210`
- `0x7280`

## callees

- `0x17c0`
- `0x1b40`
- `0x1da0`
- `0x2130`
- `0x22a0`
- `0x24b0`
- `0x27b0`
- `0x2940`
- `0x2e10`
- `0x3760`
- `0x4170`
- `0x5e80`
- `0x5fd0`
- `0x65e0`

## pseudocode

```c

```

## disassembly

```asm
0x4170  ldarg.2
0x4171  brfalse.s loc_4179
0x4173  ldarg.0
0x4174  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Init()
0x4179  ldarg.1
0x417a  brtrue.s loc_417D
0x417c  ret
0x417d  ldarg.1
0x417e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x4183  stloc.0
0x4184  br       loc_4B93
0x4189  ldloca.s 0
0x418b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x4190  stloc.1
0x4191  ldloca.s 1
0x4193  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x4198  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x419d  stloc.2
0x419e  ldloc.2
0x419f  brfalse  loc_4B93
0x41a4  ldloca.s 1
0x41a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x41ab  stloc.3
0x41ac  ldloc.3
0x41ad  ldc.i4.1
0x41ae  sub
0x41af  switch   loc_4391, loc_4955, loc_499F, loc_49B0, loc_49C1, loc_49D2, loc_4A05, loc_4A16, loc_4A27, loc_4A38, loc_4922, loc_4944, loc_4933, loc_4A49, loc_4A5A, loc_4A6B, loc_4A7C, loc_4B93, loc_4B93, loc_4AC0, loc_48DE, loc_48CD, loc_45AB, loc_4B93, loc_4B93, loc_4813, loc_4B93, loc_4479, loc_448A, loc_449B, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4B93, loc_4797, loc_47C7, loc_4725, loc_473A, loc_474F, loc_4773, loc_4556, loc_45BC, loc_4567, loc_4578, loc_4589, loc_459A, loc_4523, loc_4534, loc_4545, loc_44BD, loc_4703 \
0x438c  br       loc_4B93
0x4391  ldarg.0
0x4392  ldloc.2
0x4393  unbox.any [mscorlib]System.Int64
0x4398  stfld    int64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_sequence
0x439d  br       loc_4B93
0x43a2  ldarg.0
0x43a3  ldloc.2
0x43a4  castclass [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration
0x43a9  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_extensions
0x43ae  ldarg.0
0x43af  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension> Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_events
0x43b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension>::Clear()
0x43b9  ldarg.0
0x43ba  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_extensions
0x43bf  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration/ExtensionArray [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Event()
0x43c4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x43c9  stloc.s  6
0x43cb  br.s     loc_43EF
0x43cd  ldloc.s  6
0x43cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x43d4  castclass [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension
0x43d9  stloc.s  7
0x43db  ldarg.0
0x43dc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension> Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_events
0x43e1  ldloc.s  7
0x43e3  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension::get_EventType()
0x43e8  ldloc.s  7
0x43ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension>::Add(var<u1>, !!T0)
0x43ef  ldloc.s  6
0x43f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x43f6  brtrue.s loc_43CD
0x43f8  leave    loc_4B93
0x43fd  ldloc.s  6
0x43ff  isinst   [mscorlib]System.IDisposable
0x4404  stloc.s  8
0x4406  ldloc.s  8
0x4408  brfalse.s loc_4411
0x440a  ldloc.s  8
0x440c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4411  endfinally
0x4412  ldarg.0
0x4413  ldloc.2
0x4414  castclass [mscorlib]System.String
0x4419  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dsn
0x441e  br       loc_4B93
0x4423  ldarg.0
0x4424  ldloc.2
0x4425  unbox.any CatalogConnectionType
0x442a  stfld    valuetype CatalogConnectionType Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_connectionType
0x442f  br       loc_4B93
0x4434  ldarg.0
0x4435  ldloc.2
0x4436  castclass [mscorlib]System.String
0x443b  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogUser
0x4440  br       loc_4B93
0x4445  ldarg.0
0x4446  ldloc.2
0x4447  castclass [mscorlib]System.String
0x444c  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogDomain
0x4451  ldarg.0
0x4452  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogDomain
0x4457  brfalse  loc_4B93
0x445c  ldarg.0
0x445d  ldc.i4.0
0x445e  stfld    valuetype CatalogConnectionAuth Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_connectionAuth
0x4463  br       loc_4B93
0x4468  ldarg.0
0x4469  ldloc.2
0x446a  castclass [mscorlib]System.String
0x446f  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogCred
0x4474  br       loc_4B93
0x4479  ldarg.0
0x447a  ldloc.2
0x447b  castclass [mscorlib]System.String
0x4480  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_instanceID
0x4485  br       loc_4B93
0x448a  ldarg.0
0x448b  ldloc.2
0x448c  castclass [mscorlib]System.String
0x4491  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_installationID
0x4496  br       loc_4B93
0x449b  ldarg.0
0x449c  ldloc.2
0x449d  castclass [mscorlib]System.String
0x44a2  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_installationIDWebApp
0x44a7  br       loc_4B93
0x44ac  ldarg.0
0x44ad  ldloc.2
0x44ae  castclass [mscorlib]System.String
0x44b3  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_defaultViewerStyle
0x44b8  br       loc_4B93
0x44bd  ldarg.0
0x44be  ldloc.2
0x44bf  unbox.any [mscorlib]System.Int32
0x44c4  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxScheduleWait
0x44c9  br       loc_4B93
0x44ce  ldarg.0
0x44cf  ldloc.2
0x44d0  unbox.any [mscorlib]System.Int32
0x44d5  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBQueryTimeout
0x44da  br       loc_4B93
0x44df  ldarg.0
0x44e0  ldloc.2
0x44e1  unbox.any [mscorlib]System.Int32
0x44e6  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBCleanupTimeout
0x44eb  br       loc_4B93
0x44f0  ldarg.0
0x44f1  ldloc.2
0x44f2  unbox.any [mscorlib]System.Int32
0x44f7  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeout
0x44fc  br       loc_4B93
0x4501  ldarg.0
0x4502  ldloc.2
0x4503  unbox.any [mscorlib]System.Int32
0x4508  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeoutGcExtension
0x450d  br       loc_4B93
0x4512  ldarg.0
0x4513  ldloc.2
0x4514  unbox.any [mscorlib]System.Int32
0x4519  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBCleanupBatchFactor
0x451e  br       loc_4B93
0x4523  ldarg.0
0x4524  ldloc.2
0x4525  unbox.any [mscorlib]System.Int32
0x452a  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsScavengerCycleParam
0x452f  br       loc_4B93
0x4534  ldarg.0
0x4535  ldloc.2
0x4536  unbox.any [mscorlib]System.Int32
0x453b  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsDBCycleParam
0x4540  br       loc_4B93
0x4545  ldarg.0
0x4546  ldloc.2
0x4547  unbox.any [mscorlib]System.Int32
0x454c  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsAgeParam
0x4551  br       loc_4B93
0x4556  ldarg.0
0x4557  ldloc.2
0x4558  unbox.any [mscorlib]System.Int32
0x455d  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_CleanupCycleMinutesParam
0x4562  br       loc_4B93
0x4567  ldarg.0
0x4568  ldloc.2
0x4569  unbox.any [mscorlib]System.Int32
0x456e  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingCleanupCycleMinutesParam
0x4573  br       loc_4B93
0x4578  ldarg.0
0x4579  ldloc.2
0x457a  unbox.any [mscorlib]System.Int32
0x457f  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingDataCleanupMinutesParam
0x4584  br       loc_4B93
0x4589  ldarg.0
0x458a  ldloc.2
0x458b  unbox.any [mscorlib]System.Int32
0x4590  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingExecutionLogCleanupMinutesParam
0x4595  br       loc_4B93
0x459a  ldarg.0
0x459b  ldloc.2
0x459c  unbox.any [mscorlib]System.Int32
0x45a1  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingMaxDataRetentionDaysParam
0x45a6  br       loc_4B93
0x45ab  ldarg.0
0x45ac  ldloc.2
0x45ad  unbox.any [mscorlib]System.Int32
0x45b2  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxActiveReqForOneUser
0x45b7  br       loc_4B93
0x45bc  ldarg.0
0x45bd  ldloc.2
0x45be  unbox.any [mscorlib]System.Int32
0x45c3  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dailyCleanupMinuteOfDayParam
0x45c8  br       loc_4B93
0x45cd  ldarg.0
0x45ce  ldloc.2
0x45cf  unbox.any [mscorlib]System.Int32
0x45d4  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonFlags
0x45d9  br       loc_4B93
0x45de  ldloc.2
0x45df  castclass [mscorlib]System.String
0x45e4  ldc.i4.1
0x45e5  newarr   [mscorlib]System.Char
0x45ea  dup
0x45eb  ldc.i4.0
0x45ec  ldc.i4.s 0x2C
0x45ee  stelem.i2
0x45ef  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x45f4  stloc.s  4
0x45f6  ldarg.0
0x45f7  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x45fc  stfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpOnExceptions
0x4601  ldarg.0
0x4602  ldfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpOnExceptions
0x4607  ldloc.s  4
0x4609  callvirt instance void [System]System.Collections.Specialized.StringCollection::AddRange(string[])
0x460e  br       loc_4B93
0x4613  ldloc.2
0x4614  castclass [mscorlib]System.String
0x4619  ldc.i4.1
0x461a  newarr   [mscorlib]System.Char
0x461f  dup
0x4620  ldc.i4.0
0x4621  ldc.i4.s 0x2C
0x4623  stelem.i2
0x4624  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4629  stloc.s  5
0x462b  ldarg.0
0x462c  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x4631  stfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpExcludeIfContainsExceptions
0x4636  ldarg.0
0x4637  ldfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpExcludeIfContainsExceptions
0x463c  ldloc.s  5
0x463e  callvirt instance void [System]System.Collections.Specialized.StringCollection::AddRange(string[])
0x4643  br       loc_4B93
0x4648  ldarg.0
0x4649  ldloc.2
0x464a  unbox.any [mscorlib]System.Boolean
0x464f  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enablePowerBIFeatures
0x4654  br       loc_4B93
0x4659  ldarg.0
0x465a  ldloc.2
0x465b  unbox.any [mscorlib]System.Int32
0x4660  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_requiredHttpsLevel
0x4665  br       loc_4B93
0x466a  ldarg.0
0x466b  ldloc.2
0x466c  unbox.any [mscorlib]System.Boolean
0x4671  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_disableSecureFormsAuthenticationCookie
0x4676  br       loc_4B93
0x467b  ldarg.0
0x467c  ldloc.2
0x467d  unbox.any [mscorlib]System.Boolean
0x4682  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_displayErrorLink
0x4687  br       loc_4B93
0x468c  ldarg.0
0x468d  ldloc.2
0x468e  unbox.any [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage
0x4693  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_WebServiceUseFileShareStorage
0x4698  br       loc_4B93
0x469d  ldarg.0
0x469e  ldloc.2
0x469f  unbox.any [mscorlib]System.Boolean
0x46a4  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isSchedulingService
0x46a9  br       loc_4B93
0x46ae  ldarg.0
0x46af  ldloc.2
0x46b0  unbox.any [mscorlib]System.Boolean
0x46b5  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isAlertingService
0x46ba  br       loc_4B93
0x46bf  ldarg.0
0x46c0  ldloc.2
0x46c1  unbox.any [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage
0x46c6  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_windowsServiceUserFileShareStorage
0x46cb  br       loc_4B93
0x46d0  ldarg.0
0x46d1  ldloc.2
0x46d2  unbox.any [mscorlib]System.Boolean
0x46d7  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isNotificationService
0x46dc  br       loc_4B93
0x46e1  ldarg.0
0x46e2  ldloc.2
0x46e3  castclass [mscorlib]System.String
0x46e8  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRoot
0x46ed  br       loc_4B93
0x46f2  ldarg.0
0x46f3  ldloc.2
0x46f4  unbox.any [mscorlib]System.Boolean
0x46f9  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isEventService
0x46fe  br       loc_4B93
0x4703  ldarg.0
0x4704  ldloc.2
0x4705  unbox.any [mscorlib]System.Int32
0x470a  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_pollingInterval
0x470f  br       loc_4B93
  ... truncated ...
```
