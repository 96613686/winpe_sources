# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::InvokeMethod_0

- ea: `0x73d0`
- end: `0x75ff`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::InvokeMethod_0`
- size: `559`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x5f50`
- `0x72e0`
- `0x7300`
- `0x7320`
- `0x7350`
- `0x7360`
- `0x7370`
- `0x7380`
- `0x7390`
- `0x73a0`
- `0x73c0`
- `0x73d0`

## string_xrefs

- `0x7487`: `DeleteObject`
- `0x75da`: `DeleteObject`

## pseudocode

```c

```

## disassembly

```asm
0x73d0  ldarg.s  4
0x73d2  brtrue.s loc_73DF
0x73d4  ldstr    aProxycontext// "proxyContext"
0x73d9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73de  throw
0x73df  ldarg.1
0x73e0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x73e5  stloc.0
0x73e6  ldloc.0
0x73e7  brtrue.s loc_73F4
0x73e9  ldstr    aTarget// "target"
0x73ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x73f3  throw
0x73f4  ldarg.0
0x73f5  ldarg.2
0x73f6  ldarg.s  4
0x73f8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x73fd  starg.s  2
0x73ff  ldarg.2
0x7400  dup
0x7401  stloc.1
0x7402  brfalse  loc_75F1
0x7407  volatile.
0x7409  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000117-1
0x740e  brtrue   loc_749A
0x7413  ldc.i4.s 0xA
0x7415  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x741a  dup
0x741b  ldstr    aGetaseditable// "GetAsEditable"
0x7420  ldc.i4.0
0x7421  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7426  dup
0x7427  ldstr    aGetwithnewview// "GetWithNewView"
0x742c  ldc.i4.1
0x742d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7432  dup
0x7433  ldstr    aGetresolvedtar// "GetResolvedTargetUrl"
0x7438  ldc.i4.2
0x7439  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x743e  dup
0x743f  ldstr    aGetresolvedtar_0// "GetResolvedTargetUrlWithoutQuery"
0x7444  ldc.i4.3
0x7445  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x744a  dup
0x744b  ldstr    aGetresolvedass// "GetResolvedAssociatedFolderUrl"
0x7450  ldc.i4.4
0x7451  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7456  dup
0x7457  ldstr    aGetwebrelative// "GetWebRelativeFriendlyUrl"
0x745c  ldc.i4.5
0x745d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7462  dup
0x7463  ldstr    aGetallparentte// "GetAllParentTerms"
0x7468  ldc.i4.6
0x7469  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x746e  dup
0x746f  ldstr    aGettaxonomyter_0// "GetTaxonomyTerm"
0x7474  ldc.i4.7
0x7475  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x747a  dup
0x747b  ldstr    aMove// "Move"
0x7480  ldc.i4.8
0x7481  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7486  dup
0x7487  ldstr    aDeleteobject// "DeleteObject"
0x748c  ldc.i4.s 9
0x748e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7493  volatile.
0x7495  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000117-1
0x749a  volatile.
0x749c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000117-1
0x74a1  ldloc.1
0x74a2  ldloca.s 2
0x74a4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x74a9  brfalse  loc_75F1
0x74ae  ldloc.2
0x74af  switch   loc_74E1, loc_74FC, loc_7517, loc_7532, loc_754D, loc_7568, loc_7583, loc_759E, loc_75B9, loc_75D5
0x74dc  br       loc_75F1
0x74e1  ldarg.s  5
0x74e3  ldc.i4.0
0x74e4  stind.i1
0x74e5  ldarg.0
0x74e6  ldstr    aGetaseditable// "GetAsEditable"
0x74eb  ldarg.s  4
0x74ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x74f2  ldloc.0
0x74f3  ldarg.3
0x74f4  ldarg.s  4
0x74f6  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetAsEditable_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x74fb  ret
0x74fc  ldarg.s  5
0x74fe  ldc.i4.0
0x74ff  stind.i1
0x7500  ldarg.0
0x7501  ldstr    aGetwithnewview// "GetWithNewView"
0x7506  ldarg.s  4
0x7508  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x750d  ldloc.0
0x750e  ldarg.3
0x750f  ldarg.s  4
0x7511  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetWithNewView_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7516  ret
0x7517  ldarg.s  5
0x7519  ldc.i4.0
0x751a  stind.i1
0x751b  ldarg.0
0x751c  ldstr    aGetresolvedtar// "GetResolvedTargetUrl"
0x7521  ldarg.s  4
0x7523  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7528  ldloc.0
0x7529  ldarg.3
0x752a  ldarg.s  4
0x752c  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedTargetUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7531  ret
0x7532  ldarg.s  5
0x7534  ldc.i4.0
0x7535  stind.i1
0x7536  ldarg.0
0x7537  ldstr    aGetresolvedtar_0// "GetResolvedTargetUrlWithoutQuery"
0x753c  ldarg.s  4
0x753e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7543  ldloc.0
0x7544  ldarg.3
0x7545  ldarg.s  4
0x7547  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedTargetUrlWithoutQuery_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x754c  ret
0x754d  ldarg.s  5
0x754f  ldc.i4.0
0x7550  stind.i1
0x7551  ldarg.0
0x7552  ldstr    aGetresolvedass// "GetResolvedAssociatedFolderUrl"
0x7557  ldarg.s  4
0x7559  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x755e  ldloc.0
0x755f  ldarg.3
0x7560  ldarg.s  4
0x7562  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetResolvedAssociatedFolderUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7567  ret
0x7568  ldarg.s  5
0x756a  ldc.i4.0
0x756b  stind.i1
0x756c  ldarg.0
0x756d  ldstr    aGetwebrelative// "GetWebRelativeFriendlyUrl"
0x7572  ldarg.s  4
0x7574  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7579  ldloc.0
0x757a  ldarg.3
0x757b  ldarg.s  4
0x757d  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetWebRelativeFriendlyUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7582  ret
0x7583  ldarg.s  5
0x7585  ldc.i4.0
0x7586  stind.i1
0x7587  ldarg.0
0x7588  ldstr    aGetallparentte// "GetAllParentTerms"
0x758d  ldarg.s  4
0x758f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7594  ldloc.0
0x7595  ldarg.3
0x7596  ldarg.s  4
0x7598  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetAllParentTerms_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x759d  ret
0x759e  ldarg.s  5
0x75a0  ldc.i4.0
0x75a1  stind.i1
0x75a2  ldarg.0
0x75a3  ldstr    aGettaxonomyter_0// "GetTaxonomyTerm"
0x75a8  ldarg.s  4
0x75aa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x75af  ldloc.0
0x75b0  ldarg.3
0x75b1  ldarg.s  4
0x75b3  call     class [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetTaxonomyTerm_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x75b8  ret
0x75b9  ldarg.s  5
0x75bb  ldc.i4.1
0x75bc  stind.i1
0x75bd  ldarg.0
0x75be  ldstr    aMove// "Move"
0x75c3  ldarg.s  4
0x75c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x75ca  ldloc.0
0x75cb  ldarg.3
0x75cc  ldarg.s  4
0x75ce  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::Move_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x75d3  ldnull
0x75d4  ret
0x75d5  ldarg.s  5
0x75d7  ldc.i4.1
0x75d8  stind.i1
0x75d9  ldarg.0
0x75da  ldstr    aDeleteobject// "DeleteObject"
0x75df  ldarg.s  4
0x75e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x75e6  ldloc.0
0x75e7  ldarg.3
0x75e8  ldarg.s  4
0x75ea  call     void Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x75ef  ldnull
0x75f0  ret
0x75f1  ldarg.0
0x75f2  ldarg.1
0x75f3  ldarg.2
0x75f4  ldarg.3
0x75f5  ldarg.s  4
0x75f7  ldarg.s  5
0x75f9  call     instance object Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod(object target, string methodName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] bool& isVoid)
0x75fe  ret
```
