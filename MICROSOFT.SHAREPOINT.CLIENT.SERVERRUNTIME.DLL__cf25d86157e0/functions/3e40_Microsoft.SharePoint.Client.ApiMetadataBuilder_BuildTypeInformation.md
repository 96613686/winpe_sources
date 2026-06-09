# Microsoft.SharePoint.Client.ApiMetadataBuilder::BuildTypeInformation

- ea: `0x3e40`
- end: `0x4283`
- name: `Microsoft.SharePoint.Client.ApiMetadataBuilder::BuildTypeInformation`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3bd0`

## callees

- `0xa30`
- `0xa40`
- `0xa50`
- `0x2940`
- `0x2f10`
- `0x36d0`
- `0x3720`
- `0x3740`
- `0x37b0`
- `0x3e40`
- `0x4290`
- `0x4950`
- `0x4a60`
- `0x8b10`
- `0x8b40`
- `0x8b70`
- `0x8b80`
- `0x8bb0`
- `0x8c60`
- `0x8cd0`
- `0x8e10`
- `0x8e70`
- `0x8e80`
- `0x8ed0`
- `0x90c0`
- `0x9110`
- `0x9190`
- `0x91b0`
- `0x91d0`
- `0x91e0`
- `0x9200`
- `0x9220`
- `0xe010`
- `0x12430`
- `0x152f0`
- `0x16920`
- `0x17080`
- `0x37830`

## string_xrefs

- `0x41b8`: `Extension method {0} defined in type {1} conflict with existing method defined in {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x3e40  newobj   instance void Microsoft.SharePoint.Client.TypeInformation::.ctor()
0x3e45  stloc.0
0x3e46  ldloc.0
0x3e47  ldc.i4.0
0x3e48  callvirt instance void Microsoft.SharePoint.Client.TypeInformation::set_IsValueObject(bool value)
0x3e4d  ldloc.0
0x3e4e  ldarg.1
0x3e4f  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x3e54  callvirt instance void Microsoft.SharePoint.Client.TypeInformation::set_FullName(string value)
0x3e59  ldarg.1
0x3e5a  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x3e5f  brfalse  loc_3F00
0x3e64  ldarg.1
0x3e65  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x3e6a  ldarg.2
0x3e6b  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3e70  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x3e75  stloc.1
0x3e76  ldloc.1
0x3e77  brtrue.s loc_3EAF
0x3e79  ldarg.2
0x3e7a  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3e7f  ldc.i4   0x21C619
0x3e84  ldc.i4.1
0x3e85  ldstr    aCannotFindServ// "Cannot find server stub for type {0}"
0x3e8a  ldc.i4.1
0x3e8b  newarr   [mscorlib]System.Object
0x3e90  stloc.s  0x10
0x3e92  ldloc.s  0x10
0x3e94  ldc.i4.0
0x3e95  ldloc.1
0x3e96  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3e9b  stelem.ref
0x3e9c  ldloc.s  0x10
0x3e9e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3ea3  ldloc.1
0x3ea4  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x3ea9  newobj   instance void Microsoft.SharePoint.Client.ServerProxyNotFoundException::.ctor(class [mscorlib]System.Type type)
0x3eae  throw
0x3eaf  ldloc.1
0x3eb0  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3eb5  ldarg.2
0x3eb6  ldloca.s 2
0x3eb8  call     bool Microsoft.SharePoint.Client.ApiMetadataBuilder::TryGetTypeName(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] string& typeName)
0x3ebd  brtrue.s loc_3EEF
0x3ebf  ldarg.2
0x3ec0  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3ec5  ldc.i4   0x21C61A
0x3eca  ldc.i4.1
0x3ecb  ldstr    aCannotGetTypeN// "Cannot get type name for type {0}"
0x3ed0  ldc.i4.1
0x3ed1  newarr   [mscorlib]System.Object
0x3ed6  stloc.s  0x11
0x3ed8  ldloc.s  0x11
0x3eda  ldc.i4.0
0x3edb  ldloc.1
0x3edc  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3ee1  stelem.ref
0x3ee2  ldloc.s  0x11
0x3ee4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3ee9  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor()
0x3eee  throw
0x3eef  ldloc.0
0x3ef0  ldloc.2
0x3ef1  call     string Microsoft.SharePoint.Client.ApiMetadataBuilder::GetCollectionType(string type)
0x3ef6  callvirt instance void Microsoft.SharePoint.Client.TypeInformation::set_BaseTypeFullName(string value)
0x3efb  br       loc_4082
0x3f00  ldarg.1
0x3f01  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetBaseType()
0x3f06  ldnull
0x3f07  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3f0c  brfalse.s loc_3F55
0x3f0e  ldarg.1
0x3f0f  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetBaseType()
0x3f14  ldarg.2
0x3f15  ldloca.s 3
0x3f17  call     bool Microsoft.SharePoint.Client.ApiMetadataBuilder::TryGetTypeName(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] string& typeName)
0x3f1c  brtrue.s loc_3F4E
0x3f1e  ldarg.2
0x3f1f  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3f24  ldc.i4   0x21C61B
0x3f29  ldc.i4.1
0x3f2a  ldstr    aCannotGetTypeN// "Cannot get type name for type {0}"
0x3f2f  ldc.i4.1
0x3f30  newarr   [mscorlib]System.Object
0x3f35  stloc.s  0x12
0x3f37  ldloc.s  0x12
0x3f39  ldc.i4.0
0x3f3a  ldarg.1
0x3f3b  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetBaseType()
0x3f40  stelem.ref
0x3f41  ldloc.s  0x12
0x3f43  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3f48  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor()
0x3f4d  throw
0x3f4e  ldloc.0
0x3f4f  ldloc.3
0x3f50  callvirt instance void Microsoft.SharePoint.Client.TypeInformation::set_BaseTypeFullName(string value)
0x3f55  ldarg.1
0x3f56  ldarg.2
0x3f57  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Client.ServerStub::GetAllPropertyInfos(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3f5c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.PropertyInformation>::get_Values()
0x3f61  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x3f66  stloc.s  0x13
0x3f68  br.s     loc_3FDF
0x3f6a  ldloca.s 0x13
0x3f6c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x3f71  stloc.s  4
0x3f73  ldloc.s  4
0x3f75  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.PropertyInformation::get_PropertyODataType()
0x3f7a  brfalse.s loc_3FDF
0x3f7c  ldloc.s  4
0x3f7e  callvirt instance bool Microsoft.SharePoint.Client.PropertyInformation::get_IsStatic()
0x3f83  brtrue.s loc_3FDF
0x3f85  ldloc.s  4
0x3f87  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.PropertyInformation::get_PropertyType()
0x3f8c  ldarg.2
0x3f8d  ldloca.s 5
0x3f8f  call     bool Microsoft.SharePoint.Client.ApiMetadataBuilder::TryGetTypeName(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] string& typeName)
0x3f94  brfalse.s loc_3FAE
0x3f96  ldloc.s  4
0x3f98  ldloc.s  5
0x3f9a  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyTypeFullName(string value)
0x3f9f  ldloc.0
0x3fa0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Client.TypeInformation::get_Properties()
0x3fa5  ldloc.s  4
0x3fa7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.PropertyInformation>::Add(var<u1>)
0x3fac  br.s     loc_3FDF
0x3fae  ldarg.2
0x3faf  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3fb4  ldc.i4   0x21C61C
0x3fb9  ldc.i4.1
0x3fba  ldstr    aCannotGetTypeN_0// "Cannot get type name for {0}"
0x3fbf  ldc.i4.1
0x3fc0  newarr   [mscorlib]System.Object
0x3fc5  stloc.s  0x14
0x3fc7  ldloc.s  0x14
0x3fc9  ldc.i4.0
0x3fca  ldloc.s  4
0x3fcc  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.PropertyInformation::get_PropertyType()
0x3fd1  stelem.ref
0x3fd2  ldloc.s  0x14
0x3fd4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3fd9  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor()
0x3fde  throw
0x3fdf  ldloca.s 0x13
0x3fe1  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.PropertyInformation>::MoveNext()
0x3fe6  brtrue.s loc_3F6A
0x3fe8  leave.s  loc_3FF8
0x3fea  ldloca.s 0x13
0x3fec  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.PropertyInformation>
0x3ff2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ff7  endfinally
0x3ff8  ldarg.1
0x3ff9  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x3ffe  ldnull
0x3fff  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4004  brfalse.s loc_4082
0x4006  ldstr    aItems// "Items"
0x400b  stloc.s  6
0x400d  ldarg.1
0x400e  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x4013  ldarg.2
0x4014  ldloca.s 7
0x4016  call     bool Microsoft.SharePoint.Client.ApiMetadataBuilder::TryGetTypeName(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] string& typeName)
0x401b  brfalse.s loc_4052
0x401d  newobj   instance void Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x4022  stloc.s  8
0x4024  ldloc.s  8
0x4026  ldloc.s  6
0x4028  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_Name(string value)
0x402d  ldloc.s  8
0x402f  ldc.i4.3
0x4030  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x4035  ldloc.s  8
0x4037  ldloc.s  7
0x4039  call     string Microsoft.SharePoint.Client.ApiMetadataBuilder::GetCollectionType(string type)
0x403e  callvirt instance void Microsoft.SharePoint.Client.PropertyInformation::set_PropertyTypeFullName(string value)
0x4043  ldloc.0
0x4044  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Client.TypeInformation::get_Properties()
0x4049  ldloc.s  8
0x404b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.PropertyInformation>::Add(var<u1>)
0x4050  br.s     loc_4082
0x4052  ldarg.2
0x4053  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x4058  ldc.i4   0x21C61D
0x405d  ldc.i4.1
0x405e  ldstr    aCannotGetTypeN_0// "Cannot get type name for {0}"
0x4063  ldc.i4.1
0x4064  newarr   [mscorlib]System.Object
0x4069  stloc.s  0x15
0x406b  ldloc.s  0x15
0x406d  ldc.i4.0
0x406e  ldarg.1
0x406f  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_CollectionChildItemType()
0x4074  stelem.ref
0x4075  ldloc.s  0x15
0x4077  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x407c  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor()
0x4081  throw
0x4082  ldarg.1
0x4083  ldarg.2
0x4084  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Client.ServerStub::GetAllMethodInfos(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4089  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.MethodInformation>::get_Values()
0x408e  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x4093  stloc.s  0x16
0x4095  br       loc_4122
0x409a  ldloca.s 0x16
0x409c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x40a1  stloc.s  9
0x40a3  ldloc.s  9
0x40a5  callvirt instance valuetype Microsoft.SharePoint.Client.ClientLibraryTargets Microsoft.SharePoint.Client.MethodInformation::get_ClientLibraryTargets()
0x40aa  ldc.i4.8
0x40ab  and
0x40ac  brfalse.s loc_4122
0x40ae  ldloc.s  9
0x40b0  callvirt instance bool Microsoft.SharePoint.Client.MethodInformation::get_IsStatic()
0x40b5  brtrue.s loc_4122
0x40b7  ldloc.s  9
0x40b9  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x40be  ldstr    aCtor_0// ".ctor"
0x40c3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x40c8  brfalse.s loc_4122
0x40ca  ldloc.s  9
0x40cc  callvirt instance class Microsoft.SharePoint.Client.MethodInformation Microsoft.SharePoint.Client.MethodInformation::CloneAndKeepAllParameters()
0x40d1  stloc.s  0xA
0x40d3  ldarg.0
0x40d4  ldloc.s  0xA
0x40d6  ldarg.2
0x40d7  call     instance bool Microsoft.SharePoint.Client.ApiMetadataBuilder::UpdateParameterAndReturnTypeName(class Microsoft.SharePoint.Client.MethodInformation methodInfo, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x40dc  brfalse.s loc_40ED
0x40de  ldloc.0
0x40df  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Client.TypeInformation::get_Methods()
0x40e4  ldloc.s  0xA
0x40e6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.MethodInformation>::Add(var<u1>)
0x40eb  br.s     loc_4122
0x40ed  ldarg.2
0x40ee  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x40f3  ldc.i4   0x21C61E
0x40f8  ldc.i4.2
0x40f9  ldstr    aMethod0InType1// "Method {0} in type {1} is not supported"...
0x40fe  ldc.i4.2
0x40ff  newarr   [mscorlib]System.Object
0x4104  stloc.s  0x17
0x4106  ldloc.s  0x17
0x4108  ldc.i4.0
0x4109  ldloc.s  0xA
0x410b  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x4110  stelem.ref
0x4111  ldloc.s  0x17
0x4113  ldc.i4.1
0x4114  ldarg.1
0x4115  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x411a  stelem.ref
0x411b  ldloc.s  0x17
0x411d  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4122  ldloca.s 0x16
0x4124  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>::MoveNext()
0x4129  brtrue   loc_409A
0x412e  leave.s  loc_413E
0x4130  ldloca.s 0x16
0x4132  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.SharePoint.Client.MethodInformation>
0x4138  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x413d  endfinally
0x413e  ldarg.1
0x413f  ldarg.2
0x4140  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ServerStub> Microsoft.SharePoint.Client.ServerStub::GetAllExtensionMethodTypes(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4145  stloc.s  0xB
0x4147  ldloc.s  0xB
0x4149  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>::get_Keys()
0x414e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x4153  stloc.s  0x18
0x4155  br       loc_4267
0x415a  ldloc.s  0x18
0x415c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x4161  stloc.s  0xC
0x4163  ldnull
0x4164  stloc.s  0xE
0x4166  newobj   instance void <>c__DisplayClass2::.ctor()
0x416b  stloc.s  0xF
0x416d  ldloc.s  0xB
0x416f  ldloc.s  0xC
0x4171  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ServerStub>::get_Item(void)
0x4176  ldloc.s  0xC
0x4178  ldarg.2
0x4179  ldloc.s  0xF
0x417b  ldflda   class Microsoft.SharePoint.Client.MethodInformation <>c__DisplayClass2::methodInfo
0x4180  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::TryGetMethodInfo(string name, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [out] class Microsoft.SharePoint.Client.MethodInformation& method)
0x4185  brfalse  loc_4267
0x418a  ldloc.0
0x418b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Client.TypeInformation::get_Methods()
0x4190  ldloc.s  0xE
0x4192  brtrue.s loc_41A3
0x4194  ldloc.s  0xF
0x4196  ldftn    instance bool <>c__DisplayClass2::<BuildTypeInformation>b__0(class Microsoft.SharePoint.Client.MethodInformation m)
0x419c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Client.MethodInformation, bool>::.ctor(object, native int)
0x41a1  stloc.s  0xE
0x41a3  ldloc.s  0xE
0x41a5  call     T0x2B00000C
0x41aa  brfalse.s loc_41FA
  ... truncated ...
```
