# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::WriteOnePropertyValueAsJson

- ea: `0xb760`
- end: `0xb89f`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::WriteOnePropertyValueAsJson`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb760`

## pseudocode

```c

```

## disassembly

```asm
0xb760  ldc.i4.0
0xb761  stloc.0
0xb762  ldarg.2
0xb763  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb768  stloc.1
0xb769  ldloc.1
0xb76a  brtrue.s loc_B777
0xb76c  ldstr    aTarget// "target"
0xb771  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb776  throw
0xb777  ldarg.3
0xb778  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xb77d  dup
0xb77e  stloc.2
0xb77f  brfalse  loc_B891
0xb784  ldloc.2
0xb785  ldstr    aEnddate// "EndDate"
0xb78a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb78f  brtrue.s loc_B7B3
0xb791  ldloc.2
0xb792  ldstr    aListitem// "ListItem"
0xb797  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb79c  brtrue.s loc_B7FC
0xb79e  ldloc.2
0xb79f  ldstr    aStartdate// "StartDate"
0xb7a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb7a9  brtrue   loc_B84A
0xb7ae  br       loc_B891
0xb7b3  ldarg.3
0xb7b4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb7b9  stloc.3
0xb7ba  ldloca.s 3
0xb7bc  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xb7c1  brfalse.s loc_B7DA
0xb7c3  ldarg.3
0xb7c4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb7c9  stloc.s  4
0xb7cb  ldloca.s 4
0xb7cd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xb7d2  brtrue.s loc_B7DA
0xb7d4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xb7d9  throw
0xb7da  ldarg.0
0xb7db  ldstr    aEnddate// "EndDate"
0xb7e0  ldarg.s  4
0xb7e2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb7e7  ldc.i4.1
0xb7e8  stloc.0
0xb7e9  ldarg.1
0xb7ea  ldloc.1
0xb7eb  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_EndDate()
0xb7f0  ldarg.s  4
0xb7f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb7f7  br       loc_B89D
0xb7fc  ldarg.3
0xb7fd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb802  stloc.s  5
0xb804  ldloca.s 5
0xb806  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xb80b  brfalse.s loc_B824
0xb80d  ldarg.3
0xb80e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb813  stloc.s  6
0xb815  ldloca.s 6
0xb817  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xb81c  brfalse.s loc_B824
0xb81e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xb823  throw
0xb824  ldarg.0
0xb825  ldstr    aListitem// "ListItem"
0xb82a  ldarg.s  4
0xb82c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb831  ldc.i4.1
0xb832  stloc.0
0xb833  ldarg.0
0xb834  ldarg.1
0xb835  ldloc.1
0xb836  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_ListItem()
0xb83b  ldarg.3
0xb83c  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xb841  ldarg.s  4
0xb843  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb848  br.s     loc_B89D
0xb84a  ldarg.3
0xb84b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb850  stloc.s  7
0xb852  ldloca.s 7
0xb854  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xb859  brfalse.s loc_B872
0xb85b  ldarg.3
0xb85c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xb861  stloc.s  8
0xb863  ldloca.s 8
0xb865  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xb86a  brtrue.s loc_B872
0xb86c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xb871  throw
0xb872  ldarg.0
0xb873  ldstr    aStartdate// "StartDate"
0xb878  ldarg.s  4
0xb87a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb87f  ldc.i4.1
0xb880  stloc.0
0xb881  ldarg.1
0xb882  ldloc.1
0xb883  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_StartDate()
0xb888  ldarg.s  4
0xb88a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb88f  br.s     loc_B89D
0xb891  ldarg.0
0xb892  ldarg.1
0xb893  ldarg.2
0xb894  ldarg.3
0xb895  ldarg.s  4
0xb897  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb89c  stloc.0
0xb89d  ldloc.0
0xb89e  ret
```
