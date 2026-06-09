# Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub::WriteOnePropertyValueAsJson

- ea: `0xae20`
- end: `0xaf58`
- name: `Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub::WriteOnePropertyValueAsJson`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xae20`

## pseudocode

```c

```

## disassembly

```asm
0xae20  ldc.i4.0
0xae21  stloc.0
0xae22  ldarg.2
0xae23  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime
0xae28  stloc.1
0xae29  ldloc.1
0xae2a  brtrue.s loc_AE37
0xae2c  ldstr    aTarget// "target"
0xae31  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xae36  throw
0xae37  ldarg.3
0xae38  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xae3d  dup
0xae3e  stloc.2
0xae3f  brfalse  loc_AF4A
0xae44  ldloc.2
0xae45  ldstr    aLocation// "Location"
0xae4a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae4f  brtrue.s loc_AE73
0xae51  ldloc.2
0xae52  ldstr    aTime// "Time"
0xae57  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae5c  brtrue.s loc_AEBC
0xae5e  ldloc.2
0xae5f  ldstr    aUtcoffset// "UtcOffset"
0xae64  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae69  brtrue   loc_AF03
0xae6e  br       loc_AF4A
0xae73  ldarg.3
0xae74  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xae79  stloc.3
0xae7a  ldloca.s 3
0xae7c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xae81  brfalse.s loc_AE9A
0xae83  ldarg.3
0xae84  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xae89  stloc.s  4
0xae8b  ldloca.s 4
0xae8d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xae92  brtrue.s loc_AE9A
0xae94  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xae99  throw
0xae9a  ldarg.0
0xae9b  ldstr    aLocation// "Location"
0xaea0  ldarg.s  4
0xaea2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaea7  ldc.i4.1
0xaea8  stloc.0
0xaea9  ldarg.1
0xaeaa  ldloc.1
0xaeab  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_Location()
0xaeb0  ldarg.s  4
0xaeb2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeb7  br       loc_AF56
0xaebc  ldarg.3
0xaebd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaec2  stloc.s  5
0xaec4  ldloca.s 5
0xaec6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaecb  brfalse.s loc_AEE4
0xaecd  ldarg.3
0xaece  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaed3  stloc.s  6
0xaed5  ldloca.s 6
0xaed7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaedc  brtrue.s loc_AEE4
0xaede  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaee3  throw
0xaee4  ldarg.0
0xaee5  ldstr    aTime// "Time"
0xaeea  ldarg.s  4
0xaeec  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaef1  ldc.i4.1
0xaef2  stloc.0
0xaef3  ldarg.1
0xaef4  ldloc.1
0xaef5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_Time()
0xaefa  ldarg.s  4
0xaefc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf01  br.s     loc_AF56
0xaf03  ldarg.3
0xaf04  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaf09  stloc.s  7
0xaf0b  ldloca.s 7
0xaf0d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaf12  brfalse.s loc_AF2B
0xaf14  ldarg.3
0xaf15  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaf1a  stloc.s  8
0xaf1c  ldloca.s 8
0xaf1e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaf23  brtrue.s loc_AF2B
0xaf25  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaf2a  throw
0xaf2b  ldarg.0
0xaf2c  ldstr    aUtcoffset// "UtcOffset"
0xaf31  ldarg.s  4
0xaf33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf38  ldc.i4.1
0xaf39  stloc.0
0xaf3a  ldarg.1
0xaf3b  ldloc.1
0xaf3c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PrimaryCityTime::get_UtcOffset()
0xaf41  ldarg.s  4
0xaf43  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf48  br.s     loc_AF56
0xaf4a  ldarg.0
0xaf4b  ldarg.1
0xaf4c  ldarg.2
0xaf4d  ldarg.3
0xaf4e  ldarg.s  4
0xaf50  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf55  stloc.0
0xaf56  ldloc.0
0xaf57  ret
```
