# Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub::WriteOnePropertyValueAsJson

- ea: `0x95a0`
- end: `0x96d8`
- name: `Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettingsServerStub::WriteOnePropertyValueAsJson`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x95a0`

## pseudocode

```c

```

## disassembly

```asm
0x95a0  ldc.i4.0
0x95a1  stloc.0
0x95a2  ldarg.2
0x95a3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings
0x95a8  stloc.1
0x95a9  ldloc.1
0x95aa  brtrue.s loc_95B7
0x95ac  ldstr    aTarget// "target"
0x95b1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x95b6  throw
0x95b7  ldarg.3
0x95b8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x95bd  dup
0x95be  stloc.2
0x95bf  brfalse  loc_96CA
0x95c4  ldloc.2
0x95c5  ldstr    aSource// "Source"
0x95ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95cf  brtrue.s loc_95F3
0x95d1  ldloc.2
0x95d2  ldstr    aTermsetid// "TermSetId"
0x95d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95dc  brtrue.s loc_963C
0x95de  ldloc.2
0x95df  ldstr    aTermstoreid// "TermStoreId"
0x95e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95e9  brtrue   loc_9683
0x95ee  br       loc_96CA
0x95f3  ldarg.3
0x95f4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x95f9  stloc.3
0x95fa  ldloca.s 3
0x95fc  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9601  brfalse.s loc_961A
0x9603  ldarg.3
0x9604  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9609  stloc.s  4
0x960b  ldloca.s 4
0x960d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9612  brtrue.s loc_961A
0x9614  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x9619  throw
0x961a  ldarg.0
0x961b  ldstr    aSource// "Source"
0x9620  ldarg.s  4
0x9622  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9627  ldc.i4.1
0x9628  stloc.0
0x9629  ldarg.1
0x962a  ldloc.1
0x962b  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSource [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_Source()
0x9630  ldarg.s  4
0x9632  call     T0x2B000023
0x9637  br       loc_96D6
0x963c  ldarg.3
0x963d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9642  stloc.s  5
0x9644  ldloca.s 5
0x9646  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x964b  brfalse.s loc_9664
0x964d  ldarg.3
0x964e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9653  stloc.s  6
0x9655  ldloca.s 6
0x9657  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x965c  brtrue.s loc_9664
0x965e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x9663  throw
0x9664  ldarg.0
0x9665  ldstr    aTermsetid// "TermSetId"
0x966a  ldarg.s  4
0x966c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9671  ldc.i4.1
0x9672  stloc.0
0x9673  ldarg.1
0x9674  ldloc.1
0x9675  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_TermSetId()
0x967a  ldarg.s  4
0x967c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9681  br.s     loc_96D6
0x9683  ldarg.3
0x9684  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9689  stloc.s  7
0x968b  ldloca.s 7
0x968d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9692  brfalse.s loc_96AB
0x9694  ldarg.3
0x9695  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x969a  stloc.s  8
0x969c  ldloca.s 8
0x969e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x96a3  brtrue.s loc_96AB
0x96a5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x96aa  throw
0x96ab  ldarg.0
0x96ac  ldstr    aTermstoreid// "TermStoreId"
0x96b1  ldarg.s  4
0x96b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96b8  ldc.i4.1
0x96b9  stloc.0
0x96ba  ldarg.1
0x96bb  ldloc.1
0x96bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings::get_TermStoreId()
0x96c1  ldarg.s  4
0x96c3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96c8  br.s     loc_96D6
0x96ca  ldarg.0
0x96cb  ldarg.1
0x96cc  ldarg.2
0x96cd  ldarg.3
0x96ce  ldarg.s  4
0x96d0  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96d5  stloc.0
0x96d6  ldloc.0
0x96d7  ret
```
