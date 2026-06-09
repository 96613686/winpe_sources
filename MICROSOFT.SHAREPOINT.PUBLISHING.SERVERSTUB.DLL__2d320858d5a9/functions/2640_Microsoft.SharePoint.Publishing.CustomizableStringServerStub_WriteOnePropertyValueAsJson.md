# Microsoft.SharePoint.Publishing.CustomizableStringServerStub::WriteOnePropertyValueAsJson

- ea: `0x2640`
- end: `0x277e`
- name: `Microsoft.SharePoint.Publishing.CustomizableStringServerStub::WriteOnePropertyValueAsJson`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2640`

## pseudocode

```c

```

## disassembly

```asm
0x2640  ldc.i4.0
0x2641  stloc.0
0x2642  ldarg.2
0x2643  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString
0x2648  stloc.1
0x2649  ldloc.1
0x264a  ldnull
0x264b  call     bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::op_Equality(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString, class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString)
0x2650  brfalse.s loc_265D
0x2652  ldstr    aTarget// "target"
0x2657  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x265c  throw
0x265d  ldarg.3
0x265e  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x2663  dup
0x2664  stloc.2
0x2665  brfalse  loc_2770
0x266a  ldloc.2
0x266b  ldstr    aDefaultvalue// "DefaultValue"
0x2670  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2675  brtrue.s loc_2699
0x2677  ldloc.2
0x2678  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x267d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2682  brtrue.s loc_26E2
0x2684  ldloc.2
0x2685  ldstr    aValue// "Value"
0x268a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x268f  brtrue   loc_2729
0x2694  br       loc_2770
0x2699  ldarg.3
0x269a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x269f  stloc.3
0x26a0  ldloca.s 3
0x26a2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x26a7  brfalse.s loc_26C0
0x26a9  ldarg.3
0x26aa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x26af  stloc.s  4
0x26b1  ldloca.s 4
0x26b3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x26b8  brtrue.s loc_26C0
0x26ba  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x26bf  throw
0x26c0  ldarg.0
0x26c1  ldstr    aDefaultvalue// "DefaultValue"
0x26c6  ldarg.s  4
0x26c8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x26cd  ldc.i4.1
0x26ce  stloc.0
0x26cf  ldarg.1
0x26d0  ldloc.1
0x26d1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_DefaultValue()
0x26d6  ldarg.s  4
0x26d8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x26dd  br       loc_277C
0x26e2  ldarg.3
0x26e3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x26e8  stloc.s  5
0x26ea  ldloca.s 5
0x26ec  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x26f1  brfalse.s loc_270A
0x26f3  ldarg.3
0x26f4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x26f9  stloc.s  6
0x26fb  ldloca.s 6
0x26fd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2702  brtrue.s loc_270A
0x2704  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2709  throw
0x270a  ldarg.0
0x270b  ldstr    aUsesdefaultval// "UsesDefaultValue"
0x2710  ldarg.s  4
0x2712  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2717  ldc.i4.1
0x2718  stloc.0
0x2719  ldarg.1
0x271a  ldloc.1
0x271b  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_UsesDefaultValue()
0x2720  ldarg.s  4
0x2722  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2727  br.s     loc_277C
0x2729  ldarg.3
0x272a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x272f  stloc.s  7
0x2731  ldloca.s 7
0x2733  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2738  brfalse.s loc_2751
0x273a  ldarg.3
0x273b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x2740  stloc.s  8
0x2742  ldloca.s 8
0x2744  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2749  brtrue.s loc_2751
0x274b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2750  throw
0x2751  ldarg.0
0x2752  ldstr    aValue// "Value"
0x2757  ldarg.s  4
0x2759  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x275e  ldc.i4.1
0x275f  stloc.0
0x2760  ldarg.1
0x2761  ldloc.1
0x2762  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CustomizableString::get_Value()
0x2767  ldarg.s  4
0x2769  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x276e  br.s     loc_277C
0x2770  ldarg.0
0x2771  ldarg.1
0x2772  ldarg.2
0x2773  ldarg.3
0x2774  ldarg.s  4
0x2776  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x277b  stloc.0
0x277c  ldloc.0
0x277d  ret
```
