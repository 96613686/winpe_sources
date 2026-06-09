# Microsoft.ReportingServices.Library.Security::UpdateSecurityPolicies

- ea: `0x49190`
- end: `0x495b2`
- name: `Microsoft.ReportingServices.Library.Security::UpdateSecurityPolicies`
- size: `1058`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xfea0`

## callees

- `0x49190`
- `0x495c0`
- `0x49640`
- `0x496c0`
- `0x49730`
- `0x4b0e0`
- `0x8b090`
- `0x8b1d0`
- `0x8b210`
- `0x8b220`

## string_xrefs

- `0x493c4`: `UpdatePolicy`
- `0x491e9`: `Validating {0} out-of-date security policies.`
- `0x49292`: `Invalid security policy {0}: Exception on load: {1}`
- `0x492eb`: `Invalid security policy {0}:[{1}]: Unknown SecurityItemType`
- `0x49374`: `Marking {0} invalid security policies as orphaned.`
- `0x4948c`: `AD domain access denied {0}`
- `0x494b6`: `Invalid security policy {0}:[{1}]: {2}`
- `0x49573`: `Validated {0} security policies: valid:{1}, invalid:{2}, out-of-date left to be validated:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x49190  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::.ctor()
0x49195  stloc.0
0x49196  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::.ctor()
0x4919b  stloc.1
0x4919c  ldc.i4.0
0x4919d  stloc.2
0x4919e  ldsfld   class [mscorlib]System.Func`2<class SecurityPolicy, string> <>c::<>9__24_0
0x491a3  dup
0x491a4  brtrue.s loc_491BD
0x491a6  pop
0x491a7  ldsfld   class <>c <>c::<>9
0x491ac  ldftn    instance string <>c::<UpdateSecurityPolicies>b__24_0(class SecurityPolicy policy)
0x491b2  newobj   instance void class [mscorlib]System.Func`2<class SecurityPolicy, string>::.ctor(object, native int)
0x491b7  dup
0x491b8  stsfld   class [mscorlib]System.Func`2<class SecurityPolicy, string> <>c::<>9__24_0
0x491bd  stloc.3
0x491be  ldarg.0
0x491bf  call     instance bool Microsoft.ReportingServices.Library.Security::HasDirtyPolicies()
0x491c4  brtrue.s loc_491C8
0x491c6  ldc.i4.0
0x491c7  ret
0x491c8  ldarg.0
0x491c9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.ReportingServices.Library.Security::GetPolicyStates()
0x491ce  stloc.s  4
0x491d0  ldloc.s  4
0x491d2  ldc.i4.1
0x491d3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x491d8  brfalse.s loc_491E3
0x491da  ldloc.s  4
0x491dc  ldc.i4.1
0x491dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x491e2  stloc.2
0x491e3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x491e8  ldc.i4.3
0x491e9  ldstr    aValidating0Out// "Validating {0} out-of-date security pol"...
0x491ee  ldc.i4.1
0x491ef  newarr   [mscorlib]System.Object
0x491f4  dup
0x491f5  ldc.i4.0
0x491f6  ldloc.2
0x491f7  box      [mscorlib]System.Int32
0x491fc  stelem.ref
0x491fd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x49202  ldc.i4.0
0x49203  stloc.s  5
0x49205  ldarg.0
0x49206  ldstr    aGetinvalidpoli// "GetInvalidPolicies"
0x4920b  ldnull
0x4920c  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49211  stloc.s  9
0x49213  ldloc.s  9
0x49215  ldstr    aTopcount// "@TopCount"
0x4921a  ldc.i4.8
0x4921b  ldarg.1
0x4921c  box      [mscorlib]System.Int32
0x49221  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49226  pop
0x49227  ldloc.s  9
0x49229  ldstr    aAuthtype// "@AuthType"
0x4922e  ldc.i4.8
0x4922f  ldarg.0
0x49230  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x49235  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x4923a  box      [mscorlib]System.Int32
0x4923f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49244  pop
0x49245  ldloc.s  9
0x49247  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x4924c  stloc.s  0xA
0x4924e  ldnull
0x4924f  stloc.s  0xB
0x49251  br       loc_49344
0x49256  ldc.i4.1
0x49257  stloc.s  5
0x49259  ldloc.s  0xA
0x4925b  ldc.i4.0
0x4925c  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x49261  stloc.s  0xC
0x49263  ldloc.0
0x49264  ldloc.s  0xC
0x49266  ldloca.s 0xB
0x49268  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::TryGetValue(var<u1>, !!T0)
0x4926d  brfalse.s loc_4927D
0x4926f  ldloc.s  0xB
0x49271  ldloc.s  0xA
0x49273  callvirt instance void SecurityPolicy::AddRelatedRole(class [System.Data]System.Data.IDataRecord roleRecord)
0x49278  br       loc_49344
0x4927d  nop
0x4927e  ldarg.0
0x4927f  ldloc.s  0xA
0x49281  newobj   instance void SecurityPolicy::.ctor(class Microsoft.ReportingServices.Library.Security securityMgr, class [System.Data]System.Data.IDataRecord polRecord)
0x49286  stloc.s  0xB
0x49288  leave.s  loc_492DC
0x4928a  stloc.s  0xD
0x4928c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x49291  ldc.i4.1
0x49292  ldstr    aInvalidSecurit// "Invalid security policy {0}: Exception "...
0x49297  ldc.i4.2
0x49298  newarr   [mscorlib]System.Object
0x4929d  dup
0x4929e  ldc.i4.0
0x4929f  ldloc.s  0xA
0x492a1  ldc.i4.0
0x492a2  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x492a7  box      [mscorlib]System.Guid
0x492ac  stelem.ref
0x492ad  dup
0x492ae  ldc.i4.1
0x492af  ldloc.s  0xD
0x492b1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x492b6  stelem.ref
0x492b7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x492bc  ldloc.1
0x492bd  ldloc.s  0xB
0x492bf  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x492c4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::ContainsKey(var<u1>)
0x492c9  brtrue.s loc_492DA
0x492cb  ldloc.1
0x492cc  ldloc.s  0xB
0x492ce  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x492d3  ldloc.s  0xB
0x492d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::Add(var<u1>, !!T0)
0x492da  leave.s  loc_492DC
0x492dc  ldloc.s  0xB
0x492de  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.SecurityItemType SecurityPolicy::get_SecItemType()
0x492e3  brtrue.s loc_49335
0x492e5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x492ea  ldc.i4.1
0x492eb  ldstr    aInvalidSecurit_0// "Invalid security policy {0}:[{1}]: Unkn"...
0x492f0  ldc.i4.2
0x492f1  newarr   [mscorlib]System.Object
0x492f6  dup
0x492f7  ldc.i4.0
0x492f8  ldloc.s  0xB
0x492fa  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x492ff  box      [mscorlib]System.Guid
0x49304  stelem.ref
0x49305  dup
0x49306  ldc.i4.1
0x49307  ldloc.3
0x49308  ldloc.s  0xB
0x4930a  callvirt instance var<u1> class [mscorlib]System.Func`2<class SecurityPolicy, string>::Invoke(void)
0x4930f  stelem.ref
0x49310  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x49315  ldloc.1
0x49316  ldloc.s  0xB
0x49318  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x4931d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::ContainsKey(var<u1>)
0x49322  brtrue.s loc_49344
0x49324  ldloc.1
0x49325  ldloc.s  0xB
0x49327  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x4932c  ldloc.s  0xB
0x4932e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::Add(var<u1>, !!T0)
0x49333  br.s     loc_49344
0x49335  ldloc.0
0x49336  ldloc.s  0xB
0x49338  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x4933d  ldloc.s  0xB
0x4933f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::Add(var<u1>, !!T0)
0x49344  ldloc.s  0xA
0x49346  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x4934b  brtrue   loc_49256
0x49350  leave.s  loc_4936A
0x49352  ldloc.s  0xA
0x49354  brfalse.s loc_4935D
0x49356  ldloc.s  0xA
0x49358  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4935d  endfinally
0x4935e  ldloc.s  9
0x49360  brfalse.s loc_49369
0x49362  ldloc.s  9
0x49364  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49369  endfinally
0x4936a  ldloc.s  5
0x4936c  brtrue.s loc_49395
0x4936e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x49373  ldc.i4.3
0x49374  ldstr    aMarking0Invali// "Marking {0} invalid security policies a"...
0x49379  ldc.i4.1
0x4937a  newarr   [mscorlib]System.Object
0x4937f  dup
0x49380  ldc.i4.0
0x49381  ldloc.2
0x49382  box      [mscorlib]System.Int32
0x49387  stelem.ref
0x49388  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4938d  ldarg.0
0x4938e  call     instance void Microsoft.ReportingServices.Library.Security::UpdateInvalidPoliciesToOrphaned()
0x49393  ldc.i4.0
0x49394  ret
0x49395  ldc.i4.0
0x49396  stloc.s  6
0x49398  ldc.i4.0
0x49399  stloc.s  7
0x4939b  ldloc.0
0x4939c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Values()
0x493a1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class SecurityPolicy>::GetEnumerator()
0x493a6  stloc.s  0xE
0x493a8  br       loc_49500
0x493ad  ldloca.s 0xE
0x493af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Current()
0x493b4  stloc.s  0xF
0x493b6  ldarg.0
0x493b7  ldloc.s  0xF
0x493b9  ldloca.s 0x10
0x493bb  ldloca.s 0x11
0x493bd  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.Security::CompileXmlPolicy(class SecurityPolicy policy, [out] unsigned int8[]& realSecDesc, [out] string& stringSecDesc)
0x493c2  pop
0x493c3  ldarg.0
0x493c4  ldstr    aUpdatepolicy// "UpdatePolicy"
0x493c9  ldnull
0x493ca  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x493cf  stloc.s  0x12
0x493d1  ldloc.s  0x12
0x493d3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x493d8  ldstr    aPolicyid// "@PolicyID"
0x493dd  ldloc.s  0xF
0x493df  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x493e4  box      [mscorlib]System.Guid
0x493e9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x493ee  pop
0x493ef  ldloc.s  0x12
0x493f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x493f6  ldstr    aAuthtype// "@AuthType"
0x493fb  ldarg.0
0x493fc  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x49401  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x49406  box      [mscorlib]System.Int32
0x4940b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49410  pop
0x49411  ldloc.s  0x12
0x49413  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49418  ldstr    aPrimarysecdesc// "@PrimarySecDesc"
0x4941d  ldloc.s  0x10
0x4941f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49424  pop
0x49425  ldloc.s  0x12
0x49427  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4942c  ldstr    aSecondarysecde// "@SecondarySecDesc"
0x49431  ldloc.s  0x11
0x49433  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49438  pop
0x49439  ldloc.s  0x12
0x4943b  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49440  pop
0x49441  leave.s  loc_4944F
0x49443  ldloc.s  0x12
0x49445  brfalse.s loc_4944E
0x49447  ldloc.s  0x12
0x49449  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4944e  endfinally
0x4944f  ldloc.s  6
0x49451  ldc.i4.1
0x49452  add
0x49453  stloc.s  6
0x49455  leave    loc_49500
0x4945a  stloc.s  0x13
0x4945c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x49461  ldc.i4.1
0x49462  ldstr    aAdDomainIsNotA// "AD domain is not acessible {0}"
0x49467  ldc.i4.1
0x49468  newarr   [mscorlib]System.Object
0x4946d  dup
0x4946e  ldc.i4.0
0x4946f  ldloc.s  0x13
0x49471  callvirt instance string [mscorlib]System.Object::ToString()
0x49476  stelem.ref
0x49477  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4947c  ldc.i4.0
0x4947d  stloc.s  0x14
0x4947f  leave    loc_495AF
0x49484  stloc.s  0x15
0x49486  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4948b  ldc.i4.1
0x4948c  ldstr    aAdDomainAccess// "AD domain access denied {0}"
0x49491  ldc.i4.1
0x49492  newarr   [mscorlib]System.Object
0x49497  dup
0x49498  ldc.i4.0
0x49499  ldloc.s  0x15
0x4949b  callvirt instance string [mscorlib]System.Object::ToString()
0x494a0  stelem.ref
0x494a1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x494a6  ldc.i4.0
0x494a7  stloc.s  0x14
0x494a9  leave    loc_495AF
0x494ae  stloc.s  0x16
0x494b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x494b5  ldc.i4.1
0x494b6  ldstr    aInvalidSecurit_1// "Invalid security policy {0}:[{1}]: {2}"
0x494bb  ldc.i4.3
0x494bc  newarr   [mscorlib]System.Object
0x494c1  dup
0x494c2  ldc.i4.0
0x494c3  ldloc.s  0xF
0x494c5  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x494ca  box      [mscorlib]System.Guid
0x494cf  stelem.ref
0x494d0  dup
  ... truncated ...
```
