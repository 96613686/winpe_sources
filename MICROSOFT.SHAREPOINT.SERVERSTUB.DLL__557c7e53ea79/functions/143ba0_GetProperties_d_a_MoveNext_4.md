# <GetProperties>d__a::MoveNext_4

- ea: `0x143ba0`
- end: `0x14450e`
- name: `<GetProperties>d__a::MoveNext_4`
- size: `2414`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x68100`
- `0x143ba0`
- `0x144530`
- `0x144590`

## string_xrefs

- `0x14419c`: `TemplateFeatureId`
- `0x144216`: `TemplateFeatureId`
- `0x143fe5`: `ListTemplate`
- `0x144052`: `ListTemplate`
- `0x143c7c`: `CustomSchemaXml`
- `0x143ce9`: `CustomSchemaXml`
- `0x143f07`: `DocumentTemplateType`
- `0x143f79`: `DocumentTemplateType`
- `0x144283`: `TemplateType`
- `0x1442f5`: `TemplateType`

## pseudocode

```c

```

## disassembly

```asm
0x143ba0  ldarg.0
0x143ba1  ldfld    int32 <GetProperties>d__a::<>1__state
0x143ba6  stloc.1
0x143ba7  ldloc.1
0x143ba8  switch   loc_143BE6, loc_144501, loc_143C50, loc_143D3C, loc_143E15, loc_143EEE, loc_143FCC, loc_1440A5, loc_144183, loc_14426A, loc_144349, loc_144423, loc_1444FA
0x143be1  br       loc_144501
0x143be6  ldarg.0
0x143be7  ldc.i4.m1
0x143be8  stfld    int32 <GetProperties>d__a::<>1__state
0x143bed  ldarg.0
0x143bee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__a::proxyContext
0x143bf3  brtrue.s loc_143C00
0x143bf5  ldstr    aProxycontext// "proxyContext"
0x143bfa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x143bff  throw
0x143c00  ldarg.0
0x143c01  ldarg.0
0x143c02  ldfld    class Microsoft.SharePoint.ServerStub.SPListCreationInformationValueTypeConverter <GetProperties>d__a::<>4__this
0x143c07  ldarg.0
0x143c08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__a::proxyContext
0x143c0d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPListCreationInformationValueTypeConverter::<>n__FabricatedMethode(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x143c12  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x143c17  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a::<>7__wrapc
0x143c1c  ldarg.0
0x143c1d  ldc.i4.1
0x143c1e  stfld    int32 <GetProperties>d__a::<>1__state
0x143c23  br.s     loc_143C57
0x143c25  ldarg.0
0x143c26  ldarg.0
0x143c27  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a::<>7__wrapc
0x143c2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x143c31  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<item>5__b
0x143c36  ldarg.0
0x143c37  ldarg.0
0x143c38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<item>5__b
0x143c3d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>2__current
0x143c42  ldarg.0
0x143c43  ldc.i4.2
0x143c44  stfld    int32 <GetProperties>d__a::<>1__state
0x143c49  ldc.i4.1
0x143c4a  stloc.0
0x143c4b  leave    loc_14450C
0x143c50  ldarg.0
0x143c51  ldc.i4.1
0x143c52  stfld    int32 <GetProperties>d__a::<>1__state
0x143c57  ldarg.0
0x143c58  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a::<>7__wrapc
0x143c5d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x143c62  brtrue.s loc_143C25
0x143c64  ldarg.0
0x143c65  call     instance void <GetProperties>d__a::<>m__Finallyd()
0x143c6a  ldarg.0
0x143c6b  ldarg.0
0x143c6c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x143c71  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143c76  ldarg.0
0x143c77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143c7c  ldstr    aCustomschemaxm// "CustomSchemaXml"
0x143c81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x143c86  ldarg.0
0x143c87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143c8c  ldc.i4.0
0x143c8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x143c92  ldarg.0
0x143c93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143c98  ldc.i4.1
0x143c99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x143c9e  ldarg.0
0x143c9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143ca4  ldc.i4.0
0x143ca5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x143caa  ldarg.0
0x143cab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143cb0  ldtoken  [mscorlib]System.String
0x143cb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x143cba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x143cbf  ldarg.0
0x143cc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143cc5  ldc.i4.0
0x143cc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x143ccb  ldarg.0
0x143ccc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143cd1  ldc.i4.1
0x143cd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x143cd7  ldarg.0
0x143cd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143cdd  ldnull
0x143cde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x143ce3  ldarg.0
0x143ce4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143ce9  ldstr    aCustomschemaxm// "CustomSchemaXml"
0x143cee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x143cf3  ldarg.0
0x143cf4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143cf9  ldnull
0x143cfa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x143cff  ldarg.0
0x143d00  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143d05  ldc.i4.0
0x143d06  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x143d0b  ldarg.0
0x143d0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143d11  ldc.i4.0
0x143d12  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x143d17  ldarg.0
0x143d18  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143d1d  ldc.i4.0
0x143d1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x143d23  ldarg.0
0x143d24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal0
0x143d29  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>2__current
0x143d2e  ldarg.0
0x143d2f  ldc.i4.3
0x143d30  stfld    int32 <GetProperties>d__a::<>1__state
0x143d35  ldc.i4.1
0x143d36  stloc.0
0x143d37  leave    loc_14450C
0x143d3c  ldarg.0
0x143d3d  ldc.i4.m1
0x143d3e  stfld    int32 <GetProperties>d__a::<>1__state
0x143d43  ldarg.0
0x143d44  ldarg.0
0x143d45  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x143d4a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d4f  ldarg.0
0x143d50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d55  ldstr    aDatasourceprop// "DataSourceProperties"
0x143d5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x143d5f  ldarg.0
0x143d60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d65  ldc.i4.0
0x143d66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x143d6b  ldarg.0
0x143d6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d71  ldc.i4.3
0x143d72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x143d77  ldarg.0
0x143d78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d7d  ldc.i4.0
0x143d7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x143d83  ldarg.0
0x143d84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d89  ldtoken  class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>
0x143d8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x143d93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x143d98  ldarg.0
0x143d99  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143d9e  ldc.i4.0
0x143d9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x143da4  ldarg.0
0x143da5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143daa  ldc.i4.1
0x143dab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x143db0  ldarg.0
0x143db1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143db6  ldnull
0x143db7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x143dbc  ldarg.0
0x143dbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143dc2  ldstr    aDatasourceprop// "DataSourceProperties"
0x143dc7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x143dcc  ldarg.0
0x143dcd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143dd2  ldnull
0x143dd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x143dd8  ldarg.0
0x143dd9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143dde  ldc.i4.0
0x143ddf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x143de4  ldarg.0
0x143de5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143dea  ldc.i4.0
0x143deb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x143df0  ldarg.0
0x143df1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143df6  ldc.i4.0
0x143df7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x143dfc  ldarg.0
0x143dfd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal1
0x143e02  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>2__current
0x143e07  ldarg.0
0x143e08  ldc.i4.4
0x143e09  stfld    int32 <GetProperties>d__a::<>1__state
0x143e0e  ldc.i4.1
0x143e0f  stloc.0
0x143e10  leave    loc_14450C
0x143e15  ldarg.0
0x143e16  ldc.i4.m1
0x143e17  stfld    int32 <GetProperties>d__a::<>1__state
0x143e1c  ldarg.0
0x143e1d  ldarg.0
0x143e1e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x143e23  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e28  ldarg.0
0x143e29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e2e  ldstr    aDescription// "Description"
0x143e33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x143e38  ldarg.0
0x143e39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e3e  ldc.i4.0
0x143e3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x143e44  ldarg.0
0x143e45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e4a  ldc.i4.1
0x143e4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x143e50  ldarg.0
0x143e51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e56  ldc.i4.0
0x143e57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x143e5c  ldarg.0
0x143e5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e62  ldtoken  [mscorlib]System.String
0x143e67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x143e6c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x143e71  ldarg.0
0x143e72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e77  ldc.i4.0
0x143e78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x143e7d  ldarg.0
0x143e7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e83  ldc.i4.1
0x143e84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x143e89  ldarg.0
0x143e8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e8f  ldnull
0x143e90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x143e95  ldarg.0
0x143e96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143e9b  ldstr    aDescription// "Description"
0x143ea0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x143ea5  ldarg.0
0x143ea6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143eab  ldnull
0x143eac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x143eb1  ldarg.0
0x143eb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143eb7  ldc.i4.0
0x143eb8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x143ebd  ldarg.0
0x143ebe  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143ec3  ldc.i4.0
0x143ec4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x143ec9  ldarg.0
0x143eca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143ecf  ldc.i4.0
0x143ed0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x143ed5  ldarg.0
0x143ed6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal2
0x143edb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>2__current
0x143ee0  ldarg.0
0x143ee1  ldc.i4.5
0x143ee2  stfld    int32 <GetProperties>d__a::<>1__state
0x143ee7  ldc.i4.1
0x143ee8  stloc.0
0x143ee9  leave    loc_14450C
0x143eee  ldarg.0
0x143eef  ldc.i4.m1
0x143ef0  stfld    int32 <GetProperties>d__a::<>1__state
0x143ef5  ldarg.0
0x143ef6  ldarg.0
0x143ef7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x143efc  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f01  ldarg.0
0x143f02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f07  ldstr    aDocumenttempla_3// "DocumentTemplateType"
0x143f0c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x143f11  ldarg.0
0x143f12  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f17  ldc.i4.0
0x143f18  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x143f1d  ldarg.0
0x143f1e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f23  ldc.i4.1
0x143f24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x143f29  ldarg.0
0x143f2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f2f  ldc.i4.0
0x143f30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x143f35  ldarg.0
0x143f36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f3b  ldtoken  [mscorlib]System.Int32
0x143f40  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x143f45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x143f4a  ldarg.0
0x143f4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f50  ldc.i4.0
0x143f51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x143f56  ldarg.0
0x143f57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f5c  ldc.i4.1
0x143f5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x143f62  ldarg.0
0x143f63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f68  ldc.i4.0
0x143f69  box      [mscorlib]System.Int32
0x143f6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x143f73  ldarg.0
0x143f74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a::<>g__initLocal3
0x143f79  ldstr    aDocumenttempla_3// "DocumentTemplateType"
0x143f7e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
  ... truncated ...
```
