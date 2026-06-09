# <UpdateDataModelDataSourcesAsync>d__187::MoveNext

- ea: `0x1e6d0`
- end: `0x1eb05`
- name: `<UpdateDataModelDataSourcesAsync>d__187::MoveNext`
- size: `1077`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x1a00`
- `0x1a70`
- `0x3be0`
- `0x5ff0`
- `0x67a0`
- `0x6ce0`
- `0x6d70`
- `0x9e80`
- `0xdcf0`
- `0x12db0`
- `0x1e6d0`

## string_xrefs

- `0x1e77a`: `Unable to update the datasources for '{0}'. '{1}' is not a supported authentication type for '{2}' datasources.`

## pseudocode

```c

```

## disassembly

```asm
0x1e6d0  ldarg.0
0x1e6d1  ldfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1e6d6  stloc.0
0x1e6d7  ldarg.0
0x1e6d8  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <UpdateDataModelDataSourcesAsync>d__187::<>4__this
0x1e6dd  stloc.1
0x1e6de  ldloc.0
0x1e6df  switch   loc_1E82B, loc_1E91A, loc_1EA6E
0x1e6f0  ldarg.0
0x1e6f1  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelDataSourcesAsync>d__187::userPrincipal
0x1e6f6  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1e6fb  stloc.2
0x1e6fc  ldarg.0
0x1e6fd  ldloc.2
0x1e6fe  ldarg.0
0x1e6ff  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::itemId
0x1e704  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x1e709  stfld    string <UpdateDataModelDataSourcesAsync>d__187::<path>5__2
0x1e70e  ldloc.1
0x1e70f  ldloc.2
0x1e710  ldarg.0
0x1e711  ldfld    string <UpdateDataModelDataSourcesAsync>d__187::<path>5__2
0x1e716  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x1e71b  ldc.i4.6
0x1e71c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x1e721  ldarg.0
0x1e722  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::dataSources
0x1e727  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x1e72c  stloc.s  9
0x1e72e  br       loc_1E7C6
0x1e733  ldloca.s 9
0x1e735  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x1e73a  stloc.s  0xA
0x1e73c  ldloc.s  0xA
0x1e73e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e743  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x1e748  brfalse.s loc_1E7C6
0x1e74a  ldloc.s  0xA
0x1e74c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e751  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Kind()
0x1e756  ldloc.s  0xA
0x1e758  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e75d  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0x1e762  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType[] Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::GetSupportedAuthKinds(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind datasourceKind, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType datasourceType)
0x1e767  ldloc.s  0xA
0x1e769  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e76e  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x1e773  call     T0x2B000114
0x1e778  brtrue.s loc_1E7C6
0x1e77a  ldstr    aUnableToUpdate// "Unable to update the datasources for '{"...
0x1e77f  ldarg.0
0x1e780  ldfld    string <UpdateDataModelDataSourcesAsync>d__187::<path>5__2
0x1e785  ldloc.s  0xA
0x1e787  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e78c  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x1e791  stloc.s  0xB
0x1e793  ldloca.s 0xB
0x1e795  constrained. [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType
0x1e79b  callvirt instance string [mscorlib]System.Object::ToString()
0x1e7a0  ldloc.s  0xA
0x1e7a2  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e7a7  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0x1e7ac  stloc.s  0xC
0x1e7ae  ldloca.s 0xC
0x1e7b0  constrained. [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType
0x1e7b6  callvirt instance string [mscorlib]System.Object::ToString()
0x1e7bb  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1e7c0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x1e7c5  throw
0x1e7c6  ldloca.s 9
0x1e7c8  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::MoveNext()
0x1e7cd  brtrue   loc_1E733
0x1e7d2  leave.s  loc_1E7E6
0x1e7d4  ldloc.0
0x1e7d5  ldc.i4.0
0x1e7d6  bge.s    loc_1E7E5
0x1e7d8  ldloca.s 9
0x1e7da  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>
0x1e7e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e7e5  endfinally
0x1e7e6  ldloc.1
0x1e7e7  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x1e7ec  ldarg.0
0x1e7ed  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::itemId
0x1e7f2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x1e7f7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::GetAwaiter()
0x1e7fc  stloc.s  0xD
0x1e7fe  ldloca.s 0xD
0x1e800  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_IsCompleted()
0x1e805  brtrue.s loc_1E848
0x1e807  ldarg.0
0x1e808  ldc.i4.0
0x1e809  dup
0x1e80a  stloc.0
0x1e80b  stfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1e810  ldarg.0
0x1e811  ldloc.s  0xD
0x1e813  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1e818  ldarg.0
0x1e819  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelDataSourcesAsync>d__187::<>t__builder
0x1e81e  ldloca.s 0xD
0x1e820  ldarg.0
0x1e821  call     T0x2B000115
0x1e826  leave    loc_1EB04
0x1e82b  ldarg.0
0x1e82c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1e831  stloc.s  0xD
0x1e833  ldarg.0
0x1e834  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1e839  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>
0x1e83f  ldarg.0
0x1e840  ldc.i4.m1
0x1e841  dup
0x1e842  stloc.0
0x1e843  stfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1e848  ldloca.s 0xD
0x1e84a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::GetResult()
0x1e84f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__187_0
0x1e854  dup
0x1e855  brtrue.s loc_1E86E
0x1e857  pop
0x1e858  ldsfld   class <>c <>c::<>9
0x1e85d  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<UpdateDataModelDataSourcesAsync>b__187_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity d)
0x1e863  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0x1e868  dup
0x1e869  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__187_0
0x1e86e  call     T0x2B000001
0x1e873  stloc.3
0x1e874  ldloc.1
0x1e875  ldarg.0
0x1e876  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelDataSourcesAsync>d__187::userPrincipal
0x1e87b  ldarg.0
0x1e87c  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::itemId
0x1e881  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x1e886  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x1e88b  call     T0x2B000003
0x1e890  ldsfld   class [mscorlib]System.Predicate`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__187_1
0x1e895  dup
0x1e896  brtrue.s loc_1E8AF
0x1e898  pop
0x1e899  ldsfld   class <>c <>c::<>9
0x1e89e  ldftn    instance bool <>c::<UpdateDataModelDataSourcesAsync>b__187_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property a)
0x1e8a4  newobj   instance void class [mscorlib]System.Predicate`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor(object, native int)
0x1e8a9  dup
0x1e8aa  stsfld   class [mscorlib]System.Predicate`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__187_1
0x1e8af  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::Find(!!T0)
0x1e8b4  dup
0x1e8b5  brtrue.s loc_1E8BB
0x1e8b7  pop
0x1e8b8  ldnull
0x1e8b9  br.s     loc_1E8C0
0x1e8bb  call     instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x1e8c0  ldstr    aPowerbiV3// "PowerBI_V3"
0x1e8c5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1e8ca  stloc.s  4
0x1e8cc  ldloc.1
0x1e8cd  ldloc.3
0x1e8ce  ldarg.0
0x1e8cf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::dataSources
0x1e8d4  ldloc.s  4
0x1e8d6  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::FetchUpdatableDataSources(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> existingDataModelDataSources, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources, bool isV1Model)
0x1e8db  stloc.s  5
0x1e8dd  ldarg.0
0x1e8de  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelDataSourcesAsync>d__187::userPrincipal
0x1e8e3  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x1e8e8  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType(class [mscorlib]System.Security.Principal.IIdentity identity)
0x1e8ed  stloc.s  6
0x1e8ef  ldarg.0
0x1e8f0  ldloc.1
0x1e8f1  ldarg.0
0x1e8f2  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelDataSourcesAsync>d__187::userPrincipal
0x1e8f7  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x1e8fc  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1e901  ldloc.s  6
0x1e903  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetUserId(string userName, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x1e908  stfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::<userId>5__3
0x1e90d  ldarg.0
0x1e90e  ldloc.s  5
0x1e910  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x1e915  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1e91a  nop
0x1e91b  ldloc.0
0x1e91c  ldc.i4.1
0x1e91d  beq      loc_1E9D3
0x1e922  br       loc_1E9F8
0x1e927  ldarg.0
0x1e928  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1e92d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x1e932  stloc.s  0xE
0x1e934  ldloc.1
0x1e935  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x1e93a  ldloc.s  0xE
0x1e93c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1e941  ldloc.s  0xE
0x1e943  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e948  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x1e94d  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType
0x1e952  call     T0x2B000057
0x1e957  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x1e95c  ldloc.s  0xE
0x1e95e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x1e963  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Encrypt(string)
0x1e968  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x1e96d  ldloc.s  0xE
0x1e96f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e974  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Username()
0x1e979  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Encrypt(string)
0x1e97e  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x1e983  ldloc.s  0xE
0x1e985  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x1e98a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Secret()
0x1e98f  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::Encrypt(string)
0x1e994  ldarg.0
0x1e995  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::<userId>5__3
0x1e99a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::UpdateDataModelDataSourceAsync(valuetype [mscorlib]System.Guid, valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType, unsigned int8[], unsigned int8[], unsigned int8[], valuetype [mscorlib]System.Guid)
0x1e99f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x1e9a4  stloc.s  0xF
0x1e9a6  ldloca.s 0xF
0x1e9a8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x1e9ad  brtrue.s loc_1E9F0
0x1e9af  ldarg.0
0x1e9b0  ldc.i4.1
0x1e9b1  dup
0x1e9b2  stloc.0
0x1e9b3  stfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1e9b8  ldarg.0
0x1e9b9  ldloc.s  0xF
0x1e9bb  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelDataSourcesAsync>d__187::<>u__2
0x1e9c0  ldarg.0
0x1e9c1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelDataSourcesAsync>d__187::<>t__builder
0x1e9c6  ldloca.s 0xF
0x1e9c8  ldarg.0
0x1e9c9  call     T0x2B000116
0x1e9ce  leave    loc_1EB04
0x1e9d3  ldarg.0
0x1e9d4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelDataSourcesAsync>d__187::<>u__2
0x1e9d9  stloc.s  0xF
0x1e9db  ldarg.0
0x1e9dc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelDataSourcesAsync>d__187::<>u__2
0x1e9e1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x1e9e7  ldarg.0
0x1e9e8  ldc.i4.m1
0x1e9e9  dup
0x1e9ea  stloc.0
0x1e9eb  stfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1e9f0  ldloca.s 0xF
0x1e9f2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x1e9f7  pop
0x1e9f8  ldarg.0
0x1e9f9  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1e9fe  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ea03  brtrue   loc_1E927
0x1ea08  leave.s  loc_1EA22
0x1ea0a  ldloc.0
0x1ea0b  ldc.i4.0
0x1ea0c  bge.s    loc_1EA21
0x1ea0e  ldarg.0
0x1ea0f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1ea14  brfalse.s loc_1EA21
0x1ea16  ldarg.0
0x1ea17  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1ea1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ea21  endfinally
0x1ea22  ldarg.0
0x1ea23  ldnull
0x1ea24  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <UpdateDataModelDataSourcesAsync>d__187::<>7__wrap3
0x1ea29  ldloc.1
0x1ea2a  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x1ea2f  ldarg.0
0x1ea30  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelDataSourcesAsync>d__187::itemId
0x1ea35  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x1ea3a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::GetAwaiter()
0x1ea3f  stloc.s  0xD
0x1ea41  ldloca.s 0xD
0x1ea43  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_IsCompleted()
0x1ea48  brtrue.s loc_1EA8B
0x1ea4a  ldarg.0
0x1ea4b  ldc.i4.2
0x1ea4c  dup
0x1ea4d  stloc.0
0x1ea4e  stfld    int32 <UpdateDataModelDataSourcesAsync>d__187::<>1__state
0x1ea53  ldarg.0
0x1ea54  ldloc.s  0xD
0x1ea56  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1ea5b  ldarg.0
0x1ea5c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelDataSourcesAsync>d__187::<>t__builder
0x1ea61  ldloca.s 0xD
0x1ea63  ldarg.0
0x1ea64  call     T0x2B000115
0x1ea69  leave    loc_1EB04
0x1ea6e  ldarg.0
0x1ea6f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1ea74  stloc.s  0xD
0x1ea76  ldarg.0
0x1ea77  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> <UpdateDataModelDataSourcesAsync>d__187::<>u__1
0x1ea7c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>
0x1ea82  ldarg.0
0x1ea83  ldc.i4.m1
0x1ea84  dup
0x1ea85  stloc.0
  ... truncated ...
```
