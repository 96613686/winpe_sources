# Microsoft.ReportingServices.Library.DBInterface::CreateObject_1

- ea: `0x4b80`
- end: `0x4e3f`
- name: `Microsoft.ReportingServices.Library.DBInterface::CreateObject_1`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x4b10`
- `0x4b40`

## callees

- `0x4630`
- `0x4b80`
- `0x140e0`

## string_xrefs

- `0x4b8d`: `CreateObject`
- `0x4bda`: `@Path`
- `0x4c79`: `@LinkSourceID`
- `0x4ce0`: `@CreatedBySid`
- `0x4cf9`: `@CreatedByName`
- `0x4da2`: `objectType & componentId`
- `0x4db2`: `@ComponentID`

## pseudocode

```c

```

## disassembly

```asm
0x4b80  ldarg.s  0xB
0x4b82  ldloca.s 0
0x4b84  ldloca.s 1
0x4b86  call     string Microsoft.ReportingServices.Library.ItemProperties::PrepareForSaving(class Microsoft.ReportingServices.Library.ItemProperties properties, [out] string& description, [out] bool& hidden)
0x4b8b  stloc.2
0x4b8c  ldarg.0
0x4b8d  ldstr    aCreateobject// "CreateObject"
0x4b92  ldnull
0x4b93  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4b98  stloc.3
0x4b99  ldarg.1
0x4b9a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b9f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4ba4  brfalse.s loc_4BAF
0x4ba6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4bab  stloc.s  4
0x4bad  br.s     loc_4BB2
0x4baf  ldarg.1
0x4bb0  stloc.s  4
0x4bb2  ldloc.3
0x4bb3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4bb8  ldstr    aItemid_0// "@ItemID"
0x4bbd  ldloc.s  4
0x4bbf  box      [mscorlib]System.Guid
0x4bc4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4bc9  pop
0x4bca  ldloc.3
0x4bcb  ldstr    aName_0// "@Name"
0x4bd0  ldc.i4.s 0xC
0x4bd2  ldarg.2
0x4bd3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4bd8  pop
0x4bd9  ldloc.3
0x4bda  ldstr    aPath// "@Path"
0x4bdf  ldc.i4.s 0xC
0x4be1  ldarg.3
0x4be2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4be7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4bec  pop
0x4bed  ldloc.3
0x4bee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4bf3  ldstr    aParentid// "@ParentID"
0x4bf8  ldarg.s  5
0x4bfa  box      [mscorlib]System.Guid
0x4bff  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c04  pop
0x4c05  ldloc.3
0x4c06  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4c0b  ldstr    aType// "@Type"
0x4c10  ldarg.s  6
0x4c12  box      [mscorlib]System.Int32
0x4c17  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c1c  pop
0x4c1d  ldarg.s  7
0x4c1f  brfalse.s loc_4C39
0x4c21  ldloc.3
0x4c22  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4c27  ldstr    aContent_0// "@Content"
0x4c2c  ldc.i4.7
0x4c2d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x4c32  ldarg.s  7
0x4c34  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x4c39  ldarg.s  8
0x4c3b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c40  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c45  brfalse.s loc_4C65
0x4c47  ldloc.3
0x4c48  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4c4d  ldstr    aIntermediate// "@Intermediate"
0x4c52  ldc.i4.s 0xE
0x4c54  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x4c59  ldarg.s  8
0x4c5b  box      [mscorlib]System.Guid
0x4c60  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x4c65  ldarg.s  9
0x4c67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c6c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c71  brfalse.s loc_4C8B
0x4c73  ldloc.3
0x4c74  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4c79  ldstr    aLinksourceid// "@LinkSourceID"
0x4c7e  ldarg.s  9
0x4c80  box      [mscorlib]System.Guid
0x4c85  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c8a  pop
0x4c8b  ldloc.2
0x4c8c  brfalse.s loc_4C9D
0x4c8e  ldloc.3
0x4c8f  ldstr    aProperty_0// "@Property"
0x4c94  ldc.i4.s 0xB
0x4c96  ldloc.2
0x4c97  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4c9c  pop
0x4c9d  ldarg.s  0xC
0x4c9f  brfalse.s loc_4CB1
0x4ca1  ldloc.3
0x4ca2  ldstr    aParameter// "@Parameter"
0x4ca7  ldc.i4.s 0xB
0x4ca9  ldarg.s  0xC
0x4cab  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4cb0  pop
0x4cb1  ldloc.0
0x4cb2  brfalse.s loc_4CC3
0x4cb4  ldloc.3
0x4cb5  ldstr    aDescription// "@Description"
0x4cba  ldc.i4.s 0xB
0x4cbc  ldloc.0
0x4cbd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4cc2  pop
0x4cc3  ldloc.3
0x4cc4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4cc9  ldstr    aHidden// "@Hidden"
0x4cce  ldloc.1
0x4ccf  box      [mscorlib]System.Boolean
0x4cd4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4cd9  pop
0x4cda  ldloc.3
0x4cdb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4ce0  ldstr    aCreatedbysid// "@CreatedBySid"
0x4ce5  ldarg.s  0xD
0x4ce7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4cec  ldc.i4.s 0x15
0x4cee  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4cf3  ldloc.3
0x4cf4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4cf9  ldstr    aCreatedbyname// "@CreatedByName"
0x4cfe  ldarg.s  0xE
0x4d00  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4d05  ldc.i4.s 0xC
0x4d07  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4d0c  ldloc.3
0x4d0d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4d12  ldstr    aAuthtype// "@AuthType"
0x4d17  ldarg.0
0x4d18  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x4d1d  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x4d22  box      [mscorlib]System.Int32
0x4d27  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4d2c  ldc.i4.8
0x4d2d  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4d32  ldloc.3
0x4d33  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4d38  ldstr    aCreationdate// "@CreationDate"
0x4d3d  ldarg.s  0xF
0x4d3f  box      [mscorlib]System.DateTime
0x4d44  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4d49  pop
0x4d4a  ldloc.3
0x4d4b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4d50  ldstr    aModificationda// "@ModificationDate"
0x4d55  ldarg.s  0x10
0x4d57  box      [mscorlib]System.DateTime
0x4d5c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4d61  pop
0x4d62  ldarg.s  0x11
0x4d64  brfalse.s loc_4D76
0x4d66  ldloc.3
0x4d67  ldstr    aMimetype// "@MimeType"
0x4d6c  ldc.i4.s 0xC
0x4d6e  ldarg.s  0x11
0x4d70  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4d75  pop
0x4d76  ldloc.3
0x4d77  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4d7c  ldstr    aSubtype// "@SubType"
0x4d81  ldarg.s  0x12
0x4d83  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4d88  pop
0x4d89  ldarg.s  0x13
0x4d8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4d90  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4d95  brfalse.s loc_4DC4
0x4d97  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4d9c  ldarg.s  6
0x4d9e  ldc.i4.s 9
0x4da0  ceq
0x4da2  ldstr    aObjecttypeComp// "objectType & componentId"
0x4da7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4dac  ldloc.3
0x4dad  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4db2  ldstr    aComponentid// "@ComponentID"
0x4db7  ldarg.s  0x13
0x4db9  box      [mscorlib]System.Guid
0x4dbe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4dc3  pop
0x4dc4  ldloc.3
0x4dc5  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x4dca  pop
0x4dcb  ldloc.s  4
0x4dcd  stloc.s  5
0x4dcf  leave.s  loc_4E3C
0x4dd1  ldloc.3
0x4dd2  brfalse.s loc_4DDA
0x4dd4  ldloc.3
0x4dd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4dda  endfinally
0x4ddb  stloc.s  6
0x4ddd  ldloc.s  6
0x4ddf  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x4de4  brtrue.s loc_4DE8
0x4de6  rethrow
0x4de8  ldloc.s  6
0x4dea  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x4def  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlUniqueIndexViolationCode
0x4df4  bne.un.s loc_4DFF
0x4df6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4dfb  stloc.s  5
0x4dfd  leave.s  loc_4E3C
0x4dff  ldloc.s  6
0x4e01  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x4e06  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlConstraintViolationCode
0x4e0b  bne.un.s loc_4E1A
0x4e0d  ldarg.s  0xA
0x4e0f  ldstr    aLink// "link"
0x4e14  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string, string)
0x4e19  throw
0x4e1a  ldloc.s  6
0x4e1c  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorMessage()
0x4e21  ldstr    aParentNotFound// "Parent Not Found"
0x4e26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e2b  brfalse.s loc_4E3A
0x4e2d  ldarg.s  4
0x4e2f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4e34  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x4e39  throw
0x4e3a  rethrow
0x4e3c  ldloc.s  5
0x4e3e  ret
```
