# Microsoft.SharePoint.Client.Services.MultipleBaseAddressBasicHttpBindingServiceHost::OnOpening

- ea: `0x79f0`
- end: `0x7a56`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressBasicHttpBindingServiceHost::OnOpening`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x79f0`
- `0x7a90`
- `0xe000`
- `0xe1c0`
- `0xe620`

## string_xrefs

- `0x7a04`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is true, do not manually create endpoints.`
- `0x7a17`: `ServiceHostingEnvironment.MultipleSiteBindingsEnabled is false, creating endpoints according to hosting environment settings.`
- `0x7a3e`: `Error when opening basicHttp service: `

## pseudocode

```c

```

## disassembly

```asm
0x79f0  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x79f5  stloc.0
0x79f6  call     bool [System.ServiceModel.Activation]System.ServiceModel.ServiceHostingEnvironment::get_MultipleSiteBindingsEnabled()
0x79fb  brfalse.s loc_7A10
0x79fd  ldloc.0
0x79fe  ldc.i4   0x3CB3E1
0x7a03  ldc.i4.2
0x7a04  ldstr    aServicehosting// "ServiceHostingEnvironment.MultipleSiteB"...
0x7a09  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x7a0e  br.s     loc_7A27
0x7a10  ldloc.0
0x7a11  ldc.i4   0x3CB3E2
0x7a16  ldc.i4.2
0x7a17  ldstr    aServicehosting_0// "ServiceHostingEnvironment.MultipleSiteB"...
0x7a1c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x7a21  ldarg.0
0x7a22  call     instance void Microsoft.SharePoint.Client.Services.MultipleBaseAddressBasicHttpBindingServiceHost::CreateEndpoints()
0x7a27  ldarg.0
0x7a28  call     instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::OnOpening()
0x7a2d  ldloc.0
0x7a2e  ldarg.0
0x7a2f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::OnServiceHostOpeningInternal(class [System.ServiceModel]System.ServiceModel.ServiceHost serviceHost)
0x7a34  leave.s  loc_7A55
0x7a36  stloc.1
0x7a37  ldloc.0
0x7a38  ldc.i4   0x15755F
0x7a3d  ldc.i4.1
0x7a3e  ldstr    aErrorWhenOpeni_1// "Error when opening basicHttp service: "
0x7a43  ldloc.1
0x7a44  callvirt instance string [mscorlib]System.Object::ToString()
0x7a49  call     string [mscorlib]System.String::Concat(string, string)
0x7a4e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x7a53  rethrow
0x7a55  ret
```
