# Microsoft.ReportingServices.WebServer.RsSoapExtensionReflector::ReflectMethod

- ea: `0x34ab0`
- end: `0x34b94`
- name: `Microsoft.ReportingServices.WebServer.RsSoapExtensionReflector::ReflectMethod`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2cb90`
- `0x34ab0`

## string_xrefs

- `0x34b2c`: `%ReportServerServiceObjectURL%`
- `0x34abf`: `serviceLocation != null`

## pseudocode

```c

```

## disassembly

```asm
0x34ab0  call     string Microsoft.ReportingServices.WebServer.Global::GetWsdlServiceLocation()
0x34ab5  stloc.0
0x34ab6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x34abb  ldloc.0
0x34abc  ldnull
0x34abd  cgt.un
0x34abf  ldstr    aServicelocatio// "serviceLocation != null"
0x34ac4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x34ac9  ldarg.0
0x34aca  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0x34acf  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescription [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_ServiceDescription()
0x34ad4  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceCollection [System.Web.Services]System.Web.Services.Description.ServiceDescription::get_Services()
0x34ad9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x34ade  stloc.1
0x34adf  br       loc_34B72
0x34ae4  ldloc.1
0x34ae5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x34aea  castclass [System.Web.Services]System.Web.Services.Description.Service
0x34aef  callvirt instance class [System.Web.Services]System.Web.Services.Description.PortCollection [System.Web.Services]System.Web.Services.Description.Service::get_Ports()
0x34af4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x34af9  stloc.2
0x34afa  br.s     loc_34B54
0x34afc  ldloc.2
0x34afd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x34b02  castclass [System.Web.Services]System.Web.Services.Description.Port
0x34b07  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescriptionFormatExtensionCollection [System.Web.Services]System.Web.Services.Description.DocumentableItem::get_Extensions()
0x34b0c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x34b11  stloc.3
0x34b12  br.s     loc_34B36
0x34b14  ldloc.3
0x34b15  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x34b1a  castclass [System.Web.Services]System.Web.Services.Description.ServiceDescriptionFormatExtension
0x34b1f  isinst   [System.Web.Services]System.Web.Services.Description.SoapAddressBinding
0x34b24  stloc.s  4
0x34b26  ldloc.s  4
0x34b28  brfalse.s loc_34B36
0x34b2a  ldloc.s  4
0x34b2c  ldstr    aReportserverse// "%ReportServerServiceObjectURL%"
0x34b31  callvirt instance void [System.Web.Services]System.Web.Services.Description.SoapAddressBinding::set_Location(string)
0x34b36  ldloc.3
0x34b37  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34b3c  brtrue.s loc_34B14
0x34b3e  leave.s  loc_34B54
0x34b40  ldloc.3
0x34b41  isinst   [mscorlib]System.IDisposable
0x34b46  stloc.s  5
0x34b48  ldloc.s  5
0x34b4a  brfalse.s loc_34B53
0x34b4c  ldloc.s  5
0x34b4e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34b53  endfinally
0x34b54  ldloc.2
0x34b55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34b5a  brtrue.s loc_34AFC
0x34b5c  leave.s  loc_34B72
0x34b5e  ldloc.2
0x34b5f  isinst   [mscorlib]System.IDisposable
0x34b64  stloc.s  5
0x34b66  ldloc.s  5
0x34b68  brfalse.s loc_34B71
0x34b6a  ldloc.s  5
0x34b6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34b71  endfinally
0x34b72  ldloc.1
0x34b73  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34b78  brtrue   loc_34AE4
0x34b7d  leave.s  loc_34B93
0x34b7f  ldloc.1
0x34b80  isinst   [mscorlib]System.IDisposable
0x34b85  stloc.s  5
0x34b87  ldloc.s  5
0x34b89  brfalse.s loc_34B92
0x34b8b  ldloc.s  5
0x34b8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34b92  endfinally
0x34b93  ret
```
