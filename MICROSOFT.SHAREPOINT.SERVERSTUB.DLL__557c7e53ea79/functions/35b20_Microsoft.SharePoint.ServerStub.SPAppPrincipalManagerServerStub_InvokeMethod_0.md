# Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::InvokeMethod_0

- ea: `0x35b20`
- end: `0x35cf6`
- name: `Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::InvokeMethod_0`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x35a00`
- `0x35a30`
- `0x35a50`
- `0x35a80`
- `0x35aa0`
- `0x35ac0`
- `0x35ae0`
- `0x35b00`
- `0x35b20`

## string_xrefs

- `0x35b73`: `DeleteAppPrincipal`
- `0x35c2c`: `DeleteAppPrincipal`
- `0x35b8b`: `CreateAppPrincipal`
- `0x35c64`: `CreateAppPrincipal`
- `0x35b97`: `GetAppPrincipalConfiguration`
- `0x35c7f`: `GetAppPrincipalConfiguration`
- `0x35ba3`: `SetAppPrincipalConfiguration`
- `0x35c9a`: `SetAppPrincipalConfiguration`
- `0x35bbb`: `DeleteAppPrincipalCredential`
- `0x35cd1`: `DeleteAppPrincipalCredential`

## pseudocode

```c

```

## disassembly

```asm
0x35b20  ldarg.s  4
0x35b22  brtrue.s loc_35B2F
0x35b24  ldstr    aProxycontext// "proxyContext"
0x35b29  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35b2e  throw
0x35b2f  ldarg.1
0x35b30  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager
0x35b35  stloc.0
0x35b36  ldloc.0
0x35b37  brtrue.s loc_35B44
0x35b39  ldstr    aTarget// "target"
0x35b3e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x35b43  throw
0x35b44  ldarg.0
0x35b45  ldarg.2
0x35b46  ldarg.s  4
0x35b48  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35b4d  starg.s  2
0x35b4f  ldarg.2
0x35b50  dup
0x35b51  stloc.1
0x35b52  brfalse  loc_35CE8
0x35b57  volatile.
0x35b59  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009f4-1
0x35b5e  brtrue.s loc_35BCD
0x35b60  ldc.i4.8
0x35b61  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x35b66  dup
0x35b67  ldstr    aLookupappprinc// "LookupAppPrincipal"
0x35b6c  ldc.i4.0
0x35b6d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35b72  dup
0x35b73  ldstr    aDeleteappprinc// "DeleteAppPrincipal"
0x35b78  ldc.i4.1
0x35b79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35b7e  dup
0x35b7f  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x35b84  ldc.i4.2
0x35b85  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35b8a  dup
0x35b8b  ldstr    aCreateappprinc// "CreateAppPrincipal"
0x35b90  ldc.i4.3
0x35b91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35b96  dup
0x35b97  ldstr    aGetappprincipa// "GetAppPrincipalConfiguration"
0x35b9c  ldc.i4.4
0x35b9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35ba2  dup
0x35ba3  ldstr    aSetappprincipa// "SetAppPrincipalConfiguration"
0x35ba8  ldc.i4.5
0x35ba9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35bae  dup
0x35baf  ldstr    aGetappprincipa_0// "GetAppPrincipalCredentials"
0x35bb4  ldc.i4.6
0x35bb5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35bba  dup
0x35bbb  ldstr    aDeleteappprinc_0// "DeleteAppPrincipalCredential"
0x35bc0  ldc.i4.7
0x35bc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x35bc6  volatile.
0x35bc8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009f4-1
0x35bcd  volatile.
0x35bcf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60009f4-1
0x35bd4  ldloc.1
0x35bd5  ldloca.s 2
0x35bd7  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x35bdc  brfalse  loc_35CE8
0x35be1  ldloc.2
0x35be2  switch   loc_35C0C, loc_35C27, loc_35C43, loc_35C5F, loc_35C7A, loc_35C95, loc_35CB1, loc_35CCC
0x35c07  br       loc_35CE8
0x35c0c  ldarg.s  5
0x35c0e  ldc.i4.0
0x35c0f  stind.i1
0x35c10  ldarg.0
0x35c11  ldstr    aLookupappprinc// "LookupAppPrincipal"
0x35c16  ldarg.s  4
0x35c18  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c1d  ldloc.0
0x35c1e  ldarg.3
0x35c1f  ldarg.s  4
0x35c21  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::LookupAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35c26  ret
0x35c27  ldarg.s  5
0x35c29  ldc.i4.1
0x35c2a  stind.i1
0x35c2b  ldarg.0
0x35c2c  ldstr    aDeleteappprinc// "DeleteAppPrincipal"
0x35c31  ldarg.s  4
0x35c33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c38  ldloc.0
0x35c39  ldarg.3
0x35c3a  ldarg.s  4
0x35c3c  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::DeleteAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35c41  ldnull
0x35c42  ret
0x35c43  ldarg.s  5
0x35c45  ldc.i4.1
0x35c46  stind.i1
0x35c47  ldarg.0
0x35c48  ldstr    aAddappprincipa// "AddAppPrincipalCredential"
0x35c4d  ldarg.s  4
0x35c4f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c54  ldloc.0
0x35c55  ldarg.3
0x35c56  ldarg.s  4
0x35c58  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::AddAppPrincipalCredential_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35c5d  ldnull
0x35c5e  ret
0x35c5f  ldarg.s  5
0x35c61  ldc.i4.0
0x35c62  stind.i1
0x35c63  ldarg.0
0x35c64  ldstr    aCreateappprinc// "CreateAppPrincipal"
0x35c69  ldarg.s  4
0x35c6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c70  ldloc.0
0x35c71  ldarg.3
0x35c72  ldarg.s  4
0x35c74  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipal Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::CreateAppPrincipal_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35c79  ret
0x35c7a  ldarg.s  5
0x35c7c  ldc.i4.0
0x35c7d  stind.i1
0x35c7e  ldarg.0
0x35c7f  ldstr    aGetappprincipa// "GetAppPrincipalConfiguration"
0x35c84  ldarg.s  4
0x35c86  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35c8b  ldloc.0
0x35c8c  ldarg.3
0x35c8d  ldarg.s  4
0x35c8f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalConfiguration_Client Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::GetAppPrincipalConfiguration_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35c94  ret
0x35c95  ldarg.s  5
0x35c97  ldc.i4.1
0x35c98  stind.i1
0x35c99  ldarg.0
0x35c9a  ldstr    aSetappprincipa// "SetAppPrincipalConfiguration"
0x35c9f  ldarg.s  4
0x35ca1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35ca6  ldloc.0
0x35ca7  ldarg.3
0x35ca8  ldarg.s  4
0x35caa  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::SetAppPrincipalConfiguration_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35caf  ldnull
0x35cb0  ret
0x35cb1  ldarg.s  5
0x35cb3  ldc.i4.0
0x35cb4  stind.i1
0x35cb5  ldarg.0
0x35cb6  ldstr    aGetappprincipa_0// "GetAppPrincipalCredentials"
0x35cbb  ldarg.s  4
0x35cbd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35cc2  ldloc.0
0x35cc3  ldarg.3
0x35cc4  ldarg.s  4
0x35cc6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalCredentialReference_Client> Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::GetAppPrincipalCredentials_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35ccb  ret
0x35ccc  ldarg.s  5
0x35cce  ldc.i4.1
0x35ccf  stind.i1
0x35cd0  ldarg.0
0x35cd1  ldstr    aDeleteappprinc_0// "DeleteAppPrincipalCredential"
0x35cd6  ldarg.s  4
0x35cd8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x35cdd  ldloc.0
0x35cde  ldarg.3
0x35cdf  ldarg.s  4
0x35ce1  call     void Microsoft.SharePoint.ServerStub.SPAppPrincipalManagerServerStub::DeleteAppPrincipalCredential_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppPrincipalManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x35ce6  ldnull
0x35ce7  ret
0x35ce8  ldarg.0
0x35ce9  ldarg.1
0x35cea  ldarg.2
0x35ceb  ldarg.3
0x35cec  ldarg.s  4
0x35cee  ldarg.s  5
0x35cf0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x35cf5  ret
```
