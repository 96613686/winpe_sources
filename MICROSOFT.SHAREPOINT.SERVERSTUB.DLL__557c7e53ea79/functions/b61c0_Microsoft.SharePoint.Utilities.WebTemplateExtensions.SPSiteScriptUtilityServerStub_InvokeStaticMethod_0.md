# Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::InvokeStaticMethod_0

- ea: `0xb61c0`
- end: `0xb64de`
- name: `Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::InvokeStaticMethod_0`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xb5fa0`
- `0xb5fc0`
- `0xb5fe0`
- `0xb6000`
- `0xb6010`
- `0xb6030`
- `0xb6050`
- `0xb6070`
- `0xb6080`
- `0xb6090`
- `0xb60a0`
- `0xb60e0`
- `0xb6110`
- `0xb6130`
- `0xb6150`
- `0xb6170`
- `0xb6190`
- `0xb61c0`

## string_xrefs

- `0xb6254`: `ValidatePendingWebTemplateExtension`
- `0xb63f8`: `ValidatePendingWebTemplateExtension`
- `0xb6200`: `CreateSiteScript`
- `0xb634e`: `CreateSiteScript`
- `0xb620c`: `DeleteSiteScript`
- `0xb6366`: `DeleteSiteScript`
- `0xb6230`: `CreateSiteDesign`
- `0xb63af`: `CreateSiteDesign`
- `0xb623c`: `DeleteSiteDesign`
- `0xb63c7`: `DeleteSiteDesign`
- `0xb6294`: `UpdateSiteScript`
- `0xb647c`: `UpdateSiteScript`
- `0xb62a1`: `UpdateSiteScriptContent`
- `0xb6494`: `UpdateSiteScriptContent`
- `0xb62ae`: `UpdateSiteDesign`
- `0xb64ac`: `UpdateSiteDesign`

## pseudocode

```c

