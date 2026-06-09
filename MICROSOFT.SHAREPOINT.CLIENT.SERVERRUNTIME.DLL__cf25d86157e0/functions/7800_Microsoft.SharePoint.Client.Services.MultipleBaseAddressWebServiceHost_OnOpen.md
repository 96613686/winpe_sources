# Microsoft.SharePoint.Client.Services.MultipleBaseAddressWebServiceHost::OnOpen

- ea: `0x7800`
- end: `0x782f`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressWebServiceHost::OnOpen`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7800`
- `0xe000`
- `0xe620`

## string_xrefs

- `0x7817`: `Error when open web service: `

## pseudocode

```c

```

## disassembly

```asm
0x7800  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x7805  stloc.0
0x7806  ldarg.0
0x7807  ldarg.1
0x7808  call     instance void [System.ServiceModel]System.ServiceModel.ServiceHostBase::OnOpen(valuetype [mscorlib]System.TimeSpan)
0x780d  leave.s  loc_782E
0x780f  stloc.1
0x7810  ldloc.0
0x7811  ldc.i4   0x1C8520
0x7816  ldc.i4.1
0x7817  ldstr    aErrorWhenOpenW// "Error when open web service: "
0x781c  ldloc.1
0x781d  callvirt instance string [mscorlib]System.Object::ToString()
0x7822  call     string [mscorlib]System.String::Concat(string, string)
0x7827  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x782c  rethrow
0x782e  ret
```
