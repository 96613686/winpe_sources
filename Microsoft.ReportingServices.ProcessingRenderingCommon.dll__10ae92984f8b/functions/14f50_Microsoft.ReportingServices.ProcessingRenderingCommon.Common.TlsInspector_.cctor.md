# Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::.cctor

- ea: `0x14f50`
- end: `0x151a8`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::.cctor`
- size: `600`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x142a0`
- `0x14f50`
- `0x15210`
- `0x15290`
- `0x178d0`

## string_xrefs

- `0x15135`: `System.Net.Security.SslState`
- `0x1513f`: `SslProtocol`

## pseudocode

```c

```

## disassembly

```asm
0x14f50  ldtoken  [mscorlib]System.Type
0x14f55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f5a  ldstr    aIsinstanceofty// "IsInstanceOfType"
0x14f5f  ldc.i4.1
0x14f60  newarr   [mscorlib]System.Type
0x14f65  dup
0x14f66  ldc.i4.0
0x14f67  ldtoken  [mscorlib]System.Object
0x14f6c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f71  stelem.ref
0x14f72  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x14f77  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::isInstanceOf
0x14f7c  ldc.i4.s 0x24
0x14f7e  stloc.0
0x14f7f  ldsfld   class <>c <>c::<>9
0x14f84  ldftn    instance object <>c::<.cctor>b__9_0(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x14f8a  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object>::.ctor(object, native int)
0x14f8f  stsfld   class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpListenerRequestRequestBufferGetter
0x14f94  ldsfld   class <>c <>c::<>9
0x14f99  ldftn    instance object <>c::<.cctor>b__9_1(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x14f9f  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object>::.ctor(object, native int)
0x14fa4  stsfld   class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpListenerRequestOriginalBlobAddressGetter
0x14fa9  ldsfld   class <>c <>c::<>9
0x14fae  ldftn    instance object <>c::<.cctor>b__9_2(class [System.Net.Http]System.Net.Http.HttpContent httpContent)
0x14fb4  newobj   instance void class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpContent, object>::.ctor(object, native int)
0x14fb9  stsfld   class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpContent, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpContentStreamGetter
0x14fbe  ldsfld   class <>c <>c::<>9
0x14fc3  ldftn    instance object <>c::<.cctor>b__9_3(class [mscorlib]System.IO.Stream stream)
0x14fc9  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object>::.ctor(object, native int)
0x14fce  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::streamProtocolGetter
0x14fd3  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x14fd8  ldtoken  [System]System.Net.HttpListenerRequest
0x14fdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14fe2  ldstr    aRequestbuffer// "RequestBuffer"
0x14fe7  ldloc.0
0x14fe8  call     instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x14fed  stloc.1
0x14fee  dup
0x14fef  ldloc.1
0x14ff0  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetProperty(class [mscorlib]System.Reflection.PropertyInfo property)
0x14ff5  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::requestBufferGetter
0x14ffa  dup
0x14ffb  ldftn    instance object <>c__DisplayClass9_0::<.cctor>b__4(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x15001  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object>::.ctor(object, native int)
0x15006  stsfld   class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpListenerRequestRequestBufferGetter
0x1500b  ldtoken  [System]System.Net.HttpListenerRequest
0x15010  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15015  ldstr    aOriginalblobad// "OriginalBlobAddress"
0x1501a  ldloc.0
0x1501b  call     instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15020  stloc.2
0x15021  dup
0x15022  ldloc.2
0x15023  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetProperty(class [mscorlib]System.Reflection.PropertyInfo property)
0x15028  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::originalBlobAddressGetter
0x1502d  dup
0x1502e  ldftn    instance object <>c__DisplayClass9_0::<.cctor>b__5(class [System]System.Net.HttpListenerRequest httpListenerRequest)
0x15034  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object>::.ctor(object, native int)
0x15039  stsfld   class [mscorlib]System.Func`2<class [System]System.Net.HttpListenerRequest, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpListenerRequestOriginalBlobAddressGetter
0x1503e  ldtoken  [System.Net.Http]System.Net.Http.HttpContent
0x15043  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15048  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1504d  dup
0x1504e  ldstr    aSystemNetHttpS// "System.Net.Http.StreamContent"
0x15053  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x15058  stloc.3
0x15059  ldstr    aSystemNetHttpD// "System.Net.Http.DelegatingStream"
0x1505e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x15063  stloc.s  4
0x15065  ldloc.3
0x15066  ldstr    aContent// "content"
0x1506b  ldloc.0
0x1506c  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15071  stloc.s  5
0x15073  ldloc.s  5
0x15075  ldnull
0x15076  call     bool [mscorlib]System.Reflection.FieldInfo::op_Equality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0x1507b  brfalse.s loc_1508B
0x1507d  ldloc.3
0x1507e  ldstr    aContent_0// "_content"
0x15083  ldloc.0
0x15084  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15089  stloc.s  5
0x1508b  ldloc.s  4
0x1508d  ldstr    aInnerstream// "innerStream"
0x15092  ldloc.0
0x15093  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15098  stloc.s  6
0x1509a  ldloc.s  6
0x1509c  ldnull
0x1509d  call     bool [mscorlib]System.Reflection.FieldInfo::op_Equality(class [mscorlib]System.Reflection.FieldInfo, class [mscorlib]System.Reflection.FieldInfo)
0x150a2  brfalse.s loc_150B3
0x150a4  ldloc.s  4
0x150a6  ldstr    aInnerstream_0// "_innerStream"
0x150ab  ldloc.0
0x150ac  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x150b1  stloc.s  6
0x150b3  dup
0x150b4  ldloc.s  5
0x150b6  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetField(class [mscorlib]System.Reflection.FieldInfo field)
0x150bb  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::contentGetter
0x150c0  dup
0x150c1  ldloc.s  6
0x150c3  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetField(class [mscorlib]System.Reflection.FieldInfo field)
0x150c8  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::innerStreamGetter
0x150cd  dup
0x150ce  ldftn    instance object <>c__DisplayClass9_0::<.cctor>b__6(class [System.Net.Http]System.Net.Http.HttpContent httpContent)
0x150d4  newobj   instance void class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpContent, object>::.ctor(object, native int)
0x150d9  stsfld   class [mscorlib]System.Func`2<class [System.Net.Http]System.Net.Http.HttpContent, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::httpContentStreamGetter
0x150de  ldtoken  [System]System.Net.HttpWebRequest
0x150e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x150e8  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x150ed  dup
0x150ee  ldstr    aSystemNetConne// "System.Net.ConnectStream"
0x150f3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x150f8  ldstr    aConnection// "Connection"
0x150fd  ldloc.0
0x150fe  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15103  stloc.s  7
0x15105  dup
0x15106  ldstr    aSystemNetConne_0// "System.Net.Connection"
0x1510b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x15110  ldstr    aNetworkstream// "NetworkStream"
0x15115  ldloc.0
0x15116  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x1511b  stloc.s  8
0x1511d  dup
0x1511e  ldstr    aSystemNetTlsst// "System.Net.TlsStream"
0x15123  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x15128  ldstr    aMWorker// "m_Worker"
0x1512d  ldloc.0
0x1512e  callvirt instance class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Type::GetField(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x15133  stloc.s  9
0x15135  ldstr    aSystemNetSecur// "System.Net.Security.SslState"
0x1513a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x1513f  ldstr    aSslprotocol// "SslProtocol"
0x15144  ldloc.0
0x15145  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x1514a  stloc.s  0xA
0x1514c  dup
0x1514d  ldloc.s  7
0x1514f  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetProperty(class [mscorlib]System.Reflection.PropertyInfo property)
0x15154  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::connectionGetter
0x15159  dup
0x1515a  ldloc.s  8
0x1515c  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetProperty(class [mscorlib]System.Reflection.PropertyInfo property)
0x15161  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::networkStreamGetter
0x15166  dup
0x15167  ldloc.s  9
0x15169  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetField(class [mscorlib]System.Reflection.FieldInfo field)
0x1516e  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::workerGetter
0x15173  dup
0x15174  ldloc.s  0xA
0x15176  call     class [mscorlib]System.Func`2<object, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::GetProperty(class [mscorlib]System.Reflection.PropertyInfo property)
0x1517b  stfld    class [mscorlib]System.Func`2<object, object> <>c__DisplayClass9_0::sslProtocolPropertyGetter
0x15180  ldftn    instance object <>c__DisplayClass9_0::<.cctor>b__7(class [mscorlib]System.IO.Stream stream)
0x15186  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object>::.ctor(object, native int)
0x1518b  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IO.Stream, object> Microsoft.ReportingServices.ProcessingRenderingCommon.Common.TlsInspector::streamProtocolGetter
0x15190  leave.s  loc_151A7
0x15192  stloc.s  0xB
0x15194  ldstr    aFailedToInitia// "Failed to initialize TlsUtils class. Ex"...
0x15199  ldloc.s  0xB
0x1519b  call     string [mscorlib]System.String::Format(string, object)
0x151a0  call     void Microsoft.ReportingServices.ProcessingRenderingCommon.Tracing.EngineTracer::Error(string message)
0x151a5  leave.s  loc_151A7
0x151a7  ret
```
