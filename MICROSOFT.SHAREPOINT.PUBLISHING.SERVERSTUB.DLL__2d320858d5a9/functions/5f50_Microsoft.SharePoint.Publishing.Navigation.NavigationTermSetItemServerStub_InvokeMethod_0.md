# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod_0

- ea: `0x5f50`
- end: `0x600c`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod_0`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x73d0`
- `0x8300`

## callees

- `0x5ee0`
- `0x5f00`
- `0x5f10`
- `0x5f50`

## string_xrefs

- `0x5f9f`: `CreateTerm`
- `0x5fe8`: `CreateTerm`

## pseudocode

```c

```

## disassembly

```asm
0x5f50  ldarg.s  4
0x5f52  brtrue.s loc_5F5F
0x5f54  ldstr    aProxycontext// "proxyContext"
0x5f59  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f5e  throw
0x5f5f  ldarg.1
0x5f60  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x5f65  stloc.0
0x5f66  ldloc.0
0x5f67  brtrue.s loc_5F74
0x5f69  ldstr    aTarget// "target"
0x5f6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f73  throw
0x5f74  ldarg.0
0x5f75  ldarg.2
0x5f76  ldarg.s  4
0x5f78  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f7d  starg.s  2
0x5f7f  ldarg.2
0x5f80  dup
0x5f81  stloc.1
0x5f82  brfalse.s loc_5FFE
0x5f84  ldloc.1
0x5f85  ldstr    aGetresolveddis// "GetResolvedDisplayUrl"
0x5f8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5f8f  brtrue.s loc_5FAD
0x5f91  ldloc.1
0x5f92  ldstr    aGettaxonomyter// "GetTaxonomyTermStore"
0x5f97  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5f9c  brtrue.s loc_5FC8
0x5f9e  ldloc.1
0x5f9f  ldstr    aCreateterm// "CreateTerm"
0x5fa4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5fa9  brtrue.s loc_5FE3
0x5fab  br.s     loc_5FFE
0x5fad  ldarg.s  5
0x5faf  ldc.i4.0
0x5fb0  stind.i1
0x5fb1  ldarg.0
0x5fb2  ldstr    aGetresolveddis// "GetResolvedDisplayUrl"
0x5fb7  ldarg.s  4
0x5fb9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5fbe  ldloc.0
0x5fbf  ldarg.3
0x5fc0  ldarg.s  4
0x5fc2  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetResolvedDisplayUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5fc7  ret
0x5fc8  ldarg.s  5
0x5fca  ldc.i4.0
0x5fcb  stind.i1
0x5fcc  ldarg.0
0x5fcd  ldstr    aGettaxonomyter// "GetTaxonomyTermStore"
0x5fd2  ldarg.s  4
0x5fd4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5fd9  ldloc.0
0x5fda  ldarg.3
0x5fdb  ldarg.s  4
0x5fdd  call     class [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetTaxonomyTermStore_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5fe2  ret
0x5fe3  ldarg.s  5
0x5fe5  ldc.i4.0
0x5fe6  stind.i1
0x5fe7  ldarg.0
0x5fe8  ldstr    aCreateterm// "CreateTerm"
0x5fed  ldarg.s  4
0x5fef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ff4  ldloc.0
0x5ff5  ldarg.3
0x5ff6  ldarg.s  4
0x5ff8  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::CreateTerm_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5ffd  ret
0x5ffe  ldarg.0
0x5fff  ldarg.1
0x6000  ldarg.2
0x6001  ldarg.3
0x6002  ldarg.s  4
0x6004  ldarg.s  5
0x6006  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x600b  ret
```
