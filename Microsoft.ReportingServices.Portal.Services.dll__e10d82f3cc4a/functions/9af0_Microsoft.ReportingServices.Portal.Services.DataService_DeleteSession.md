# Microsoft.ReportingServices.Portal.Services.DataService::DeleteSession

- ea: `0x9af0`
- end: `0x9b4c`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::DeleteSession`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20520`

## callees

- `0x9af0`

## string_xrefs

- `0x9b14`: `Successfully deleted item {0} async`

## pseudocode

```c

```

## disassembly

```asm
0x9af0  ldarg.0
0x9af1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Services.DataService::_rs2010Proxy
0x9af6  brfalse.s loc_9B24
0x9af8  ldarg.1
0x9af9  brfalse.s loc_9B24
0x9afb  ldarg.0
0x9afc  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Services.DataService::_rs2010Proxy
0x9b01  ldarg.1
0x9b02  ldarg.2
0x9b03  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::DeleteItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x9b08  ldarg.0
0x9b09  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.DataService::_logger
0x9b0e  ldc.i4.4
0x9b0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b14  ldstr    aSuccessfullyDe// "Successfully deleted item {0} async"
0x9b19  ldarg.2
0x9b1a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x9b1f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9b24  leave.s  loc_9B4B
0x9b26  stloc.0
0x9b27  ldarg.0
0x9b28  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.DataService::_logger
0x9b2d  ldc.i4.1
0x9b2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9b33  ldstr    aErrorWhenDelet// "Error when deleting item {0} async: {1}"
0x9b38  ldarg.2
0x9b39  ldloc.0
0x9b3a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9b3f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x9b44  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9b49  leave.s  loc_9B4B
0x9b4b  ret
```
