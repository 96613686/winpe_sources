# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::FetchUpdatableDataSources

- ea: `0x6d70`
- end: `0x6eca`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::FetchUpdatableDataSources`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1e6d0`

## callees

- `0x6d70`
- `0x1ec50`

## string_xrefs

- `0x6e25`: `Connection strings for reports created with October 2020 or newer with enhanced metadata can only update Live connections. Prior versions can update Live and Direct Query connections.`
- `0x6ea6`: `Only AuthType, UserName, Secret and ConnectionString properties can be updated for datasources of DataModel DataSourceSubType`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0x6d75  stloc.0
0x6d76  ldarg.2
0x6d77  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x6d7c  stloc.1
0x6d7d  br       loc_6EB1
0x6d82  newobj   instance void <>c__DisplayClass190_0::.ctor()
0x6d87  stloc.2
0x6d88  ldloc.2
0x6d89  ldloc.1
0x6d8a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x6d8f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6d94  ldarg.1
0x6d95  ldloc.2
0x6d96  ldftn    instance bool <>c__DisplayClass190_0::<FetchUpdatableDataSources>b__0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource x)
0x6d9c  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool>::.ctor(object, native int)
0x6da1  call     T0x2B00002E
0x6da6  call     T0x2B00005A
0x6dab  stloc.3
0x6dac  ldloc.3
0x6dad  brfalse  loc_6EA6
0x6db2  ldloc.3
0x6db3  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x6db8  ldloc.2
0x6db9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6dbe  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_ConnectionString()
0x6dc3  ldc.i4.5
0x6dc4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x6dc9  stloc.s  4
0x6dcb  ldloc.3
0x6dcc  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6dd1  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0x6dd6  stloc.s  5
0x6dd8  ldarg.3
0x6dd9  brfalse.s loc_6DE9
0x6ddb  ldloc.s  4
0x6ddd  brtrue.s loc_6DF5
0x6ddf  ldloc.s  5
0x6de1  ldc.i4.1
0x6de2  beq.s    loc_6DF5
0x6de4  ldloc.s  5
0x6de6  ldc.i4.2
0x6de7  beq.s    loc_6DF5
0x6de9  ldarg.3
0x6dea  brtrue.s loc_6E06
0x6dec  ldloc.s  4
0x6dee  brtrue.s loc_6DF5
0x6df0  ldloc.s  5
0x6df2  ldc.i4.1
0x6df3  bne.un.s loc_6E06
0x6df5  ldloc.0
0x6df6  ldloc.2
0x6df7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6dfc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Add(var<u1>)
0x6e01  br       loc_6EB1
0x6e06  ldloc.s  4
0x6e08  brtrue.s loc_6E30
0x6e0a  ldarg.3
0x6e0b  brfalse.s loc_6E17
0x6e0d  ldloc.s  5
0x6e0f  ldc.i4.1
0x6e10  beq.s    loc_6E17
0x6e12  ldloc.s  5
0x6e14  ldc.i4.2
0x6e15  bne.un.s loc_6E25
0x6e17  ldarg.3
0x6e18  brtrue   loc_6EB1
0x6e1d  ldloc.s  5
0x6e1f  ldc.i4.1
0x6e20  beq      loc_6EB1
0x6e25  ldstr    aConnectionStri// "Connection strings for reports created "...
0x6e2a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x6e2f  throw
0x6e30  ldloc.2
0x6e31  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e36  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6e3b  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x6e40  ldc.i4.2
0x6e41  beq.s    loc_6E8D
0x6e43  ldloc.2
0x6e44  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e49  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6e4e  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x6e53  ldc.i4.3
0x6e54  beq.s    loc_6E69
0x6e56  ldloc.2
0x6e57  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e5c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6e61  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_AuthType()
0x6e66  ldc.i4.4
0x6e67  bne.un.s loc_6E9B
0x6e69  ldloc.2
0x6e6a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e6f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6e74  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Username()
0x6e79  brfalse.s loc_6E9B
0x6e7b  ldloc.2
0x6e7c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e81  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0x6e86  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Secret()
0x6e8b  brfalse.s loc_6E9B
0x6e8d  ldloc.0
0x6e8e  ldloc.2
0x6e8f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass190_0::'ds'
0x6e94  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Add(var<u1>)
0x6e99  br.s     loc_6EB1
0x6e9b  ldstr    aConnectionstri// "ConnectionString modified without updat"...
0x6ea0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x6ea5  throw
0x6ea6  ldstr    aOnlyAuthtypeUs// "Only AuthType, UserName, Secret and Con"...
0x6eab  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CatalogItemContentInvalidException::.ctor(string)
0x6eb0  throw
0x6eb1  ldloc.1
0x6eb2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6eb7  brtrue   loc_6D82
0x6ebc  leave.s  loc_6EC8
0x6ebe  ldloc.1
0x6ebf  brfalse.s loc_6EC7
0x6ec1  ldloc.1
0x6ec2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ec7  endfinally
0x6ec8  ldloc.0
0x6ec9  ret
```
