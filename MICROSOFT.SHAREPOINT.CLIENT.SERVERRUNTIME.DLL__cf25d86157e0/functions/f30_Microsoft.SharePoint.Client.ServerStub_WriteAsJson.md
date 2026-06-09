# Microsoft.SharePoint.Client.ServerStub::WriteAsJson

- ea: `0xf30`
- end: `0x15fb`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteAsJson`
- size: `1739`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1600`

## callees

- `0xa30`
- `0xa50`
- `0xa60`
- `0xb70`
- `0xb80`
- `0xb90`
- `0xbb0`
- `0xf10`
- `0xf30`
- `0x1650`
- `0x16e0`
- `0x2580`
- `0x2590`
- `0x25a0`
- `0x25b0`
- `0x25d0`
- `0x27c0`
- `0x3a40`
- `0x9560`
- `0x95a0`
- `0x9720`
- `0x9790`
- `0x97a0`
- `0xe040`
- `0xe120`
- `0xe6c0`
- `0x11ee0`
- `0x12e20`
- `0x13030`
- `0x13220`
- `0x132d0`
- `0x13720`
- `0x15110`
- `0x15200`
- `0x15220`
- `0x15240`
- `0x152f0`
- `0x16f10`
- `0x18670`
- `0x187f0`

## string_xrefs

