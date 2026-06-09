# Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::InvokeMethod

- ea: `0x35750`
- end: `0x35926`
- name: `Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::InvokeMethod`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x35630`
- `0x35660`
- `0x35680`
- `0x356b0`
- `0x356d0`
- `0x356f0`
- `0x35710`
- `0x35730`
- `0x35750`

## string_xrefs

- `0x357a3`: `DeleteAppPrincipal`
- `0x3585c`: `DeleteAppPrincipal`
- `0x357bb`: `CreateAppPrincipal`
- `0x35894`: `CreateAppPrincipal`
- `0x357c7`: `GetAppPrincipalConfiguration`
- `0x358af`: `GetAppPrincipalConfiguration`
- `0x357d3`: `SetAppPrincipalConfiguration`
- `0x358ca`: `SetAppPrincipalConfiguration`
- `0x357eb`: `DeleteAppPrincipalCredential`
- `0x35901`: `DeleteAppPrincipalCredential`

## pseudocode

```c

```

## disassembly

```asm
0x35750  ldarg.s  4
0x35752  brtrue.s loc_3575F
0x35754  ldstr    aProxycontext// "proxyContext"
0x35759  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3575e  throw
0x3575f  ldarg.1
0x35760  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager
0x35765  stloc.0
0x35766  ldloc.0
0x35767  brtrue.s loc_35774
0x35769  ldstr    aTarget// "target"
0x3576e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35773  throw
0x35774  ldarg.0
0x35775  ldarg.2
0x35776  ldarg.s  4
0x35778  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3577d  starg.s  2
0x3577f  ldarg.2
0x35780  dup
0x35781  stloc.1
0x35782  brfalse  loc_35918
0x35787  volatile.
0x35789  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009e6-1
0x3578e  brtrue.s loc_357FD
0x35790  ldc.i4.8
0x35791  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x35796  dup
0x35797  ldstr    aLookupappprinc// "LookupAppPrincipal"
0x3579c  ldc.i4.0
0x3579d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357a2  dup
0x357a3  ldstr    aDeleteappprinc// "DeleteAppPrincipal"
0x357a8  ldc.i4.1
0x357a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357ae  dup
0x357af  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x357b4  ldc.i4.2
0x357b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357ba  dup
0x357bb  ldstr    aCreateappprinc// "CreateAppPrincipal"
0x357c0  ldc.i4.3
0x357c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357c6  dup
0x357c7  ldstr    aGetappprincipa// "GetAppPrincipalConfiguration"
0x357cc  ldc.i4.4
0x357cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357d2  dup
0x357d3  ldstr    aSetappprincipa// "SetAppPrincipalConfiguration"
0x357d8  ldc.i4.5
0x357d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357de  dup
0x357df  ldstr    aGetappprincipa_0// "GetAppPrincipalCredentials"
0x357e4  ldc.i4.6
0x357e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357ea  dup
0x357eb  ldstr    aDeleteappprinc_0// "DeleteAppPrincipalCredential"
0x357f0  ldc.i4.7
0x357f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x357f6  volatile.
0x357f8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009e6-1
0x357fd  volatile.
0x357ff  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009e6-1
0x35804  ldloc.1
0x35805  ldloca.s 2
0x35807  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3580c  brfalse  loc_35918
0x35811  ldloc.2
0x35812  switch   loc_3583C, loc_35857, loc_35873, loc_3588F, loc_358AA, loc_358C5, loc_358E1, loc_358FC
0x35837  br       loc_35918
0x3583c  ldarg.s  5
0x3583e  ldc.i4.0
0x3583f  stind.i1
0x35840  ldarg.0
0x35841  ldstr    aLookupappprinc// "LookupAppPrincipal"
0x35846  ldarg.s  4
0x35848  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3584d  ldloc.0
0x3584e  ldarg.3
0x3584f  ldarg.s  4
0x35851  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::LookupAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35856  ret
0x35857  ldarg.s  5
0x35859  ldc.i4.1
0x3585a  stind.i1
0x3585b  ldarg.0
0x3585c  ldstr    aDeleteappprinc// "DeleteAppPrincipal"
0x35861  ldarg.s  4
0x35863  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35868  ldloc.0
0x35869  ldarg.3
0x3586a  ldarg.s  4
0x3586c  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::DeleteAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35871  ldnull
0x35872  ret
0x35873  ldarg.s  5
0x35875  ldc.i4.1
0x35876  stind.i1
0x35877  ldarg.0
0x35878  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x3587d  ldarg.s  4
0x3587f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35884  ldloc.0
0x35885  ldarg.3
0x35886  ldarg.s  4
0x35888  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::AddAppPrincipalCredential_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3588d  ldnull
0x3588e  ret
0x3588f  ldarg.s  5
0x35891  ldc.i4.0
0x35892  stind.i1
0x35893  ldarg.0
0x35894  ldstr    aCreateappprinc// "CreateAppPrincipal"
0x35899  ldarg.s  4
0x3589b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x358a0  ldloc.0
0x358a1  ldarg.3
0x358a2  ldarg.s  4
0x358a4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::CreateAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x358a9  ret
0x358aa  ldarg.s  5
0x358ac  ldc.i4.0
0x358ad  stind.i1
0x358ae  ldarg.0
0x358af  ldstr    aGetappprincipa// "GetAppPrincipalConfiguration"
0x358b4  ldarg.s  4
0x358b6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x358bb  ldloc.0
0x358bc  ldarg.3
0x358bd  ldarg.s  4
0x358bf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalConfiguration_Client Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::GetAppPrincipalConfiguration_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x358c4  ret
0x358c5  ldarg.s  5
0x358c7  ldc.i4.1
0x358c8  stind.i1
0x358c9  ldarg.0
0x358ca  ldstr    aSetappprincipa// "SetAppPrincipalConfiguration"
0x358cf  ldarg.s  4
0x358d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x358d6  ldloc.0
0x358d7  ldarg.3
0x358d8  ldarg.s  4
0x358da  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::SetAppPrincipalConfiguration_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x358df  ldnull
0x358e0  ret
0x358e1  ldarg.s  5
0x358e3  ldc.i4.0
0x358e4  stind.i1
0x358e5  ldarg.0
0x358e6  ldstr    aGetappprincipa_0// "GetAppPrincipalCredentials"
0x358eb  ldarg.s  4
0x358ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x358f2  ldloc.0
0x358f3  ldarg.3
0x358f4  ldarg.s  4
0x358f6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalCredentialReference_Client> Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::GetAppPrincipalCredentials_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x358fb  ret
0x358fc  ldarg.s  5
0x358fe  ldc.i4.1
0x358ff  stind.i1
0x35900  ldarg.0
0x35901  ldstr    aDeleteappprinc_0// "DeleteAppPrincipalCredential"
0x35906  ldarg.s  4
0x35908  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3590d  ldloc.0
0x3590e  ldarg.3
0x3590f  ldarg.s  4
0x35911  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::DeleteAppPrincipalCredential_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35916  ldnull
0x35917  ret
0x35918  ldarg.0
0x35919  ldarg.1
0x3591a  ldarg.2
0x3591b  ldarg.3
0x3591c  ldarg.s  4
0x3591e  ldarg.s  5
0x35920  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x35925  ret
```
