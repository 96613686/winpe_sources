# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeStaticMethod_0

- ea: `0x114e0`
- end: `0x11555`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeStaticMethod_0`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x114b0`
- `0x114d0`
- `0x114e0`

## pseudocode

```c

```

## disassembly

```asm
0x114e0  ldarg.3
0x114e1  brtrue.s loc_114EE
0x114e3  ldstr    aProxycontext// "proxyContext"
0x114e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x114ed  throw
0x114ee  ldarg.0
0x114ef  ldarg.1
0x114f0  ldarg.3
0x114f1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x114f6  starg.s  1
0x114f8  ldarg.1
0x114f9  dup
0x114fa  stloc.0
0x114fb  brfalse.s loc_1154E
0x114fd  ldloc.0
0x114fe  ldstr    aGettimezone// "GetTimeZone"
0x11503  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11508  brtrue.s loc_11519
0x1150a  ldloc.0
0x1150b  ldstr    aIsfilepickerex// "IsFilePickerExternalImageSearchEnabled"
0x11510  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11515  brtrue.s loc_11531
0x11517  br.s     loc_1154E
0x11519  ldarg.s  4
0x1151b  ldc.i4.0
0x1151c  stind.i1
0x1151d  ldarg.0
0x1151e  ldstr    aGettimezone// "GetTimeZone"
0x11523  ldarg.3
0x11524  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11529  ldarg.2
0x1152a  ldarg.3
0x1152b  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime Microsoft.SharePoint.Publishing.SitePageServiceServerStub::GetTimeZone_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11530  ret
0x11531  ldarg.s  4
0x11533  ldc.i4.0
0x11534  stind.i1
0x11535  ldarg.0
0x11536  ldstr    aIsfilepickerex// "IsFilePickerExternalImageSearchEnabled"
0x1153b  ldarg.3
0x1153c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11541  ldarg.2
0x11542  ldarg.3
0x11543  call     bool Microsoft.SharePoint.Publishing.SitePageServiceServerStub::IsFilePickerExternalImageSearchEnabled_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11548  box      [mscorlib]System.Boolean
0x1154d  ret
0x1154e  ldarg.1
0x1154f  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x11554  throw
```
