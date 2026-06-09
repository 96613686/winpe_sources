# Microsoft.ReportingServices.Portal.Services.DataService::GetCachedDataSetJson

- ea: `0x95b0`
- end: `0x970e`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::GetCachedDataSetJson`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x92e0`
- `0x93c0`

## callees

- `0x95b0`
- `0x9710`
- `0x203d0`

## string_xrefs

- `0x9666`: `Unexpected version {0} when fetching Json cache for shared dataSet. Expected version {1}`
- `0x96be`: `SHAREDDATASETJSON`

## pseudocode

```c

```

## disassembly

```asm
0x95b0  ldc.i4.0
0x95b1  newarr   [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter
0x95b6  stloc.0
0x95b7  ldarg.s  4
0x95b9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameterInfo> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetSchema::get_Parameters()
0x95be  call     T0x2B00008B
0x95c3  brfalse.s loc_9612
0x95c5  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x95ca  stloc.1
0x95cb  ldloc.1
0x95cc  ldarg.0
0x95cd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Services.DataService::_rs2010Proxy
0x95d2  ldarg.s  5
0x95d4  ldarg.s  6
0x95d6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetParameterTypes(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x95db  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> <>c__DisplayClass22_0::parameterTypes
0x95e0  call     T0x2B000040
0x95e5  stloc.2
0x95e6  ldarg.3
0x95e7  ldloc.1
0x95e8  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue <>c__DisplayClass22_0::<GetCachedDataSetJson>b__0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter parameterValue)
0x95ee  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue>::.ctor(object, native int)
0x95f3  call     T0x2B00008C
0x95f8  stloc.2
0x95f9  ldarg.0
0x95fa  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Services.DataService::_rs2010Proxy
0x95ff  ldarg.s  5
0x9601  ldarg.s  6
0x9603  ldnull
0x9604  ldc.i4.1
0x9605  ldloc.2
0x9606  call     T0x2B000043
0x960b  ldnull
0x960c  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetItemParameters(class [mscorlib]System.Security.Principal.IPrincipal, string, string, bool, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[], class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceCredentials[])
0x9611  stloc.0
0x9612  ldarg.1
0x9613  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x9618  stloc.3
0x9619  ldloc.0
0x961a  ldarg.3
0x961b  call     class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Portal.Services.DataService::GetParameterInfoCollection(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[] parameters, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameterOverrides)
0x9620  stloc.s  4
0x9622  ldloc.s  4
0x9624  ldc.i4.1
0x9625  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToXml(bool)
0x962a  call     T0x2B00008D
0x962f  stloc.s  5
0x9631  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9636  stloc.s  6
0x9638  ldarg.1
0x9639  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x963e  ldarg.2
0x963f  ldloc.s  5
0x9641  ldc.i4.0
0x9642  ldloca.s 7
0x9644  ldloca.s 8
0x9646  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::TryGetContentCache(valuetype [mscorlib]System.Guid, int32, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DBInterface/ContentCacheTypes, unsigned int8[]&, int32&)
0x964b  stloc.s  9
0x964d  ldloc.s  9
0x964f  brfalse.s loc_968A
0x9651  ldloc.s  7
0x9653  brfalse.s loc_968A
0x9655  ldloc.s  8
0x9657  ldc.i4.1
0x9658  beq.s    loc_968A
0x965a  ldarg.0
0x965b  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.DataService::_logger
0x9660  ldc.i4.2
0x9661  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9666  ldstr    aUnexpectedVers// "Unexpected version {0} when fetching Js"...
0x966b  ldloc.s  8
0x966d  box      [mscorlib]System.Int32
0x9672  ldc.i4.1
0x9673  box      [mscorlib]System.Int32
0x9678  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x967d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9682  ldnull
0x9683  stloc.s  0xA
0x9685  leave    loc_970B
0x968a  ldloc.s  9
0x968c  brfalse.s loc_96FB
0x968e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::.ctor()
0x9693  dup
0x9694  ldc.i4.2
0x9695  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_Source(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogExecType)
0x969a  dup
0x969b  ldarg.s  6
0x969d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_ItemPath(string)
0x96a2  dup
0x96a3  ldloc.s  6
0x96a5  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_StartTime(valuetype [mscorlib]System.DateTime)
0x96aa  dup
0x96ab  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x96b0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_EndTime(valuetype [mscorlib]System.DateTime)
0x96b5  dup
0x96b6  ldc.i4.0
0x96b7  conv.i8
0x96b8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_Status(int64)
0x96bd  dup
0x96be  ldstr    aShareddatasetj// "SHAREDDATASETJSON"
0x96c3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_Format(string)
0x96c8  dup
0x96c9  ldloc.s  4
0x96cb  ldc.i4.0
0x96cc  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToUrl(bool)
0x96d1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_Parameters(string)
0x96d6  dup
0x96d7  ldc.i4.s 9
0x96d9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_EventType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogEventType)
0x96de  dup
0x96df  ldloc.s  7
0x96e1  ldlen
0x96e2  conv.i4
0x96e3  conv.i8
0x96e4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::set_ByteCount(int64)
0x96e9  stloc.s  0xB
0x96eb  ldarg.0
0x96ec  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Services.DataService::_rsCatalogRepository
0x96f1  ldarg.s  5
0x96f3  ldloc.s  0xB
0x96f5  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::AddExecutionLogInfo(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo)
0x96fa  pop
0x96fb  ldloc.s  7
0x96fd  stloc.s  0xA
0x96ff  leave.s  loc_970B
0x9701  ldloc.3
0x9702  brfalse.s loc_970A
0x9704  ldloc.3
0x9705  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x970a  endfinally
0x970b  ldloc.s  0xA
0x970d  ret
```
