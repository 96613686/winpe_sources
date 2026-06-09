# Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::InvokeStaticMethod_0

- ea: `0xb5780`
- end: `0xb594c`
- name: `Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::InvokeStaticMethod_0`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xb5690`
- `0xb56b0`
- `0xb56d0`
- `0xb56f0`
- `0xb5700`
- `0xb5720`
- `0xb5740`
- `0xb5760`
- `0xb5770`
- `0xb5780`

## string_xrefs

- `0xb57bd`: `CreateRecipe`
- `0xb5883`: `CreateRecipe`
- `0xb57c9`: `DeleteRecipe`
- `0xb589b`: `DeleteRecipe`
- `0xb57ed`: `CreateFormula`
- `0xb58e4`: `CreateFormula`
- `0xb57f9`: `DeleteFormula`
- `0xb58fc`: `DeleteFormula`
- `0xb5811`: `ValidatePendingWebTemplateExtension`
- `0xb592d`: `ValidatePendingWebTemplateExtension`

## pseudocode

```c

```

## disassembly

```asm
0xb5780  ldarg.3
0xb5781  brtrue.s loc_B578E
0xb5783  ldstr    aProxycontext// "proxyContext"
0xb5788  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb578d  throw
0xb578e  ldarg.0
0xb578f  ldarg.1
0xb5790  ldarg.3
0xb5791  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5796  starg.s  1
0xb5798  ldarg.1
0xb5799  dup
0xb579a  stloc.0
0xb579b  brfalse  loc_B5945
0xb57a0  volatile.
0xb57a2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dca-1
0xb57a7  brtrue.s loc_B5823
0xb57a9  ldc.i4.s 9
0xb57ab  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb57b0  dup
0xb57b1  ldstr    aGetrecipemetad// "GetRecipeMetadata"
0xb57b6  ldc.i4.0
0xb57b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57bc  dup
0xb57bd  ldstr    aCreaterecipe// "CreateRecipe"
0xb57c2  ldc.i4.1
0xb57c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57c8  dup
0xb57c9  ldstr    aDeleterecipe// "DeleteRecipe"
0xb57ce  ldc.i4.2
0xb57cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57d4  dup
0xb57d5  ldstr    aGetrecipes// "GetRecipes"
0xb57da  ldc.i4.3
0xb57db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57e0  dup
0xb57e1  ldstr    aGetformulameta// "GetFormulaMetadata"
0xb57e6  ldc.i4.4
0xb57e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57ec  dup
0xb57ed  ldstr    aCreateformula// "CreateFormula"
0xb57f2  ldc.i4.5
0xb57f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb57f8  dup
0xb57f9  ldstr    aDeleteformula// "DeleteFormula"
0xb57fe  ldc.i4.6
0xb57ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5804  dup
0xb5805  ldstr    aGetformulas// "GetFormulas"
0xb580a  ldc.i4.7
0xb580b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb5810  dup
0xb5811  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb5816  ldc.i4.8
0xb5817  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb581c  volatile.
0xb581e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dca-1
0xb5823  volatile.
0xb5825  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001dca-1
0xb582a  ldloc.0
0xb582b  ldloca.s 1
0xb582d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb5832  brfalse  loc_B5945
0xb5837  ldloc.1
0xb5838  switch   loc_B5866, loc_B587E, loc_B5896, loc_B58AF, loc_B58C7, loc_B58DF, loc_B58F7, loc_B5910, loc_B5928
0xb5861  br       loc_B5945
0xb5866  ldarg.s  4
0xb5868  ldc.i4.0
0xb5869  stind.i1
0xb586a  ldarg.0
0xb586b  ldstr    aGetrecipemetad// "GetRecipeMetadata"
0xb5870  ldarg.3
0xb5871  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5876  ldarg.2
0xb5877  ldarg.3
0xb5878  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetRecipeMetadata_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb587d  ret
0xb587e  ldarg.s  4
0xb5880  ldc.i4.0
0xb5881  stind.i1
0xb5882  ldarg.0
0xb5883  ldstr    aCreaterecipe// "CreateRecipe"
0xb5888  ldarg.3
0xb5889  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb588e  ldarg.2
0xb588f  ldarg.3
0xb5890  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::CreateRecipe_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5895  ret
0xb5896  ldarg.s  4
0xb5898  ldc.i4.1
0xb5899  stind.i1
0xb589a  ldarg.0
0xb589b  ldstr    aDeleterecipe// "DeleteRecipe"
0xb58a0  ldarg.3
0xb58a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb58a6  ldarg.2
0xb58a7  ldarg.3
0xb58a8  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::DeleteRecipe_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb58ad  ldnull
0xb58ae  ret
0xb58af  ldarg.s  4
0xb58b1  ldc.i4.0
0xb58b2  stind.i1
0xb58b3  ldarg.0
0xb58b4  ldstr    aGetrecipes// "GetRecipes"
0xb58b9  ldarg.3
0xb58ba  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb58bf  ldarg.2
0xb58c0  ldarg.3
0xb58c1  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetRecipes_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb58c6  ret
0xb58c7  ldarg.s  4
0xb58c9  ldc.i4.0
0xb58ca  stind.i1
0xb58cb  ldarg.0
0xb58cc  ldstr    aGetformulameta// "GetFormulaMetadata"
0xb58d1  ldarg.3
0xb58d2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb58d7  ldarg.2
0xb58d8  ldarg.3
0xb58d9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetFormulaMetadata_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb58de  ret
0xb58df  ldarg.s  4
0xb58e1  ldc.i4.0
0xb58e2  stind.i1
0xb58e3  ldarg.0
0xb58e4  ldstr    aCreateformula// "CreateFormula"
0xb58e9  ldarg.3
0xb58ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb58ef  ldarg.2
0xb58f0  ldarg.3
0xb58f1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::CreateFormula_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb58f6  ret
0xb58f7  ldarg.s  4
0xb58f9  ldc.i4.1
0xb58fa  stind.i1
0xb58fb  ldarg.0
0xb58fc  ldstr    aDeleteformula// "DeleteFormula"
0xb5901  ldarg.3
0xb5902  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5907  ldarg.2
0xb5908  ldarg.3
0xb5909  call     void Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::DeleteFormula_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb590e  ldnull
0xb590f  ret
0xb5910  ldarg.s  4
0xb5912  ldc.i4.0
0xb5913  stind.i1
0xb5914  ldarg.0
0xb5915  ldstr    aGetformulas// "GetFormulas"
0xb591a  ldarg.3
0xb591b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5920  ldarg.2
0xb5921  ldarg.3
0xb5922  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::GetFormulas_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5927  ret
0xb5928  ldarg.s  4
0xb592a  ldc.i4.0
0xb592b  stind.i1
0xb592c  ldarg.0
0xb592d  ldstr    aValidatependin// "ValidatePendingWebTemplateExtension"
0xb5932  ldarg.3
0xb5933  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5938  ldarg.2
0xb5939  ldarg.3
0xb593a  call     bool Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::ValidatePendingWebTemplateExtension_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb593f  box      [mscorlib]System.Boolean
0xb5944  ret
0xb5945  ldarg.1
0xb5946  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb594b  throw
```
