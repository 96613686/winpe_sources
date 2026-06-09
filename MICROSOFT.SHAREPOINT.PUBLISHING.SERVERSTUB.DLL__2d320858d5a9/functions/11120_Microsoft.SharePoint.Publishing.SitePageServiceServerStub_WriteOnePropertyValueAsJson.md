# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::WriteOnePropertyValueAsJson

- ea: `0x11120`
- end: `0x11266`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::WriteOnePropertyValueAsJson`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x11120`

## string_xrefs

- `0x11145`: `CommunicationSite`
- `0x1119b`: `CommunicationSite`

## pseudocode

```c

```

## disassembly

```asm
0x11120  ldc.i4.0
0x11121  stloc.0
0x11122  ldarg.2
0x11123  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService
0x11128  stloc.1
0x11129  ldloc.1
0x1112a  brtrue.s loc_11137
0x1112c  ldstr    aTarget// "target"
0x11131  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11136  throw
0x11137  ldarg.3
0x11138  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x1113d  dup
0x1113e  stloc.2
0x1113f  brfalse  loc_11258
0x11144  ldloc.2
0x11145  ldstr    aCommunications// "CommunicationSite"
0x1114a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1114f  brtrue.s loc_11173
0x11151  ldloc.2
0x11152  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x11157  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1115c  brtrue.s loc_111C3
0x1115e  ldloc.2
0x1115f  ldstr    aPages// "Pages"
0x11164  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11169  brtrue   loc_1120A
0x1116e  br       loc_11258
0x11173  ldarg.3
0x11174  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11179  stloc.3
0x1117a  ldloca.s 3
0x1117c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x11181  brfalse.s loc_1119A
0x11183  ldarg.3
0x11184  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11189  stloc.s  4
0x1118b  ldloca.s 4
0x1118d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x11192  brfalse.s loc_1119A
0x11194  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x11199  throw
0x1119a  ldarg.0
0x1119b  ldstr    aCommunications// "CommunicationSite"
0x111a0  ldarg.s  4
0x111a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x111a7  ldc.i4.1
0x111a8  stloc.0
0x111a9  ldarg.0
0x111aa  ldarg.1
0x111ab  ldloc.1
0x111ac  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_CommunicationSite()
0x111b1  ldarg.3
0x111b2  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x111b7  ldarg.s  4
0x111b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x111be  br       loc_11264
0x111c3  ldarg.3
0x111c4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x111c9  stloc.s  5
0x111cb  ldloca.s 5
0x111cd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x111d2  brfalse.s loc_111EB
0x111d4  ldarg.3
0x111d5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x111da  stloc.s  6
0x111dc  ldloca.s 6
0x111de  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x111e3  brtrue.s loc_111EB
0x111e5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x111ea  throw
0x111eb  ldarg.0
0x111ec  ldstr    aCustomcontenta// "CustomContentApprovalEnabled"
0x111f1  ldarg.s  4
0x111f3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x111f8  ldc.i4.1
0x111f9  stloc.0
0x111fa  ldarg.1
0x111fb  ldloc.1
0x111fc  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_CustomContentApprovalEnabled()
0x11201  ldarg.s  4
0x11203  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11208  br.s     loc_11264
0x1120a  ldarg.3
0x1120b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11210  stloc.s  7
0x11212  ldloca.s 7
0x11214  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x11219  brfalse.s loc_11232
0x1121b  ldarg.3
0x1121c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x11221  stloc.s  8
0x11223  ldloca.s 8
0x11225  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1122a  brfalse.s loc_11232
0x1122c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x11231  throw
0x11232  ldarg.0
0x11233  ldstr    aPages// "Pages"
0x11238  ldarg.s  4
0x1123a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1123f  ldc.i4.1
0x11240  stloc.0
0x11241  ldarg.0
0x11242  ldarg.1
0x11243  ldloc.1
0x11244  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService::get_Pages()
0x11249  ldarg.3
0x1124a  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x1124f  ldarg.s  4
0x11251  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11256  br.s     loc_11264
0x11258  ldarg.0
0x11259  ldarg.1
0x1125a  ldarg.2
0x1125b  ldarg.3
0x1125c  ldarg.s  4
0x1125e  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11263  stloc.0
0x11264  ldloc.0
0x11265  ret
```
