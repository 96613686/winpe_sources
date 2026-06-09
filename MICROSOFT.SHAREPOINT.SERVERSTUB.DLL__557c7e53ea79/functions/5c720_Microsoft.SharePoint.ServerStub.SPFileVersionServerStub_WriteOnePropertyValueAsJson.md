# Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::WriteOnePropertyValueAsJson

- ea: `0x5c720`
- end: `0x5cab3`
- name: `Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::WriteOnePropertyValueAsJson`
- size: `915`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5c720`

## string_xrefs

- `0x5c761`: `Created`
- `0x5c87d`: `Created`
- `0x5c76d`: `CreatedBy`
- `0x5c8c7`: `CreatedBy`
- `0x5c755`: `CheckInComment`
- `0x5c833`: `CheckInComment`

## pseudocode

```c

```

## disassembly

```asm
0x5c720  ldc.i4.0
0x5c721  stloc.0
0x5c722  ldarg.2
0x5c723  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion
0x5c728  stloc.1
0x5c729  ldloc.1
0x5c72a  brtrue.s loc_5C737
0x5c72c  ldstr    aTarget// "target"
0x5c731  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5c736  throw
0x5c737  ldarg.3
0x5c738  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x5c73d  dup
0x5c73e  stloc.2
0x5c73f  brfalse  loc_5CAA5
0x5c744  volatile.
0x5c746  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600106a-1
0x5c74b  brtrue.s loc_5C7C7
0x5c74d  ldc.i4.s 9
0x5c74f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5c754  dup
0x5c755  ldstr    aCheckincomment_0// "CheckInComment"
0x5c75a  ldc.i4.0
0x5c75b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c760  dup
0x5c761  ldstr    aCreated// "Created"
0x5c766  ldc.i4.1
0x5c767  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c76c  dup
0x5c76d  ldstr    aCreatedby// "CreatedBy"
0x5c772  ldc.i4.2
0x5c773  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c778  dup
0x5c779  ldstr    aId_1// "ID"
0x5c77e  ldc.i4.3
0x5c77f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c784  dup
0x5c785  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5c78a  ldc.i4.4
0x5c78b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c790  dup
0x5c791  ldstr    aLength// "Length"
0x5c796  ldc.i4.5
0x5c797  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c79c  dup
0x5c79d  ldstr    aSize_0// "Size"
0x5c7a2  ldc.i4.6
0x5c7a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c7a8  dup
0x5c7a9  ldstr    aUrl// "Url"
0x5c7ae  ldc.i4.7
0x5c7af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c7b4  dup
0x5c7b5  ldstr    aVersionlabel_0// "VersionLabel"
0x5c7ba  ldc.i4.8
0x5c7bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c7c0  volatile.
0x5c7c2  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600106a-1
0x5c7c7  volatile.
0x5c7c9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600106a-1
0x5c7ce  ldloc.2
0x5c7cf  ldloca.s 3
0x5c7d1  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5c7d6  brfalse  loc_5CAA5
0x5c7db  ldloc.3
0x5c7dc  switch   loc_5C80A, loc_5C854, loc_5C89E, loc_5C8EF, loc_5C939, loc_5C983, loc_5C9CD, loc_5CA17, loc_5CA5E
0x5c805  br       loc_5CAA5
0x5c80a  ldarg.3
0x5c80b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c810  stloc.s  4
0x5c812  ldloca.s 4
0x5c814  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c819  brfalse.s loc_5C832
0x5c81b  ldarg.3
0x5c81c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c821  stloc.s  5
0x5c823  ldloca.s 5
0x5c825  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c82a  brtrue.s loc_5C832
0x5c82c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c831  throw
0x5c832  ldarg.0
0x5c833  ldstr    aCheckincomment_0// "CheckInComment"
0x5c838  ldarg.s  4
0x5c83a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c83f  ldc.i4.1
0x5c840  stloc.0
0x5c841  ldarg.1
0x5c842  ldloc.1
0x5c843  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_CheckInComment()
0x5c848  ldarg.s  4
0x5c84a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c84f  br       loc_5CAB1
0x5c854  ldarg.3
0x5c855  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c85a  stloc.s  6
0x5c85c  ldloca.s 6
0x5c85e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c863  brfalse.s loc_5C87C
0x5c865  ldarg.3
0x5c866  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c86b  stloc.s  7
0x5c86d  ldloca.s 7
0x5c86f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c874  brtrue.s loc_5C87C
0x5c876  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c87b  throw
0x5c87c  ldarg.0
0x5c87d  ldstr    aCreated// "Created"
0x5c882  ldarg.s  4
0x5c884  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c889  ldc.i4.1
0x5c88a  stloc.0
0x5c88b  ldarg.1
0x5c88c  ldloc.1
0x5c88d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Created()
0x5c892  ldarg.s  4
0x5c894  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c899  br       loc_5CAB1
0x5c89e  ldarg.3
0x5c89f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c8a4  stloc.s  8
0x5c8a6  ldloca.s 8
0x5c8a8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c8ad  brfalse.s loc_5C8C6
0x5c8af  ldarg.3
0x5c8b0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c8b5  stloc.s  9
0x5c8b7  ldloca.s 9
0x5c8b9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c8be  brfalse.s loc_5C8C6
0x5c8c0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c8c5  throw
0x5c8c6  ldarg.0
0x5c8c7  ldstr    aCreatedby// "CreatedBy"
0x5c8cc  ldarg.s  4
0x5c8ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c8d3  ldc.i4.1
0x5c8d4  stloc.0
0x5c8d5  ldarg.0
0x5c8d6  ldarg.1
0x5c8d7  ldloc.1
0x5c8d8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_CreatedBy_Client()
0x5c8dd  ldarg.3
0x5c8de  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5c8e3  ldarg.s  4
0x5c8e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c8ea  br       loc_5CAB1
0x5c8ef  ldarg.3
0x5c8f0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c8f5  stloc.s  0xA
0x5c8f7  ldloca.s 0xA
0x5c8f9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c8fe  brfalse.s loc_5C917
0x5c900  ldarg.3
0x5c901  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c906  stloc.s  0xB
0x5c908  ldloca.s 0xB
0x5c90a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c90f  brtrue.s loc_5C917
0x5c911  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c916  throw
0x5c917  ldarg.0
0x5c918  ldstr    aId_1// "ID"
0x5c91d  ldarg.s  4
0x5c91f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c924  ldc.i4.1
0x5c925  stloc.0
0x5c926  ldarg.1
0x5c927  ldloc.1
0x5c928  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_ID()
0x5c92d  ldarg.s  4
0x5c92f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c934  br       loc_5CAB1
0x5c939  ldarg.3
0x5c93a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c93f  stloc.s  0xC
0x5c941  ldloca.s 0xC
0x5c943  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c948  brfalse.s loc_5C961
0x5c94a  ldarg.3
0x5c94b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c950  stloc.s  0xD
0x5c952  ldloca.s 0xD
0x5c954  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c959  brtrue.s loc_5C961
0x5c95b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c960  throw
0x5c961  ldarg.0
0x5c962  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5c967  ldarg.s  4
0x5c969  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c96e  ldc.i4.1
0x5c96f  stloc.0
0x5c970  ldarg.1
0x5c971  ldloc.1
0x5c972  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_IsCurrentVersion()
0x5c977  ldarg.s  4
0x5c979  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c97e  br       loc_5CAB1
0x5c983  ldarg.3
0x5c984  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c989  stloc.s  0xE
0x5c98b  ldloca.s 0xE
0x5c98d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c992  brfalse.s loc_5C9AB
0x5c994  ldarg.3
0x5c995  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c99a  stloc.s  0xF
0x5c99c  ldloca.s 0xF
0x5c99e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c9a3  brtrue.s loc_5C9AB
0x5c9a5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c9aa  throw
0x5c9ab  ldarg.0
0x5c9ac  ldstr    aLength// "Length"
0x5c9b1  ldarg.s  4
0x5c9b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c9b8  ldc.i4.1
0x5c9b9  stloc.0
0x5c9ba  ldarg.1
0x5c9bb  ldloc.1
0x5c9bc  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Length()
0x5c9c1  ldarg.s  4
0x5c9c3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c9c8  br       loc_5CAB1
0x5c9cd  ldarg.3
0x5c9ce  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c9d3  stloc.s  0x10
0x5c9d5  ldloca.s 0x10
0x5c9d7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5c9dc  brfalse.s loc_5C9F5
0x5c9de  ldarg.3
0x5c9df  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5c9e4  stloc.s  0x11
0x5c9e6  ldloca.s 0x11
0x5c9e8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5c9ed  brtrue.s loc_5C9F5
0x5c9ef  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5c9f4  throw
0x5c9f5  ldarg.0
0x5c9f6  ldstr    aSize_0// "Size"
0x5c9fb  ldarg.s  4
0x5c9fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ca02  ldc.i4.1
0x5ca03  stloc.0
0x5ca04  ldarg.1
0x5ca05  ldloc.1
0x5ca06  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Size_Client()
0x5ca0b  ldarg.s  4
0x5ca0d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ca12  br       loc_5CAB1
0x5ca17  ldarg.3
0x5ca18  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ca1d  stloc.s  0x12
0x5ca1f  ldloca.s 0x12
0x5ca21  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5ca26  brfalse.s loc_5CA3F
0x5ca28  ldarg.3
0x5ca29  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ca2e  stloc.s  0x13
0x5ca30  ldloca.s 0x13
0x5ca32  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5ca37  brtrue.s loc_5CA3F
0x5ca39  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5ca3e  throw
0x5ca3f  ldarg.0
0x5ca40  ldstr    aUrl// "Url"
0x5ca45  ldarg.s  4
0x5ca47  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ca4c  ldc.i4.1
0x5ca4d  stloc.0
0x5ca4e  ldarg.1
0x5ca4f  ldloc.1
0x5ca50  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Url()
0x5ca55  ldarg.s  4
0x5ca57  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ca5c  br.s     loc_5CAB1
0x5ca5e  ldarg.3
0x5ca5f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ca64  stloc.s  0x14
0x5ca66  ldloca.s 0x14
0x5ca68  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5ca6d  brfalse.s loc_5CA86
0x5ca6f  ldarg.3
0x5ca70  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ca75  stloc.s  0x15
0x5ca77  ldloca.s 0x15
0x5ca79  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5ca7e  brtrue.s loc_5CA86
0x5ca80  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5ca85  throw
0x5ca86  ldarg.0
0x5ca87  ldstr    aVersionlabel_0// "VersionLabel"
0x5ca8c  ldarg.s  4
0x5ca8e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ca93  ldc.i4.1
0x5ca94  stloc.0
0x5ca95  ldarg.1
0x5ca96  ldloc.1
  ... truncated ...
```
