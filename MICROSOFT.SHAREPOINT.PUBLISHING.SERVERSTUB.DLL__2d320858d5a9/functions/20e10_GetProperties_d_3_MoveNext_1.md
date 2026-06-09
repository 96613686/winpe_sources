# <GetProperties>d__3::MoveNext_1

- ea: `0x20e10`
- end: `0x21153`
- name: `<GetProperties>d__3::MoveNext_1`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb190`
- `0x20e10`
- `0x21180`
- `0x211e0`

## pseudocode

```c

```

## disassembly

```asm
0x20e10  ldarg.0
0x20e11  ldfld    int32 <GetProperties>d__3::<>1__state
0x20e16  stloc.1
0x20e17  ldloc.1
0x20e18  switch   loc_20E3A, loc_21146, loc_20EA4, loc_20F90, loc_21069, loc_2113F
0x20e35  br       loc_21146
0x20e3a  ldarg.0
0x20e3b  ldc.i4.m1
0x20e3c  stfld    int32 <GetProperties>d__3::<>1__state
0x20e41  ldarg.0
0x20e42  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x20e47  brtrue.s loc_20E54
0x20e49  ldstr    aProxycontext// "proxyContext"
0x20e4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20e53  throw
0x20e54  ldarg.0
0x20e55  ldarg.0
0x20e56  ldfld    class Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub <GetProperties>d__3::<>4__this
0x20e5b  ldarg.0
0x20e5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__3::proxyContext
0x20e61  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.PrimaryCityTimeServerStub::<>n__FabricatedMethod7(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x20e66  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x20e6b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x20e70  ldarg.0
0x20e71  ldc.i4.1
0x20e72  stfld    int32 <GetProperties>d__3::<>1__state
0x20e77  br.s     loc_20EAB
0x20e79  ldarg.0
0x20e7a  ldarg.0
0x20e7b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x20e80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x20e85  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x20e8a  ldarg.0
0x20e8b  ldarg.0
0x20e8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<item>5__4
0x20e91  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x20e96  ldarg.0
0x20e97  ldc.i4.2
0x20e98  stfld    int32 <GetProperties>d__3::<>1__state
0x20e9d  ldc.i4.1
0x20e9e  stloc.0
0x20e9f  leave    loc_21151
0x20ea4  ldarg.0
0x20ea5  ldc.i4.1
0x20ea6  stfld    int32 <GetProperties>d__3::<>1__state
0x20eab  ldarg.0
0x20eac  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__3::<>7__wrap5
0x20eb1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20eb6  brtrue.s loc_20E79
0x20eb8  ldarg.0
0x20eb9  call     instance void <GetProperties>d__3::<>m__Finally6()
0x20ebe  ldarg.0
0x20ebf  ldarg.0
0x20ec0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20ec5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20eca  ldarg.0
0x20ecb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20ed0  ldstr    aLocation// "Location"
0x20ed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x20eda  ldarg.0
0x20edb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20ee0  ldc.i4.0
0x20ee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20ee6  ldarg.0
0x20ee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20eec  ldc.i4.1
0x20eed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20ef2  ldarg.0
0x20ef3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20ef8  ldc.i4.0
0x20ef9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20efe  ldarg.0
0x20eff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f04  ldtoken  [mscorlib]System.String
0x20f09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20f0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x20f13  ldarg.0
0x20f14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f19  ldc.i4.0
0x20f1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20f1f  ldarg.0
0x20f20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f25  ldc.i4.1
0x20f26  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x20f2b  ldarg.0
0x20f2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f31  ldnull
0x20f32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x20f37  ldarg.0
0x20f38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f3d  ldstr    aLocation// "Location"
0x20f42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x20f47  ldarg.0
0x20f48  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f4d  ldnull
0x20f4e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x20f53  ldarg.0
0x20f54  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f59  ldc.i4.0
0x20f5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20f5f  ldarg.0
0x20f60  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f65  ldc.i4.0
0x20f66  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x20f6b  ldarg.0
0x20f6c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f71  ldc.i4.0
0x20f72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x20f77  ldarg.0
0x20f78  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal0
0x20f7d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x20f82  ldarg.0
0x20f83  ldc.i4.3
0x20f84  stfld    int32 <GetProperties>d__3::<>1__state
0x20f89  ldc.i4.1
0x20f8a  stloc.0
0x20f8b  leave    loc_21151
0x20f90  ldarg.0
0x20f91  ldc.i4.m1
0x20f92  stfld    int32 <GetProperties>d__3::<>1__state
0x20f97  ldarg.0
0x20f98  ldarg.0
0x20f99  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x20f9e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fa3  ldarg.0
0x20fa4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fa9  ldstr    aTime// "Time"
0x20fae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x20fb3  ldarg.0
0x20fb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fb9  ldc.i4.0
0x20fba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x20fbf  ldarg.0
0x20fc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fc5  ldc.i4.1
0x20fc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x20fcb  ldarg.0
0x20fcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fd1  ldc.i4.0
0x20fd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x20fd7  ldarg.0
0x20fd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20fdd  ldtoken  [mscorlib]System.String
0x20fe2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20fe7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x20fec  ldarg.0
0x20fed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20ff2  ldc.i4.0
0x20ff3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x20ff8  ldarg.0
0x20ff9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x20ffe  ldc.i4.1
0x20fff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x21004  ldarg.0
0x21005  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2100a  ldnull
0x2100b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x21010  ldarg.0
0x21011  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21016  ldstr    aTime// "Time"
0x2101b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x21020  ldarg.0
0x21021  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21026  ldnull
0x21027  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2102c  ldarg.0
0x2102d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21032  ldc.i4.0
0x21033  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21038  ldarg.0
0x21039  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2103e  ldc.i4.0
0x2103f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x21044  ldarg.0
0x21045  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x2104a  ldc.i4.0
0x2104b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21050  ldarg.0
0x21051  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal1
0x21056  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x2105b  ldarg.0
0x2105c  ldc.i4.4
0x2105d  stfld    int32 <GetProperties>d__3::<>1__state
0x21062  ldc.i4.1
0x21063  stloc.0
0x21064  leave    loc_21151
0x21069  ldarg.0
0x2106a  ldc.i4.m1
0x2106b  stfld    int32 <GetProperties>d__3::<>1__state
0x21070  ldarg.0
0x21071  ldarg.0
0x21072  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x21077  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2107c  ldarg.0
0x2107d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21082  ldstr    aUtcoffset// "UtcOffset"
0x21087  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2108c  ldarg.0
0x2108d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21092  ldc.i4.0
0x21093  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x21098  ldarg.0
0x21099  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2109e  ldc.i4.1
0x2109f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x210a4  ldarg.0
0x210a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210aa  ldc.i4.0
0x210ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x210b0  ldarg.0
0x210b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210b6  ldtoken  [mscorlib]System.String
0x210bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x210c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x210c5  ldarg.0
0x210c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210cb  ldc.i4.0
0x210cc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x210d1  ldarg.0
0x210d2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210d7  ldc.i4.1
0x210d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x210dd  ldarg.0
0x210de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210e3  ldnull
0x210e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x210e9  ldarg.0
0x210ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210ef  ldstr    aUtcoffset// "UtcOffset"
0x210f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x210f9  ldarg.0
0x210fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x210ff  ldnull
0x21100  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x21105  ldarg.0
0x21106  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2110b  ldc.i4.0
0x2110c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x21111  ldarg.0
0x21112  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21117  ldc.i4.0
0x21118  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2111d  ldarg.0
0x2111e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x21123  ldc.i4.0
0x21124  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x21129  ldarg.0
0x2112a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>g__initLocal2
0x2112f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__3::<>2__current
0x21134  ldarg.0
0x21135  ldc.i4.5
0x21136  stfld    int32 <GetProperties>d__3::<>1__state
0x2113b  ldc.i4.1
0x2113c  stloc.0
0x2113d  leave.s  loc_21151
0x2113f  ldarg.0
0x21140  ldc.i4.m1
0x21141  stfld    int32 <GetProperties>d__3::<>1__state
0x21146  ldc.i4.0
0x21147  stloc.0
0x21148  leave.s  loc_21151
0x2114a  ldarg.0
0x2114b  call     instance void <GetProperties>d__3::System.IDisposable.Dispose()
0x21150  endfinally
0x21151  ldloc.0
0x21152  ret
```
