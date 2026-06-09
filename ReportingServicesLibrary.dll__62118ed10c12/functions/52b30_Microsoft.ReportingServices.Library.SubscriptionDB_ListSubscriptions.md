# Microsoft.ReportingServices.Library.SubscriptionDB::ListSubscriptions

- ea: `0x52b30`
- end: `0x52d1a`
- name: `Microsoft.ReportingServices.Library.SubscriptionDB::ListSubscriptions`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x54790`

## callees

- `0x522d0`
- `0x52b30`
- `0x52db0`
- `0x52de0`

## string_xrefs

- `0x52b98`: `@UserSid`
- `0x52c45`: `@Path`
- `0x52b36`: `select \n                                                    S.[SubscriptionID],\n                                                    S.[Report_OID],\n                                                    S.[ReportZone],\n                                                    S.[Locale],\n                                                    S.[InactiveFlags],\n                                                    S.[DeliveryExtension], \n                                                    S.[Exte`
- `0x52b4f`: `select \n                                                    S.[SubscriptionID],\n                                                    S.[Report_OID],\n                                                    S.[ReportZone],\n                                                    S.[Locale],\n                                                    S.[InactiveFlags],\n                                                    S.[DeliveryExtension], \n                                                    S.[Exte`
- `0x52b86`: `Owner.[Sid] = @UserSid`
- `0x52c1b`: `SUBSTRING(CAT.[Path],1,{0}) = @Path`
- `0x52c57`: `CAT.[Path] = @Report`
- `0x52c84`: `S.[EventType] = 'TimedSubscription' OR S.[EventType] = 'SnapshotUpdated'`
- `0x52c94`: `S.[EventType] = 'RefreshCache' OR S.[EventType] = 'DataModelRefresh' `

## pseudocode

```c

```

## disassembly

```asm
0x52b30  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.SubscriptionImpl>::.ctor()
0x52b35  stloc.0
0x52b36  ldstr    aSelectS// "select \r\n                            "...
0x52b3b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x52b40  stloc.1
0x52b41  ldc.i4.1
0x52b42  stloc.2
0x52b43  ldarg.0
0x52b44  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x52b49  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x52b4e  stloc.3
0x52b4f  ldstr    aSelectS// "select \r\n                            "...
0x52b54  ldc.i4.1
0x52b55  ldarg.0
0x52b56  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_Connection()
0x52b5b  ldarg.0
0x52b5c  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_Transaction()
0x52b61  ldarg.0
0x52b62  call     instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_SqlCommandTimeout()
0x52b67  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewSqlCommand(string, valuetype [System.Data]System.Data.CommandType, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction, int32)
0x52b6c  stloc.s  4
0x52b6e  ldarg.1
0x52b6f  brfalse.s loc_52BCC
0x52b71  ldarg.1
0x52b72  ldstr    asc_90EAC// ""
0x52b77  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x52b7c  brfalse.s loc_52BCC
0x52b7e  ldarg.s  4
0x52b80  ldc.i4.1
0x52b81  bne.un.s loc_52BAB
0x52b83  ldarg.0
0x52b84  ldloc.1
0x52b85  ldloc.2
0x52b86  ldstr    aOwnerSidUsersi// "Owner.[Sid] = @UserSid"
0x52b8b  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52b90  stloc.2
0x52b91  ldloc.s  4
0x52b93  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52b98  ldstr    aUsersid// "@UserSid"
0x52b9d  ldarg.1
0x52b9e  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::NameToSid(string)
0x52ba3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52ba8  pop
0x52ba9  br.s     loc_52BCC
0x52bab  ldarg.0
0x52bac  ldloc.1
0x52bad  ldloc.2
0x52bae  ldstr    aOwnerUsernameU// "Owner.[UserName] = @UserName"
0x52bb3  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52bb8  stloc.2
0x52bb9  ldloc.s  4
0x52bbb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52bc0  ldstr    aUsername_0// "@UserName"
0x52bc5  ldarg.1
0x52bc6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52bcb  pop
0x52bcc  ldarg.2
0x52bcd  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::IsNullOrEmpty(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase)
0x52bd2  brtrue   loc_52C76
0x52bd7  ldarg.s  5
0x52bd9  ldarg.2
0x52bda  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x52bdf  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0x52be4  stloc.s  5
0x52be6  ldarg.0
0x52be7  ldloc.1
0x52be8  ldloc.2
0x52be9  ldstr    aSReportzoneRep// "S.[ReportZone] = @ReportZone"
0x52bee  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52bf3  stloc.2
0x52bf4  ldloc.s  4
0x52bf6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52bfb  ldstr    aReportzone// "@ReportZone"
0x52c00  ldarg.s  5
0x52c02  ldarg.2
0x52c03  callvirt instance int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::GetExternalRootZone(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath)
0x52c08  box      [mscorlib]System.Int32
0x52c0d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52c12  pop
0x52c13  ldarg.3
0x52c14  brfalse.s loc_52C54
0x52c16  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52c1b  ldstr    aSubstringCatPa// "SUBSTRING(CAT.[Path],1,{0}) = @Path"
0x52c20  ldloc.s  5
0x52c22  callvirt instance int32 [mscorlib]System.String::get_Length()
0x52c27  box      [mscorlib]System.Int32
0x52c2c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x52c31  stloc.s  6
0x52c33  ldarg.0
0x52c34  ldloc.1
0x52c35  ldloc.2
0x52c36  ldloc.s  6
0x52c38  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52c3d  stloc.2
0x52c3e  ldloc.s  4
0x52c40  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52c45  ldstr    aPath// "@Path"
0x52c4a  ldloc.s  5
0x52c4c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52c51  pop
0x52c52  br.s     loc_52C76
0x52c54  ldarg.0
0x52c55  ldloc.1
0x52c56  ldloc.2
0x52c57  ldstr    aCatPathReport// "CAT.[Path] = @Report"
0x52c5c  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52c61  stloc.2
0x52c62  ldloc.s  4
0x52c64  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52c69  ldstr    aReport// "@Report"
0x52c6e  ldloc.s  5
0x52c70  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52c75  pop
0x52c76  ldarg.s  6
0x52c78  brfalse.s loc_52C81
0x52c7a  ldarg.s  6
0x52c7c  ldc.i4.1
0x52c7d  beq.s    loc_52C91
0x52c7f  br.s     loc_52C9F
0x52c81  ldarg.0
0x52c82  ldloc.1
0x52c83  ldloc.2
0x52c84  ldstr    aSEventtypeTime// "S.[EventType] = 'TimedSubscription' OR "...
0x52c89  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52c8e  stloc.2
0x52c8f  br.s     loc_52C9F
0x52c91  ldarg.0
0x52c92  ldloc.1
0x52c93  ldloc.2
0x52c94  ldstr    aSEventtypeRefr// "S.[EventType] = 'RefreshCache' OR S.[Ev"...
0x52c99  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::AddClause(class [mscorlib]System.Text.StringBuilder query, bool isFirst, string clause)
0x52c9e  stloc.2
0x52c9f  ldloc.s  4
0x52ca1  ldloc.1
0x52ca2  callvirt instance string [mscorlib]System.Object::ToString()
0x52ca7  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandText(string)
0x52cac  ldloc.s  4
0x52cae  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x52cb3  stloc.s  7
0x52cb5  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x52cba  stloc.s  8
0x52cbc  br.s     loc_52CEB
0x52cbe  ldnull
0x52cbf  stloc.s  9
0x52cc1  ldloc.s  7
0x52cc3  ldc.i4.0
0x52cc4  ldarg.s  5
0x52cc6  newobj   instance void Microsoft.ReportingServices.Library.SubscriptionImpl::.ctor(class [System.Data]System.Data.IDataRecord record, int32 indexStart, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator)
0x52ccb  stloc.s  9
0x52ccd  leave.s  loc_52CD2
0x52ccf  pop
0x52cd0  leave.s  loc_52CEB
0x52cd2  ldarg.0
0x52cd3  ldloc.s  8
0x52cd5  ldloc.s  9
0x52cd7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x52cdc  call     instance bool Microsoft.ReportingServices.Library.SubscriptionDB::IsDuplicateSubscription(class [mscorlib]System.Collections.Hashtable list, valuetype [mscorlib]System.Guid id)
0x52ce1  brtrue.s loc_52CEB
0x52ce3  ldloc.0
0x52ce4  ldloc.s  9
0x52ce6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.SubscriptionImpl>::Add(var<u1>)
0x52ceb  ldloc.s  7
0x52ced  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x52cf2  brtrue.s loc_52CBE
0x52cf4  leave.s  loc_52D18
0x52cf6  ldloc.s  7
0x52cf8  brfalse.s loc_52D01
0x52cfa  ldloc.s  7
0x52cfc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52d01  endfinally
0x52d02  ldloc.s  4
0x52d04  brfalse.s loc_52D0D
0x52d06  ldloc.s  4
0x52d08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52d0d  endfinally
0x52d0e  ldloc.3
0x52d0f  brfalse.s loc_52D17
0x52d11  ldloc.3
0x52d12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52d17  endfinally
0x52d18  ldloc.0
0x52d19  ret
```
