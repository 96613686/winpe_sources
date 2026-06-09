# Microsoft.ReportingServices.WebServer.RsSoapExtension::Initialize

- ea: `0x34e00`
- end: `0x34ef3`
- name: `Microsoft.ReportingServices.WebServer.RsSoapExtension::Initialize`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x34e00`

## string_xrefs

- `0x34e3a`: `http://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices`
- `0x34e80`: `http://schemas.microsoft.com/sqlserver/2006/03/15/reporting/reportingservices`
- `0x34ec6`: `http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer`

## pseudocode

```c

```

## disassembly

```asm
0x34e00  ldarg.1
0x34e01  isinst   [mscorlib]System.Type
0x34e06  stloc.0
0x34e07  ldloc.0
0x34e08  ldtoken  Microsoft.ReportingServices.WebServer.ReportingService2005
0x34e0d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e12  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34e17  brtrue.s loc_34E2B
0x34e19  ldloc.0
0x34e1a  ldtoken  Microsoft.ReportingServices.WebServer.ReportExecutionService
0x34e1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e24  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34e29  brfalse.s loc_34E5F
0x34e2b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34e30  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34e35  ldstr    aRsnamespacekey// "RSNamespaceKey"
0x34e3a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x34e3f  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34e44  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34e49  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34e4e  ldstr    aRsendpointkey// "RSEndpointKey"
0x34e53  ldc.i4.1
0x34e54  box      [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.SoapEndpoint
0x34e59  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34e5e  ret
0x34e5f  ldloc.0
0x34e60  ldtoken  Microsoft.ReportingServices.WebServer.ReportingService2006
0x34e65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34e6a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34e6f  brfalse.s loc_34EA5
0x34e71  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34e76  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34e7b  ldstr    aRsnamespacekey// "RSNamespaceKey"
0x34e80  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0x34e85  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34e8a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34e8f  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34e94  ldstr    aRsendpointkey// "RSEndpointKey"
0x34e99  ldc.i4.2
0x34e9a  box      [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.SoapEndpoint
0x34e9f  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34ea4  ret
0x34ea5  ldloc.0
0x34ea6  ldtoken  Microsoft.ReportingServices.WebServer.ReportingService2010
0x34eab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34eb0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x34eb5  brfalse.s loc_34EEB
0x34eb7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34ebc  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34ec1  ldstr    aRsnamespacekey// "RSNamespaceKey"
0x34ec6  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/sqlserver/"...
0x34ecb  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34ed0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34ed5  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x34eda  ldstr    aRsendpointkey// "RSEndpointKey"
0x34edf  ldc.i4.3
0x34ee0  box      [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.SoapEndpoint
0x34ee5  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x34eea  ret
0x34eeb  ldarg.0
0x34eec  ldc.i4.0
0x34eed  stfld    bool Microsoft.ReportingServices.WebServer.RsSoapExtension::m_isRsService
0x34ef2  ret
```
