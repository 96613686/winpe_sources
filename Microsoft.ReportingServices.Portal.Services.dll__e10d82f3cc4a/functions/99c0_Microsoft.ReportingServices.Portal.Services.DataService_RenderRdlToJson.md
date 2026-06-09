# Microsoft.ReportingServices.Portal.Services.DataService::RenderRdlToJson

- ea: `0x99c0`
- end: `0x9ae3`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::RenderRdlToJson`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9b50`

## callees

- `0x99c0`
- `0xa890`
- `0x20510`

## string_xrefs

- `0x9a77`: `SHAREDDATASETJSON`

## pseudocode

```c

```

## disassembly

```asm
0x99c0  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x99c5  stloc.0
0x99c6  ldloc.0
0x99c7  ldarg.0
0x99c8  stfld    class Microsoft.ReportingServices.Portal.Services.DataService <>c__DisplayClass27_0::<>4__this
0x99cd  ldloc.0
0x99ce  ldarg.1
0x99cf  stfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass27_0::userPrincipal
0x99d4  ldarg.0
0x99d5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxyFactory Microsoft.ReportingServices.Portal.Services.DataService::_rsProxyFactory
0x99da  ldloc.0
0x99db  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass27_0::userPrincipal
0x99e0  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxy [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxyFactory::CreateSoapRSExecutionProxy(class [mscorlib]System.Security.Principal.IPrincipal)
0x99e5  stloc.1
0x99e6  ldloc.1
0x99e7  ldc.i4   0x36EE80
0x99ec  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxy::set_Timeout(int32)
0x99f1  ldloc.0
0x99f2  ldnull
0x99f3  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult <>c__DisplayClass27_0::editSession
0x99f8  ldnull
0x99f9  stloc.2
0x99fa  ldarg.s  4
0x99fc  ldc.i4.1
0x99fd  newarr   [mscorlib]System.Char
0x9a02  dup
0x9a03  ldc.i4.0
0x9a04  ldc.i4.s 0x2F
0x9a06  stelem.i2
0x9a07  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x9a0c  stloc.3
0x9a0d  ldloc.3
0x9a0e  call     T0x2B000094
0x9a13  stloc.s  4
0x9a15  ldstr    asc_25576// "/"
0x9a1a  ldloc.3
0x9a1b  ldloc.3
0x9a1c  ldlen
0x9a1d  conv.i4
0x9a1e  ldc.i4.1
0x9a1f  sub
0x9a20  call     T0x2B000095
0x9a25  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x9a2a  stloc.s  5
0x9a2c  ldloc.s  5
0x9a2e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9a33  brfalse.s loc_9A3C
0x9a35  ldstr    asc_25576// "/"
0x9a3a  stloc.s  5
0x9a3c  ldloc.0
0x9a3d  ldarg.0
0x9a3e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Services.DataService::_rs2010Proxy
0x9a43  ldloc.0
0x9a44  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass27_0::userPrincipal
0x9a49  ldloc.s  4
0x9a4b  ldloc.s  5
0x9a4d  ldarg.2
0x9a4e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::CreateReportEditSession(class [mscorlib]System.Security.Principal.IPrincipal, string, string, unsigned int8[])
0x9a53  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult <>c__DisplayClass27_0::editSession
0x9a58  ldloc.1
0x9a59  ldloc.0
0x9a5a  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass27_0::userPrincipal
0x9a5f  ldloc.0
0x9a60  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult <>c__DisplayClass27_0::editSession
0x9a65  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult::get_Report()
0x9a6a  ldnull
0x9a6b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxy::LoadReport(class [mscorlib]System.Security.Principal.IPrincipal, string, string)
0x9a70  ldloc.1
0x9a71  ldloc.0
0x9a72  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass27_0::userPrincipal
0x9a77  ldstr    aShareddatasetj// "SHAREDDATASETJSON"
0x9a7c  ldarg.3
0x9a7d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.RenderResults [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxy::Render(class [mscorlib]System.Security.Principal.IPrincipal, string, string)
0x9a82  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.RenderResults::get_ByteContents()
0x9a87  stloc.2
0x9a88  leave.s  loc_9ADC
0x9a8a  stloc.s  6
0x9a8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a91  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_DataSetSoapError()
0x9a96  ldloc.s  6
0x9a98  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9a9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x9aa2  stloc.s  7
0x9aa4  ldarg.0
0x9aa5  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.DataService::_logger
0x9aaa  ldc.i4.1
0x9aab  ldloc.s  7
0x9aad  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9ab2  ldloc.s  7
0x9ab4  ldloc.s  6
0x9ab6  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.DataSetRenderingSoapException::.ctor(string, class [mscorlib]System.Exception)
0x9abb  throw
0x9abc  ldloc.0
0x9abd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.CreateReportEditSessionResult <>c__DisplayClass27_0::editSession
0x9ac2  brfalse.s loc_9ADB
0x9ac4  ldarg.0
0x9ac5  ldfld    class [mscorlib]System.Action`1<class [mscorlib]System.Action> Microsoft.ReportingServices.Portal.Services.DataService::ScheduleAsyncAction
0x9aca  ldloc.0
0x9acb  ldftn    instance void <>c__DisplayClass27_0::<RenderRdlToJson>b__0()
0x9ad1  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x9ad6  callvirt instance void class [mscorlib]System.Action`1<class [mscorlib]System.Action>::Invoke(var<u1>)
0x9adb  endfinally
0x9adc  ldloc.2
0x9add  call     string [ReportingServicesLibrary]Microsoft.ReportingServices.Common.ConversionUtils::Utf8BytesToString(unsigned int8[])
0x9ae2  ret
```
