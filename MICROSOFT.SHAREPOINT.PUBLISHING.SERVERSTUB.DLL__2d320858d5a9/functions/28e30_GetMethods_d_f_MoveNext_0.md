# <GetMethods>d__f::MoveNext_0

- ea: `0x28e30`
- end: `0x298af`
- name: `<GetMethods>d__f::MoveNext_0`
- size: `2687`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x11630`
- `0x28e30`
- `0x298d0`
- `0x29930`

## string_xrefs

- `0x297dd`: `Update`
- `0x29811`: `Update`
- `0x294d8`: `CanCreatePromotedPage`
- `0x2950c`: `CanCreatePromotedPage`

## pseudocode

```c

```

## disassembly

```asm
0x28e30  ldarg.0
0x28e31  ldfld    int32 <GetMethods>d__f::<>1__state
0x28e36  stloc.1
0x28e37  ldloc.1
0x28e38  switch   loc_28E6A, loc_298A2, loc_28ED4, loc_28FBB, loc_29202, loc_294BF, loc_29598, loc_296EB, loc_297C4, loc_2989B
0x28e65  br       loc_298A2
0x28e6a  ldarg.0
0x28e6b  ldc.i4.m1
0x28e6c  stfld    int32 <GetMethods>d__f::<>1__state
0x28e71  ldarg.0
0x28e72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x28e77  brtrue.s loc_28E84
0x28e79  ldstr    aProxycontext// "proxyContext"
0x28e7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28e83  throw
0x28e84  ldarg.0
0x28e85  ldarg.0
0x28e86  ldfld    class Microsoft.SharePoint.Publishing.SitePageServiceServerStub <GetMethods>d__f::<>4__this
0x28e8b  ldarg.0
0x28e8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__f::proxyContext
0x28e91  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.SitePageServiceServerStub::<>n__FabricatedMethod14(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x28e96  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x28e9b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x28ea0  ldarg.0
0x28ea1  ldc.i4.1
0x28ea2  stfld    int32 <GetMethods>d__f::<>1__state
0x28ea7  br.s     loc_28EDB
0x28ea9  ldarg.0
0x28eaa  ldarg.0
0x28eab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x28eb0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x28eb5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x28eba  ldarg.0
0x28ebb  ldarg.0
0x28ebc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<itemBase>5__10
0x28ec1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x28ec6  ldarg.0
0x28ec7  ldc.i4.2
0x28ec8  stfld    int32 <GetMethods>d__f::<>1__state
0x28ecd  ldc.i4.1
0x28ece  stloc.0
0x28ecf  leave    loc_298AD
0x28ed4  ldarg.0
0x28ed5  ldc.i4.1
0x28ed6  stfld    int32 <GetMethods>d__f::<>1__state
0x28edb  ldarg.0
0x28edc  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__f::<>7__wrap12
0x28ee1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x28ee6  brtrue.s loc_28EA9
0x28ee8  ldarg.0
0x28ee9  call     instance void <GetMethods>d__f::<>m__Finally13()
0x28eee  ldarg.0
0x28eef  ldarg.0
0x28ef0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x28ef5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28efa  ldarg.0
0x28efb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f00  ldstr    aCtor// ".ctor"
0x28f05  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x28f0a  ldarg.0
0x28f0b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f10  ldc.i4.0
0x28f11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x28f16  ldarg.0
0x28f17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f1c  ldc.i4.0
0x28f1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x28f22  ldarg.0
0x28f23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f28  ldc.i4   0xFFFFFFF
0x28f2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x28f32  ldarg.0
0x28f33  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f38  ldstr    aCtor// ".ctor"
0x28f3d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x28f42  ldarg.0
0x28f43  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f48  ldc.i4.0
0x28f49  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x28f4e  ldarg.0
0x28f4f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f54  ldnull
0x28f55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x28f5a  ldarg.0
0x28f5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f60  ldc.i4.0
0x28f61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x28f66  ldarg.0
0x28f67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f6c  ldc.i4.0
0x28f6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x28f72  ldarg.0
0x28f73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f78  ldc.i4.0
0x28f79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x28f7e  ldarg.0
0x28f7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f84  ldc.i4.0
0x28f85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x28f8a  ldarg.0
0x28f8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f90  ldc.i4.1
0x28f91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x28f96  ldarg.0
0x28f97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal0
0x28f9c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x28fa1  ldarg.0
0x28fa2  ldarg.0
0x28fa3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x28fa8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x28fad  ldarg.0
0x28fae  ldc.i4.3
0x28faf  stfld    int32 <GetMethods>d__f::<>1__state
0x28fb4  ldc.i4.1
0x28fb5  stloc.0
0x28fb6  leave    loc_298AD
0x28fbb  ldarg.0
0x28fbc  ldc.i4.m1
0x28fbd  stfld    int32 <GetMethods>d__f::<>1__state
0x28fc2  ldarg.0
0x28fc3  ldarg.0
0x28fc4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x28fc9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x28fce  ldarg.0
0x28fcf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x28fd4  ldstr    aAddimage// "AddImage"
0x28fd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x28fde  ldarg.0
0x28fdf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x28fe4  ldc.i4.0
0x28fe5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x28fea  ldarg.0
0x28feb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x28ff0  ldc.i4.0
0x28ff1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x28ff6  ldarg.0
0x28ff7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x28ffc  ldc.i4.8
0x28ffd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x29002  ldarg.0
0x29003  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29008  ldstr    aAddimage// "AddImage"
0x2900d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x29012  ldarg.0
0x29013  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29018  ldc.i4.0
0x29019  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x2901e  ldarg.0
0x2901f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29024  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x29029  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2902e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x29033  ldarg.0
0x29034  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29039  ldc.i4.4
0x2903a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2903f  ldarg.0
0x29040  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29045  ldc.i4.0
0x29046  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x2904b  ldarg.0
0x2904c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29051  ldc.i4.0
0x29052  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x29057  ldarg.0
0x29058  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x2905d  ldc.i4.0
0x2905e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x29063  ldarg.0
0x29064  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29069  ldc.i4.1
0x2906a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x2906f  ldarg.0
0x29070  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal1
0x29075  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x2907a  ldarg.0
0x2907b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x29080  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x29085  ldarg.0
0x29086  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2908b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x29090  ldarg.0
0x29091  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x29096  ldstr    aPagename// "pageName"
0x2909b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x290a0  ldarg.0
0x290a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290a6  ldc.i4.1
0x290a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x290ac  ldarg.0
0x290ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290b2  ldtoken  [mscorlib]System.String
0x290b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x290bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x290c1  ldarg.0
0x290c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290c7  ldc.i4.1
0x290c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x290cd  ldarg.0
0x290ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290d3  ldc.i4.0
0x290d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x290d9  ldarg.0
0x290da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290df  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x290e4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x290e9  ldarg.0
0x290ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal2
0x290ef  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x290f4  ldarg.0
0x290f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x290fa  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x290ff  ldarg.0
0x29100  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x29105  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x2910a  ldarg.0
0x2910b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x29110  ldstr    aImagefilename// "imageFileName"
0x29115  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2911a  ldarg.0
0x2911b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x29120  ldc.i4.1
0x29121  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x29126  ldarg.0
0x29127  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x2912c  ldtoken  [mscorlib]System.String
0x29131  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29136  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x2913b  ldarg.0
0x2913c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x29141  ldc.i4.1
0x29142  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x29147  ldarg.0
0x29148  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x2914d  ldc.i4.0
0x2914e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x29153  ldarg.0
0x29154  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x29159  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2915e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x29163  ldarg.0
0x29164  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal3
0x29169  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x2916e  ldarg.0
0x2916f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x29174  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x29179  ldarg.0
0x2917a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2917f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x29184  ldarg.0
0x29185  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x2918a  ldstr    aImagestream// "imageStream"
0x2918f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x29194  ldarg.0
0x29195  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x2919a  ldc.i4.0
0x2919b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x291a0  ldarg.0
0x291a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x291a6  ldtoken  [mscorlib]System.IO.Stream
0x291ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x291b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x291b5  ldarg.0
0x291b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x291bb  ldc.i4.0
0x291bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x291c1  ldarg.0
0x291c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x291c7  ldc.i4.0
0x291c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x291cd  ldarg.0
0x291ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x291d3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x291d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x291dd  ldarg.0
0x291de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__f::<>g__initLocal4
0x291e3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x291e8  ldarg.0
0x291e9  ldarg.0
0x291ea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<item>5__11
0x291ef  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>2__current
0x291f4  ldarg.0
0x291f5  ldc.i4.4
0x291f6  stfld    int32 <GetMethods>d__f::<>1__state
0x291fb  ldc.i4.1
0x291fc  stloc.0
0x291fd  leave    loc_298AD
0x29202  ldarg.0
0x29203  ldc.i4.m1
0x29204  stfld    int32 <GetMethods>d__f::<>1__state
0x29209  ldarg.0
0x2920a  ldarg.0
0x2920b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x29210  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal5
0x29215  ldarg.0
0x29216  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal5
0x2921b  ldstr    aAddimagefromex// "AddImageFromExternalUrl"
0x29220  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x29225  ldarg.0
0x29226  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__f::<>g__initLocal5
  ... truncated ...
```
