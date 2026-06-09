# Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsForUsage

- ea: `0x3850`
- end: `0x3924`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsForUsage`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3930`
- `0x39e0`

## callees

- `0x3b60`
- `0x7480`

## string_xrefs

- `0x3864`: `ReportServerWebService`
- `0x389e`: `ManagementService`
- `0x38ba`: `ManagementService`
- `0x38d7`: `PowerBIService`
- `0x38f4`: `OfficeService`

## pseudocode

```c

```

## disassembly

```asm
0x3850  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x3855  stloc.0
0x3856  ldloc.0
0x3857  ldarg.1
0x3858  stfld    valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage <>c__DisplayClass5_0::targetUsage
0x385d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::.ctor()
0x3862  dup
0x3863  ldarg.0
0x3864  ldstr    aReportserverwe// "ReportServerWebService"
0x3869  ldstr    aReportserver// "ReportServer"
0x386e  ldstr    aHttp80// "http://+:80"
0x3873  ldc.i4.s 0x4E
0x3875  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x387a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x387f  dup
0x3880  ldarg.0
0x3881  ldstr    aReportserverwe_0// "ReportServerWebApp"
0x3886  ldstr    aReports// "Reports"
0x388b  ldstr    aHttp80// "http://+:80"
0x3890  ldc.i4.s 0x4E
0x3892  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x3897  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x389c  dup
0x389d  ldarg.0
0x389e  ldstr    aManagementserv// "ManagementService"
0x38a3  ldstr    asc_9DE4// ""
0x38a8  ldstr    aHttp8082// "http://+:8082"
0x38ad  ldc.i4.7
0x38ae  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x38b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x38b8  dup
0x38b9  ldarg.0
0x38ba  ldstr    aManagementserv// "ManagementService"
0x38bf  ldstr    asc_9DE4// ""
0x38c4  ldstr    aHttp8083// "http://+:8083"
0x38c9  ldc.i4.s 0xB
0x38cb  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x38d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x38d5  dup
0x38d6  ldarg.0
0x38d7  ldstr    aPowerbiservice// "PowerBIService"
0x38dc  ldstr    aPowerbi// "powerbi"
0x38e1  ldstr    aHttp80// "http://+:80"
0x38e6  ldc.i4.s 0x1A
0x38e8  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x38ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x38f2  dup
0x38f3  ldarg.0
0x38f4  ldstr    aOfficeservice// "OfficeService"
0x38f9  ldstr    aWopi// "wopi"
0x38fe  ldstr    aHttp80// "http://+:80"
0x3903  ldc.i4   0x9A
0x3908  newobj   instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, string name, string virtualDirectory, string urlString, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage urlEndpointUsage)
0x390d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::Add(var<u1>)
0x3912  ldloc.0
0x3913  ldftn    instance bool <>c__DisplayClass5_0::<GetEndpointsForUsage>b__0(class Microsoft.BIServer.Configuration.UrlEndpointDefinition endpoint)
0x3919  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.UrlEndpointDefinition, bool>::.ctor(object, native int)
0x391e  call     T0x2B00002D
0x3923  ret
```
