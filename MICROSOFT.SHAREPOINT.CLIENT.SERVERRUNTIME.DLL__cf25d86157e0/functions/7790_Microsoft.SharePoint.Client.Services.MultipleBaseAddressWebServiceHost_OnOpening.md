# Microsoft.SharePoint.Client.Services.MultipleBaseAddressWebServiceHost::OnOpening

- ea: `0x7790`
- end: `0x77f6`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressWebServiceHost::OnOpening`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7790`
- `0x7830`
- `0xe000`
- `0xe1c0`
- `0xe620`

## string_xrefs

- `0x77a4`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is true, do not manually create endpoints.`
- `0x77b7`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is false, creating endpoints according to hosting environment settings.`
- `0x77de`: `Error when opening web service: `

## pseudocode

```c

```

## disassembly

```asm
0x7790  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x7795  stloc.0
0x7796  call     bool [System.ServiceModel.Activation]System.ServiceModel.ServiceHostingEnvironment::get_MultipleSiteBindingsEnabled()
0x779b  brfalse.s loc_77B0
0x779d  ldloc.0
0x779e  ldc.i4   0x3CB3DD
0x77a3  ldc.i4.2
0x77a4  ldstr    aServicehosting// "ServiceHostingEnvironment.MultipleSiteB"...
0x77a9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x77ae  br.s     loc_77C7
0x77b0  ldloc.0
0x77b1  ldc.i4   0x3CB3DE
0x77b6  ldc.i4.2
0x77b7  ldstr    aServicehosting_0// "ServiceHostingEnvironment.MultipleSiteB"...
0x77bc  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x77c1  ldarg.0
0x77c2  call     instance void Microsoft.SharePoint.Client.Services.MultipleBaseAddressWebServiceHost::CreateEndpoints()
0x77c7  ldarg.0
0x77c8  call     instance void [System.ServiceModel.Web]System.ServiceModel.Web.WebServiceHost::OnOpening()
0x77cd  ldloc.0
0x77ce  ldarg.0
0x77cf  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnServiceHostOpeningInternal(class [System.ServiceModel]System.ServiceModel.ServiceHost serviceHost)
0x77d4  leave.s  loc_77F5
0x77d6  stloc.1
0x77d7  ldloc.0
0x77d8  ldc.i4   0x15755D
0x77dd  ldc.i4.1
0x77de  ldstr    aErrorWhenOpeni// "Error when opening web service: "
0x77e3  ldloc.1
0x77e4  callvirt instance string [mscorlib]System.Object::ToString()
0x77e9  call     string [mscorlib]System.String::Concat(string, string)
0x77ee  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x77f3  rethrow
0x77f5  ret
```
