# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelDataSourcesTrusted

- ea: `0x6940`
- end: `0x6c74`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelDataSourcesTrusted`
- size: `820`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x38d0`
- `0x1d7f0`

## callees

- `0x67a0`
- `0x6940`
- `0x12db0`
- `0x1cbf0`

## pseudocode

```c

```

## disassembly

```asm
0x6940  ldarg.1
0x6941  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6946  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType(class [mscorlib]System.Security.Principal.IIdentity identity)
0x694b  stloc.0
0x694c  ldarg.0
0x694d  ldarg.1
0x694e  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6953  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x6958  ldloc.0
0x6959  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetUserId(string userName, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x695e  stloc.1
0x695f  ldarg.3
0x6960  stloc.2
0x6961  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0x6966  stloc.3
0x6967  ldarg.3
0x6968  brfalse  loc_6C73
0x696d  ldarg.s  4
0x696f  brfalse  loc_6B4D
0x6974  ldarg.0
0x6975  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x697a  ldarg.2
0x697b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x6980  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_Result()
0x6985  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__185_0
0x698a  dup
0x698b  brtrue.s loc_69A4
0x698d  pop
0x698e  ldsfld   class <>c <>c::<>9
0x6993  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<SetDataModelDataSourcesTrusted>b__185_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity d)
0x6999  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0x699e  dup
0x699f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__185_0
0x69a4  call     T0x2B000001
0x69a9  stloc.s  4
0x69ab  ldarg.3
0x69ac  ldloc.s  4
0x69ae  newobj   instance void DataSourceModelComparer::.ctor()
0x69b3  call     T0x2B000052
0x69b8  stloc.2
0x69b9  ldloc.s  4
0x69bb  ldarg.3
0x69bc  newobj   instance void DataSourceModelComparer::.ctor()
0x69c1  call     T0x2B000052
0x69c6  call     T0x2B000002
0x69cb  stloc.3
0x69cc  ldarg.3
0x69cd  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__185_1
0x69d2  dup
0x69d3  brtrue.s loc_69EC
0x69d5  pop
0x69d6  ldsfld   class <>c <>c::<>9
0x69db  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<SetDataModelDataSourcesTrusted>b__185_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource p)
0x69e1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0x69e6  dup
0x69e7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__185_1
0x69ec  newobj   instance void DataSourceModelComparer::.ctor()
0x69f1  call     T0x2B000053
0x69f6  stloc.s  5
0x69f8  ldloc.s  4
0x69fa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x69ff  stloc.s  8
0x6a01  br       loc_6A93
0x6a06  ldloc.s  8
0x6a08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x6a0d  stloc.s  9
0x6a0f  ldloc.s  5
0x6a11  ldloc.s  9
0x6a13  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::ContainsKey(var<u1>)
0x6a18  brfalse.s loc_6A93
0x6a1a  ldloc.s  5
0x6a1c  ldloc.s  9
0x6a1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Item(void)
0x6a23  stloc.s  0xA
0x6a25  ldloc.s  9
0x6a27  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6a2c  dup
0x6a2d  brtrue.s loc_6A33
0x6a2f  pop
0x6a30  ldnull
0x6a31  br.s     loc_6A38
0x6a33  call     instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_ModelConnectionName()
0x6a38  ldloc.s  0xA
0x6a3a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6a3f  dup
0x6a40  brtrue.s loc_6A46
0x6a42  pop
0x6a43  ldnull
0x6a44  br.s     loc_6A4B
0x6a46  call     instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_ModelConnectionName()
0x6a4b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6a50  brfalse.s loc_6A93
0x6a52  ldarg.0
0x6a53  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x6a58  ldloc.s  9
0x6a5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x6a5f  ldloc.s  0xA
0x6a61  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6a66  dup
0x6a67  brtrue.s loc_6A6D
0x6a69  pop
0x6a6a  ldnull
0x6a6b  br.s     loc_6A72
0x6a6d  call     instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_ModelConnectionName()
0x6a72  ldarg.0
0x6a73  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_crypto
0x6a78  ldloc.s  0xA
0x6a7a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x6a7f  dup
0x6a80  brtrue.s loc_6A88
0x6a82  pop
0x6a83  ldsfld   string [mscorlib]System.String::Empty
0x6a88  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::Encrypt(string)
0x6a8d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::UpdateDataModelDataSourceConnectionNameAsync(valuetype [mscorlib]System.Guid, string, unsigned int8[])
0x6a92  pop
0x6a93  ldloc.s  8
0x6a95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a9a  brtrue   loc_6A06
0x6a9f  leave.s  loc_6AAD
0x6aa1  ldloc.s  8
0x6aa3  brfalse.s loc_6AAC
0x6aa5  ldloc.s  8
0x6aa7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6aac  endfinally
0x6aad  ldloc.2
0x6aae  call     T0x2B00002F
0x6ab3  brtrue.s loc_6ABC
0x6ab5  ldstr    aNone// "None"
0x6aba  br.s     loc_6AEB
0x6abc  ldstr    asc_2610A// ","
0x6ac1  ldloc.2
0x6ac2  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string> <>c::<>9__185_2
0x6ac7  dup
0x6ac8  brtrue.s loc_6AE1
0x6aca  pop
0x6acb  ldsfld   class <>c <>c::<>9
0x6ad0  ldftn    instance string <>c::<SetDataModelDataSourcesTrusted>b__185_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource p)
0x6ad6  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string>::.ctor(object, native int)
0x6adb  dup
0x6adc  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string> <>c::<>9__185_2
0x6ae1  call     T0x2B000054
0x6ae6  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x6aeb  stloc.s  6
0x6aed  ldloc.3
0x6aee  call     T0x2B00002F
0x6af3  brtrue.s loc_6AFC
0x6af5  ldstr    aNone// "None"
0x6afa  br.s     loc_6B2B
0x6afc  ldstr    asc_2610A// ","
0x6b01  ldloc.3
0x6b02  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string> <>c::<>9__185_3
0x6b07  dup
0x6b08  brtrue.s loc_6B21
0x6b0a  pop
0x6b0b  ldsfld   class <>c <>c::<>9
0x6b10  ldftn    instance string <>c::<SetDataModelDataSourcesTrusted>b__185_3(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource p)
0x6b16  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string>::.ctor(object, native int)
0x6b1b  dup
0x6b1c  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, string> <>c::<>9__185_3
0x6b21  call     T0x2B000054
0x6b26  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x6b2b  stloc.s  7
0x6b2d  ldarg.0
0x6b2e  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x6b33  ldc.i4.3
0x6b34  ldstr    aOverwrittingFo// "Overwritting for item {0} is removing c"...
0x6b39  ldarg.2
0x6b3a  box      [mscorlib]System.Guid
0x6b3f  ldloc.s  7
0x6b41  ldloc.s  6
0x6b43  call     string [mscorlib]System.String::Format(string, object, object, object)
0x6b48  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6b4d  ldloc.2
0x6b4e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x6b53  stloc.s  8
0x6b55  br       loc_6C1A
0x6b5a  ldloc.s  8
0x6b5c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x6b61  stloc.s  0xB
0x6b63  ldarg.0
0x6b64  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x6b69  ldarg.2
0x6b6a  ldloc.s  0xB
0x6b6c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6b71  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0x6b76  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType
0x6b7b  call     T0x2B000055
0x6b80  ldloc.s  0xB
0x6b82  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6b87  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Kind()
0x6b8c  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind
0x6b91  call     T0x2B000056
0x6b96  ldloc.s  0xB
0x6b98  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6b9d  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x6ba2  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType
0x6ba7  call     T0x2B000057
0x6bac  ldarg.0
0x6bad  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_crypto
0x6bb2  ldloc.s  0xB
0x6bb4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x6bb9  dup
0x6bba  brtrue.s loc_6BC2
0x6bbc  pop
0x6bbd  ldsfld   string [mscorlib]System.String::Empty
0x6bc2  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::Encrypt(string)
0x6bc7  ldarg.0
0x6bc8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_crypto
0x6bcd  ldloc.s  0xB
0x6bcf  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6bd4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Username()
0x6bd9  dup
0x6bda  brtrue.s loc_6BE2
0x6bdc  pop
0x6bdd  ldsfld   string [mscorlib]System.String::Empty
0x6be2  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::Encrypt(string)
0x6be7  ldarg.0
0x6be8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_crypto
0x6bed  ldloc.s  0xB
0x6bef  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6bf4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Secret()
0x6bf9  dup
0x6bfa  brtrue.s loc_6C02
0x6bfc  pop
0x6bfd  ldsfld   string [mscorlib]System.String::Empty
0x6c02  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::Encrypt(string)
0x6c07  ldloc.1
0x6c08  ldloc.s  0xB
0x6c0a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6c0f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_ModelConnectionName()
0x6c14  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::AddDataModelDataSourceAsync(valuetype [mscorlib]System.Guid, valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceType, valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceKind, valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity/DataModelDataSourceAuthType, unsigned int8[], unsigned int8[], unsigned int8[], valuetype [mscorlib]System.Guid, string)
0x6c19  pop
0x6c1a  ldloc.s  8
0x6c1c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6c21  brtrue   loc_6B5A
0x6c26  leave.s  loc_6C34
0x6c28  ldloc.s  8
0x6c2a  brfalse.s loc_6C33
0x6c2c  ldloc.s  8
0x6c2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c33  endfinally
0x6c34  ldloc.3
0x6c35  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x6c3a  stloc.s  0xC
0x6c3c  br.s     loc_6C5A
0x6c3e  ldloca.s 0xC
0x6c40  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x6c45  stloc.s  0xD
0x6c47  ldarg.0
0x6c48  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x6c4d  ldloc.s  0xD
0x6c4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x6c54  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::DeleteDataModelDataSourceByIdAsync(valuetype [mscorlib]System.Guid)
0x6c59  pop
0x6c5a  ldloca.s 0xC
0x6c5c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::MoveNext()
0x6c61  brtrue.s loc_6C3E
0x6c63  leave.s  loc_6C73
0x6c65  ldloca.s 0xC
0x6c67  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>
0x6c6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c72  endfinally
0x6c73  ret
```
