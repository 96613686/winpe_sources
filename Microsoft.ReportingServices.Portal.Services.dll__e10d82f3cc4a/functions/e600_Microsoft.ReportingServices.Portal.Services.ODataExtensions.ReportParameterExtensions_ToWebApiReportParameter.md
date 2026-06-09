# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ReportParameterExtensions::ToWebApiReportParameter

- ea: `0xe600`
- end: `0xe789`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ReportParameterExtensions::ToWebApiReportParameter`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1d380`
- `0x1d3a0`

## callees

- `0xe600`
- `0xe790`
- `0x21f10`

## string_xrefs

- `0xe609`: `itemParameter`

## pseudocode

```c

```

## disassembly

```asm
0xe600  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xe605  stloc.0
0xe606  ldarg.0
0xe607  brtrue.s loc_E614
0xe609  ldstr    aItemparameter// "itemParameter"
0xe60e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe613  throw
0xe614  ldloc.0
0xe615  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType
0xe61a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe61f  ldarg.0
0xe620  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ParameterTypeName()
0xe625  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xe62a  unbox.any [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType
0xe62f  stfld    valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType <>c__DisplayClass0_0::reportParameterType
0xe634  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::.ctor()
0xe639  stloc.1
0xe63a  ldloc.1
0xe63b  ldarg.0
0xe63c  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_Name()
0xe641  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_Name(string)
0xe646  ldloc.1
0xe647  ldloc.0
0xe648  ldfld    valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType <>c__DisplayClass0_0::reportParameterType
0xe64d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ParameterType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType)
0xe652  ldloc.1
0xe653  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterState
0xe658  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe65d  ldarg.0
0xe65e  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ParameterStateName()
0xe663  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xe668  unbox.any [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterState
0xe66d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ParameterState(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterState)
0xe672  ldloc.1
0xe673  ldarg.0
0xe674  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ValidValues()
0xe679  brtrue.s loc_E685
0xe67b  ldc.i4.0
0xe67c  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue
0xe681  stloc.2
0xe682  ldloc.2
0xe683  br.s     loc_E69C
0xe685  ldarg.0
0xe686  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ValidValues()
0xe68b  ldloc.0
0xe68c  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue <>c__DisplayClass0_0::<ToWebApiReportParameter>b__0(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue validValue)
0xe692  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue>::.ctor(object, native int)
0xe697  call     T0x2B0000C4
0xe69c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ValidValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue>)
0xe6a1  ldloc.1
0xe6a2  ldarg.0
0xe6a3  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ValidValues()
0xe6a8  ldnull
0xe6a9  ceq
0xe6ab  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ValidValuesIsNull(bool)
0xe6b0  ldloc.1
0xe6b1  ldarg.0
0xe6b2  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_Nullable()
0xe6b7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_Nullable(bool)
0xe6bc  ldloc.1
0xe6bd  ldarg.0
0xe6be  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_AllowBlank()
0xe6c3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_AllowBlank(bool)
0xe6c8  ldloc.1
0xe6c9  ldarg.0
0xe6ca  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_MultiValue()
0xe6cf  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_MultiValue(bool)
0xe6d4  ldloc.1
0xe6d5  ldarg.0
0xe6d6  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_Prompt()
0xe6db  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_Prompt(string)
0xe6e0  ldloc.1
0xe6e1  ldarg.0
0xe6e2  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_PromptUser()
0xe6e7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_PromptUser(bool)
0xe6ec  ldloc.1
0xe6ed  ldarg.0
0xe6ee  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_PromptUser()
0xe6f3  ldarg.0
0xe6f4  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_Prompt()
0xe6f9  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterVisibility Microsoft.ReportingServices.Portal.Services.ODataExtensions.ReportParameterExtensions::GetVisiblity(bool promptUser, string prompt)
0xe6fe  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ParameterVisibility(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterVisibility)
0xe703  ldloc.1
0xe704  ldarg.0
0xe705  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_QueryParameter()
0xe70a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_QueryParameter(bool)
0xe70f  ldloc.1
0xe710  ldarg.0
0xe711  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_DefaultValuesQueryBased()
0xe716  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_DefaultValuesQueryBased(bool)
0xe71b  ldloc.1
0xe71c  ldarg.0
0xe71d  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ValidValuesQueryBased()
0xe722  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ValidValuesQueryBased(bool)
0xe727  ldloc.1
0xe728  ldarg.0
0xe729  callvirt instance string[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_Dependencies()
0xe72e  dup
0xe72f  brtrue.s loc_E738
0xe731  pop
0xe732  ldc.i4.0
0xe733  newarr   [mscorlib]System.String
0xe738  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_Dependencies(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xe73d  ldloc.1
0xe73e  ldarg.0
0xe73f  callvirt instance string[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_DefaultValues()
0xe744  brtrue.s loc_E750
0xe746  ldc.i4.0
0xe747  newarr   [mscorlib]System.String
0xe74c  stloc.3
0xe74d  ldloc.3
0xe74e  br.s     loc_E767
0xe750  ldarg.0
0xe751  callvirt instance string[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_DefaultValues()
0xe756  ldloc.0
0xe757  ldftn    instance string <>c__DisplayClass0_0::<ToWebApiReportParameter>b__1(string defaultValue)
0xe75d  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xe762  call     T0x2B00006B
0xe767  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_DefaultValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xe76c  ldloc.1
0xe76d  ldarg.0
0xe76e  callvirt instance string[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_DefaultValues()
0xe773  ldnull
0xe774  ceq
0xe776  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_DefaultValuesIsNull(bool)
0xe77b  ldloc.1
0xe77c  ldarg.0
0xe77d  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter::get_ErrorMessage()
0xe782  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition::set_ErrorMessage(string)
0xe787  ldloc.1
0xe788  ret
```
