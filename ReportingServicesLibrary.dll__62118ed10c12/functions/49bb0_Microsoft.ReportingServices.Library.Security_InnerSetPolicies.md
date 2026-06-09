# Microsoft.ReportingServices.Library.Security::InnerSetPolicies

- ea: `0x49bb0`
- end: `0x49e86`
- name: `Microsoft.ReportingServices.Library.Security::InnerSetPolicies`
- size: `726`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x497a0`
- `0x49b10`
- `0x49b70`
- `0x49b90`

## callees

- `0x48b40`
- `0x49bb0`
- `0x49e90`
- `0x4b0e0`
- `0x8b230`
- `0x8b240`
- `0x8b260`

## string_xrefs

- `0x49c24`: `@XmlPolicy`
- `0x49c9c`: `UpdatePolicyPrincipal`
- `0x49cdc`: `@PrincipalSid`
- `0x49db2`: `UpdatePolicyRole`

## pseudocode

```c

```

## disassembly

```asm
0x49bb0  ldarg.1
0x49bb1  callvirt instance valuetype SecurityScope SecurityPolicy::get_Scope()
0x49bb6  stloc.0
0x49bb7  ldarg.1
0x49bb8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath SecurityPolicy::get_CatalogItemPath()
0x49bbd  stloc.1
0x49bbe  ldnull
0x49bbf  stloc.2
0x49bc0  ldnull
0x49bc1  stloc.3
0x49bc2  ldarg.0
0x49bc3  ldarg.1
0x49bc4  ldloca.s 2
0x49bc6  ldloca.s 3
0x49bc8  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.Security::CompileXmlPolicy(class SecurityPolicy policy, [out] unsigned int8[]& realSecDesc, [out] string& stringSecDesc)
0x49bcd  stloc.s  4
0x49bcf  ldarg.0
0x49bd0  ldarg.1
0x49bd1  ldloc.0
0x49bd2  ldloc.1
0x49bd3  call     instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Security::BuildSqlCommandFromScope(class SecurityPolicy policy, valuetype SecurityScope scope, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemName)
0x49bd8  stloc.s  6
0x49bda  ldloc.s  6
0x49bdc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49be1  ldstr    aAuthtype// "@AuthType"
0x49be6  ldarg.0
0x49be7  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x49bec  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x49bf1  box      [mscorlib]System.Int32
0x49bf6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49bfb  pop
0x49bfc  ldloc.s  6
0x49bfe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49c03  ldstr    aPrimarysecdesc// "@PrimarySecDesc"
0x49c08  ldloc.2
0x49c09  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49c0e  pop
0x49c0f  ldloc.3
0x49c10  brfalse.s loc_49C22
0x49c12  ldloc.s  6
0x49c14  ldstr    aSecondarysecde// "@SecondarySecDesc"
0x49c19  ldc.i4.s 0xB
0x49c1b  ldloc.3
0x49c1c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49c21  pop
0x49c22  ldloc.s  6
0x49c24  ldstr    aXmlpolicy// "@XmlPolicy"
0x49c29  ldc.i4.s 0xB
0x49c2b  ldarg.1
0x49c2c  callvirt instance string SecurityPolicy::get_XmlPolicy()
0x49c31  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49c36  pop
0x49c37  ldloc.s  6
0x49c39  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49c3e  ldstr    aPolicyid// "@PolicyID"
0x49c43  ldc.i4.s 0xE
0x49c45  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x49c4a  dup
0x49c4b  ldc.i4.2
0x49c4c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x49c51  ldloc.s  6
0x49c53  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49c58  pop
0x49c59  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x49c5e  unbox.any [mscorlib]System.Guid
0x49c63  stloc.s  5
0x49c65  leave.s  loc_49C73
0x49c67  ldloc.s  6
0x49c69  brfalse.s loc_49C72
0x49c6b  ldloc.s  6
0x49c6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49c72  endfinally
0x49c73  ldloc.s  4
0x49c75  brfalse  loc_49E85
0x49c7a  ldloc.s  4
0x49c7c  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x49c81  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x49c86  stloc.s  7
0x49c88  br       loc_49E62
0x49c8d  ldloc.s  7
0x49c8f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x49c94  castclass PrincipalAndRoles
0x49c99  stloc.s  8
0x49c9b  ldarg.0
0x49c9c  ldstr    aUpdatepolicypr// "UpdatePolicyPrincipal"
0x49ca1  ldnull
0x49ca2  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49ca7  stloc.s  0xA
0x49ca9  ldloc.s  0xA
0x49cab  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49cb0  ldstr    aPolicyid// "@PolicyID"
0x49cb5  ldloc.s  5
0x49cb7  box      [mscorlib]System.Guid
0x49cbc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49cc1  pop
0x49cc2  ldarg.0
0x49cc3  ldloc.s  8
0x49cc5  ldfld    string PrincipalAndRoles::m_principal
0x49cca  call     instance unsigned int8[] Microsoft.ReportingServices.Library.Security::GetPrincipalSid(string principalName)
0x49ccf  stloc.s  0xB
0x49cd1  ldloc.s  0xB
0x49cd3  brfalse.s loc_49CEF
0x49cd5  ldloc.s  0xA
0x49cd7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49cdc  ldstr    aPrincipalsid// "@PrincipalSid"
0x49ce1  ldloc.s  0xB
0x49ce3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49ce8  ldc.i4.s 0x15
0x49cea  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x49cef  ldloc.s  0xA
0x49cf1  ldstr    aPrincipalname// "@PrincipalName"
0x49cf6  ldc.i4.s 0xC
0x49cf8  ldloc.s  8
0x49cfa  ldfld    string PrincipalAndRoles::m_principal
0x49cff  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49d04  pop
0x49d05  ldloc.s  0xA
0x49d07  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49d0c  ldstr    aPrincipalautht// "@PrincipalAuthType"
0x49d11  ldarg.0
0x49d12  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x49d17  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x49d1c  box      [mscorlib]System.Int32
0x49d21  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49d26  pop
0x49d27  ldloc.s  0xA
0x49d29  ldstr    aRolename// "@RoleName"
0x49d2e  ldc.i4.s 0xC
0x49d30  ldloc.s  8
0x49d32  ldfld    class [mscorlib]System.Collections.ArrayList PrincipalAndRoles::m_Roles
0x49d37  ldc.i4.0
0x49d38  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x49d3d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49d42  pop
0x49d43  ldloc.s  0xA
0x49d45  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49d4a  ldstr    aPrincipalid// "@PrincipalID"
0x49d4f  ldc.i4.s 0xE
0x49d51  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x49d56  stloc.s  0xC
0x49d58  ldloc.s  0xC
0x49d5a  ldc.i4.2
0x49d5b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x49d60  ldloc.s  0xA
0x49d62  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49d67  ldstr    aRoleid// "@RoleID"
0x49d6c  ldc.i4.s 0xE
0x49d6e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x49d73  dup
0x49d74  ldc.i4.2
0x49d75  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x49d7a  ldloc.s  0xA
0x49d7c  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49d81  pop
0x49d82  ldloc.s  0xC
0x49d84  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x49d89  unbox.any [mscorlib]System.Guid
0x49d8e  stloc.s  9
0x49d90  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x49d95  unbox.any [mscorlib]System.Guid
0x49d9a  pop
0x49d9b  leave.s  loc_49DA9
0x49d9d  ldloc.s  0xA
0x49d9f  brfalse.s loc_49DA8
0x49da1  ldloc.s  0xA
0x49da3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49da8  endfinally
0x49da9  ldc.i4.1
0x49daa  stloc.s  0xD
0x49dac  br       loc_49E4F
0x49db1  ldarg.0
0x49db2  ldstr    aUpdatepolicyro// "UpdatePolicyRole"
0x49db7  ldnull
0x49db8  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49dbd  stloc.s  0xE
0x49dbf  ldloc.s  0xE
0x49dc1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49dc6  ldstr    aPolicyid// "@PolicyID"
0x49dcb  ldloc.s  5
0x49dcd  box      [mscorlib]System.Guid
0x49dd2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49dd7  pop
0x49dd8  ldloc.s  0xE
0x49dda  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49ddf  ldstr    aPrincipalid// "@PrincipalID"
0x49de4  ldloc.s  9
0x49de6  box      [mscorlib]System.Guid
0x49deb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x49df0  pop
0x49df1  ldloc.s  0xE
0x49df3  ldstr    aRolename// "@RoleName"
0x49df8  ldc.i4.s 0xC
0x49dfa  ldloc.s  8
0x49dfc  ldfld    class [mscorlib]System.Collections.ArrayList PrincipalAndRoles::m_Roles
0x49e01  ldloc.s  0xD
0x49e03  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x49e08  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49e0d  pop
0x49e0e  ldloc.s  0xE
0x49e10  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x49e15  ldstr    aRoleid// "@RoleID"
0x49e1a  ldc.i4.s 0xE
0x49e1c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x49e21  dup
0x49e22  ldc.i4.2
0x49e23  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x49e28  ldloc.s  0xE
0x49e2a  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x49e2f  pop
0x49e30  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x49e35  unbox.any [mscorlib]System.Guid
0x49e3a  pop
0x49e3b  leave.s  loc_49E49
0x49e3d  ldloc.s  0xE
0x49e3f  brfalse.s loc_49E48
0x49e41  ldloc.s  0xE
0x49e43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49e48  endfinally
0x49e49  ldloc.s  0xD
0x49e4b  ldc.i4.1
0x49e4c  add
0x49e4d  stloc.s  0xD
0x49e4f  ldloc.s  0xD
0x49e51  ldloc.s  8
0x49e53  ldfld    class [mscorlib]System.Collections.ArrayList PrincipalAndRoles::m_Roles
0x49e58  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x49e5d  blt      loc_49DB1
0x49e62  ldloc.s  7
0x49e64  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x49e69  brtrue   loc_49C8D
0x49e6e  leave.s  loc_49E85
0x49e70  ldloc.s  7
0x49e72  isinst   [mscorlib]System.IDisposable
0x49e77  stloc.s  0xF
0x49e79  ldloc.s  0xF
0x49e7b  brfalse.s loc_49E84
0x49e7d  ldloc.s  0xF
0x49e7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49e84  endfinally
0x49e85  ret
```
