# Microsoft.SharePoint.Publishing.SitePageServerStub::WriteOnePropertyValueAsJson

- ea: `0x10420`
- end: `0x105b2`
- name: `Microsoft.SharePoint.Publishing.SitePageServerStub::WriteOnePropertyValueAsJson`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xecb0`
- `0x10420`

## string_xrefs

- `0x1045f`: `CanvasJson1`
- `0x1053f`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0x10420  ldc.i4.0
0x10421  stloc.0
0x10422  ldarg.2
0x10423  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage
0x10428  stloc.1
0x10429  ldloc.1
0x1042a  brtrue.s loc_10437
0x1042c  ldstr    aTarget// "target"
0x10431  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10436  throw
0x10437  ldarg.3
0x10438  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x1043d  dup
0x1043e  stloc.2
0x1043f  brfalse  loc_105A4
0x10444  ldloc.2
0x10445  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x1044a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1044f  brtrue.s loc_10483
0x10451  ldloc.2
0x10452  ldstr    aCanvascontent1// "CanvasContent1"
0x10457  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1045c  brtrue.s loc_104CC
0x1045e  ldloc.2
0x1045f  ldstr    aCanvasjson1// "CanvasJson1"
0x10464  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10469  brtrue   loc_10516
0x1046e  ldloc.2
0x1046f  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x10474  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10479  brtrue   loc_1055D
0x1047e  br       loc_105A4
0x10483  ldarg.3
0x10484  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10489  stloc.3
0x1048a  ldloca.s 3
0x1048c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10491  brfalse.s loc_104AA
0x10493  ldarg.3
0x10494  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10499  stloc.s  4
0x1049b  ldloca.s 4
0x1049d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x104a2  brtrue.s loc_104AA
0x104a4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x104a9  throw
0x104aa  ldarg.0
0x104ab  ldstr    aAlternativeurl// "AlternativeUrlMap"
0x104b0  ldarg.s  4
0x104b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x104b7  ldc.i4.1
0x104b8  stloc.0
0x104b9  ldarg.1
0x104ba  ldloc.1
0x104bb  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_AlternativeUrlMap()
0x104c0  ldarg.s  4
0x104c2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x104c7  br       loc_105B0
0x104cc  ldarg.3
0x104cd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x104d2  stloc.s  5
0x104d4  ldloca.s 5
0x104d6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x104db  brfalse.s loc_104F4
0x104dd  ldarg.3
0x104de  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x104e3  stloc.s  6
0x104e5  ldloca.s 6
0x104e7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x104ec  brtrue.s loc_104F4
0x104ee  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x104f3  throw
0x104f4  ldarg.0
0x104f5  ldstr    aCanvascontent1// "CanvasContent1"
0x104fa  ldarg.s  4
0x104fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10501  ldc.i4.1
0x10502  stloc.0
0x10503  ldarg.1
0x10504  ldloc.1
0x10505  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_CanvasContent1()
0x1050a  ldarg.s  4
0x1050c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10511  br       loc_105B0
0x10516  ldarg.3
0x10517  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1051c  stloc.s  7
0x1051e  ldloca.s 7
0x10520  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10525  brfalse.s loc_1053E
0x10527  ldarg.3
0x10528  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x1052d  stloc.s  8
0x1052f  ldloca.s 8
0x10531  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x10536  brtrue.s loc_1053E
0x10538  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x1053d  throw
0x1053e  ldarg.0
0x1053f  ldstr    aCanvasjson1// "CanvasJson1"
0x10544  ldarg.s  4
0x10546  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1054b  ldc.i4.1
0x1054c  stloc.0
0x1054d  ldarg.1
0x1054e  ldloc.1
0x1054f  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_CanvasJson1()
0x10554  ldarg.s  4
0x10556  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1055b  br.s     loc_105B0
0x1055d  ldarg.3
0x1055e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10563  stloc.s  9
0x10565  ldloca.s 9
0x10567  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1056c  brfalse.s loc_10585
0x1056e  ldarg.3
0x1056f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x10574  stloc.s  0xA
0x10576  ldloca.s 0xA
0x10578  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1057d  brtrue.s loc_10585
0x1057f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x10584  throw
0x10585  ldarg.0
0x10586  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0x1058b  ldarg.s  4
0x1058d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x10592  ldc.i4.1
0x10593  stloc.0
0x10594  ldarg.1
0x10595  ldloc.1
0x10596  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage::get_LayoutWebpartsContent()
0x1059b  ldarg.s  4
0x1059d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x105a2  br.s     loc_105B0
0x105a4  ldarg.0
0x105a5  ldarg.1
0x105a6  ldarg.2
0x105a7  ldarg.3
0x105a8  ldarg.s  4
0x105aa  call     instance bool Microsoft.SharePoint.Publishing.SitePageMetadataServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter writer, object target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty field, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x105af  stloc.0
0x105b0  ldloc.0
0x105b1  ret
```
