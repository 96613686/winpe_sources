# Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntity

- ea: `0x1f820`
- end: `0x1faad`
- name: `Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntity`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1f7c0`

## callees

- `0xa30`
- `0xa50`
- `0xba0`
- `0x2930`
- `0x2c20`
- `0xe080`
- `0xe110`
- `0xe6c0`
- `0x15030`
- `0x15200`
- `0x152f0`
- `0x18670`
- `0x1d4a0`
- `0x1d670`
- `0x1d680`
- `0x1f380`
- `0x1f820`
- `0x1fab0`
- `0x1fc70`
- `0x1fca0`

## string_xrefs

- `0x1f99a`: `_WriteAsEntity`
- `0x1f864`: `_GetObjectUrlPath`

## pseudocode

```c

```

## disassembly

```asm
0x1f820  ldarg.1
0x1f821  ldarg.0
0x1f822  ldarg.s  4
0x1f824  callvirt instance void Microsoft.SharePoint.Client.ServerStub::OnRESTfulQuerying(object obj, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x1f829  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::.ctor()
0x1f82e  stloc.0
0x1f82f  ldarg.s  5
0x1f831  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x1f836  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x1f83b  brfalse.s loc_1F847
0x1f83d  ldloc.0
0x1f83e  ldarg.0
0x1f83f  ldarg.s  5
0x1f841  ldnull
0x1f842  call     void Microsoft.SharePoint.Client.Rest.JsonLightUtility::LightupJsonLightWriter(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataItem item, object entity, class Microsoft.SharePoint.Client.ProxyContext proxyContext, string expectedTypeName)
0x1f847  ldarg.2
0x1f848  ldnull
0x1f849  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1f84e  brfalse.s loc_1F899
0x1f850  call     bool Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1f855  brfalse.s loc_1F890
0x1f857  ldarg.s  5
0x1f859  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f85e  ldarg.1
0x1f85f  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1f864  ldstr    aGetobjecturlpa// "_GetObjectUrlPath"
0x1f869  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName)
0x1f86e  stloc.1
0x1f86f  ldarg.1
0x1f870  ldarg.0
0x1f871  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ServerStub::GetObjectUrlPath(object target)
0x1f876  starg.s  2
0x1f878  leave.s  loc_1F884
0x1f87a  stloc.2
0x1f87b  ldloc.1
0x1f87c  ldloc.2
0x1f87d  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x1f882  rethrow
0x1f884  leave.s  loc_1F899
0x1f886  ldloc.1
0x1f887  brfalse.s loc_1F88F
0x1f889  ldloc.1
0x1f88a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f88f  endfinally
0x1f890  ldarg.1
0x1f891  ldarg.0
0x1f892  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ServerStub::GetObjectUrlPath(object target)
0x1f897  starg.s  2
0x1f899  ldarg.2
0x1f89a  ldnull
0x1f89b  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1f8a0  brfalse.s loc_1F8C9
0x1f8a2  ldarg.1
0x1f8a3  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x1f8a8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1f8ad  stloc.s  9
0x1f8af  ldloca.s 9
0x1f8b1  constrained. [mscorlib]System.Guid
0x1f8b7  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8bc  call     string [mscorlib]System.String::Concat(string, string)
0x1f8c1  ldc.i4.2
0x1f8c2  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1f8c7  starg.s  2
0x1f8c9  ldloc.0
0x1f8ca  ldarg.s  5
0x1f8cc  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f8d1  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x1f8d6  ldarg.2
0x1f8d7  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8dc  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x1f8e1  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8e6  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Id(string)
0x1f8eb  ldloc.0
0x1f8ec  ldarg.2
0x1f8ed  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_EditLink(class [System]System.Uri)
0x1f8f2  ldloc.0
0x1f8f3  ldarg.1
0x1f8f4  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x1f8f9  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_TypeName(string)
0x1f8fe  ldarg.s  5
0x1f900  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x1f905  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::ShouldAddTypeNameAnnotation(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x1f90a  brfalse.s loc_1F925
0x1f90c  ldloc.0
0x1f90d  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.SerializationTypeNameAnnotation::.ctor()
0x1f912  stloc.3
0x1f913  ldloc.3
0x1f914  ldarg.1
0x1f915  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x1f91a  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.SerializationTypeNameAnnotation::set_TypeName(string)
0x1f91f  ldloc.3
0x1f920  callvirt T0x2B000008
0x1f925  ldnull
0x1f926  stloc.s  4
0x1f928  call     bool Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1f92d  brfalse.s loc_1F96E
0x1f92f  ldarg.s  5
0x1f931  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f936  ldarg.1
0x1f937  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1f93c  ldstr    aGetetag// "_GetETag"
0x1f941  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName)
0x1f946  stloc.s  5
0x1f948  ldarg.1
0x1f949  ldarg.0
0x1f94a  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x1f94f  stloc.s  4
0x1f951  leave.s  loc_1F960
0x1f953  stloc.s  6
0x1f955  ldloc.s  5
0x1f957  ldloc.s  6
0x1f959  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x1f95e  rethrow
0x1f960  leave.s  loc_1F977
0x1f962  ldloc.s  5
0x1f964  brfalse.s loc_1F96D
0x1f966  ldloc.s  5
0x1f968  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f96d  endfinally
0x1f96e  ldarg.1
0x1f96f  ldarg.0
0x1f970  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x1f975  stloc.s  4
0x1f977  ldloc.s  4
0x1f979  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f97e  brtrue.s loc_1F988
0x1f980  ldloc.0
0x1f981  ldloc.s  4
0x1f983  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_ETag(string)
0x1f988  call     bool Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1f98d  brfalse  loc_1FA34
0x1f992  ldarg.s  5
0x1f994  ldarg.1
0x1f995  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1f99a  ldstr    aWriteasentity// "_WriteAsEntity"
0x1f99f  call     string Microsoft.SharePoint.Client.Utility::GetMonitoredScopeName(class [mscorlib]System.Type type, string memberName)
0x1f9a4  callvirt instance class [mscorlib]System.IDisposable Microsoft.SharePoint.Client.ProxyContext::CreatePerformanceMarkerScope(string scopeName)
0x1f9a9  stloc.s  0xA
0x1f9ab  ldloc.0
0x1f9ac  ldarg.0
0x1f9ad  ldarg.1
0x1f9ae  ldarg.s  4
0x1f9b0  ldarg.s  5
0x1f9b2  ldc.i4.1
0x1f9b3  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::GetODataScalarProperties(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, bool includeExpandoField)
0x1f9b8  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty>)
0x1f9bd  ldarg.0
0x1f9be  ldarg.1
0x1f9bf  ldarg.s  5
0x1f9c1  ldarg.s  4
0x1f9c3  ldftn    instance bool Microsoft.SharePoint.Client.RESTfulQuery::ShouldSelectProperty(string propName)
0x1f9c9  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x1f9ce  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::GetODataInstanceAnnotations(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [opt] class [mscorlib]System.Func`2<string, bool> shouldReturnAnnotation)
0x1f9d3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::GetEnumerator()
0x1f9d8  stloc.s  0xB
0x1f9da  br.s     loc_1F9F2
0x1f9dc  ldloc.s  0xB
0x1f9de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::get_Current()
0x1f9e3  stloc.s  7
0x1f9e5  ldloc.0
0x1f9e6  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::get_InstanceAnnotations()
0x1f9eb  ldloc.s  7
0x1f9ed  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x1f9f2  ldloc.s  0xB
0x1f9f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f9f9  brtrue.s loc_1F9DC
0x1f9fb  leave.s  loc_1FA09
0x1f9fd  ldloc.s  0xB
0x1f9ff  brfalse.s loc_1FA08
0x1fa01  ldloc.s  0xB
0x1fa03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fa08  endfinally
0x1fa09  ldarg.3
0x1fa0a  ldloc.0
0x1fa0b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry)
0x1fa10  ldarg.0
0x1fa11  ldarg.1
0x1fa12  ldarg.2
0x1fa13  ldarg.3
0x1fa14  ldarg.s  4
0x1fa16  ldarg.s  5
0x1fa18  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteNavigationProperties(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1fa1d  ldarg.3
0x1fa1e  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x1fa23  leave    loc_1FAAC
0x1fa28  ldloc.s  0xA
0x1fa2a  brfalse.s loc_1FA33
0x1fa2c  ldloc.s  0xA
0x1fa2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fa33  endfinally
0x1fa34  ldloc.0
0x1fa35  ldarg.0
0x1fa36  ldarg.1
0x1fa37  ldarg.s  4
0x1fa39  ldarg.s  5
0x1fa3b  ldc.i4.1
0x1fa3c  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::GetODataScalarProperties(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, bool includeExpandoField)
0x1fa41  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty>)
0x1fa46  ldarg.0
0x1fa47  ldarg.1
0x1fa48  ldarg.s  5
0x1fa4a  ldarg.s  4
0x1fa4c  ldftn    instance bool Microsoft.SharePoint.Client.RESTfulQuery::ShouldSelectProperty(string propName)
0x1fa52  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x1fa57  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::GetODataInstanceAnnotations(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class Microsoft.SharePoint.Client.ProxyContext proxyContext, [opt] class [mscorlib]System.Func`2<string, bool> shouldReturnAnnotation)
0x1fa5c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::GetEnumerator()
0x1fa61  stloc.s  0xC
0x1fa63  br.s     loc_1FA7B
0x1fa65  ldloc.s  0xC
0x1fa67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::get_Current()
0x1fa6c  stloc.s  8
0x1fa6e  ldloc.0
0x1fa6f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation> [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::get_InstanceAnnotations()
0x1fa74  ldloc.s  8
0x1fa76  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataInstanceAnnotation>::Add(var<u1>)
0x1fa7b  ldloc.s  0xC
0x1fa7d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fa82  brtrue.s loc_1FA65
0x1fa84  leave.s  loc_1FA92
0x1fa86  ldloc.s  0xC
0x1fa88  brfalse.s loc_1FA91
0x1fa8a  ldloc.s  0xC
0x1fa8c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fa91  endfinally
0x1fa92  ldarg.3
0x1fa93  ldloc.0
0x1fa94  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry)
0x1fa99  ldarg.0
0x1fa9a  ldarg.1
0x1fa9b  ldarg.2
0x1fa9c  ldarg.3
0x1fa9d  ldarg.s  4
0x1fa9f  ldarg.s  5
0x1faa1  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteNavigationProperties(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1faa6  ldarg.3
0x1faa7  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x1faac  ret
```
