# Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeMethod

- ea: `0x4a80`
- end: `0x4aea`
- name: `Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeMethod`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4a50`
- `0x4a80`

## pseudocode

```c

```

## disassembly

```asm
0x4a80  ldarg.s  4
0x4a82  brtrue.s loc_4A8F
0x4a84  ldstr    aProxycontext// "proxyContext"
0x4a89  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a8e  throw
0x4a8f  ldarg.1
0x4a90  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService
0x4a95  stloc.0
0x4a96  ldloc.0
0x4a97  brtrue.s loc_4AA4
0x4a99  ldstr    aTarget// "target"
0x4a9e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4aa3  throw
0x4aa4  ldarg.0
0x4aa5  ldarg.2
0x4aa6  ldarg.s  4
0x4aa8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4aad  starg.s  2
0x4aaf  ldarg.2
0x4ab0  dup
0x4ab1  stloc.1
0x4ab2  brfalse.s loc_4ADC
0x4ab4  ldloc.1
0x4ab5  ldstr    aEmbeddata// "EmbedData"
0x4aba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4abf  brfalse.s loc_4ADC
0x4ac1  ldarg.s  5
0x4ac3  ldc.i4.0
0x4ac4  stind.i1
0x4ac5  ldarg.0
0x4ac6  ldstr    aEmbeddata// "EmbedData"
0x4acb  ldarg.s  4
0x4acd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ad2  ldloc.0
0x4ad3  ldarg.3
0x4ad4  ldarg.s  4
0x4ad6  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1 Microsoft.SharePoint.Publishing.EmbedServiceServerStub::EmbedData_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4adb  ret
0x4adc  ldarg.0
0x4add  ldarg.1
0x4ade  ldarg.2
0x4adf  ldarg.3
0x4ae0  ldarg.s  4
0x4ae2  ldarg.s  5
0x4ae4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4ae9  ret
```
