# Microsoft.SharePoint.Client.ServerStub::GetAllExtensionMethodTypes

- ea: `0x37b0`
- end: `0x392b`
- name: `Microsoft.SharePoint.Client.ServerStub::GetAllExtensionMethodTypes`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3e40`
- `0x252a0`

## callees

- `0xa30`
- `0x36d0`
- `0x37b0`
- `0x8d30`
- `0x8e10`
- `0x8e70`
- `0x8e90`
- `0x8f50`
- `0xe010`
- `0x152f0`
- `0x168c0`

## string_xrefs

- `0x3887`: `Method {0} was defined as extension method of {1} in both {2} and {3}`

## pseudocode

```c

```

## disassembly

```asm
0x37b0  ldarg.0
0x37b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ServerStub::m_extensionMethodTypes
0x37b6  stloc.0
0x37b7  ldloc.0
0x37b8  brtrue   loc_3929
0x37bd  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x37c2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x37c7  stloc.0
0x37c8  ldarg.1
0x37c9  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x37ce  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ProxyMap::GetServerStubs(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x37d3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ServerStub>::GetEnumerator()
0x37d8  stloc.s  4
0x37da  br       loc_3908
0x37df  ldloc.s  4
0x37e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.ServerStub>::get_Current()
0x37e6  stloc.1
0x37e7  ldloc.1
0x37e8  ldarg.1
0x37e9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Client.ServerStub::GetAllMethodInfos(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x37ee  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.MethodInformation>::get_Values()
0x37f3  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x37f8  stloc.s  5
0x37fa  br       loc_38EC
0x37ff  ldloca.s 5
0x3801  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x3806  stloc.2
0x3807  ldloc.2
0x3808  callvirt instance bool Microsoft.SharePoint.Client.MethodInformation::get_IsStatic()
0x380d  brfalse  loc_38EC
0x3812  ldloc.2
0x3813  callvirt instance bool Microsoft.SharePoint.Client.MethodInformation::get_RESTfulExtensionMethod()
0x3818  brfalse  loc_38EC
0x381d  ldloc.2
0x381e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x3823  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Count()
0x3828  ldc.i4.0
0x3829  ble      loc_38EC
0x382e  ldloc.2
0x382f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x3834  ldc.i4.0
0x3835  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x383a  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x383f  ldnull
0x3840  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3845  brfalse  loc_38EC
0x384a  ldloc.2
0x384b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x3850  ldc.i4.0
0x3851  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x3856  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x385b  ldarg.0
0x385c  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3861  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x3866  brfalse  loc_38EC
0x386b  ldloc.0
0x386c  ldloc.2
0x386d  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x3872  ldloca.s 3
0x3874  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>::TryGetValue(var<u1>, !!T0)
0x3879  brfalse.s loc_38DF
0x387b  ldarg.1
0x387c  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3881  ldc.i4   0x59F68E
0x3886  ldc.i4.1
0x3887  ldstr    aMethod0WasDefi// "Method {0} was defined as extension met"...
0x388c  ldc.i4.4
0x388d  newarr   [mscorlib]System.Object
0x3892  stloc.s  6
0x3894  ldloc.s  6
0x3896  ldc.i4.0
0x3897  ldloc.2
0x3898  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x389d  stelem.ref
0x389e  ldloc.s  6
0x38a0  ldc.i4.1
0x38a1  ldloc.2
0x38a2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x38a7  ldc.i4.0
0x38a8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x38ad  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x38b2  callvirt instance string [mscorlib]System.Type::get_FullName()
0x38b7  stelem.ref
0x38b8  ldloc.s  6
0x38ba  ldc.i4.2
0x38bb  ldloc.3
0x38bc  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x38c1  callvirt instance string [mscorlib]System.Type::get_FullName()
0x38c6  stelem.ref
0x38c7  ldloc.s  6
0x38c9  ldc.i4.3
0x38ca  ldloc.1
0x38cb  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x38d0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x38d5  stelem.ref
0x38d6  ldloc.s  6
0x38d8  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x38dd  br.s     loc_38EC
0x38df  ldloc.0
0x38e0  ldloc.2
0x38e1  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x38e6  ldloc.1
0x38e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>::set_Item(var<u1>, !!T0)
0x38ec  ldloca.s 5
0x38ee  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>::MoveNext()
0x38f3  brtrue   loc_37FF
0x38f8  leave.s  loc_3908
0x38fa  ldloca.s 5
0x38fc  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>
0x3902  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3907  endfinally
0x3908  ldloc.s  4
0x390a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x390f  brtrue   loc_37DF
0x3914  leave.s  loc_3922
0x3916  ldloc.s  4
0x3918  brfalse.s loc_3921
0x391a  ldloc.s  4
0x391c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3921  endfinally
0x3922  ldarg.0
0x3923  ldloc.0
0x3924  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ServerStub::m_extensionMethodTypes
0x3929  ldloc.0
0x392a  ret
```
