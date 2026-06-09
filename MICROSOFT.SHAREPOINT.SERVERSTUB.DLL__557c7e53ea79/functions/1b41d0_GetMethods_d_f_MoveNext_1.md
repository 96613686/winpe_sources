# <GetMethods>d__f::MoveNext_1

- ea: `0x1b41d0`
- end: `0x1b4d20`
- name: `<GetMethods>d__f::MoveNext_1`
- size: `2896`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0xb5980`
- `0x1b41d0`
- `0x1b4d40`
- `0x1b4da0`

## string_xrefs

- `0x1b43fb`: `CreateRecipe`
- `0x1b442f`: `CreateRecipe`
- `0x1b46a1`: `DeleteRecipe`
- `0x1b46d5`: `DeleteRecipe`
- `0x1b42a8`: `CreateFormula`
- `0x1b42dc`: `CreateFormula`
- `0x1b454e`: `DeleteFormula`
- `0x1b4582`: `DeleteFormula`
- `0x1b4c4e`: `ValidatePendingWebTemplateExtension`
- `0x1b4c82`: `ValidatePendingWebTemplateExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1b41d0  ldarg.0
0x1b41d1  ldfld    int32 <GetMethods>d__f::<>1__state
0x1b41d6  stloc.1
0x1b41d7  ldloc.1
0x1b41d8  switch   loc_1B4212, loc_1B4D13, loc_1B427C, loc_1B43E2, loc_1B4535, loc_1B4688, loc_1B47DB, loc_1B492E, loc_1B4A07, loc_1B4B5B, loc_1B4C35, loc_1B4D0C
0x1b420d  br       loc_1B4D13
0x1b4212  ldarg.0
0x1b4213  ldc.i4.m1
0x1b4214  stfld    int32 <GetMethods>d__f::<>1__state
0x1b4219  ldarg.0
0x1b421a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x1b421f  brtrue.s loc_1B422C
0x1b4221  ldstr    aProxycontext// "proxyContext"
0x1b4226  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b422b  throw
0x1b422c  ldarg.0
0x1b422d  ldarg.0
0x1b422e  ldfld    class Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub <GetMethods>d__f::<>4__this
0x1b4233  ldarg.0
0x1b4234  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x1b4239  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Utilities.WebTemplateExtensions.SPRecipeUtilityServerStub::<>n__FabricatedMethod14(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x1b423e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1b4243  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1b4248  ldarg.0
0x1b4249  ldc.i4.1
0x1b424a  stfld    int32 <GetMethods>d__f::<>1__state
0x1b424f  br.s     loc_1B4283
0x1b4251  ldarg.0
0x1b4252  ldarg.0
0x1b4253  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1b4258  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1b425d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x1b4262  ldarg.0
0x1b4263  ldarg.0
0x1b4264  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x1b4269  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1b426e  ldarg.0
0x1b426f  ldc.i4.2
0x1b4270  stfld    int32 <GetMethods>d__f::<>1__state
0x1b4275  ldc.i4.1
0x1b4276  stloc.0
0x1b4277  leave    loc_1B4D1E
0x1b427c  ldarg.0
0x1b427d  ldc.i4.1
0x1b427e  stfld    int32 <GetMethods>d__f::<>1__state
0x1b4283  ldarg.0
0x1b4284  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x1b4289  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b428e  brtrue.s loc_1B4251
0x1b4290  ldarg.0
0x1b4291  call     instance void <GetMethods>d__f::<>m__Finally13()
0x1b4296  ldarg.0
0x1b4297  ldarg.0
0x1b4298  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b429d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42a2  ldarg.0
0x1b42a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42a8  ldstr    aCreateformula// "CreateFormula"
0x1b42ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b42b2  ldarg.0
0x1b42b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42b8  ldc.i4.1
0x1b42b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b42be  ldarg.0
0x1b42bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42c4  ldc.i4.0
0x1b42c5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b42ca  ldarg.0
0x1b42cb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42d0  ldc.i4.8
0x1b42d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b42d6  ldarg.0
0x1b42d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42dc  ldstr    aCreateformula// "CreateFormula"
0x1b42e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b42e6  ldarg.0
0x1b42e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42ec  ldc.i4.0
0x1b42ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b42f2  ldarg.0
0x1b42f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b42f8  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaMetadata
0x1b42fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b4302  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b4307  ldarg.0
0x1b4308  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b430d  ldc.i4.2
0x1b430e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b4313  ldarg.0
0x1b4314  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b4319  ldc.i4.0
0x1b431a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b431f  ldarg.0
0x1b4320  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b4325  ldc.i4.0
0x1b4326  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1b432b  ldarg.0
0x1b432c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b4331  ldc.i4.0
0x1b4332  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1b4337  ldarg.0
0x1b4338  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b433d  ldc.i4.1
0x1b433e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1b4343  ldarg.0
0x1b4344  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x1b4349  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b434e  ldarg.0
0x1b434f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b4354  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1b4359  ldarg.0
0x1b435a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1b435f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b4364  ldarg.0
0x1b4365  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b436a  ldstr    aInfo// "info"
0x1b436f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1b4374  ldarg.0
0x1b4375  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b437a  ldc.i4.0
0x1b437b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1b4380  ldarg.0
0x1b4381  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b4386  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.FormulaCreationInfo
0x1b438b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b4390  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1b4395  ldarg.0
0x1b4396  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b439b  ldc.i4.2
0x1b439c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b43a1  ldarg.0
0x1b43a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b43a7  ldc.i4.0
0x1b43a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1b43ad  ldarg.0
0x1b43ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b43b3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b43b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1b43bd  ldarg.0
0x1b43be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal1
0x1b43c3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1b43c8  ldarg.0
0x1b43c9  ldarg.0
0x1b43ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b43cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1b43d4  ldarg.0
0x1b43d5  ldc.i4.3
0x1b43d6  stfld    int32 <GetMethods>d__f::<>1__state
0x1b43db  ldc.i4.1
0x1b43dc  stloc.0
0x1b43dd  leave    loc_1B4D1E
0x1b43e2  ldarg.0
0x1b43e3  ldc.i4.m1
0x1b43e4  stfld    int32 <GetMethods>d__f::<>1__state
0x1b43e9  ldarg.0
0x1b43ea  ldarg.0
0x1b43eb  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b43f0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b43f5  ldarg.0
0x1b43f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b43fb  ldstr    aCreaterecipe// "CreateRecipe"
0x1b4400  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b4405  ldarg.0
0x1b4406  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b440b  ldc.i4.1
0x1b440c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b4411  ldarg.0
0x1b4412  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4417  ldc.i4.0
0x1b4418  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b441d  ldarg.0
0x1b441e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4423  ldc.i4.8
0x1b4424  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b4429  ldarg.0
0x1b442a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b442f  ldstr    aCreaterecipe// "CreateRecipe"
0x1b4434  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b4439  ldarg.0
0x1b443a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b443f  ldc.i4.0
0x1b4440  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b4445  ldarg.0
0x1b4446  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b444b  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeMetadata
0x1b4450  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b4455  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b445a  ldarg.0
0x1b445b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4460  ldc.i4.2
0x1b4461  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b4466  ldarg.0
0x1b4467  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b446c  ldc.i4.0
0x1b446d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b4472  ldarg.0
0x1b4473  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4478  ldc.i4.1
0x1b4479  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1b447e  ldarg.0
0x1b447f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4484  ldc.i4.0
0x1b4485  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1b448a  ldarg.0
0x1b448b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b4490  ldc.i4.1
0x1b4491  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1b4496  ldarg.0
0x1b4497  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal2
0x1b449c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b44a1  ldarg.0
0x1b44a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b44a7  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1b44ac  ldarg.0
0x1b44ad  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1b44b2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44b7  ldarg.0
0x1b44b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44bd  ldstr    aInfo// "info"
0x1b44c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1b44c7  ldarg.0
0x1b44c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44cd  ldc.i4.1
0x1b44ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1b44d3  ldarg.0
0x1b44d4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44d9  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WebTemplateExtensions.RecipeCreationInfo
0x1b44de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b44e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1b44e8  ldarg.0
0x1b44e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44ee  ldc.i4.2
0x1b44ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b44f4  ldarg.0
0x1b44f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b44fa  ldc.i4.0
0x1b44fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1b4500  ldarg.0
0x1b4501  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b4506  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b450b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1b4510  ldarg.0
0x1b4511  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x1b4516  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1b451b  ldarg.0
0x1b451c  ldarg.0
0x1b451d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x1b4522  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x1b4527  ldarg.0
0x1b4528  ldc.i4.4
0x1b4529  stfld    int32 <GetMethods>d__f::<>1__state
0x1b452e  ldc.i4.1
0x1b452f  stloc.0
0x1b4530  leave    loc_1B4D1E
0x1b4535  ldarg.0
0x1b4536  ldc.i4.m1
0x1b4537  stfld    int32 <GetMethods>d__f::<>1__state
0x1b453c  ldarg.0
0x1b453d  ldarg.0
0x1b453e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1b4543  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b4548  ldarg.0
0x1b4549  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b454e  ldstr    aDeleteformula// "DeleteFormula"
0x1b4553  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1b4558  ldarg.0
0x1b4559  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b455e  ldc.i4.1
0x1b455f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1b4564  ldarg.0
0x1b4565  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b456a  ldc.i4.0
0x1b456b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1b4570  ldarg.0
0x1b4571  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b4576  ldc.i4.8
0x1b4577  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1b457c  ldarg.0
0x1b457d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b4582  ldstr    aDeleteformula// "DeleteFormula"
0x1b4587  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1b458c  ldarg.0
0x1b458d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b4592  ldc.i4.0
0x1b4593  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1b4598  ldarg.0
0x1b4599  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b459e  ldtoken  [mscorlib]System.Void
0x1b45a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b45a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1b45ad  ldarg.0
0x1b45ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b45b3  ldc.i4.0
0x1b45b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1b45b9  ldarg.0
0x1b45ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
0x1b45bf  ldc.i4.0
0x1b45c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1b45c5  ldarg.0
0x1b45c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal4
  ... truncated ...
```