- `0xf33`: `writer`
- `0x10ed`: `_SerializeToJson`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.1
0xf31  brtrue.s loc_F3E
0xf33  ldstr    aWriter// "writer"
0xf38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf3d  throw
0xf3e  ldarg.2
0xf3f  brtrue.s loc_F4C
0xf41  ldstr    aObj// "obj"
0xf46  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf4b  throw
0xf4c  ldarg.3
0xf4d  brtrue.s loc_F5A
0xf4f  ldstr    aObjectquery// "objectQuery"
0xf54  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf59  throw
0xf5a  ldarg.3
0xf5b  callvirt instance class Microsoft.SharePoint.Client.ClientQuery Microsoft.SharePoint.Client.ClientObjectQuery::get_Query()
0xf60  stloc.0
0xf61  ldarg.1
0xf62  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0xf67  ldarg.1
0xf68  ldstr    aObjecttype// "_ObjectType_"
0xf6d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0xf72  ldarg.0
0xf73  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeAlias()
0xf78  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf7d  brfalse.s loc_F8D
0xf7f  ldarg.1
0xf80  ldarg.0
0xf81  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0xf86  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0xf8b  br.s     loc_F99
0xf8d  ldarg.1
0xf8e  ldarg.0
0xf8f  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeAlias()
0xf94  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0xf99  ldnull
0xf9a  stloc.1
0xf9b  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0xfa0  brfalse.s loc_FEE
0xfa2  ldarg.s  4
0xfa4  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0xfa9  ldarg.0
0xfaa  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0xfaf  ldstr    aGetobjectident// "_GetObjectIdentity"
0xfb4  ldc.i4.0
0xfb5  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0xfba  stloc.2
0xfbb  ldarg.0
0xfbc  ldarg.2
0xfbd  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectIdentity(object obj)
0xfc2  stloc.1
0xfc3  ldloc.1
0xfc4  ldarg.s  4
0xfc6  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0xfcb  callvirt instance string Microsoft.SharePoint.Client.ClientServiceHost::get_TraceCorrelationId()
0xfd0  call     string Microsoft.SharePoint.Client.Utility::AddCorrelationIdToObjectId(string identity, string correlationId)
0xfd5  stloc.1
0xfd6  leave.s  loc_FE2
0xfd8  stloc.3
0xfd9  ldloc.2
0xfda  ldloc.3
0xfdb  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0xfe0  rethrow
0xfe2  leave.s  loc_1009
0xfe4  ldloc.2
0xfe5  brfalse.s loc_FED
0xfe7  ldloc.2
0xfe8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfed  endfinally
0xfee  ldarg.0
0xfef  ldarg.2
0xff0  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectIdentity(object obj)
0xff5  stloc.1
0xff6  ldloc.1
0xff7  ldarg.s  4
0xff9  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0xffe  callvirt instance string Microsoft.SharePoint.Client.ClientServiceHost::get_TraceCorrelationId()
0x1003  call     string Microsoft.SharePoint.Client.Utility::AddCorrelationIdToObjectId(string identity, string correlationId)
0x1008  stloc.1
0x1009  ldloc.1
0x100a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x100f  brtrue.s loc_1023
0x1011  ldarg.1
0x1012  ldstr    aObjectidentity// "_ObjectIdentity_"
0x1017  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x101c  ldarg.1
0x101d  ldloc.1
0x101e  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1023  ldnull
0x1024  stloc.s  4
0x1026  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x102b  brfalse.s loc_106D
0x102d  ldarg.s  4
0x102f  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1034  ldarg.0
0x1035  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x103a  ldstr    aGetobjectversi// "_GetObjectVersion"
0x103f  ldc.i4.0
0x1040  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x1045  stloc.s  5
0x1047  ldarg.0
0x1048  ldarg.2
0x1049  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectVersion(object obj)
0x104e  stloc.s  4
0x1050  leave.s  loc_105F
0x1052  stloc.s  6
0x1054  ldloc.s  5
0x1056  ldloc.s  6
0x1058  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x105d  rethrow
0x105f  leave.s  loc_1076
0x1061  ldloc.s  5
0x1063  brfalse.s loc_106C
0x1065  ldloc.s  5
0x1067  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x106c  endfinally
0x106d  ldarg.0
0x106e  ldarg.2
0x106f  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectVersion(object obj)
0x1074  stloc.s  4
0x1076  ldloc.s  4
0x1078  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x107d  brtrue.s loc_1092
0x107f  ldarg.1
0x1080  ldstr    aObjectversion// "_ObjectVersion_"
0x1085  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x108a  ldarg.1
0x108b  ldloc.s  4
0x108d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x1092  ldnull
0x1093  stloc.s  7
0x1095  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x109a  brfalse.s loc_10DC
0x109c  ldarg.s  4
0x109e  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x10a3  ldarg.0
0x10a4  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x10a9  ldstr    aGetexpandofiel// "_GetExpandoFieldNames"
0x10ae  ldc.i4.0
0x10af  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x10b4  stloc.s  8
0x10b6  ldarg.0
0x10b7  ldarg.2
0x10b8  callvirt instance string[] Microsoft.SharePoint.Client.ServerStub::GetExpandoFieldNames(object obj)
0x10bd  stloc.s  7
0x10bf  leave.s  loc_10CE
0x10c1  stloc.s  9
0x10c3  ldloc.s  8
0x10c5  ldloc.s  9
0x10c7  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x10cc  rethrow
0x10ce  leave.s  loc_10E5
0x10d0  ldloc.s  8
0x10d2  brfalse.s loc_10DB
0x10d4  ldloc.s  8
0x10d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10db  endfinally
0x10dc  ldarg.0
0x10dd  ldarg.2
0x10de  callvirt instance string[] Microsoft.SharePoint.Client.ServerStub::GetExpandoFieldNames(object obj)
0x10e3  stloc.s  7
0x10e5  ldarg.s  4
0x10e7  ldarg.0
0x10e8  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x10ed  ldstr    aSerializetojso// "_SerializeToJson"
0x10f2  call     string Microsoft.SharePoint.Client.Utility::GetMonitoredScopeName(class [mscorlib]System.Type type, string memberName)
0x10f7  callvirt instance class [mscorlib]System.IDisposable Microsoft.SharePoint.Client.ProxyContext::CreatePerformanceMarkerScope(string scopeName)
0x10fc  stloc.s  0x1B
0x10fe  ldarg.3
0x10ff  callvirt instance bool Microsoft.SharePoint.Client.ClientObjectQuery::get_SelectAll()
0x1104  brtrue.s loc_1114
0x1106  ldloc.0
0x1107  brfalse.s loc_1114
0x1109  ldloc.0
0x110a  callvirt instance bool Microsoft.SharePoint.Client.ClientQuery::get_SelectAllProperties()
0x110f  brfalse  loc_13E0
0x1114  ldarg.0
0x1115  ldarg.1
0x1116  ldarg.2
0x1117  ldarg.s  4
0x1119  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x111e  ldloc.s  7
0x1120  brtrue   loc_1206
0x1125  ldloc.0
0x1126  brfalse  loc_15DB
0x112b  ldloc.0
0x112c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty> Microsoft.SharePoint.Client.ClientQuery::get_Properties()
0x1131  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty>::get_Count()
0x1136  brfalse  loc_15DB
0x113b  ldloc.0
0x113c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty> Microsoft.SharePoint.Client.ClientQuery::get_Properties()
0x1141  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty>::GetEnumerator()
0x1146  stloc.s  0x1C
0x1148  br       loc_11E7
0x114d  ldloca.s 0x1C
0x114f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Client.ClientQueryProperty>::get_Current()
0x1154  stloc.s  0xA
0x1156  ldarg.0
0x1157  ldloc.s  0xA
0x1159  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x115e  ldc.i4.1
0x115f  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::HasProperty(string propName, bool valueObject)
0x1164  brfalse.s loc_1175
0x1166  ldarg.0
0x1167  ldloc.s  0xA
0x1169  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x116e  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::ExcludeFromDefaultRetrieve(string propName)
0x1173  brfalse.s loc_11E7
0x1175  ldarg.1
0x1176  ldloc.s  0xA
0x1178  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x117d  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0x1182  ldarg.s  4
0x1184  ldloc.s  0xA
0x1186  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x118b  callvirt instance void Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string markerName)
0x1190  ldarg.0
0x1191  ldarg.1
0x1192  ldarg.2
0x1193  ldloc.s  0xA
0x1195  ldarg.s  4
0x1197  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::CustomWriteOnePropertyValueAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ClientQueryProperty field, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x119c  stloc.s  0xB
0x119e  ldloc.s  0xB
0x11a0  brtrue.s loc_11B0
0x11a2  ldarg.0
0x11a3  ldarg.1
0x11a4  ldarg.2
0x11a5  ldloc.s  0xA
0x11a7  ldarg.s  4
0x11a9  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ClientQueryProperty field, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11ae  stloc.s  0xB
0x11b0  ldarg.s  4
0x11b2  ldloc.s  0xA
0x11b4  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x11b9  callvirt instance void Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string markerName)
0x11be  ldloc.s  0xB
0x11c0  brtrue.s loc_11E7
0x11c2  ldstr    aClientrequestf// "ClientRequestFieldNotExist"
0x11c7  ldc.i4.1
0x11c8  newarr   [mscorlib]System.Object
0x11cd  stloc.s  0x1D
0x11cf  ldloc.s  0x1D
0x11d1  ldc.i4.0
0x11d2  ldloc.s  0xA
0x11d4  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x11d9  stelem.ref
0x11da  ldloc.s  0x1D
0x11dc  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x11e1  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x11e6  throw
0x11e7  ldloca.s 0x1C
0x11e9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Client.ClientQueryProperty>::MoveNext()
0x11ee  brtrue   loc_114D
0x11f3  leave    loc_15DB
0x11f8  ldloca.s 0x1C
0x11fa  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Client.ClientQueryProperty>
0x1200  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1205  endfinally
0x1206  ldloc.s  7
0x1208  stloc.s  0xC
0x120a  ldloc.0
0x120b  brfalse  loc_1339
0x1210  ldloc.0
0x1211  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty> Microsoft.SharePoint.Client.ClientQuery::get_Properties()
0x1216  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty>::get_Count()
0x121b  brfalse  loc_1339
0x1220  ldloc.0
0x1221  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty> Microsoft.SharePoint.Client.ClientQuery::get_Properties()
0x1226  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.ClientQueryProperty>::GetEnumerator()
0x122b  stloc.s  0x1E
0x122d  br       loc_131D
0x1232  ldloca.s 0x1E
0x1234  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Client.ClientQueryProperty>::get_Current()
0x1239  stloc.s  0xD
0x123b  ldarg.0
0x123c  ldloc.s  0xD
0x123e  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x1243  ldc.i4.1
0x1244  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::HasProperty(string propName, bool valueObject)
0x1249  stloc.s  0xE
0x124b  ldloc.s  0xE
0x124d  brfalse.s loc_1261
0x124f  ldarg.0
0x1250  ldloc.s  0xD
0x1252  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x1257  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::ExcludeFromDefaultRetrieve(string propName)
0x125c  brfalse  loc_131D
0x1261  ldloc.s  0xE
0x1263  brtrue.s loc_1275
0x1265  ldarg.0
0x1266  ldloc.s  0xD
0x1268  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x126d  ldc.i4.0
0x126e  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::HasProperty(string propName, bool valueObject)
0x1273  brfalse.s loc_12E7
0x1275  ldarg.1
0x1276  ldloc.s  0xD
0x1278  callvirt instance string Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
  ... truncated ...
```
