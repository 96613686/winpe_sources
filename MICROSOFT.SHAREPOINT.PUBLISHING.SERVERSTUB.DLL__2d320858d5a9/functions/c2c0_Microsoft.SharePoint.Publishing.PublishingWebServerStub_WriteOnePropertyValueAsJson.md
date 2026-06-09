# Microsoft.SharePoint.Publishing.PublishingWebServerStub::WriteOnePropertyValueAsJson

- ea: `0xc2c0`
- end: `0xc349`
- name: `Microsoft.SharePoint.Publishing.PublishingWebServerStub::WriteOnePropertyValueAsJson`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc2c0`

## pseudocode

```c

```

## disassembly

```asm
0xc2c0  ldc.i4.0
0xc2c1  stloc.0
0xc2c2  ldarg.2
0xc2c3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingWeb
0xc2c8  stloc.1
0xc2c9  ldloc.1
0xc2ca  brtrue.s loc_C2D7
0xc2cc  ldstr    aTarget// "target"
0xc2d1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc2d6  throw
0xc2d7  ldarg.3
0xc2d8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xc2dd  dup
0xc2de  stloc.2
0xc2df  brfalse.s loc_C33B
0xc2e1  ldloc.2
0xc2e2  ldstr    aWeb_0// "Web"
0xc2e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc2ec  brfalse.s loc_C33B
0xc2ee  ldarg.3
0xc2ef  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xc2f4  stloc.3
0xc2f5  ldloca.s 3
0xc2f7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xc2fc  brfalse.s loc_C315
0xc2fe  ldarg.3
0xc2ff  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xc304  stloc.s  4
0xc306  ldloca.s 4
0xc308  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xc30d  brfalse.s loc_C315
0xc30f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xc314  throw
0xc315  ldarg.0
0xc316  ldstr    aWeb_0// "Web"
0xc31b  ldarg.s  4
0xc31d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc322  ldc.i4.1
0xc323  stloc.0
0xc324  ldarg.0
0xc325  ldarg.1
0xc326  ldloc.1
0xc327  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingWeb::get_Web()
0xc32c  ldarg.3
0xc32d  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xc332  ldarg.s  4
0xc334  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc339  br.s     loc_C347
0xc33b  ldarg.0
0xc33c  ldarg.1
0xc33d  ldarg.2
0xc33e  ldarg.3
0xc33f  ldarg.s  4
0xc341  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc346  stloc.0
0xc347  ldloc.0
0xc348  ret
```
