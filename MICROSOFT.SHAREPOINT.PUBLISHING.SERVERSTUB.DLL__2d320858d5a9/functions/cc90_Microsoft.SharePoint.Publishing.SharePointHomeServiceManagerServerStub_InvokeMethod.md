# Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeMethod

- ea: `0xcc90`
- end: `0xccfa`
- name: `Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeMethod`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xcc70`
- `0xcc90`

## pseudocode

```c

```

## disassembly

```asm
0xcc90  ldarg.s  4
0xcc92  brtrue.s loc_CC9F
0xcc94  ldstr    aProxycontext// "proxyContext"
0xcc99  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcc9e  throw
0xcc9f  ldarg.1
0xcca0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager
0xcca5  stloc.0
0xcca6  ldloc.0
0xcca7  brtrue.s loc_CCB4
0xcca9  ldstr    aTarget// "target"
0xccae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xccb3  throw
0xccb4  ldarg.0
0xccb5  ldarg.2
0xccb6  ldarg.s  4
0xccb8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xccbd  starg.s  2
0xccbf  ldarg.2
0xccc0  dup
0xccc1  stloc.1
0xccc2  brfalse.s loc_CCEC
0xccc4  ldloc.1
0xccc5  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0xccca  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcccf  brfalse.s loc_CCEC
0xccd1  ldarg.s  5
0xccd3  ldc.i4.0
0xccd4  stind.i1
0xccd5  ldarg.0
0xccd6  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0xccdb  ldarg.s  4
0xccdd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xcce2  ldloc.0
0xcce3  ldarg.3
0xcce4  ldarg.s  4
0xcce6  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation[] Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::GetAcronymsAndColors_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xcceb  ret
0xccec  ldarg.0
0xcced  ldarg.1
0xccee  ldarg.2
0xccef  ldarg.3
0xccf0  ldarg.s  4
0xccf2  ldarg.s  5
0xccf4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xccf9  ret
```
