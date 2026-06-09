# Microsoft.ReportingServices.Library.Security::SetRoleProperties

- ea: `0x48e90`
- end: `0x4910d`
- name: `Microsoft.ReportingServices.Library.Security::SetRoleProperties`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3d660`

## callees

- `0x48e90`
- `0x4b0e0`
- `0x8b090`
- `0x8b1d0`
- `0x8b210`
- `0x8b220`

## string_xrefs

- `0x48ebf`: `@TaskMask`
- `0x48f0b`: `\nSELECT  \n    PrimeRoles.PolicyID,\n    SecData.XmlDescription, \n    PrimeRoles.PolicyFlag,\n    Catalog.Type,\n    Catalog.Path,\n    ModelItemPolicy.CatalogItemID,\n    ModelItemPolicy.ModelItemID,\n    RelatedRoles.RoleID,\n    RelatedRoles.RoleName,\n    RelatedRoles.TaskMask,\n    RelatedRoles.RoleFlags\nFROM\n	(SELECT * FROM Roles \n	INNER JOIN Policies ON \n		EXISTS (\n			SELECT * FROM PolicyUserRole \n			WHERE PolicyUserRole.RoleID = Roles.RoleID\n			AND PolicyUserR`
- `0x48f8d`: `Policy record with unknown SecurityItemType. Id : {0}`
- `0x49009`: `UpdatePolicy`

## pseudocode

```c

```

## disassembly

```asm
0x48e90  ldarg.0
0x48e91  ldstr    aSetrolepropert_0// "SetRoleProperties"
0x48e96  ldnull
0x48e97  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x48e9c  stloc.1
0x48e9d  ldloc.1
0x48e9e  ldstr    aRolename// "@RoleName"
0x48ea3  ldc.i4.s 0xC
0x48ea5  ldarg.1
0x48ea6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48eab  pop
0x48eac  ldarg.2
0x48ead  brfalse.s loc_48EBE
0x48eaf  ldloc.1
0x48eb0  ldstr    aDescription// "@Description"
0x48eb5  ldc.i4.s 0xC
0x48eb7  ldarg.2
0x48eb8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48ebd  pop
0x48ebe  ldloc.1
0x48ebf  ldstr    aTaskmask// "@TaskMask"
0x48ec4  ldc.i4.s 0xC
0x48ec6  ldarg.3
0x48ec7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48ecc  pop
0x48ecd  ldarg.s  4
0x48ecf  conv.u1
0x48ed0  stloc.2
0x48ed1  ldloc.1
0x48ed2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x48ed7  ldstr    aRoleflags// "@RoleFlags"
0x48edc  ldloc.2
0x48edd  box      [mscorlib]System.Byte
0x48ee2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x48ee7  pop
0x48ee8  ldloc.1
0x48ee9  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x48eee  ldc.i4.1
0x48eef  beq.s    loc_48EF8
0x48ef1  ldarg.1
0x48ef2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RoleNotFoundException::.ctor(string)
0x48ef7  throw
0x48ef8  leave.s  loc_48F04
0x48efa  ldloc.1
0x48efb  brfalse.s loc_48F03
0x48efd  ldloc.1
0x48efe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48f03  endfinally
0x48f04  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::.ctor()
0x48f09  stloc.0
0x48f0a  ldarg.0
0x48f0b  ldstr    aSelectPrimerol// "\r\nSELECT  \r\n    PrimeRoles.PolicyID"...
0x48f10  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommandQuery(string)
0x48f15  stloc.3
0x48f16  ldloc.3
0x48f17  ldstr    aRolename// "@RoleName"
0x48f1c  ldc.i4.s 0xC
0x48f1e  ldarg.1
0x48f1f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48f24  pop
0x48f25  ldloc.3
0x48f26  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x48f2b  ldstr    aAuthtype// "@AuthType"
0x48f30  ldarg.0
0x48f31  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x48f36  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x48f3b  box      [mscorlib]System.Int32
0x48f40  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x48f45  pop
0x48f46  ldloc.3
0x48f47  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x48f4c  stloc.s  4
0x48f4e  ldnull
0x48f4f  stloc.s  5
0x48f51  br.s     loc_48FBD
0x48f53  ldloc.s  4
0x48f55  ldc.i4.0
0x48f56  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x48f5b  stloc.s  6
0x48f5d  ldloc.0
0x48f5e  ldloc.s  6
0x48f60  ldloca.s 5
0x48f62  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::TryGetValue(var<u1>, !!T0)
0x48f67  brfalse.s loc_48F74
0x48f69  ldloc.s  5
0x48f6b  ldloc.s  4
0x48f6d  callvirt instance void SecurityPolicy::AddRelatedRole(class [System.Data]System.Data.IDataRecord roleRecord)
0x48f72  br.s     loc_48FBD
0x48f74  ldarg.0
0x48f75  ldloc.s  4
0x48f77  newobj   instance void SecurityPolicy::.ctor(class Microsoft.ReportingServices.Library.Security securityMgr, class [System.Data]System.Data.IDataRecord polRecord)
0x48f7c  stloc.s  5
0x48f7e  ldloc.s  5
0x48f80  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.SecurityItemType SecurityPolicy::get_SecItemType()
0x48f85  brtrue.s loc_48FAE
0x48f87  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x48f8c  ldc.i4.4
0x48f8d  ldstr    aPolicyRecordWi// "Policy record with unknown SecurityItem"...
0x48f92  ldc.i4.1
0x48f93  newarr   [mscorlib]System.Object
0x48f98  dup
0x48f99  ldc.i4.0
0x48f9a  ldloc.s  5
0x48f9c  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x48fa1  box      [mscorlib]System.Guid
0x48fa6  stelem.ref
0x48fa7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x48fac  br.s     loc_48FBD
0x48fae  ldloc.0
0x48faf  ldloc.s  5
0x48fb1  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x48fb6  ldloc.s  5
0x48fb8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::Add(var<u1>, !!T0)
0x48fbd  ldloc.s  4
0x48fbf  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x48fc4  brtrue.s loc_48F53
0x48fc6  leave.s  loc_48FD4
0x48fc8  ldloc.s  4
0x48fca  brfalse.s loc_48FD3
0x48fcc  ldloc.s  4
0x48fce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48fd3  endfinally
0x48fd4  leave.s  loc_48FE0
0x48fd6  ldloc.3
0x48fd7  brfalse.s loc_48FDF
0x48fd9  ldloc.3
0x48fda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48fdf  endfinally
0x48fe0  ldloc.0
0x48fe1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Values()
0x48fe6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class SecurityPolicy>::GetEnumerator()
0x48feb  stloc.s  7
0x48fed  br       loc_490AC
0x48ff2  ldloca.s 7
0x48ff4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>::get_Current()
0x48ff9  stloc.s  8
0x48ffb  ldarg.0
0x48ffc  ldloc.s  8
0x48ffe  ldloca.s 9
0x49000  ldloca.s 0xA
0x49002  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.Security::CompileXmlPolicy(class SecurityPolicy policy, [out] unsigned int8[]& realSecDesc, [out] string& stringSecDesc)
0x49007  pop
0x49008  ldarg.0
0x49009  ldstr    aUpdatepolicy// "UpdatePolicy"
0x4900e  ldnull
0x4900f  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49014  stloc.s  0xB
0x49016  ldloc.s  0xB
0x49018  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4901d  ldstr    aPolicyid// "@PolicyID"
0x49022  ldloc.s  8
0x49024  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_PolicyId()
0x49029  box      [mscorlib]System.Guid
0x4902e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49033  pop
0x49034  ldloc.s  0xB
0x49036  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4903b  ldstr    aPrimarysecdesc// "@PrimarySecDesc"
0x49040  ldloc.s  9
0x49042  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49047  pop
0x49048  ldloc.s  0xB
0x4904a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4904f  ldstr    aSecondarysecde// "@SecondarySecDesc"
0x49054  ldloc.s  0xA
0x49056  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4905b  pop
0x4905c  ldloc.s  0xB
0x4905e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49063  ldstr    aAuthtype// "@AuthType"
0x49068  ldarg.0
0x49069  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4906e  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x49073  box      [mscorlib]System.Int32
0x49078  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4907d  pop
0x4907e  ldloc.s  0xB
0x49080  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49085  pop
0x49086  leave.s  loc_49094
0x49088  ldloc.s  0xB
0x4908a  brfalse.s loc_49093
0x4908c  ldloc.s  0xB
0x4908e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49093  endfinally
0x49094  leave.s  loc_490AC
0x49096  stloc.s  0xC
0x49098  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4909d  ldc.i4.4
0x4909e  ldloc.s  0xC
0x490a0  callvirt instance string [mscorlib]System.Object::ToString()
0x490a5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x490aa  leave.s  loc_490AC
0x490ac  ldloca.s 7
0x490ae  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>::MoveNext()
0x490b3  brtrue   loc_48FF2
0x490b8  leave.s  loc_490C8
0x490ba  ldloca.s 7
0x490bc  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class SecurityPolicy>
0x490c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x490c7  endfinally
0x490c8  leave.s  loc_4910C
0x490ca  stloc.s  0xD
0x490cc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x490d1  ldc.i4.1
0x490d2  ldstr    aSetRolePropert// "Set role properties failed: "
0x490d7  ldloc.s  0xD
0x490d9  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorMessage()
0x490de  call     string [mscorlib]System.String::Concat(string, string)
0x490e3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x490e8  ldloc.s  0xD
0x490ea  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x490ef  brfalse.s loc_4910A
0x490f1  ldloc.s  0xD
0x490f3  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorMessage()
0x490f8  ldstr    aBadRoleFlags// "Bad role flags"
0x490fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x49102  brfalse.s loc_4910A
0x49104  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MixedTasksException::.ctor()
0x49109  throw
0x4910a  rethrow
0x4910c  ret
```
