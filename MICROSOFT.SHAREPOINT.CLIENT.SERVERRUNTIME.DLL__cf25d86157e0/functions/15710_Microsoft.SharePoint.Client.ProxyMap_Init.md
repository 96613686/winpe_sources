# Microsoft.SharePoint.Client.ProxyMap::Init

- ea: `0x15710`
- end: `0x15a68`
- name: `Microsoft.SharePoint.Client.ProxyMap::Init`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15680`

## callees

- `0xe000`
- `0xe4b0`
- `0x15710`
- `0x15ab0`
- `0x15eb0`
- `0x17ea0`
- `0x18af0`

## string_xrefs

- `0x157e9`: `Error when processing types in server stub DLL {0}, Error={1}`
- `0x15830`: `Error when processing types in server stub DLL {0}, Error={1}`
- `0x159b7`: `Error when processing types in server stub DLL {0}, Error={1}`
- `0x159f8`: `Error when processing types in server stub DLL {0}, Error={1}`
- `0x15894`: `Processing server stub dll {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x15710  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.ValueTypeConverter>::.ctor()
0x15715  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.ValueTypeConverter> Microsoft.SharePoint.Client.ProxyMap::s_typeToDataConverterMap
0x1571a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.ServerStub>::.ctor()
0x1571f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ProxyMap::s_typeToServerProxyMap
0x15724  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Client.ValueTypeConverter>::.ctor()
0x15729  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Client.ValueTypeConverter> Microsoft.SharePoint.Client.ProxyMap::s_guidToDataConverterMap
0x1572e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Client.ServerStub>::.ctor()
0x15733  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ProxyMap::s_guidToServerProxyMap
0x15738  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type>::.ctor()
0x1573d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type> Microsoft.SharePoint.Client.ProxyMap::s_guidToFactoryTypeMap
0x15742  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15747  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1574c  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>> Microsoft.SharePoint.Client.ProxyMap::s_edmTypeFullNameToServerProxyMap
0x15751  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15756  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ValueTypeConverter>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1575b  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ValueTypeConverter>> Microsoft.SharePoint.Client.ProxyMap::s_edmTypeFullNameToDataConverterMap
0x15760  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15765  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1576a  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>> Microsoft.SharePoint.Client.ProxyMap::s_urlSegmentAliasMap
0x1576f  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15774  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Reflection.Assembly>>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x15779  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Reflection.Assembly>>> Microsoft.SharePoint.Client.ProxyMap::s_urlSegmentRequestHandlerMap
0x1577e  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15783  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Collections.Generic.ISet`1<string>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x15788  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System]System.Collections.Generic.ISet`1<string>> Microsoft.SharePoint.Client.ProxyMap::s_excludedFromMetadataDocumentTypeFullNames
0x1578d  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15792  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class UrlPathPartitionedInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x15797  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_urlPathPartitionedInfoMap
0x1579c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor()
0x157a1  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.SharePoint.Client.ProxyMap::s_requestHandlerTypes
0x157a6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo>::.ctor()
0x157ab  stsfld   class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_sortedUrlPathPartitionInfos
0x157b0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x157b5  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Client.ProxyMap::s_clientObjectListServerStubs
0x157ba  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Reflection.Assembly>::.ctor()
0x157bf  stloc.0
0x157c0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x157c5  ldarg.0
0x157c6  call     void Microsoft.SharePoint.Client.ProxyMap::ProcessOneAssembly(class [mscorlib]System.Reflection.Assembly azzembly, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x157cb  ldloc.0
0x157cc  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x157d1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Reflection.Assembly>::Add(var<u1>)
0x157d6  pop
0x157d7  leave    loc_15863
0x157dc  stloc.1
0x157dd  ldarg.0
0x157de  ldc.i4   0x21C644
0x157e3  ldc.i4.1
0x157e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x157e9  ldstr    aErrorWhenProce// "Error when processing types in server s"...
0x157ee  ldc.i4.2
0x157ef  newarr   [mscorlib]System.Object
0x157f4  stloc.s  9
0x157f6  ldloc.s  9
0x157f8  ldc.i4.0
0x157f9  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x157fe  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x15803  stelem.ref
0x15804  ldloc.s  9
0x15806  ldc.i4.1
0x15807  ldloc.1
0x15808  callvirt instance string [mscorlib]System.Object::ToString()
0x1580d  stelem.ref
0x1580e  ldloc.s  9
0x15810  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15815  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x1581a  ldloc.1
0x1581b  ldarg.0
0x1581c  call     void Microsoft.SharePoint.Client.ProxyMap::LogLoaderExceptions(class [mscorlib]System.Reflection.ReflectionTypeLoadException loadEx, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x15821  rethrow
0x15823  stloc.2
0x15824  ldarg.0
0x15825  ldc.i4   0x21C645
0x1582a  ldc.i4.1
0x1582b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15830  ldstr    aErrorWhenProce// "Error when processing types in server s"...
0x15835  ldc.i4.2
0x15836  newarr   [mscorlib]System.Object
0x1583b  stloc.s  0xA
0x1583d  ldloc.s  0xA
0x1583f  ldc.i4.0
0x15840  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x15845  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1584a  stelem.ref
0x1584b  ldloc.s  0xA
0x1584d  ldc.i4.1
0x1584e  ldloc.2
0x1584f  callvirt instance string [mscorlib]System.Object::ToString()
0x15854  stelem.ref
0x15855  ldloc.s  0xA
0x15857  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1585c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x15861  rethrow
0x15863  ldarg.0
0x15864  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.SharePoint.Client.ClientServiceHost::get_ProxyAssemblyNames()
0x15869  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1586e  stloc.s  0xB
0x15870  br       loc_15A23
0x15875  ldloc.s  0xB
0x15877  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1587c  stloc.3
0x1587d  ldloc.3
0x1587e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15883  brtrue   loc_15A23
0x15888  ldarg.0
0x15889  ldc.i4   0x18C251
0x1588e  ldc.i4.3
0x1588f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15894  ldstr    aProcessingServ// "Processing server stub dll {0}."
0x15899  ldc.i4.1
0x1589a  newarr   [mscorlib]System.Object
0x1589f  stloc.s  0xC
0x158a1  ldloc.s  0xC
0x158a3  ldc.i4.0
0x158a4  ldloc.3
0x158a5  stelem.ref
0x158a6  ldloc.s  0xC
0x158a8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x158ad  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x158b2  ldnull
0x158b3  stloc.s  4
0x158b5  ldloc.3
0x158b6  call     class [mscorlib]System.Reflection.Assembly Microsoft.SharePoint.Client.Utility::LoadAssembly(string assemblyName)
0x158bb  stloc.s  4
0x158bd  leave    loc_1597C
0x158c2  stloc.s  5
0x158c4  ldarg.0
0x158c5  ldc.i4   0x1C518B
0x158ca  ldc.i4.1
0x158cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x158d0  ldstr    aErrorWhenLoadi// "Error when loading {0}, Error={1}"
0x158d5  ldc.i4.2
0x158d6  newarr   [mscorlib]System.Object
0x158db  stloc.s  0xD
0x158dd  ldloc.s  0xD
0x158df  ldc.i4.0
0x158e0  ldloc.3
0x158e1  stelem.ref
0x158e2  ldloc.s  0xD
0x158e4  ldc.i4.1
0x158e5  ldloc.s  5
0x158e7  callvirt instance string [mscorlib]System.Object::ToString()
0x158ec  stelem.ref
0x158ed  ldloc.s  0xD
0x158ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x158f4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x158f9  ldloc.s  5
0x158fb  ldarg.0
0x158fc  call     void Microsoft.SharePoint.Client.ProxyMap::LogLoaderExceptions(class [mscorlib]System.Reflection.ReflectionTypeLoadException loadEx, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x15901  leave.s  loc_1597C
0x15903  stloc.s  6
0x15905  ldarg.0
0x15906  ldc.i4   0x18C252
0x1590b  ldc.i4.1
0x1590c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15911  ldstr    aErrorWhenLoadi// "Error when loading {0}, Error={1}"
0x15916  ldc.i4.2
0x15917  newarr   [mscorlib]System.Object
0x1591c  stloc.s  0xE
0x1591e  ldloc.s  0xE
0x15920  ldc.i4.0
0x15921  ldloc.3
0x15922  stelem.ref
0x15923  ldloc.s  0xE
0x15925  ldc.i4.1
0x15926  ldloc.s  6
0x15928  callvirt instance string [mscorlib]System.Object::ToString()
0x1592d  stelem.ref
0x1592e  ldloc.s  0xE
0x15930  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15935  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x1593a  ldloc.s  6
0x1593c  call     bool Microsoft.SharePoint.Client.Utility::FIsFatalException(class [mscorlib]System.Exception e)
0x15941  brfalse.s loc_15945
0x15943  rethrow
0x15945  ldarg.0
0x15946  ldc.i4   0x18C253
0x1594b  ldc.i4.3
0x1594c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15951  ldstr    aContinueAsItSN// "Continue as it's not fatal error when l"...
0x15956  ldc.i4.2
0x15957  newarr   [mscorlib]System.Object
0x1595c  stloc.s  0xF
0x1595e  ldloc.s  0xF
0x15960  ldc.i4.0
0x15961  ldloc.3
0x15962  stelem.ref
0x15963  ldloc.s  0xF
0x15965  ldc.i4.1
0x15966  ldloc.s  6
0x15968  callvirt instance string [mscorlib]System.Object::ToString()
0x1596d  stelem.ref
0x1596e  ldloc.s  0xF
0x15970  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15975  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x1597a  leave.s  loc_1597C
0x1597c  ldloc.s  4
0x1597e  ldnull
0x1597f  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x15984  brtrue   loc_15A23
0x15989  ldloc.0
0x1598a  ldloc.s  4
0x1598c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Reflection.Assembly>::Contains(var<u1>)
0x15991  brtrue   loc_15A23
0x15996  ldloc.0
0x15997  ldloc.s  4
0x15999  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class [mscorlib]System.Reflection.Assembly>::Add(var<u1>)
0x1599e  pop
0x1599f  ldloc.s  4
0x159a1  ldarg.0
0x159a2  call     void Microsoft.SharePoint.Client.ProxyMap::ProcessOneAssembly(class [mscorlib]System.Reflection.Assembly azzembly, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x159a7  leave.s  loc_15A23
0x159a9  stloc.s  7
0x159ab  ldarg.0
0x159ac  ldc.i4   0x1C518C
0x159b1  ldc.i4.1
0x159b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x159b7  ldstr    aErrorWhenProce// "Error when processing types in server s"...
0x159bc  ldc.i4.2
0x159bd  newarr   [mscorlib]System.Object
0x159c2  stloc.s  0x10
0x159c4  ldloc.s  0x10
0x159c6  ldc.i4.0
0x159c7  ldloc.3
0x159c8  stelem.ref
0x159c9  ldloc.s  0x10
0x159cb  ldc.i4.1
0x159cc  ldloc.s  7
0x159ce  callvirt instance string [mscorlib]System.Object::ToString()
0x159d3  stelem.ref
0x159d4  ldloc.s  0x10
0x159d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x159db  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x159e0  ldloc.s  7
0x159e2  ldarg.0
0x159e3  call     void Microsoft.SharePoint.Client.ProxyMap::LogLoaderExceptions(class [mscorlib]System.Reflection.ReflectionTypeLoadException loadEx, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x159e8  rethrow
0x159ea  stloc.s  8
0x159ec  ldarg.0
0x159ed  ldc.i4   0x18C254
0x159f2  ldc.i4.1
0x159f3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x159f8  ldstr    aErrorWhenProce// "Error when processing types in server s"...
0x159fd  ldc.i4.2
0x159fe  newarr   [mscorlib]System.Object
0x15a03  stloc.s  0x11
0x15a05  ldloc.s  0x11
0x15a07  ldc.i4.0
0x15a08  ldloc.3
0x15a09  stelem.ref
0x15a0a  ldloc.s  0x11
0x15a0c  ldc.i4.1
0x15a0d  ldloc.s  8
0x15a0f  callvirt instance string [mscorlib]System.Object::ToString()
0x15a14  stelem.ref
0x15a15  ldloc.s  0x11
0x15a17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15a1c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x15a21  rethrow
0x15a23  ldloc.s  0xB
0x15a25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15a2a  brtrue   loc_15875
0x15a2f  leave.s  loc_15A3D
0x15a31  ldloc.s  0xB
0x15a33  brfalse.s loc_15A3C
0x15a35  ldloc.s  0xB
0x15a37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15a3c  endfinally
0x15a3d  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_urlPathPartitionedInfoMap
0x15a42  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class UrlPathPartitionedInfo>::get_Values()
0x15a47  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x15a4c  stsfld   class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_sortedUrlPathPartitionInfos
0x15a51  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_sortedUrlPathPartitionInfos
0x15a56  ldnull
0x15a57  ldftn    int32 Microsoft.SharePoint.Client.ProxyMap::CompareStringByLengthDescendingOrder(class UrlPathPartitionedInfo leftInfo, class UrlPathPartitionedInfo rightInfo)
0x15a5d  newobj   instance void class [mscorlib]System.Comparison`1<class UrlPathPartitionedInfo>::.ctor(object, native int)
0x15a62  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class UrlPathPartitionedInfo>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x15a67  ret
```
