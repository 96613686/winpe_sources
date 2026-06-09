# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::SetProperty_0

- ea: `0x76e0`
- end: `0x7862`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::SetProperty_0`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6010`
- `0x76e0`

## string_xrefs

- `0x7771`: `SimpleLinkUrl`
- `0x783d`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x76e0  ldarg.s  4
0x76e2  brtrue.s loc_76EF
0x76e4  ldstr    aProxycontext// "proxyContext"
0x76e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x76ee  throw
0x76ef  ldarg.1
0x76f0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x76f5  stloc.0
0x76f6  ldloc.0
0x76f7  brtrue.s loc_7704
0x76f9  ldstr    aTarget// "target"
0x76fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7703  throw
0x7704  ldarg.2
0x7705  brtrue.s loc_7712
0x7707  ldstr    aPropname// "propName"
0x770c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7711  throw
0x7712  ldarg.0
0x7713  ldarg.2
0x7714  ldarg.s  4
0x7716  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x771b  starg.s  2
0x771d  ldarg.2
0x771e  dup
0x771f  stloc.1
0x7720  brfalse  loc_7856
0x7725  volatile.
0x7727  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600011b-1
0x772c  brtrue.s loc_7783
0x772e  ldc.i4.6
0x772f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x7734  dup
0x7735  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x773a  ldc.i4.0
0x773b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7740  dup
0x7741  ldstr    aCategoryimageu// "CategoryImageUrl"
0x7746  ldc.i4.1
0x7747  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x774c  dup
0x774d  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x7752  ldc.i4.2
0x7753  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7758  dup
0x7759  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x775e  ldc.i4.3
0x775f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7764  dup
0x7765  ldstr    aHovertext// "HoverText"
0x776a  ldc.i4.4
0x776b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7770  dup
0x7771  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x7776  ldc.i4.5
0x7777  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x777c  volatile.
0x777e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600011b-1
0x7783  volatile.
0x7785  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600011b-1
0x778a  ldloc.1
0x778b  ldloca.s 2
0x778d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x7792  brfalse  loc_7856
0x7797  ldloc.2
0x7798  switch   loc_77BA, loc_77D4, loc_77EE, loc_7808, loc_7822, loc_783C
0x77b5  br       loc_7856
0x77ba  ldarg.0
0x77bb  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x77c0  ldarg.s  4
0x77c2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x77c7  ldloc.0
0x77c8  ldarg.3
0x77c9  callvirt T0x2B000001
0x77ce  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_AssociatedFolderUrl(string)
0x77d3  ret
0x77d4  ldarg.0
0x77d5  ldstr    aCategoryimageu// "CategoryImageUrl"
0x77da  ldarg.s  4
0x77dc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x77e1  ldloc.0
0x77e2  ldarg.3
0x77e3  callvirt T0x2B000001
0x77e8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_CategoryImageUrl(string)
0x77ed  ret
0x77ee  ldarg.0
0x77ef  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x77f4  ldarg.s  4
0x77f6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x77fb  ldloc.0
0x77fc  ldarg.3
0x77fd  callvirt T0x2B000007
0x7802  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_ExcludeFromCurrentNavigation(bool)
0x7807  ret
0x7808  ldarg.0
0x7809  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x780e  ldarg.s  4
0x7810  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7815  ldloc.0
0x7816  ldarg.3
0x7817  callvirt T0x2B000007
0x781c  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_ExcludeFromGlobalNavigation(bool)
0x7821  ret
0x7822  ldarg.0
0x7823  ldstr    aHovertext// "HoverText"
0x7828  ldarg.s  4
0x782a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x782f  ldloc.0
0x7830  ldarg.3
0x7831  callvirt T0x2B000001
0x7836  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_HoverText(string)
0x783b  ret
0x783c  ldarg.0
0x783d  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x7842  ldarg.s  4
0x7844  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7849  ldloc.0
0x784a  ldarg.3
0x784b  callvirt T0x2B000001
0x7850  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::set_SimpleLinkUrl(string)
0x7855  ret
0x7856  ldarg.0
0x7857  ldarg.1
0x7858  ldarg.2
0x7859  ldarg.3
0x785a  ldarg.s  4
0x785c  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7861  ret
```
