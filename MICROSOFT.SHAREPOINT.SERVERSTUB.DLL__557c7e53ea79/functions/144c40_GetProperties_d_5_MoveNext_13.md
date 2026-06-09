# <GetProperties>d__5::MoveNext_13

- ea: `0x144c40`
- end: `0x14514f`
- name: `<GetProperties>d__5::MoveNext_13`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x687d0`
- `0x144c40`
- `0x145170`
- `0x1451d0`

## string_xrefs

- `0x144d08`: `BaseTemplate`
- `0x144d7a`: `BaseTemplate`
- `0x144ebf`: `SchemaXml`
- `0x144f2c`: `SchemaXml`
- `0x144f98`: `TemplateFeatureId`
- `0x145012`: `TemplateFeatureId`

## pseudocode

```c

```

## disassembly

```asm
0x144c40  ldarg.0
0x144c41  ldfld    int32 <GetProperties>d__5::<>1__state
0x144c46  stloc.1
0x144c47  ldloc.1
0x144c48  switch   loc_144C72, loc_145142, loc_144CDC, loc_144DCD, loc_144EA6, loc_144F7F, loc_145065, loc_14513B
0x144c6d  br       loc_145142
0x144c72  ldarg.0
0x144c73  ldc.i4.m1
0x144c74  stfld    int32 <GetProperties>d__5::<>1__state
0x144c79  ldarg.0
0x144c7a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x144c7f  brtrue.s loc_144C8C
0x144c81  ldstr    aProxycontext// "proxyContext"
0x144c86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x144c8b  throw
0x144c8c  ldarg.0
0x144c8d  ldarg.0
0x144c8e  ldfld    class Microsoft.SharePoint.ServerStub.SPListEntityDataValueTypeConverter <GetProperties>d__5::<>4__this
0x144c93  ldarg.0
0x144c94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__5::proxyContext
0x144c99  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPListEntityDataValueTypeConverter::<>n__FabricatedMethod9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x144c9e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x144ca3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x144ca8  ldarg.0
0x144ca9  ldc.i4.1
0x144caa  stfld    int32 <GetProperties>d__5::<>1__state
0x144caf  br.s     loc_144CE3
0x144cb1  ldarg.0
0x144cb2  ldarg.0
0x144cb3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x144cb8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x144cbd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x144cc2  ldarg.0
0x144cc3  ldarg.0
0x144cc4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<item>5__6
0x144cc9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x144cce  ldarg.0
0x144ccf  ldc.i4.2
0x144cd0  stfld    int32 <GetProperties>d__5::<>1__state
0x144cd5  ldc.i4.1
0x144cd6  stloc.0
0x144cd7  leave    loc_14514D
0x144cdc  ldarg.0
0x144cdd  ldc.i4.1
0x144cde  stfld    int32 <GetProperties>d__5::<>1__state
0x144ce3  ldarg.0
0x144ce4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__5::<>7__wrap7
0x144ce9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x144cee  brtrue.s loc_144CB1
0x144cf0  ldarg.0
0x144cf1  call     instance void <GetProperties>d__5::<>m__Finally8()
0x144cf6  ldarg.0
0x144cf7  ldarg.0
0x144cf8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x144cfd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d02  ldarg.0
0x144d03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d08  ldstr    aBasetemplate// "BaseTemplate"
0x144d0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x144d12  ldarg.0
0x144d13  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d18  ldc.i4.0
0x144d19  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x144d1e  ldarg.0
0x144d1f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d24  ldc.i4.1
0x144d25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x144d2a  ldarg.0
0x144d2b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d30  ldc.i4.0
0x144d31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x144d36  ldarg.0
0x144d37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d3c  ldtoken  [mscorlib]System.Int32
0x144d41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144d46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x144d4b  ldarg.0
0x144d4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d51  ldc.i4.0
0x144d52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x144d57  ldarg.0
0x144d58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d5d  ldc.i4.1
0x144d5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x144d63  ldarg.0
0x144d64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d69  ldc.i4.0
0x144d6a  box      [mscorlib]System.Int32
0x144d6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x144d74  ldarg.0
0x144d75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d7a  ldstr    aBasetemplate// "BaseTemplate"
0x144d7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x144d84  ldarg.0
0x144d85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d8a  ldnull
0x144d8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x144d90  ldarg.0
0x144d91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144d96  ldc.i4.0
0x144d97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x144d9c  ldarg.0
0x144d9d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144da2  ldc.i4.0
0x144da3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x144da8  ldarg.0
0x144da9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144dae  ldc.i4.0
0x144daf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x144db4  ldarg.0
0x144db5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal0
0x144dba  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x144dbf  ldarg.0
0x144dc0  ldc.i4.3
0x144dc1  stfld    int32 <GetProperties>d__5::<>1__state
0x144dc6  ldc.i4.1
0x144dc7  stloc.0
0x144dc8  leave    loc_14514D
0x144dcd  ldarg.0
0x144dce  ldc.i4.m1
0x144dcf  stfld    int32 <GetProperties>d__5::<>1__state
0x144dd4  ldarg.0
0x144dd5  ldarg.0
0x144dd6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x144ddb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144de0  ldarg.0
0x144de1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144de6  ldstr    aDescription// "Description"
0x144deb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x144df0  ldarg.0
0x144df1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144df6  ldc.i4.0
0x144df7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x144dfc  ldarg.0
0x144dfd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e02  ldc.i4.1
0x144e03  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x144e08  ldarg.0
0x144e09  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e0e  ldc.i4.0
0x144e0f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x144e14  ldarg.0
0x144e15  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e1a  ldtoken  [mscorlib]System.String
0x144e1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144e24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x144e29  ldarg.0
0x144e2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e2f  ldc.i4.0
0x144e30  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x144e35  ldarg.0
0x144e36  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e3b  ldc.i4.1
0x144e3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x144e41  ldarg.0
0x144e42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e47  ldnull
0x144e48  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x144e4d  ldarg.0
0x144e4e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e53  ldstr    aDescription// "Description"
0x144e58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x144e5d  ldarg.0
0x144e5e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e63  ldnull
0x144e64  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x144e69  ldarg.0
0x144e6a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e6f  ldc.i4.0
0x144e70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x144e75  ldarg.0
0x144e76  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e7b  ldc.i4.0
0x144e7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x144e81  ldarg.0
0x144e82  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e87  ldc.i4.0
0x144e88  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x144e8d  ldarg.0
0x144e8e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal1
0x144e93  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x144e98  ldarg.0
0x144e99  ldc.i4.4
0x144e9a  stfld    int32 <GetProperties>d__5::<>1__state
0x144e9f  ldc.i4.1
0x144ea0  stloc.0
0x144ea1  leave    loc_14514D
0x144ea6  ldarg.0
0x144ea7  ldc.i4.m1
0x144ea8  stfld    int32 <GetProperties>d__5::<>1__state
0x144ead  ldarg.0
0x144eae  ldarg.0
0x144eaf  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x144eb4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144eb9  ldarg.0
0x144eba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144ebf  ldstr    aSchemaxml// "SchemaXml"
0x144ec4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x144ec9  ldarg.0
0x144eca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144ecf  ldc.i4.0
0x144ed0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x144ed5  ldarg.0
0x144ed6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144edb  ldc.i4.1
0x144edc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x144ee1  ldarg.0
0x144ee2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144ee7  ldc.i4.0
0x144ee8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x144eed  ldarg.0
0x144eee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144ef3  ldtoken  [mscorlib]System.String
0x144ef8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144efd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x144f02  ldarg.0
0x144f03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f08  ldc.i4.0
0x144f09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x144f0e  ldarg.0
0x144f0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f14  ldc.i4.1
0x144f15  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x144f1a  ldarg.0
0x144f1b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f20  ldnull
0x144f21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x144f26  ldarg.0
0x144f27  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f2c  ldstr    aSchemaxml// "SchemaXml"
0x144f31  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x144f36  ldarg.0
0x144f37  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f3c  ldnull
0x144f3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x144f42  ldarg.0
0x144f43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f48  ldc.i4.0
0x144f49  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x144f4e  ldarg.0
0x144f4f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f54  ldc.i4.0
0x144f55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x144f5a  ldarg.0
0x144f5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f60  ldc.i4.0
0x144f61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x144f66  ldarg.0
0x144f67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal2
0x144f6c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>2__current
0x144f71  ldarg.0
0x144f72  ldc.i4.5
0x144f73  stfld    int32 <GetProperties>d__5::<>1__state
0x144f78  ldc.i4.1
0x144f79  stloc.0
0x144f7a  leave    loc_14514D
0x144f7f  ldarg.0
0x144f80  ldc.i4.m1
0x144f81  stfld    int32 <GetProperties>d__5::<>1__state
0x144f86  ldarg.0
0x144f87  ldarg.0
0x144f88  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x144f8d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144f92  ldarg.0
0x144f93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144f98  ldstr    aTemplatefeatur// "TemplateFeatureId"
0x144f9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x144fa2  ldarg.0
0x144fa3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fa8  ldc.i4.0
0x144fa9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x144fae  ldarg.0
0x144faf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fb4  ldc.i4.1
0x144fb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x144fba  ldarg.0
0x144fbb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fc0  ldc.i4.0
0x144fc1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x144fc6  ldarg.0
0x144fc7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fcc  ldtoken  [mscorlib]System.Guid
0x144fd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144fd6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x144fdb  ldarg.0
0x144fdc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fe1  ldc.i4.0
0x144fe2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x144fe7  ldarg.0
0x144fe8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144fed  ldc.i4.1
0x144fee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x144ff3  ldarg.0
0x144ff4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__5::<>g__initLocal3
0x144ff9  ldloca.s 2
0x144ffb  initobj  [mscorlib]System.Guid
0x145001  ldloc.2
0x145002  box      [mscorlib]System.Guid
0x145007  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14500c  ldarg.0
  ... truncated ...
```
