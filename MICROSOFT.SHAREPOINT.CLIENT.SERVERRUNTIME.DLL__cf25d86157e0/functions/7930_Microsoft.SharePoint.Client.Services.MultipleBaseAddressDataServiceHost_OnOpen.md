# Microsoft.SharePoint.Client.Services.MultipleBaseAddressDataServiceHost::OnOpen

- ea: `0x7930`
- end: `0x795f`
- name: `Microsoft.SharePoint.Client.Services.MultipleBaseAddressDataServiceHost::OnOpen`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7930`
- `0xe000`
- `0xe620`

## string_xrefs

- `0x7947`: `Error when open web service: `

## pseudocode

```c

```

## disassembly

```asm
0x7930  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x7935  stloc.0
0x7936  ldarg.0
0x7937  ldarg.1
0x7938  call     instance void [System.ServiceModel]System.ServiceModel.ServiceHostBase::OnOpen(valuetype [mscorlib]System.TimeSpan)
0x793d  leave.s  loc_795E
0x793f  stloc.1
0x7940  ldloc.0
0x7941  ldc.i4   0x1C8521
0x7946  ldc.i4.1
0x7947  ldstr    aErrorWhenOpenW// "Error when open web service: "
0x794c  ldloc.1
0x794d  callvirt instance string [mscorlib]System.Object::ToString()
0x7952  call     string [mscorlib]System.String::Concat(string, string)
0x7957  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x795c  rethrow
0x795e  ret
```
