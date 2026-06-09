# Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetProperty

- ea: `0x6500`
- end: `0x67b2`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::GetProperty`
- size: `690`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5750`
- `0x6500`

## string_xrefs

- `0x65ea`: `SimpleLinkUrl`
- `0x6770`: `SimpleLinkUrl`

## pseudocode

```c

```

## disassembly

```asm
0x6500  ldarg.2
0x6501  brtrue.s loc_650E
0x6503  ldstr    aPropname// "propName"
0x6508  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x650d  throw
0x650e  ldarg.3
0x650f  brtrue.s loc_651C
0x6511  ldstr    aProxycontext// "proxyContext"
0x6516  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x651b  throw
0x651c  ldarg.1
0x651d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x6522  stloc.0
0x6523  ldloc.0
0x6524  brtrue.s loc_6531
0x6526  ldstr    aTarget// "target"
0x652b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6530  throw
0x6531  ldarg.0
0x6532  ldarg.2
0x6533  ldarg.3
0x6534  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6539  starg.s  2
0x653b  ldarg.2
0x653c  dup
0x653d  stloc.1
0x653e  brfalse  loc_67A8
0x6543  volatile.
0x6545  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000101-1
0x654a  brtrue   loc_6617
0x654f  ldc.i4.s 0xF
0x6551  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6556  dup
0x6557  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x655c  ldc.i4.0
0x655d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6562  dup
0x6563  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x6568  ldc.i4.1
0x6569  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x656e  dup
0x656f  ldstr    aCategoryimageu// "CategoryImageUrl"
0x6574  ldc.i4.2
0x6575  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x657a  dup
0x657b  ldstr    aExcludedprovid// "ExcludedProviders"
0x6580  ldc.i4.3
0x6581  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6586  dup
0x6587  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x658c  ldc.i4.4
0x658d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6592  dup
0x6593  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x6598  ldc.i4.5
0x6599  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x659e  dup
0x659f  ldstr    aFriendlyurlseg// "FriendlyUrlSegment"
0x65a4  ldc.i4.6
0x65a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65aa  dup
0x65ab  ldstr    aHovertext// "HoverText"
0x65b0  ldc.i4.7
0x65b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65b6  dup
0x65b7  ldstr    aIsdeprecated// "IsDeprecated"
0x65bc  ldc.i4.8
0x65bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65c2  dup
0x65c3  ldstr    aIspinned// "IsPinned"
0x65c8  ldc.i4.s 9
0x65ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65cf  dup
0x65d0  ldstr    aIspinnedroot// "IsPinnedRoot"
0x65d5  ldc.i4.s 0xA
0x65d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65dc  dup
0x65dd  ldstr    aParent// "Parent"
0x65e2  ldc.i4.s 0xB
0x65e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65e9  dup
0x65ea  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x65ef  ldc.i4.s 0xC
0x65f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x65f6  dup
0x65f7  ldstr    aTargeturl// "TargetUrl"
0x65fc  ldc.i4.s 0xD
0x65fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6603  dup
0x6604  ldstr    aTermset// "TermSet"
0x6609  ldc.i4.s 0xE
0x660b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6610  volatile.
0x6612  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000101-1
0x6617  volatile.
0x6619  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000101-1
0x661e  ldloc.1
0x661f  ldloca.s 2
0x6621  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6626  brfalse  loc_67A8
0x662b  ldloc.2
0x662c  switch   loc_6672, loc_6685, loc_6698, loc_66AB, loc_66BE, loc_66D6, loc_66EE, loc_6701, loc_6714, loc_672C, loc_6744, loc_675C, loc_676F, loc_6782, loc_6795
0x666d  br       loc_67A8
0x6672  ldarg.0
0x6673  ldstr    aAssociatedfold// "AssociatedFolderUrl"
0x6678  ldarg.3
0x6679  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x667e  ldloc.0
0x667f  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_AssociatedFolderUrl()
0x6684  ret
0x6685  ldarg.0
0x6686  ldstr    aCatalogtargetu_0// "CatalogTargetUrl"
0x668b  ldarg.3
0x668c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6691  ldloc.0
0x6692  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_CatalogTargetUrl()
0x6697  ret
0x6698  ldarg.0
0x6699  ldstr    aCategoryimageu// "CategoryImageUrl"
0x669e  ldarg.3
0x669f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66a4  ldloc.0
0x66a5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_CategoryImageUrl()
0x66aa  ret
0x66ab  ldarg.0
0x66ac  ldstr    aExcludedprovid// "ExcludedProviders"
0x66b1  ldarg.3
0x66b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66b7  ldloc.0
0x66b8  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermProviderNameCollectionCsom [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludedProvidersCsom()
0x66bd  ret
0x66be  ldarg.0
0x66bf  ldstr    aExcludefromcur// "ExcludeFromCurrentNavigation"
0x66c4  ldarg.3
0x66c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66ca  ldloc.0
0x66cb  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromCurrentNavigation()
0x66d0  box      [mscorlib]System.Boolean
0x66d5  ret
0x66d6  ldarg.0
0x66d7  ldstr    aExcludefromglo// "ExcludeFromGlobalNavigation"
0x66dc  ldarg.3
0x66dd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66e2  ldloc.0
0x66e3  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_ExcludeFromGlobalNavigation()
0x66e8  box      [mscorlib]System.Boolean
0x66ed  ret
0x66ee  ldarg.0
0x66ef  ldstr    aFriendlyurlseg// "FriendlyUrlSegment"
0x66f4  ldarg.3
0x66f5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66fa  ldloc.0
0x66fb  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_FriendlyUrlSegment()
0x6700  ret
0x6701  ldarg.0
0x6702  ldstr    aHovertext// "HoverText"
0x6707  ldarg.3
0x6708  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x670d  ldloc.0
0x670e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_HoverText()
0x6713  ret
0x6714  ldarg.0
0x6715  ldstr    aIsdeprecated// "IsDeprecated"
0x671a  ldarg.3
0x671b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6720  ldloc.0
0x6721  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsDeprecated()
0x6726  box      [mscorlib]System.Boolean
0x672b  ret
0x672c  ldarg.0
0x672d  ldstr    aIspinned// "IsPinned"
0x6732  ldarg.3
0x6733  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6738  ldloc.0
0x6739  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsPinned()
0x673e  box      [mscorlib]System.Boolean
0x6743  ret
0x6744  ldarg.0
0x6745  ldstr    aIspinnedroot// "IsPinnedRoot"
0x674a  ldarg.3
0x674b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6750  ldloc.0
0x6751  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_IsPinnedRoot()
0x6756  box      [mscorlib]System.Boolean
0x675b  ret
0x675c  ldarg.0
0x675d  ldstr    aParent// "Parent"
0x6762  ldarg.3
0x6763  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6768  ldloc.0
0x6769  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_Parent()
0x676e  ret
0x676f  ldarg.0
0x6770  ldstr    aSimplelinkurl// "SimpleLinkUrl"
0x6775  ldarg.3
0x6776  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x677b  ldloc.0
0x677c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_SimpleLinkUrl()
0x6781  ret
0x6782  ldarg.0
0x6783  ldstr    aTargeturl// "TargetUrl"
0x6788  ldarg.3
0x6789  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x678e  ldloc.0
0x678f  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_TargetUrl()
0x6794  ret
0x6795  ldarg.0
0x6796  ldstr    aTermset// "TermSet"
0x679b  ldarg.3
0x679c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x67a1  ldloc.0
0x67a2  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm::get_TermSet()
0x67a7  ret
0x67a8  ldarg.0
0x67a9  ldarg.1
0x67aa  ldarg.2
0x67ab  ldarg.3
0x67ac  call     instance object Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x67b1  ret
```
