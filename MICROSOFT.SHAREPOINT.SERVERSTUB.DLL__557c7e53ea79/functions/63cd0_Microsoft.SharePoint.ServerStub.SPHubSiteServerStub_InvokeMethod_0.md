# Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::InvokeMethod_0

- ea: `0x63cd0`
- end: `0x63d8f`
- name: `Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::InvokeMethod_0`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x63ca0`
- `0x63cb0`
- `0x63cc0`
- `0x63cd0`

## string_xrefs

- `0x63d12`: `Update`
- `0x63d4e`: `Update`
- `0x63d05`: `Delete`
- `0x63d32`: `Delete`
- `0x63d1f`: `UpdateWithFieldValues`
- `0x63d6a`: `UpdateWithFieldValues`

## pseudocode

```c

```

## disassembly

```asm
0x63cd0  ldarg.s  4
0x63cd2  brtrue.s loc_63CDF
0x63cd4  ldstr    aProxycontext// "proxyContext"
0x63cd9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x63cde  throw
0x63cdf  ldarg.1
0x63ce0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite
0x63ce5  stloc.0
0x63ce6  ldloc.0
0x63ce7  brtrue.s loc_63CF4
0x63ce9  ldstr    aTarget// "target"
0x63cee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x63cf3  throw
0x63cf4  ldarg.0
0x63cf5  ldarg.2
0x63cf6  ldarg.s  4
0x63cf8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63cfd  starg.s  2
0x63cff  ldarg.2
0x63d00  dup
0x63d01  stloc.1
0x63d02  brfalse.s loc_63D81
0x63d04  ldloc.1
0x63d05  ldstr    aDelete// "Delete"
0x63d0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63d0f  brtrue.s loc_63D2D
0x63d11  ldloc.1
0x63d12  ldstr    aUpdate// "Update"
0x63d17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63d1c  brtrue.s loc_63D49
0x63d1e  ldloc.1
0x63d1f  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x63d24  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63d29  brtrue.s loc_63D65
0x63d2b  br.s     loc_63D81
0x63d2d  ldarg.s  5
0x63d2f  ldc.i4.1
0x63d30  stind.i1
0x63d31  ldarg.0
0x63d32  ldstr    aDelete// "Delete"
0x63d37  ldarg.s  4
0x63d39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63d3e  ldloc.0
0x63d3f  ldarg.3
0x63d40  ldarg.s  4
0x63d42  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::Delete_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x63d47  ldnull
0x63d48  ret
0x63d49  ldarg.s  5
0x63d4b  ldc.i4.1
0x63d4c  stind.i1
0x63d4d  ldarg.0
0x63d4e  ldstr    aUpdate// "Update"
0x63d53  ldarg.s  4
0x63d55  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63d5a  ldloc.0
0x63d5b  ldarg.3
0x63d5c  ldarg.s  4
0x63d5e  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x63d63  ldnull
0x63d64  ret
0x63d65  ldarg.s  5
0x63d67  ldc.i4.1
0x63d68  stind.i1
0x63d69  ldarg.0
0x63d6a  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x63d6f  ldarg.s  4
0x63d71  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63d76  ldloc.0
0x63d77  ldarg.3
0x63d78  ldarg.s  4
0x63d7a  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::UpdateWithFieldValues_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x63d7f  ldnull
0x63d80  ret
0x63d81  ldarg.0
0x63d82  ldarg.1
0x63d83  ldarg.2
0x63d84  ldarg.3
0x63d85  ldarg.s  4
0x63d87  ldarg.s  5
0x63d89  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x63d8e  ret
```
