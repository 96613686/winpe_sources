# Microsoft.SharePoint.Client.Services.MultipleBaseAddressDataServiceHost::OnOpening

- ea: `0x78c0`
- end: `0x7926`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressDataServiceHost::OnOpening`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x78c0`
- `0x7960`
- `0xe000`
- `0xe1c0`
- `0xe620`

## string_xrefs

- `0x78d4`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is true, do not manually create endpoints.`
- `0x78e7`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is false, creating endpoints according to hosting environment settings.`
- `0x790e`: `Error when opening data service: `

## pseudocode

```c

```

## disassembly

```asm
0x78c0  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x78c5  stloc.0
0x78c6  call     bool [System.ServiceModel.Activation]System.ServiceModel.ServiceHostingEnvironment::get_MultipleSiteBindingsEnabled()
0x78cb  brfalse.s loc_78E0
0x78cd  ldloc.0
0x78ce  ldc.i4   0x3CB3DF
0x78d3  ldc.i4.2
0x78d4  ldstr    aServicehosting// "ServiceHostingEnvironment.MultipleSiteB"...
0x78d9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x78de  br.s     loc_78F7
0x78e0  ldloc.0
0x78e1  ldc.i4   0x3CB3E0
0x78e6  ldc.i4.2
0x78e7  ldstr    aServicehosting_0// "ServiceHostingEnvironment.MultipleSiteB"...
0x78ec  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x78f1  ldarg.0
0x78f2  call     instance void Microsoft.SharePoint.Client.Services.MultipleBaseAddressDataServiceHost::CreateEndpoints()
0x78f7  ldarg.0
0x78f8  call     instance void [System.ServiceModel.Web]System.ServiceModel.Web.WebServiceHost::OnOpening()
0x78fd  ldloc.0
0x78fe  ldarg.0
0x78ff  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnServiceHostOpeningInternal(class [System.ServiceModel]System.ServiceModel.ServiceHost serviceHost)
0x7904  leave.s  loc_7925
0x7906  stloc.1
0x7907  ldloc.0
0x7908  ldc.i4   0x15755E
0x790d  ldc.i4.1
0x790e  ldstr    aErrorWhenOpeni_0// "Error when opening data service: "
0x7913  ldloc.1
0x7914  callvirt instance string [mscorlib]System.Object::ToString()
0x7919  call     string [mscorlib]System.String::Concat(string, string)
0x791e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x7923  rethrow
0x7925  ret
```
