# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeStaticMethod

- ea: `0x11050`
- end: `0x110c5`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeStaticMethod`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x11020`
- `0x11040`
- `0x11050`

## pseudocode

```c

```

## disassembly

```asm
0x11050  ldarg.3
0x11051  brtrue.s loc_1105E
0x11053  ldstr    aProxycontext// "proxyContext"
0x11058  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1105d  throw
0x1105e  ldarg.0
0x1105f  ldarg.1
0x11060  ldarg.3
0x11061  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11066  starg.s  1
0x11068  ldarg.1
0x11069  dup
0x1106a  stloc.0
0x1106b  brfalse.s loc_110BE
0x1106d  ldloc.0
0x1106e  ldstr    aGettimezone// "GetTimeZone"
0x11073  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11078  brtrue.s loc_11089
0x1107a  ldloc.0
0x1107b  ldstr    aIsfilepickerex// "IsFilePickerExternalImageSearchEnabled"
0x11080  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11085  brtrue.s loc_110A1
0x11087  br.s     loc_110BE
0x11089  ldarg.s  4
0x1108b  ldc.i4.0
0x1108c  stind.i1
0x1108d  ldarg.0
0x1108e  ldstr    aGettimezone// "GetTimeZone"
0x11093  ldarg.3
0x11094  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11099  ldarg.2
0x1109a  ldarg.3
0x1109b  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime Microsoft.SharePoint.Publishing.SitePageServiceServerStub::GetTimeZone_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x110a0  ret
0x110a1  ldarg.s  4
0x110a3  ldc.i4.0
0x110a4  stind.i1
0x110a5  ldarg.0
0x110a6  ldstr    aIsfilepickerex// "IsFilePickerExternalImageSearchEnabled"
0x110ab  ldarg.3
0x110ac  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x110b1  ldarg.2
0x110b2  ldarg.3
0x110b3  call     bool Microsoft.SharePoint.Publishing.SitePageServiceServerStub::IsFilePickerExternalImageSearchEnabled_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x110b8  box      [mscorlib]System.Boolean
0x110bd  ret
0x110be  ldarg.1
0x110bf  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x110c4  throw
```
