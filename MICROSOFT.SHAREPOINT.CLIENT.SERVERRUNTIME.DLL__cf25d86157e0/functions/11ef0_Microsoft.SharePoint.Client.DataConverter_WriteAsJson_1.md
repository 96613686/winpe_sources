# Microsoft.SharePoint.Client.DataConverter::WriteAsJson_1

- ea: `0x11ef0`
- end: `0x120ab`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteAsJson_1`
- size: `443`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11ee0`
- `0x11ef0`
- `0x13a40`

## callees

- `0x360`
- `0x1600`
- `0xf3a0`
- `0x11700`
- `0x11ef0`
- `0x120b0`
- `0x12440`
- `0x12f80`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13560`
- `0x13720`
- `0x152f0`
- `0x168e0`
- `0x16920`
- `0x16f00`
- `0x18c50`

## string_xrefs

- `0x1209b`: `ClientRequestCannotSerializeToJson`

## pseudocode

```c

```

## disassembly

```asm
0x11ef0  ldarg.1
0x11ef1  brfalse.s loc_11EFB
0x11ef3  ldarg.1
0x11ef4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x11ef9  bne.un.s loc_11F02
0x11efb  ldarg.0
0x11efc  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x11f01  ret
0x11f02  ldarg.1
0x11f03  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11f08  stloc.0
0x11f09  ldnull
0x11f0a  stloc.1
0x11f0b  ldloc.0
0x11f0c  call     class Microsoft.SharePoint.Client.WellknownTypeBehavior Microsoft.SharePoint.Client.DataConverter::GetWellKnownTypeBehavior(class [mscorlib]System.Type type)
0x11f11  dup
0x11f12  stloc.1
0x11f13  brfalse.s loc_11F24
0x11f15  ldloc.1
0x11f16  ldfld    class Microsoft.SharePoint.Client.WriteObjectAsJsonHandler Microsoft.SharePoint.Client.WellknownTypeBehavior::WriteObjectAsJsonFunc
0x11f1b  ldarg.0
0x11f1c  ldarg.1
0x11f1d  ldarg.2
0x11f1e  callvirt instance void Microsoft.SharePoint.Client.WriteObjectAsJsonHandler::Invoke(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11f23  ret
0x11f24  ldloc.0
0x11f25  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x11f2a  brfalse.s loc_11F39
0x11f2c  ldarg.0
0x11f2d  ldarg.1
0x11f2e  castclass [mscorlib]System.Enum
0x11f33  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(class [mscorlib]System.Enum value)
0x11f38  ret
0x11f39  ldloc.0
0x11f3a  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x11f3f  brfalse.s loc_11F95
0x11f41  ldarg.0
0x11f42  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x11f47  ldarg.3
0x11f48  call     class Microsoft.SharePoint.Client.JsonSerializationOptions Microsoft.SharePoint.Client.JsonSerializationOptions::ToChildItemOptions(class Microsoft.SharePoint.Client.JsonSerializationOptions options)
0x11f4d  stloc.2
0x11f4e  ldarg.1
0x11f4f  castclass [mscorlib]System.Array
0x11f54  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Array::GetEnumerator()
0x11f59  stloc.s  0xC
0x11f5b  br.s     loc_11F6E
0x11f5d  ldloc.s  0xC
0x11f5f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11f64  stloc.3
0x11f65  ldarg.0
0x11f66  ldloc.3
0x11f67  ldarg.2
0x11f68  ldloc.2
0x11f69  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext, class Microsoft.SharePoint.Client.JsonSerializationOptions options)
0x11f6e  ldloc.s  0xC
0x11f70  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11f75  brtrue.s loc_11F5D
0x11f77  leave.s  loc_11F8E
0x11f79  ldloc.s  0xC
0x11f7b  isinst   [mscorlib]System.IDisposable
0x11f80  stloc.s  0xD
0x11f82  ldloc.s  0xD
0x11f84  brfalse.s loc_11F8D
0x11f86  ldloc.s  0xD
0x11f88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11f8d  endfinally
0x11f8e  ldarg.0
0x11f8f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x11f94  ret
0x11f95  ldloc.0
0x11f96  callvirt instance bool [mscorlib]System.Type::get_IsClass()
0x11f9b  brfalse  loc_12069
0x11fa0  ldloc.0
0x11fa1  ldarg.2
0x11fa2  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x11fa7  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x11fac  stloc.s  4
0x11fae  ldloc.0
0x11faf  ldarg.2
0x11fb0  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x11fb5  call     class Microsoft.SharePoint.Client.ValueTypeConverter Microsoft.SharePoint.Client.ProxyMap::GetValueTypeConverter(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x11fba  stloc.s  5
0x11fbc  ldarg.1
0x11fbd  isinst   [mscorlib]System.Collections.IEnumerable
0x11fc2  stloc.s  7
0x11fc4  ldloc.s  4
0x11fc6  brfalse.s loc_11FE0
0x11fc8  ldarg.3
0x11fc9  ldloc.s  7
0x11fcb  call     class Microsoft.SharePoint.Client.ClientObjectQuery Microsoft.SharePoint.Client.DataConverter::CreateClientObjectQueryFromSerializeToJsonOptions(class Microsoft.SharePoint.Client.JsonSerializationOptions options, class [mscorlib]System.Collections.IEnumerable enumerable)
0x11fd0  stloc.s  8
0x11fd2  ldloc.s  4
0x11fd4  ldarg.0
0x11fd5  ldarg.1
0x11fd6  ldloc.s  8
0x11fd8  ldarg.2
0x11fd9  ldc.i4.1
0x11fda  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope(class Microsoft.SharePoint.Client.JsonWriter writer, object value, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x11fdf  ret
0x11fe0  ldloc.s  5
0x11fe2  brfalse.s loc_11FEF
0x11fe4  ldloc.s  5
0x11fe6  ldarg.0
0x11fe7  ldarg.1
0x11fe8  ldarg.2
0x11fe9  callvirt instance void Microsoft.SharePoint.Client.ValueTypeConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11fee  ret
0x11fef  ldarg.1
0x11ff0  isinst   [mscorlib]System.Collections.IDictionary
0x11ff5  dup
0x11ff6  stloc.s  6
0x11ff8  brfalse.s loc_12004
0x11ffa  ldarg.0
0x11ffb  ldloc.s  6
0x11ffd  ldarg.2
0x11ffe  call     void Microsoft.SharePoint.Client.DataConverter::WriteDictionary(class Microsoft.SharePoint.Client.JsonWriter writer, class [mscorlib]System.Collections.IDictionary dict, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x12003  ret
0x12004  ldloc.s  7
0x12006  brfalse.s loc_1205C
0x12008  ldarg.3
0x12009  call     class Microsoft.SharePoint.Client.JsonSerializationOptions Microsoft.SharePoint.Client.JsonSerializationOptions::ToChildItemOptions(class Microsoft.SharePoint.Client.JsonSerializationOptions options)
0x1200e  stloc.s  9
0x12010  ldarg.0
0x12011  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x12016  ldloc.s  7
0x12018  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1201d  stloc.s  0xE
0x1201f  br.s     loc_12035
0x12021  ldloc.s  0xE
0x12023  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x12028  stloc.s  0xA
0x1202a  ldarg.0
0x1202b  ldloc.s  0xA
0x1202d  ldarg.2
0x1202e  ldloc.s  9
0x12030  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext, class Microsoft.SharePoint.Client.JsonSerializationOptions options)
0x12035  ldloc.s  0xE
0x12037  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1203c  brtrue.s loc_12021
0x1203e  leave.s  loc_12055
0x12040  ldloc.s  0xE
0x12042  isinst   [mscorlib]System.IDisposable
0x12047  stloc.s  0xF
0x12049  ldloc.s  0xF
0x1204b  brfalse.s loc_12054
0x1204d  ldloc.s  0xF
0x1204f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12054  endfinally
0x12055  ldarg.0
0x12056  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1205b  ret
0x1205c  ldarg.0
0x1205d  ldarg.1
0x1205e  callvirt instance string [mscorlib]System.Object::ToString()
0x12063  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x12068  ret
0x12069  ldloc.0
0x1206a  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x1206f  brfalse.s loc_1209B
0x12071  ldloc.0
0x12072  ldarg.2
0x12073  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x12078  call     class Microsoft.SharePoint.Client.ValueTypeConverter Microsoft.SharePoint.Client.ProxyMap::GetValueTypeConverter(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x1207d  stloc.s  0xB
0x1207f  ldloc.s  0xB
0x12081  brfalse.s loc_1208E
0x12083  ldloc.s  0xB
0x12085  ldarg.0
0x12086  ldarg.1
0x12087  ldarg.2
0x12088  callvirt instance void Microsoft.SharePoint.Client.ValueTypeConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1208d  ret
0x1208e  ldarg.0
0x1208f  ldarg.1
0x12090  callvirt instance string [mscorlib]System.Object::ToString()
0x12095  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1209a  ret
0x1209b  ldstr    aClientrequestc_1// "ClientRequestCannotSerializeToJson"
0x120a0  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0x120a5  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x120aa  throw
```
