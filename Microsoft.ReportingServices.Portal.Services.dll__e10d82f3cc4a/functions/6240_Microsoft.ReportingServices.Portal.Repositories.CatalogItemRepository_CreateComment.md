# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateComment

- ea: `0x6240`
- end: `0x648d`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateComment`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a70`
- `0x61b0`
- `0x6240`
- `0x65d0`
- `0x9e80`
- `0xaab0`
- `0xd820`

## string_xrefs

- `0x6257`: `ItemId was null when passed to CreateComment`
- `0x62c0`: `Comment {0} has an invalid attachment path.`
- `0x6354`: `Comment {0}`
- `0x6389`: `Parent of comment {0} is not top-level`
- `0x646f`: `Error in creating a CommentAddedAlert event: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6240  ldarg.2
0x6241  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6246  stloc.3
0x6247  ldloca.s 3
0x6249  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x624e  brtrue.s loc_6261
0x6250  ldarg.0
0x6251  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x6256  ldc.i4.1
0x6257  ldstr    aItemidWasNullW// "ItemId was null when passed to CreateCo"...
0x625c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6261  ldarg.1
0x6262  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x6267  stloc.0
0x6268  ldloc.0
0x6269  ldc.i4.1
0x626a  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x626f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x6274  ldarg.0
0x6275  ldloc.0
0x6276  ldarg.2
0x6277  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x627c  stloc.3
0x627d  ldloca.s 3
0x627f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x6284  ldc.i4.0
0x6285  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid itemId, bool checkDelete)
0x628a  ldarg.0
0x628b  ldarg.1
0x628c  ldarg.2
0x628d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6292  stloc.3
0x6293  ldloca.s 3
0x6295  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x629a  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x629f  stloc.1
0x62a0  ldarg.2
0x62a1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_AttachmentPath()
0x62a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x62ab  brtrue.s loc_62E3
0x62ad  ldarg.2
0x62ae  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_AttachmentPath()
0x62b3  ldloc.1
0x62b4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x62b9  call     bool Microsoft.ReportingServices.Portal.Services.Util.CatalogItemPathUtils::IsParentOf(string path, string basePath)
0x62be  brtrue.s loc_62E3
0x62c0  ldstr    aComment0HasAnI// "Comment {0} has an invalid attachment p"...
0x62c5  ldarg.2
0x62c6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x62cb  stloc.3
0x62cc  ldloca.s 3
0x62ce  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x62d3  box      [mscorlib]System.Guid
0x62d8  call     string [mscorlib]System.String::Format(string, object)
0x62dd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x62e2  throw
0x62e3  ldarg.2
0x62e4  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ThreadId()
0x62e9  stloc.s  4
0x62eb  ldloca.s 4
0x62ed  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x62f2  brfalse  loc_63AC
0x62f7  ldarg.0
0x62f8  ldarg.1
0x62f9  ldarg.2
0x62fa  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ThreadId()
0x62ff  stloc.s  4
0x6301  ldloca.s 4
0x6303  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x6308  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetComment(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, int64 id)
0x630d  stloc.s  5
0x630f  ldloc.s  5
0x6311  brfalse.s loc_6354
0x6313  ldloc.s  5
0x6315  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x631a  stloc.3
0x631b  ldarg.2
0x631c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6321  stloc.s  7
0x6323  ldloca.s 7
0x6325  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x632a  stloc.s  6
0x632c  ldloca.s 3
0x632e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x6333  brtrue.s loc_6338
0x6335  ldc.i4.1
0x6336  br.s     loc_6352
0x6338  ldloca.s 3
0x633a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x633f  brtrue.s loc_6344
0x6341  ldc.i4.0
0x6342  br.s     loc_6352
0x6344  ldloca.s 3
0x6346  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x634b  ldloc.s  6
0x634d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6352  brfalse.s loc_6377
0x6354  ldstr    aComment0// "Comment {0}"
0x6359  ldarg.2
0x635a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x635f  stloc.3
0x6360  ldloca.s 3
0x6362  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x6367  box      [mscorlib]System.Guid
0x636c  call     string [mscorlib]System.String::Format(string, object)
0x6371  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x6376  throw
0x6377  ldloc.s  5
0x6379  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ThreadId()
0x637e  stloc.s  4
0x6380  ldloca.s 4
0x6382  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x6387  brfalse.s loc_63AC
0x6389  ldstr    aParentOfCommen// "Parent of comment {0} is not top-level"
0x638e  ldarg.2
0x638f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6394  stloc.3
0x6395  ldloca.s 3
0x6397  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x639c  box      [mscorlib]System.Guid
0x63a1  call     string [mscorlib]System.String::Format(string, object)
0x63a6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x63ab  throw
0x63ac  ldarg.0
0x63ad  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x63b2  ldarg.2
0x63b3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x63b8  stloc.3
0x63b9  ldloca.s 3
0x63bb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x63c0  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::GetCommentsCountByItemAsync(valuetype [mscorlib]System.Guid)
0x63c5  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<int32>::get_Result()
0x63ca  ldc.i4.s 0x64
0x63cc  blt.s    loc_63D4
0x63ce  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MaxCountCommentsException::.ctor()
0x63d3  throw
0x63d4  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::.ctor()
0x63d9  dup
0x63da  ldarg.2
0x63db  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x63e0  stloc.3
0x63e1  ldloca.s 3
0x63e3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x63e8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_ItemId(valuetype [mscorlib]System.Guid)
0x63ed  dup
0x63ee  ldarg.2
0x63ef  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_Text()
0x63f4  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_Text(string)
0x63f9  dup
0x63fa  ldarg.2
0x63fb  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ThreadId()
0x6400  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_ThreadId(valuetype [mscorlib]System.Nullable`1<int64>)
0x6405  dup
0x6406  ldarg.2
0x6407  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_AttachmentPath()
0x640c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_AttachmentPath(string)
0x6411  stloc.2
0x6412  ldloc.0
0x6413  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x6418  stloc.s  8
0x641a  ldloc.0
0x641b  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x6420  ldloc.2
0x6421  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::InsertComment(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment)
0x6426  stloc.s  9
0x6428  ldarg.3
0x6429  ldloc.s  9
0x642b  brtrue.s loc_6430
0x642d  ldnull
0x642e  br.s     loc_6437
0x6430  ldloc.s  9
0x6432  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment Microsoft.ReportingServices.Portal.Services.ODataExtensions.CommentExtensions::ToOdataModel(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment comment)
0x6437  stind.ref
0x6438  ldloc.s  8
0x643a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::Commit()
0x643f  leave.s  loc_644D
0x6441  ldloc.s  8
0x6443  brfalse.s loc_644C
0x6445  ldloc.s  8
0x6447  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x644c  endfinally
0x644d  ldarg.3
0x644e  ldind.ref
0x644f  brfalse.s loc_6487
0x6451  ldarg.0
0x6452  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x6457  ldarg.3
0x6458  ldind.ref
0x6459  callvirt instance int64 [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_Id()
0x645e  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::AddCommentEvent(int64)
0x6463  pop
0x6464  leave.s  loc_6487
0x6466  stloc.s  0xA
0x6468  ldarg.0
0x6469  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x646e  ldc.i4.1
0x646f  ldstr    aErrorInCreatin// "Error in creating a CommentAddedAlert e"...
0x6474  ldloc.s  0xA
0x6476  callvirt instance string [mscorlib]System.Object::ToString()
0x647b  call     string [mscorlib]System.String::Format(string, object)
0x6480  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6485  leave.s  loc_6487
0x6487  ldarg.3
0x6488  ldind.ref
0x6489  ldnull
0x648a  cgt.un
0x648c  ret
```
