# ModelStorage::ListModelPerspectives

- ea: `0x89530`
- end: `0x896f3`
- name: `ModelStorage::ListModelPerspectives`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x30d80`

## callees

- `0x1d860`
- `0x1e2e0`
- `0x1e510`
- `0x1e570`
- `0x4aa70`
- `0x6fd80`
- `0x6fda0`
- `0x89530`

## string_xrefs

- `0x89540`: `@Path`
- `0x895cf`: `ModelStorage.ListModelPerspectives: Read several models`

## pseudocode

```c

```

## disassembly

```asm
0x89530  ldnull
0x89531  stloc.0
0x89532  ldarg.0
0x89533  ldstr    aGetmodelperspe// "GetModelPerspectives"
0x89538  ldnull
0x89539  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8953e  stloc.1
0x8953f  ldloc.1
0x89540  ldstr    aPath// "@Path"
0x89545  ldc.i4.s 0xC
0x89547  ldarg.1
0x89548  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x8954d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x89552  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x89557  pop
0x89558  ldloc.1
0x89559  ldstr    aAuthtype// "@AuthType"
0x8955e  ldc.i4.8
0x8955f  ldarg.2
0x89560  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x89565  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x8956a  box      [mscorlib]System.Int32
0x8956f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x89574  pop
0x89575  ldloc.1
0x89576  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x8957b  stloc.2
0x8957c  ldloc.2
0x8957d  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x89582  brtrue.s loc_89595
0x89584  ldarg.1
0x89585  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0x8958a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8958f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x89594  throw
0x89595  ldloc.2
0x89596  ldc.i4.0
0x89597  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x8959c  stloc.3
0x8959d  ldnull
0x8959e  stloc.s  4
0x895a0  ldloc.2
0x895a1  ldc.i4.1
0x895a2  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x895a7  brtrue.s loc_895B2
0x895a9  ldloc.2
0x895aa  ldc.i4.1
0x895ab  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x895b0  stloc.s  4
0x895b2  ldnull
0x895b3  stloc.s  5
0x895b5  ldloc.2
0x895b6  ldc.i4.2
0x895b7  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x895bc  brtrue.s loc_895C7
0x895be  ldloc.2
0x895bf  ldc.i4.2
0x895c0  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x895c5  stloc.s  5
0x895c7  ldloc.2
0x895c8  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x895cd  brfalse.s loc_895DA
0x895cf  ldstr    aModelstorageLi// "ModelStorage.ListModelPerspectives: Rea"...
0x895d4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x895d9  throw
0x895da  ldloc.3
0x895db  ldarg.1
0x895dc  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0x895e1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x895e6  ldc.i4.1
0x895e7  newarr   Microsoft.ReportingServices.Library.ItemType
0x895ec  dup
0x895ed  ldc.i4.0
0x895ee  ldc.i4.6
0x895ef  stelem.i4
0x895f0  call     void Microsoft.ReportingServices.Library.RSService::EnsureItemType(valuetype Microsoft.ReportingServices.Library.ItemType actualType, string path, valuetype Microsoft.ReportingServices.Library.ItemType[] expectedTypes)
0x895f5  ldarg.2
0x895f6  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x895fb  ldloc.3
0x895fc  ldloc.s  4
0x895fe  ldc.i4.1
0x895ff  ldarg.1
0x89600  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x89605  callvirt instance bool Microsoft.ReportingServices.Library.Security::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType catItemType, unsigned int8[] secDesc, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation modelOperation, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath path)
0x8960a  brtrue.s loc_8961A
0x8960c  ldarg.2
0x8960d  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x89612  ldc.i4.s 0x59
0x89614  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x89619  throw
0x8961a  newobj   instance void Microsoft.ReportingServices.Library.Soap2005.ModelCatalogItem::.ctor()
0x8961f  stloc.0
0x89620  ldloc.0
0x89621  ldarg.1
0x89622  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x89627  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8962c  stfld    string Microsoft.ReportingServices.Library.Soap2005.ModelCatalogItem::Model
0x89631  ldloc.0
0x89632  ldloc.s  5
0x89634  stfld    string Microsoft.ReportingServices.Library.Soap2005.ModelCatalogItem::Description
0x89639  ldloc.2
0x8963a  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x8963f  brtrue.s loc_8964C
0x89641  ldstr    aModelstorageLi_0// "ModelStorage.ListModelPerspectives: no "...
0x89646  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8964b  throw
0x8964c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelPerspective>::.ctor()
0x89651  stloc.s  6
0x89653  br.s     loc_896B3
0x89655  ldloc.2
0x89656  ldc.i4.0
0x89657  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x8965c  stloc.s  7
0x8965e  ldnull
0x8965f  stloc.s  8
0x89661  ldloc.2
0x89662  ldc.i4.1
0x89663  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x89668  brtrue.s loc_89673
0x8966a  ldloc.2
0x8966b  ldc.i4.1
0x8966c  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x89671  stloc.s  8
0x89673  ldnull
0x89674  stloc.s  9
0x89676  ldloc.2
0x89677  ldc.i4.2
0x89678  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x8967d  brtrue.s loc_89688
0x8967f  ldloc.2
0x89680  ldc.i4.2
0x89681  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x89686  stloc.s  9
0x89688  newobj   instance void Microsoft.ReportingServices.Library.Soap2005.ModelPerspective::.ctor()
0x8968d  stloc.s  0xA
0x8968f  ldloc.s  0xA
0x89691  ldloc.s  7
0x89693  stfld    string Microsoft.ReportingServices.Library.Soap2005.ModelPerspective::ID
0x89698  ldloc.s  0xA
0x8969a  ldloc.s  8
0x8969c  stfld    string Microsoft.ReportingServices.Library.Soap2005.ModelPerspective::Name
0x896a1  ldloc.s  0xA
0x896a3  ldloc.s  9
0x896a5  stfld    string Microsoft.ReportingServices.Library.Soap2005.ModelPerspective::Description
0x896aa  ldloc.s  6
0x896ac  ldloc.s  0xA
0x896ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelPerspective>::Add(var<u1>)
0x896b3  ldloc.2
0x896b4  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x896b9  brtrue.s loc_89655
0x896bb  ldloc.0
0x896bc  ldloc.s  6
0x896be  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.Soap2005.ModelPerspective>::ToArray()
0x896c3  stfld    class Microsoft.ReportingServices.Library.Soap2005.ModelPerspective[] Microsoft.ReportingServices.Library.Soap2005.ModelCatalogItem::Perspectives
0x896c8  ldloc.2
0x896c9  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x896ce  brfalse.s loc_896DB
0x896d0  ldstr    aModelstorageLi_1// "ModelStorage.ListModelPerspectives: thi"...
0x896d5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x896da  throw
0x896db  leave.s  loc_896F1
0x896dd  ldloc.2
0x896de  brfalse.s loc_896E6
0x896e0  ldloc.2
0x896e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x896e6  endfinally
0x896e7  ldloc.1
0x896e8  brfalse.s loc_896F0
0x896ea  ldloc.1
0x896eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x896f0  endfinally
0x896f1  ldloc.0
0x896f2  ret
```
