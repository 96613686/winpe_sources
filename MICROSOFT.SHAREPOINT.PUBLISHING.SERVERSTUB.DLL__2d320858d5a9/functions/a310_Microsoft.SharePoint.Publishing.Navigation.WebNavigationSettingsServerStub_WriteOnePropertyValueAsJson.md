# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0xa310`
- end: `0xa4b0`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa310`

## string_xrefs

- `0xa342`: `CreateFriendlyUrlsForNewPages`
- `0xa3e5`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa310  ldc.i4.0
0xa311  stloc.0
0xa312  ldarg.2
0xa313  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa318  stloc.1
0xa319  ldloc.1
0xa31a  brtrue.s loc_A327
0xa31c  ldstr    aTarget// "target"
0xa321  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa326  throw
0xa327  ldarg.3
0xa328  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xa32d  dup
0xa32e  stloc.2
0xa32f  brfalse  loc_A4A2
0xa334  ldloc.2
0xa335  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa33a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa33f  brtrue.s loc_A373
0xa341  ldloc.2
0xa342  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa347  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa34c  brtrue.s loc_A3BC
0xa34e  ldloc.2
0xa34f  ldstr    aCurrentnavigat// "CurrentNavigation"
0xa354  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa359  brtrue   loc_A406
0xa35e  ldloc.2
0xa35f  ldstr    aGlobalnavigati// "GlobalNavigation"
0xa364  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa369  brtrue   loc_A454
0xa36e  br       loc_A4A2
0xa373  ldarg.3
0xa374  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa379  stloc.3
0xa37a  ldloca.s 3
0xa37c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa381  brfalse.s loc_A39A
0xa383  ldarg.3
0xa384  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa389  stloc.s  4
0xa38b  ldloca.s 4
0xa38d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa392  brtrue.s loc_A39A
0xa394  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa399  throw
0xa39a  ldarg.0
0xa39b  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa3a0  ldarg.s  4
0xa3a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3a7  ldc.i4.1
0xa3a8  stloc.0
0xa3a9  ldarg.1
0xa3aa  ldloc.1
0xa3ab  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_AddNewPagesToNavigation()
0xa3b0  ldarg.s  4
0xa3b2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3b7  br       loc_A4AE
0xa3bc  ldarg.3
0xa3bd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa3c2  stloc.s  5
0xa3c4  ldloca.s 5
0xa3c6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa3cb  brfalse.s loc_A3E4
0xa3cd  ldarg.3
0xa3ce  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa3d3  stloc.s  6
0xa3d5  ldloca.s 6
0xa3d7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa3dc  brtrue.s loc_A3E4
0xa3de  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa3e3  throw
0xa3e4  ldarg.0
0xa3e5  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa3ea  ldarg.s  4
0xa3ec  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3f1  ldc.i4.1
0xa3f2  stloc.0
0xa3f3  ldarg.1
0xa3f4  ldloc.1
0xa3f5  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_CreateFriendlyUrlsForNewPages()
0xa3fa  ldarg.s  4
0xa3fc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa401  br       loc_A4AE
0xa406  ldarg.3
0xa407  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa40c  stloc.s  7
0xa40e  ldloca.s 7
0xa410  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa415  brfalse.s loc_A42E
0xa417  ldarg.3
0xa418  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa41d  stloc.s  8
0xa41f  ldloca.s 8
0xa421  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa426  brfalse.s loc_A42E
0xa428  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa42d  throw
0xa42e  ldarg.0
0xa42f  ldstr    aCurrentnavigat// "CurrentNavigation"
0xa434  ldarg.s  4
0xa436  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa43b  ldc.i4.1
0xa43c  stloc.0
0xa43d  ldarg.0
0xa43e  ldarg.1
0xa43f  ldloc.1
0xa440  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_CurrentNavigation()
0xa445  ldarg.3
0xa446  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xa44b  ldarg.s  4
0xa44d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa452  br.s     loc_A4AE
0xa454  ldarg.3
0xa455  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa45a  stloc.s  9
0xa45c  ldloca.s 9
0xa45e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa463  brfalse.s loc_A47C
0xa465  ldarg.3
0xa466  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa46b  stloc.s  0xA
0xa46d  ldloca.s 0xA
0xa46f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa474  brfalse.s loc_A47C
0xa476  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa47b  throw
0xa47c  ldarg.0
0xa47d  ldstr    aGlobalnavigati// "GlobalNavigation"
0xa482  ldarg.s  4
0xa484  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa489  ldc.i4.1
0xa48a  stloc.0
0xa48b  ldarg.0
0xa48c  ldarg.1
0xa48d  ldloc.1
0xa48e  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_GlobalNavigation()
0xa493  ldarg.3
0xa494  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xa499  ldarg.s  4
0xa49b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4a0  br.s     loc_A4AE
0xa4a2  ldarg.0
0xa4a3  ldarg.1
0xa4a4  ldarg.2
0xa4a5  ldarg.3
0xa4a6  ldarg.s  4
0xa4a8  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4ad  stloc.0
0xa4ae  ldloc.0
0xa4af  ret
```