```

## disassembly

```asm
0xb61c0  ldarg.3
0xb61c1  brtrue.s loc_B61CE
0xb61c3  ldstr    aProxycontext// "proxyContext"
0xb61c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb61cd  throw
0xb61ce  ldarg.0
0xb61cf  ldarg.1
0xb61d0  ldarg.3
0xb61d1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb61d6  starg.s  1
0xb61d8  ldarg.1
0xb61d9  dup
0xb61da  stloc.0
0xb61db  brfalse  loc_B64D7
0xb61e0  volatile.
0xb61e2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001df8-1
0xb61e7  brtrue   loc_B62CE
0xb61ec  ldc.i4.s 0x11
0xb61ee  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb61f3  dup
0xb61f4  ldstr    aGetsitescriptm// "GetSiteScriptMetadata"
0xb61f9  ldc.i4.0
0xb61fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb61ff  dup
0xb6200  ldstr    aCreatesitescri// "CreateSiteScript"
0xb6205  ldc.i4.1
0xb6206  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb620b  dup
0xb620c  ldstr    aDeletesitescri// "DeleteSiteScript"
0xb6211  ldc.i4.2
0xb6212  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6217  dup
0xb6218  ldstr    aGetsitescripts// "GetSiteScripts"
0xb621d  ldc.i4.3
0xb621e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6223  dup
0xb6224  ldstr    aGetsitedesignm// "GetSiteDesignMetadata"
0xb6229  ldc.i4.4
0xb622a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb622f  dup
0xb6230  ldstr    aCreatesitedesi// "CreateSiteDesign"
0xb6235  ldc.i4.5
0xb6236  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb623b  dup
0xb623c  ldstr    aDeletesitedesi// "DeleteSiteDesign"
0xb6241  ldc.i4.6
0xb6242  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6247  dup
0xb6248  ldstr    aGetsitedesigns// "GetSiteDesigns"
0xb624d  ldc.i4.7
0xb624e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6253  dup
0xb6254  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb6259  ldc.i4.8
0xb625a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb625f  dup
0xb6260  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0xb6265  ldc.i4.s 9
0xb6267  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb626c  dup
0xb626d  ldstr    aGrantsitedesig// "GrantSiteDesignRights"
0xb6272  ldc.i4.s 0xA
0xb6274  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6279  dup
0xb627a  ldstr    aRevokesitedesi// "RevokeSiteDesignRights"
0xb627f  ldc.i4.s 0xB
0xb6281  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6286  dup
0xb6287  ldstr    aGetsitedesignr// "GetSiteDesignRights"
0xb628c  ldc.i4.s 0xC
0xb628e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb6293  dup
0xb6294  ldstr    aUpdatesitescri// "UpdateSiteScript"
0xb6299  ldc.i4.s 0xD
0xb629b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb62a0  dup
0xb62a1  ldstr    aUpdatesitescri_0// "UpdateSiteScriptContent"
0xb62a6  ldc.i4.s 0xE
0xb62a8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb62ad  dup
0xb62ae  ldstr    aUpdatesitedesi// "UpdateSiteDesign"
0xb62b3  ldc.i4.s 0xF
0xb62b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb62ba  dup
0xb62bb  ldstr    aApplysitedesig// "ApplySiteDesign"
0xb62c0  ldc.i4.s 0x10
0xb62c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb62c7  volatile.
0xb62c9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001df8-1
0xb62ce  volatile.
0xb62d0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001df8-1
0xb62d5  ldloc.0
0xb62d6  ldloca.s 1
0xb62d8  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb62dd  brfalse  loc_B64D7
0xb62e2  ldloc.1
0xb62e3  switch   loc_B6331, loc_B6349, loc_B6361, loc_B637A, loc_B6392, loc_B63AA, loc_B63C2, loc_B63DB, loc_B63F3, loc_B6410, loc_B642D, loc_B6446, loc_B645F, loc_B6477, loc_B648F, loc_B64A7, loc_B64BF
0xb632c  br       loc_B64D7
0xb6331  ldarg.s  4
0xb6333  ldc.i4.0
0xb6334  stind.i1
0xb6335  ldarg.0
0xb6336  ldstr    aGetsitescriptm// "GetSiteScriptMetadata"
0xb633b  ldarg.3
0xb633c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6341  ldarg.2
0xb6342  ldarg.3
0xb6343  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteScriptMetadata_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6348  ret
0xb6349  ldarg.s  4
0xb634b  ldc.i4.0
0xb634c  stind.i1
0xb634d  ldarg.0
0xb634e  ldstr    aCreatesitescri// "CreateSiteScript"
0xb6353  ldarg.3
0xb6354  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6359  ldarg.2
0xb635a  ldarg.3
0xb635b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::CreateSiteScript_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6360  ret
0xb6361  ldarg.s  4
0xb6363  ldc.i4.1
0xb6364  stind.i1
0xb6365  ldarg.0
0xb6366  ldstr    aDeletesitescri// "DeleteSiteScript"
0xb636b  ldarg.3
0xb636c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6371  ldarg.2
0xb6372  ldarg.3
0xb6373  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::DeleteSiteScript_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6378  ldnull
0xb6379  ret
0xb637a  ldarg.s  4
0xb637c  ldc.i4.0
0xb637d  stind.i1
0xb637e  ldarg.0
0xb637f  ldstr    aGetsitescripts// "GetSiteScripts"
0xb6384  ldarg.3
0xb6385  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb638a  ldarg.2
0xb638b  ldarg.3
0xb638c  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteScripts_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6391  ret
0xb6392  ldarg.s  4
0xb6394  ldc.i4.0
0xb6395  stind.i1
0xb6396  ldarg.0
0xb6397  ldstr    aGetsitedesignm// "GetSiteDesignMetadata"
0xb639c  ldarg.3
0xb639d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb63a2  ldarg.2
0xb63a3  ldarg.3
0xb63a4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesignMetadata_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb63a9  ret
0xb63aa  ldarg.s  4
0xb63ac  ldc.i4.0
0xb63ad  stind.i1
0xb63ae  ldarg.0
0xb63af  ldstr    aCreatesitedesi// "CreateSiteDesign"
0xb63b4  ldarg.3
0xb63b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb63ba  ldarg.2
0xb63bb  ldarg.3
0xb63bc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::CreateSiteDesign_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb63c1  ret
0xb63c2  ldarg.s  4
0xb63c4  ldc.i4.1
0xb63c5  stind.i1
0xb63c6  ldarg.0
0xb63c7  ldstr    aDeletesitedesi// "DeleteSiteDesign"
0xb63cc  ldarg.3
0xb63cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb63d2  ldarg.2
0xb63d3  ldarg.3
0xb63d4  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::DeleteSiteDesign_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb63d9  ldnull
0xb63da  ret
0xb63db  ldarg.s  4
0xb63dd  ldc.i4.0
0xb63de  stind.i1
0xb63df  ldarg.0
0xb63e0  ldstr    aGetsitedesigns// "GetSiteDesigns"
0xb63e5  ldarg.3
0xb63e6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb63eb  ldarg.2
0xb63ec  ldarg.3
0xb63ed  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesigns_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb63f2  ret
0xb63f3  ldarg.s  4
0xb63f5  ldc.i4.0
0xb63f6  stind.i1
0xb63f7  ldarg.0
0xb63f8  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb63fd  ldarg.3
0xb63fe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6403  ldarg.2
0xb6404  ldarg.3
0xb6405  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ValidatePendingWebTemplateExtension_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb640a  box      [mscorlib]System.Boolean
0xb640f  ret
0xb6410  ldarg.s  4
0xb6412  ldc.i4.0
0xb6413  stind.i1
0xb6414  ldarg.0
0xb6415  ldstr    aApplyimplicits// "ApplyImplicitSiteDesign"
0xb641a  ldarg.3
0xb641b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6420  ldarg.2
0xb6421  ldarg.3
0xb6422  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ApplyImplicitSiteDesign_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6427  box      [mscorlib]System.Boolean
0xb642c  ret
0xb642d  ldarg.s  4
0xb642f  ldc.i4.1
0xb6430  stind.i1
0xb6431  ldarg.0
0xb6432  ldstr    aGrantsitedesig// "GrantSiteDesignRights"
0xb6437  ldarg.3
0xb6438  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb643d  ldarg.2
0xb643e  ldarg.3
0xb643f  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GrantSiteDesignRights_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6444  ldnull
0xb6445  ret
0xb6446  ldarg.s  4
0xb6448  ldc.i4.1
0xb6449  stind.i1
0xb644a  ldarg.0
0xb644b  ldstr    aRevokesitedesi// "RevokeSiteDesignRights"
0xb6450  ldarg.3
0xb6451  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6456  ldarg.2
0xb6457  ldarg.3
0xb6458  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::RevokeSiteDesignRights_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb645d  ldnull
0xb645e  ret
0xb645f  ldarg.s  4
0xb6461  ldc.i4.0
0xb6462  stind.i1
0xb6463  ldarg.0
0xb6464  ldstr    aGetsitedesignr// "GetSiteDesignRights"
0xb6469  ldarg.3
0xb646a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb646f  ldarg.2
0xb6470  ldarg.3
0xb6471  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignPrincipal> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::GetSiteDesignRights_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb6476  ret
0xb6477  ldarg.s  4
0xb6479  ldc.i4.0
0xb647a  stind.i1
0xb647b  ldarg.0
0xb647c  ldstr    aUpdatesitescri// "UpdateSiteScript"
0xb6481  ldarg.3
0xb6482  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb6487  ldarg.2
0xb6488  ldarg.3
0xb6489  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteScript_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb648e  ret
0xb648f  ldarg.s  4
0xb6491  ldc.i4.0
0xb6492  stind.i1
0xb6493  ldarg.0
0xb6494  ldstr    aUpdatesitescri_0// "UpdateSiteScriptContent"
0xb6499  ldarg.3
0xb649a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb649f  ldarg.2
0xb64a0  ldarg.3
0xb64a1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteScriptContent_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb64a6  ret
0xb64a7  ldarg.s  4
0xb64a9  ldc.i4.0
0xb64aa  stind.i1
0xb64ab  ldarg.0
0xb64ac  ldstr    aUpdatesitedesi// "UpdateSiteDesign"
0xb64b1  ldarg.3
0xb64b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb64b7  ldarg.2
0xb64b8  ldarg.3
0xb64b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteDesignMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::UpdateSiteDesign_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb64be  ret
0xb64bf  ldarg.s  4
0xb64c1  ldc.i4.0
0xb64c2  stind.i1
0xb64c3  ldarg.0
0xb64c4  ldstr    aApplysitedesig// "ApplySiteDesign"
0xb64c9  ldarg.3
0xb64ca  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb64cf  ldarg.2
0xb64d0  ldarg.3
0xb64d1  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptActionResult> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPSiteScriptUtilityServerStub::ApplySiteDesign_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb64d6  ret
0xb64d7  ldarg.1
0xb64d8  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb64dd  throw
```
