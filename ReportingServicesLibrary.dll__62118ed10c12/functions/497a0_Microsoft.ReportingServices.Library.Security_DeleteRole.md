# Microsoft.ReportingServices.Library.Security::DeleteRole

- ea: `0x497a0`
- end: `0x498c9`
- name: `Microsoft.ReportingServices.Library.Security::DeleteRole`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3d260`

## callees

- `0x497a0`
- `0x498d0`
- `0x49bb0`
- `0x8b090`
- `0x8b1d0`
- `0x8b220`
- `0x8b240`
- `0x8b250`

## string_xrefs

- `0x497a7`: `\nSELECT  \n    PrimeRoles.PolicyID,\n    SecData.XmlDescription, \n    PrimeRoles.PolicyFlag,\n    Catalog.Type,\n    Catalog.Path,\n    ModelItemPolicy.CatalogItemID,\n    ModelItemPolicy.ModelItemID,\n    RelatedRoles.RoleID,\n    RelatedRoles.RoleName,\n    RelatedRoles.TaskMask,\n    RelatedRoles.RoleFlags\nFROM\n	(SELECT * FROM Roles \n	INNER JOIN Policies ON \n		EXISTS (\n			SELECT * FROM PolicyUserRole \n			WHERE PolicyUserRole.RoleID = Roles.RoleID\n			AND PolicyUserR`
- `0x4988d`: `DeleteRole`

## pseudocode

```c

```

## disassembly

```asm
0x497a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::.ctor()
0x497a5  stloc.0
0x497a6  ldarg.0
0x497a7  ldstr    aSelectPrimerol// "\r\nSELECT  \r\n    PrimeRoles.PolicyID"...
0x497ac  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string)
0x497b1  stloc.1
0x497b2  ldloc.1
0x497b3  ldstr    aRolename// "@RoleName"
0x497b8  ldc.i4.s 0xC
0x497ba  ldarg.1
0x497bb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x497c0  pop
0x497c1  ldloc.1
0x497c2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x497c7  ldstr    aAuthtype// "@AuthType"
0x497cc  ldarg.0
0x497cd  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x497d2  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x497d7  box      [mscorlib]System.Int32
0x497dc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x497e1  pop
0x497e2  ldloc.1
0x497e3  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x497e8  stloc.2
0x497e9  ldnull
0x497ea  stloc.3
0x497eb  br.s     loc_49820
0x497ed  ldloc.2
0x497ee  ldc.i4.0
0x497ef  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x497f4  stloc.s  4
0x497f6  ldloc.0
0x497f7  ldloc.s  4
0x497f9  ldloca.s 3
0x497fb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::TryGetValue(var<u1>, !!T0)
0x49800  brfalse.s loc_4980B
0x49802  ldloc.3
0x49803  ldloc.2
0x49804  callvirt instance void SecurityPolicy::AddRelatedRole(class [System.Data]System.Data.IDataRecord roleRecord)
0x49809  br.s     loc_49820
0x4980b  ldarg.0
0x4980c  ldloc.2
0x4980d  newobj   instance void SecurityPolicy::.ctor(class Microsoft.ReportingServices.Library.Security securityMgr, class [System.Data]System.Data.IDataRecord polRecord)
0x49812  stloc.3
0x49813  ldloc.0
0x49814  ldloc.3
0x49815  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x4981a  ldloc.3
0x4981b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::Add(var<u1>, !!T0)
0x49820  ldloc.2
0x49821  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x49826  brtrue.s loc_497ED
0x49828  leave.s  loc_4983E
0x4982a  ldloc.2
0x4982b  brfalse.s loc_49833
0x4982d  ldloc.2
0x4982e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49833  endfinally
0x49834  ldloc.1
0x49835  brfalse.s loc_4983D
0x49837  ldloc.1
0x49838  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4983d  endfinally
0x4983e  ldloc.0
0x4983f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Values()
0x49844  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class SecurityPolicy>::GetEnumerator()
0x49849  stloc.s  5
0x4984b  br.s     loc_49873
0x4984d  ldloca.s 5
0x4984f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Current()
0x49854  stloc.s  6
0x49856  ldloc.s  6
0x49858  ldarg.0
0x49859  ldloc.s  6
0x4985b  callvirt instance string SecurityPolicy::get_XmlPolicy()
0x49860  ldarg.1
0x49861  call     instance string Microsoft.ReportingServices.Library.Security::RemoveRoleFromPolicy(string xmlPolicy, string role)
0x49866  callvirt instance void SecurityPolicy::set_XmlPolicy(string value)
0x4986b  ldarg.0
0x4986c  ldloc.s  6
0x4986e  call     instance void Microsoft.ReportingServices.Library.Security::InnerSetPolicies(class SecurityPolicy policy)
0x49873  ldloca.s 5
0x49875  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>::MoveNext()
0x4987a  brtrue.s loc_4984D
0x4987c  leave.s  loc_4988C
0x4987e  ldloca.s 5
0x49880  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>
0x49886  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4988b  endfinally
0x4988c  ldarg.0
0x4988d  ldstr    aDeleterole// "DeleteRole"
0x49892  ldnull
0x49893  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49898  stloc.s  7
0x4989a  ldloc.s  7
0x4989c  ldstr    aRolename// "@RoleName"
0x498a1  ldc.i4.s 0xC
0x498a3  ldarg.1
0x498a4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x498a9  pop
0x498aa  ldloc.s  7
0x498ac  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x498b1  brtrue.s loc_498BA
0x498b3  ldarg.1
0x498b4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RoleNotFoundException::.ctor(string)
0x498b9  throw
0x498ba  leave.s  loc_498C8
0x498bc  ldloc.s  7
0x498be  brfalse.s loc_498C7
0x498c0  ldloc.s  7
0x498c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x498c7  endfinally
0x498c8  ret
```
