# Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeMethod_0

- ea: `0x4bc0`
- end: `0x4c2a`
- name: `Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeMethod_0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4b90`
- `0x4bc0`

## pseudocode

```c

```

## disassembly

```asm
0x4bc0  ldarg.s  4
0x4bc2  brtrue.s loc_4BCF
0x4bc4  ldstr    aProxycontext// "proxyContext"
0x4bc9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4bce  throw
0x4bcf  ldarg.1
0x4bd0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService
0x4bd5  stloc.0
0x4bd6  ldloc.0
0x4bd7  brtrue.s loc_4BE4
0x4bd9  ldstr    aTarget// "target"
0x4bde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4be3  throw
0x4be4  ldarg.0
0x4be5  ldarg.2
0x4be6  ldarg.s  4
0x4be8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bed  starg.s  2
0x4bef  ldarg.2
0x4bf0  dup
0x4bf1  stloc.1
0x4bf2  brfalse.s loc_4C1C
0x4bf4  ldloc.1
0x4bf5  ldstr    aEmbeddata// "EmbedData"
0x4bfa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bff  brfalse.s loc_4C1C
0x4c01  ldarg.s  5
0x4c03  ldc.i4.0
0x4c04  stind.i1
0x4c05  ldarg.0
0x4c06  ldstr    aEmbeddata// "EmbedData"
0x4c0b  ldarg.s  4
0x4c0d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c12  ldloc.0
0x4c13  ldarg.3
0x4c14  ldarg.s  4
0x4c16  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1 Microsoft.SharePoint.Publishing.EmbedServiceServerStub::EmbedData_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4c1b  ret
0x4c1c  ldarg.0
0x4c1d  ldarg.1
0x4c1e  ldarg.2
0x4c1f  ldarg.3
0x4c20  ldarg.s  4
0x4c22  ldarg.s  5
0x4c24  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4c29  ret
```
