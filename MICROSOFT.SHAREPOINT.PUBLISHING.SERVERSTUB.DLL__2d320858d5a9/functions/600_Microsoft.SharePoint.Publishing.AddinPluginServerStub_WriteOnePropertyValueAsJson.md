# Microsoft.SharePoint.Publishing.AddinPluginServerStub::WriteOnePropertyValueAsJson

- ea: `0x600`
- end: `0x738`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::WriteOnePropertyValueAsJson`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x600`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldc.i4.0
0x601  stloc.0
0x602  ldarg.2
0x603  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x608  stloc.1
0x609  ldloc.1
0x60a  brtrue.s loc_617
0x60c  ldstr    aTarget// "target"
0x611  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x616  throw
0x617  ldarg.3
0x618  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x61d  dup
0x61e  stloc.2
0x61f  brfalse  loc_72A
0x624  ldloc.2
0x625  ldstr    aDescription// "Description"
0x62a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f  brtrue.s loc_653
0x631  ldloc.2
0x632  ldstr    aMarkup// "Markup"
0x637  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63c  brtrue.s loc_69C
0x63e  ldloc.2
0x63f  ldstr    aTitle// "Title"
0x644  call     bool [mscorlib]System.String::op_Equality(string, string)
0x649  brtrue   loc_6E3
0x64e  br       loc_72A
0x653  ldarg.3
0x654  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x659  stloc.3
0x65a  ldloca.s 3
0x65c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x661  brfalse.s loc_67A
0x663  ldarg.3
0x664  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x669  stloc.s  4
0x66b  ldloca.s 4
0x66d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x672  brtrue.s loc_67A
0x674  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x679  throw
0x67a  ldarg.0
0x67b  ldstr    aDescription// "Description"
0x680  ldarg.s  4
0x682  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x687  ldc.i4.1
0x688  stloc.0
0x689  ldarg.1
0x68a  ldloc.1
0x68b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Description()
0x690  ldarg.s  4
0x692  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x697  br       loc_736
0x69c  ldarg.3
0x69d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6a2  stloc.s  5
0x6a4  ldloca.s 5
0x6a6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6ab  brfalse.s loc_6C4
0x6ad  ldarg.3
0x6ae  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6b3  stloc.s  6
0x6b5  ldloca.s 6
0x6b7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6bc  brtrue.s loc_6C4
0x6be  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6c3  throw
0x6c4  ldarg.0
0x6c5  ldstr    aMarkup// "Markup"
0x6ca  ldarg.s  4
0x6cc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d1  ldc.i4.1
0x6d2  stloc.0
0x6d3  ldarg.1
0x6d4  ldloc.1
0x6d5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Markup()
0x6da  ldarg.s  4
0x6dc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e1  br.s     loc_736
0x6e3  ldarg.3
0x6e4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6e9  stloc.s  7
0x6eb  ldloca.s 7
0x6ed  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6f2  brfalse.s loc_70B
0x6f4  ldarg.3
0x6f5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6fa  stloc.s  8
0x6fc  ldloca.s 8
0x6fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x703  brtrue.s loc_70B
0x705  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x70a  throw
0x70b  ldarg.0
0x70c  ldstr    aTitle// "Title"
0x711  ldarg.s  4
0x713  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x718  ldc.i4.1
0x719  stloc.0
0x71a  ldarg.1
0x71b  ldloc.1
0x71c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Title()
0x721  ldarg.s  4
0x723  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x728  br.s     loc_736
0x72a  ldarg.0
0x72b  ldarg.1
0x72c  ldarg.2
0x72d  ldarg.3
0x72e  ldarg.s  4
0x730  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x735  stloc.0
0x736  ldloc.0
0x737  ret
```
