# Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::InvokeStaticMethod

- ea: `0xb5460`
- end: `0xb562c`
- name: `Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::InvokeStaticMethod`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xb5370`
- `0xb5390`
- `0xb53b0`
- `0xb53d0`
- `0xb53e0`
- `0xb5400`
- `0xb5420`
- `0xb5440`
- `0xb5450`
- `0xb5460`

## string_xrefs

- `0xb549d`: `CreateRecipe`
- `0xb5563`: `CreateRecipe`
- `0xb54a9`: `DeleteRecipe`
- `0xb557b`: `DeleteRecipe`
- `0xb54cd`: `CreateFormula`
- `0xb55c4`: `CreateFormula`
- `0xb54d9`: `DeleteFormula`
- `0xb55dc`: `DeleteFormula`
- `0xb54f1`: `ValidatePendingWebTemplateExtension`
- `0xb560d`: `ValidatePendingWebTemplateExtension`

## pseudocode

```c

```

## disassembly

```asm
0xb5460  ldarg.3
0xb5461  brtrue.s loc_B546E
0xb5463  ldstr    aProxycontext// "proxyContext"
0xb5468  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb546d  throw
0xb546e  ldarg.0
0xb546f  ldarg.1
0xb5470  ldarg.3
0xb5471  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5476  starg.s  1
0xb5478  ldarg.1
0xb5479  dup
0xb547a  stloc.0
0xb547b  brfalse  loc_B5625
0xb5480  volatile.
0xb5482  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dbd-1
0xb5487  brtrue.s loc_B5503
0xb5489  ldc.i4.s 9
0xb548b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb5490  dup
0xb5491  ldstr    aGetrecipemetad// "GetRecipeMetadata"
0xb5496  ldc.i4.0
0xb5497  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb549c  dup
0xb549d  ldstr    aCreaterecipe// "CreateRecipe"
0xb54a2  ldc.i4.1
0xb54a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54a8  dup
0xb54a9  ldstr    aDeleterecipe// "DeleteRecipe"
0xb54ae  ldc.i4.2
0xb54af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54b4  dup
0xb54b5  ldstr    aGetrecipes// "GetRecipes"
0xb54ba  ldc.i4.3
0xb54bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54c0  dup
0xb54c1  ldstr    aGetformulameta// "GetFormulaMetadata"
0xb54c6  ldc.i4.4
0xb54c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54cc  dup
0xb54cd  ldstr    aCreateformula// "CreateFormula"
0xb54d2  ldc.i4.5
0xb54d3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54d8  dup
0xb54d9  ldstr    aDeleteformula// "DeleteFormula"
0xb54de  ldc.i4.6
0xb54df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54e4  dup
0xb54e5  ldstr    aGetformulas// "GetFormulas"
0xb54ea  ldc.i4.7
0xb54eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54f0  dup
0xb54f1  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb54f6  ldc.i4.8
0xb54f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb54fc  volatile.
0xb54fe  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dbd-1
0xb5503  volatile.
0xb5505  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dbd-1
0xb550a  ldloc.0
0xb550b  ldloca.s 1
0xb550d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb5512  brfalse  loc_B5625
0xb5517  ldloc.1
0xb5518  switch   loc_B5546, loc_B555E, loc_B5576, loc_B558F, loc_B55A7, loc_B55BF, loc_B55D7, loc_B55F0, loc_B5608
0xb5541  br       loc_B5625
0xb5546  ldarg.s  4
0xb5548  ldc.i4.0
0xb5549  stind.i1
0xb554a  ldarg.0
0xb554b  ldstr    aGetrecipemetad// "GetRecipeMetadata"
0xb5550  ldarg.3
0xb5551  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5556  ldarg.2
0xb5557  ldarg.3
0xb5558  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetRecipeMetadata_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb555d  ret
0xb555e  ldarg.s  4
0xb5560  ldc.i4.0
0xb5561  stind.i1
0xb5562  ldarg.0
0xb5563  ldstr    aCreaterecipe// "CreateRecipe"
0xb5568  ldarg.3
0xb5569  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb556e  ldarg.2
0xb556f  ldarg.3
0xb5570  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::CreateRecipe_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5575  ret
0xb5576  ldarg.s  4
0xb5578  ldc.i4.1
0xb5579  stind.i1
0xb557a  ldarg.0
0xb557b  ldstr    aDeleterecipe// "DeleteRecipe"
0xb5580  ldarg.3
0xb5581  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5586  ldarg.2
0xb5587  ldarg.3
0xb5588  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::DeleteRecipe_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb558d  ldnull
0xb558e  ret
0xb558f  ldarg.s  4
0xb5591  ldc.i4.0
0xb5592  stind.i1
0xb5593  ldarg.0
0xb5594  ldstr    aGetrecipes// "GetRecipes"
0xb5599  ldarg.3
0xb559a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb559f  ldarg.2
0xb55a0  ldarg.3
0xb55a1  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetRecipes_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb55a6  ret
0xb55a7  ldarg.s  4
0xb55a9  ldc.i4.0
0xb55aa  stind.i1
0xb55ab  ldarg.0
0xb55ac  ldstr    aGetformulameta// "GetFormulaMetadata"
0xb55b1  ldarg.3
0xb55b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb55b7  ldarg.2
0xb55b8  ldarg.3
0xb55b9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetFormulaMetadata_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb55be  ret
0xb55bf  ldarg.s  4
0xb55c1  ldc.i4.0
0xb55c2  stind.i1
0xb55c3  ldarg.0
0xb55c4  ldstr    aCreateformula// "CreateFormula"
0xb55c9  ldarg.3
0xb55ca  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb55cf  ldarg.2
0xb55d0  ldarg.3
0xb55d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::CreateFormula_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb55d6  ret
0xb55d7  ldarg.s  4
0xb55d9  ldc.i4.1
0xb55da  stind.i1
0xb55db  ldarg.0
0xb55dc  ldstr    aDeleteformula// "DeleteFormula"
0xb55e1  ldarg.3
0xb55e2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb55e7  ldarg.2
0xb55e8  ldarg.3
0xb55e9  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::DeleteFormula_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb55ee  ldnull
0xb55ef  ret
0xb55f0  ldarg.s  4
0xb55f2  ldc.i4.0
0xb55f3  stind.i1
0xb55f4  ldarg.0
0xb55f5  ldstr    aGetformulas// "GetFormulas"
0xb55fa  ldarg.3
0xb55fb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5600  ldarg.2
0xb5601  ldarg.3
0xb5602  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetFormulas_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5607  ret
0xb5608  ldarg.s  4
0xb560a  ldc.i4.0
0xb560b  stind.i1
0xb560c  ldarg.0
0xb560d  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb5612  ldarg.3
0xb5613  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5618  ldarg.2
0xb5619  ldarg.3
0xb561a  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::ValidatePendingWebTemplateExtension_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb561f  box      [mscorlib]System.Boolean
0xb5624  ret
0xb5625  ldarg.1
0xb5626  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb562b  throw
```
