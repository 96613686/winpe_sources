# Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::WriteOnePropertyValueAsJson

- ea: `0x91e20`
- end: `0x92265`
- name: `Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::WriteOnePropertyValueAsJson`
- size: `1093`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x91e20`

## string_xrefs

- `0x91e64`: `Created`
- `0x91fa2`: `Created`
- `0x91ec4`: `WebTemplate`
- `0x921f2`: `WebTemplate`
- `0x91e58`: `Configuration`
- `0x91f58`: `Configuration`
- `0x91ed1`: `WebTemplateId`
- `0x92239`: `WebTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x91e20  ldc.i4.0
0x91e21  stloc.0
0x91e22  ldarg.2
0x91e23  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation
0x91e28  stloc.1
0x91e29  ldloc.1
0x91e2a  brtrue.s loc_91E37
0x91e2c  ldstr    aTarget// "target"
0x91e31  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x91e36  throw
0x91e37  ldarg.3
0x91e38  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x91e3d  dup
0x91e3e  stloc.2
0x91e3f  brfalse  loc_92257
0x91e44  volatile.
0x91e46  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001826-1
0x91e4b  brtrue   loc_91EE4
0x91e50  ldc.i4.s 0xB
0x91e52  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x91e57  dup
0x91e58  ldstr    aConfiguration// "Configuration"
0x91e5d  ldc.i4.0
0x91e5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e63  dup
0x91e64  ldstr    aCreated// "Created"
0x91e69  ldc.i4.1
0x91e6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e6f  dup
0x91e70  ldstr    aDescription// "Description"
0x91e75  ldc.i4.2
0x91e76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e7b  dup
0x91e7c  ldstr    aId_0// "Id"
0x91e81  ldc.i4.3
0x91e82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e87  dup
0x91e88  ldstr    aLanguage// "Language"
0x91e8d  ldc.i4.4
0x91e8e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e93  dup
0x91e94  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x91e99  ldc.i4.5
0x91e9a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91e9f  dup
0x91ea0  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x91ea5  ldc.i4.6
0x91ea6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91eab  dup
0x91eac  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x91eb1  ldc.i4.7
0x91eb2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91eb7  dup
0x91eb8  ldstr    aTitle// "Title"
0x91ebd  ldc.i4.8
0x91ebe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91ec3  dup
0x91ec4  ldstr    aWebtemplate// "WebTemplate"
0x91ec9  ldc.i4.s 9
0x91ecb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91ed0  dup
0x91ed1  ldstr    aWebtemplateid// "WebTemplateId"
0x91ed6  ldc.i4.s 0xA
0x91ed8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91edd  volatile.
0x91edf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001826-1
0x91ee4  volatile.
0x91ee6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001826-1
0x91eeb  ldloc.2
0x91eec  ldloca.s 3
0x91eee  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x91ef3  brfalse  loc_92257
0x91ef8  ldloc.3
0x91ef9  switch   loc_91F2F, loc_91F79, loc_91FC3, loc_9200D, loc_92057, loc_920A1, loc_920EB, loc_92135, loc_9217F, loc_921C9, loc_92210
0x91f2a  br       loc_92257
0x91f2f  ldarg.3
0x91f30  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91f35  stloc.s  4
0x91f37  ldloca.s 4
0x91f39  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x91f3e  brfalse.s loc_91F57
0x91f40  ldarg.3
0x91f41  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91f46  stloc.s  5
0x91f48  ldloca.s 5
0x91f4a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x91f4f  brtrue.s loc_91F57
0x91f51  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x91f56  throw
0x91f57  ldarg.0
0x91f58  ldstr    aConfiguration// "Configuration"
0x91f5d  ldarg.s  4
0x91f5f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91f64  ldc.i4.1
0x91f65  stloc.0
0x91f66  ldarg.1
0x91f67  ldloc.1
0x91f68  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Configuration()
0x91f6d  ldarg.s  4
0x91f6f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int16, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91f74  br       loc_92263
0x91f79  ldarg.3
0x91f7a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91f7f  stloc.s  6
0x91f81  ldloca.s 6
0x91f83  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x91f88  brfalse.s loc_91FA1
0x91f8a  ldarg.3
0x91f8b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91f90  stloc.s  7
0x91f92  ldloca.s 7
0x91f94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x91f99  brtrue.s loc_91FA1
0x91f9b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x91fa0  throw
0x91fa1  ldarg.0
0x91fa2  ldstr    aCreated// "Created"
0x91fa7  ldarg.s  4
0x91fa9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91fae  ldc.i4.1
0x91faf  stloc.0
0x91fb0  ldarg.1
0x91fb1  ldloc.1
0x91fb2  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Created()
0x91fb7  ldarg.s  4
0x91fb9  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91fbe  br       loc_92263
0x91fc3  ldarg.3
0x91fc4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91fc9  stloc.s  8
0x91fcb  ldloca.s 8
0x91fcd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x91fd2  brfalse.s loc_91FEB
0x91fd4  ldarg.3
0x91fd5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x91fda  stloc.s  9
0x91fdc  ldloca.s 9
0x91fde  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x91fe3  brtrue.s loc_91FEB
0x91fe5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x91fea  throw
0x91feb  ldarg.0
0x91fec  ldstr    aDescription// "Description"
0x91ff1  ldarg.s  4
0x91ff3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91ff8  ldc.i4.1
0x91ff9  stloc.0
0x91ffa  ldarg.1
0x91ffb  ldloc.1
0x91ffc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Description()
0x92001  ldarg.s  4
0x92003  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92008  br       loc_92263
0x9200d  ldarg.3
0x9200e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x92013  stloc.s  0xA
0x92015  ldloca.s 0xA
0x92017  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9201c  brfalse.s loc_92035
0x9201e  ldarg.3
0x9201f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x92024  stloc.s  0xB
0x92026  ldloca.s 0xB
0x92028  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9202d  brtrue.s loc_92035
0x9202f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x92034  throw
0x92035  ldarg.0
0x92036  ldstr    aId_0// "Id"
0x9203b  ldarg.s  4
0x9203d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92042  ldc.i4.1
0x92043  stloc.0
0x92044  ldarg.1
0x92045  ldloc.1
0x92046  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Id()
0x9204b  ldarg.s  4
0x9204d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92052  br       loc_92263
0x92057  ldarg.3
0x92058  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9205d  stloc.s  0xC
0x9205f  ldloca.s 0xC
0x92061  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x92066  brfalse.s loc_9207F
0x92068  ldarg.3
0x92069  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9206e  stloc.s  0xD
0x92070  ldloca.s 0xD
0x92072  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x92077  brtrue.s loc_9207F
0x92079  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x9207e  throw
0x9207f  ldarg.0
0x92080  ldstr    aLanguage// "Language"
0x92085  ldarg.s  4
0x92087  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9208c  ldc.i4.1
0x9208d  stloc.0
0x9208e  ldarg.1
0x9208f  ldloc.1
0x92090  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Language()
0x92095  ldarg.s  4
0x92097  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteUInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, unsigned int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9209c  br       loc_92263
0x920a1  ldarg.3
0x920a2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x920a7  stloc.s  0xE
0x920a9  ldloca.s 0xE
0x920ab  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x920b0  brfalse.s loc_920C9
0x920b2  ldarg.3
0x920b3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x920b8  stloc.s  0xF
0x920ba  ldloca.s 0xF
0x920bc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x920c1  brtrue.s loc_920C9
0x920c3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x920c8  throw
0x920c9  ldarg.0
0x920ca  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x920cf  ldarg.s  4
0x920d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x920d6  ldc.i4.1
0x920d7  stloc.0
0x920d8  ldarg.1
0x920d9  ldloc.1
0x920da  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemModifiedDate()
0x920df  ldarg.s  4
0x920e1  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x920e6  br       loc_92263
0x920eb  ldarg.3
0x920ec  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x920f1  stloc.s  0x10
0x920f3  ldloca.s 0x10
0x920f5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x920fa  brfalse.s loc_92113
0x920fc  ldarg.3
0x920fd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x92102  stloc.s  0x11
0x92104  ldloca.s 0x11
0x92106  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9210b  brtrue.s loc_92113
0x9210d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x92112  throw
0x92113  ldarg.0
0x92114  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x92119  ldarg.s  4
0x9211b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92120  ldc.i4.1
0x92121  stloc.0
0x92122  ldarg.1
0x92123  ldloc.1
0x92124  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemUserModifiedDate()
0x92129  ldarg.s  4
0x9212b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x92130  br       loc_92263
0x92135  ldarg.3
0x92136  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9213b  stloc.s  0x12
0x9213d  ldloca.s 0x12
0x9213f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x92144  brfalse.s loc_9215D
0x92146  ldarg.3
0x92147  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x9214c  stloc.s  0x13
0x9214e  ldloca.s 0x13
0x92150  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x92155  brtrue.s loc_9215D
0x92157  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x9215c  throw
0x9215d  ldarg.0
0x9215e  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x92163  ldarg.s  4
0x92165  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9216a  ldc.i4.1
0x9216b  stloc.0
0x9216c  ldarg.1
0x9216d  ldloc.1
0x9216e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_ServerRelativeUrl()
0x92173  ldarg.s  4
0x92175  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9217a  br       loc_92263
0x9217f  ldarg.3
0x92180  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x92185  stloc.s  0x14
0x92187  ldloca.s 0x14
0x92189  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9218e  brfalse.s loc_921A7
0x92190  ldarg.3
0x92191  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x92196  stloc.s  0x15
0x92198  ldloca.s 0x15
0x9219a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9219f  brtrue.s loc_921A7
0x921a1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x921a6  throw
0x921a7  ldarg.0
0x921a8  ldstr    aTitle// "Title"
0x921ad  ldarg.s  4
  ... truncated ...
```
