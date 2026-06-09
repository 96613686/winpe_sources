# Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::InvokeMethod_0

- ea: `0x54b0`
- end: `0x5576`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::InvokeMethod_0`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x5460`
- `0x5480`
- `0x5490`
- `0x54b0`

## string_xrefs

- `0x5502`: `Remove`
- `0x554d`: `Remove`

## pseudocode

```c

```

## disassembly

```asm
0x54b0  ldarg.s  4
0x54b2  brtrue.s loc_54BF
0x54b4  ldstr    aProxycontext// "proxyContext"
0x54b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x54be  throw
0x54bf  ldarg.1
0x54c0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom
0x54c5  stloc.0
0x54c6  ldloc.0
0x54c7  brtrue.s loc_54D4
0x54c9  ldstr    aTarget// "target"
0x54ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x54d3  throw
0x54d4  ldarg.0
0x54d5  ldarg.2
0x54d6  ldarg.s  4
0x54d8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x54dd  starg.s  2
0x54df  ldarg.2
0x54e0  dup
0x54e1  stloc.1
0x54e2  brfalse  loc_5568
0x54e7  ldloc.1
0x54e8  ldstr    aAdd// "Add"
0x54ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54f2  brtrue.s loc_5510
0x54f4  ldloc.1
0x54f5  ldstr    aClear// "Clear"
0x54fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54ff  brtrue.s loc_552C
0x5501  ldloc.1
0x5502  ldstr    aRemove// "Remove"
0x5507  call     bool [mscorlib]System.String::op_Equality(string, string)
0x550c  brtrue.s loc_5548
0x550e  br.s     loc_5568
0x5510  ldarg.s  5
0x5512  ldc.i4.1
0x5513  stind.i1
0x5514  ldarg.0
0x5515  ldstr    aAdd// "Add"
0x551a  ldarg.s  4
0x551c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5521  ldloc.0
0x5522  ldarg.3
0x5523  ldarg.s  4
0x5525  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Add_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x552a  ldnull
0x552b  ret
0x552c  ldarg.s  5
0x552e  ldc.i4.1
0x552f  stind.i1
0x5530  ldarg.0
0x5531  ldstr    aClear// "Clear"
0x5536  ldarg.s  4
0x5538  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x553d  ldloc.0
0x553e  ldarg.3
0x553f  ldarg.s  4
0x5541  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Clear_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5546  ldnull
0x5547  ret
0x5548  ldarg.s  5
0x554a  ldc.i4.0
0x554b  stind.i1
0x554c  ldarg.0
0x554d  ldstr    aRemove// "Remove"
0x5552  ldarg.s  4
0x5554  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5559  ldloc.0
0x555a  ldarg.3
0x555b  ldarg.s  4
0x555d  call     bool Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsomServerStub::Remove_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5562  box      [mscorlib]System.Boolean
0x5567  ret
0x5568  ldarg.0
0x5569  ldarg.1
0x556a  ldarg.2
0x556b  ldarg.3
0x556c  ldarg.s  4
0x556e  ldarg.s  5
0x5570  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5575  ret
```
