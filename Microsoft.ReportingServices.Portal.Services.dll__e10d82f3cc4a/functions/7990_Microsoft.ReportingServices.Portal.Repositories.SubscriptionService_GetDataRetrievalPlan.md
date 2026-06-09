# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetDataRetrievalPlan

- ea: `0x7990`
- end: `0x7a85`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetDataRetrievalPlan`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7600`
- `0x7910`

## callees

- `0x7990`
- `0xe320`
- `0x113e0`
- `0x11510`

## pseudocode

```c

```

## disassembly

```asm
0x7990  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::.ctor()
0x7995  stloc.0
0x7996  ldarg.2
0x7997  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_DataSource()
0x799c  brfalse.s loc_79EB
0x799e  ldarg.2
0x799f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_DataSource()
0x79a4  call     class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSource Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToProxy2010DataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource 'ds')
0x79a9  stloc.1
0x79aa  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition::.ctor()
0x79af  dup
0x79b0  ldarg.2
0x79b1  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_DataQuery()
0x79b6  call     class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.QueryDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.QueryExtensions::ToSoapQueryDefinition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query query)
0x79bb  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition::set_Query(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.QueryDefinition)
0x79c0  stloc.2
0x79c1  ldloc.0
0x79c2  ldarg.2
0x79c3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_DataSource()
0x79c8  call     class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinitionOrReference(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x79cd  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::set_Item(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference)
0x79d2  ldloc.0
0x79d3  ldarg.0
0x79d4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x79d9  ldarg.1
0x79da  ldloc.1
0x79db  ldloc.2
0x79dc  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::PrepareQuery(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSource, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition)
0x79e1  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::set_DataSet(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition)
0x79e6  br       loc_7A83
0x79eb  ldarg.0
0x79ec  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x79f1  ldarg.1
0x79f2  ldarg.2
0x79f3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Id()
0x79f8  stloc.s  5
0x79fa  ldloca.s 5
0x79fc  constrained. [mscorlib]System.Guid
0x7a02  callvirt instance string [mscorlib]System.Object::ToString()
0x7a07  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetDataDrivenSubscriptionProperties(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x7a0c  stloc.3
0x7a0d  ldloc.0
0x7a0e  ldloc.3
0x7a0f  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0x7a14  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_Item()
0x7a19  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::set_Item(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference)
0x7a1e  ldloc.0
0x7a1f  ldloc.3
0x7a20  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0x7a25  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_DataSet()
0x7a2a  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::set_DataSet(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition)
0x7a2f  ldloc.0
0x7a30  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_Item()
0x7a35  isinst   [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition
0x7a3a  stloc.s  4
0x7a3c  ldloc.s  4
0x7a3e  brfalse.s loc_7A83
0x7a40  ldloc.s  4
0x7a42  callvirt instance valuetype [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CredentialRetrievalEnum [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::get_CredentialRetrieval()
0x7a47  ldc.i4.1
0x7a48  bne.un.s loc_7A83
0x7a4a  ldloc.s  4
0x7a4c  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::get_Password()
0x7a51  brtrue.s loc_7A83
0x7a53  ldarg.0
0x7a54  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_catalogRepository
0x7a59  ldarg.1
0x7a5a  ldarg.2
0x7a5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Id()
0x7a60  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSourcePasswordForSubscription(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x7a65  stloc.s  6
0x7a67  ldloc.s  6
0x7a69  brfalse.s loc_7A83
0x7a6b  ldloc.s  4
0x7a6d  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.CatalogEncryption::get_Instance()
0x7a72  ldloc.s  6
0x7a74  ldstr    aPassword// "Password"
0x7a79  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(unsigned int8[], string)
0x7a7e  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition::set_Password(string)
0x7a83  ldloc.0
0x7a84  ret
```
