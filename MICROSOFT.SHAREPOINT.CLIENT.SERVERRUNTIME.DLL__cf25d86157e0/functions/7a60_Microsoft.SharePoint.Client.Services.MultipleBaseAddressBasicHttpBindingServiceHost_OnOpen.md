# Microsoft.SharePoint.Client.Services.MultipleBaseAddressBasicHttpBindingServiceHost::OnOpen

- ea: `0x7a60`
- end: `0x7a8f`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressBasicHttpBindingServiceHost::OnOpen`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7a60`
- `0xe000`
- `0xe620`

## string_xrefs

- `0x7a77`: `Error when open web service: `

## pseudocode

```c

```

## disassembly

```asm
0x7a60  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x7a65  stloc.0
0x7a66  ldarg.0
0x7a67  ldarg.1
0x7a68  call     instance void [System.ServiceModel]System.ServiceModel.ServiceHostBase::OnOpen(valuetype [mscorlib]System.TimeSpan)
0x7a6d  leave.s  loc_7A8E
0x7a6f  stloc.1
0x7a70  ldloc.0
0x7a71  ldc.i4   0x1C8522
0x7a76  ldc.i4.1
0x7a77  ldstr    aErrorWhenOpenW// "Error when open web service: "
0x7a7c  ldloc.1
0x7a7d  callvirt instance string [mscorlib]System.Object::ToString()
0x7a82  call     string [mscorlib]System.String::Concat(string, string)
0x7a87  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x7a8c  rethrow
0x7a8e  ret
```
