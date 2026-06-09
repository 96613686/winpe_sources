# <GetProperties>d__c::MoveNext

- ea: `0x13eb0`
- end: `0x141f3`
- name: `<GetProperties>d__c::MoveNext`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x9e0`
- `0x13eb0`
- `0x14220`
- `0x14280`

## pseudocode

```c

```

## disassembly

```asm
0x13eb0  ldarg.0
0x13eb1  ldfld    int32 <GetProperties>d__c::<>1__state
0x13eb6  stloc.1
0x13eb7  ldloc.1
0x13eb8  switch   loc_13EDA, loc_141E6, loc_13F44, loc_14030, loc_14109, loc_141DF
0x13ed5  br       loc_141E6
0x13eda  ldarg.0
0x13edb  ldc.i4.m1
0x13edc  stfld    int32 <GetProperties>d__c::<>1__state
0x13ee1  ldarg.0
0x13ee2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__c::proxyContext
0x13ee7  brtrue.s loc_13EF4
0x13ee9  ldstr    aProxycontext// "proxyContext"
0x13eee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13ef3  throw
0x13ef4  ldarg.0
0x13ef5  ldarg.0
0x13ef6  ldfld    class Microsoft.SharePoint.Publishing.AddinPluginServerStub <GetProperties>d__c::<>4__this
0x13efb  ldarg.0
0x13efc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__c::proxyContext
0x13f01  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.AddinPluginServerStub::<>n__FabricatedMethod10(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x13f06  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x13f0b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x13f10  ldarg.0
0x13f11  ldc.i4.1
0x13f12  stfld    int32 <GetProperties>d__c::<>1__state
0x13f17  br.s     loc_13F4B
0x13f19  ldarg.0
0x13f1a  ldarg.0
0x13f1b  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x13f20  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x13f25  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<item>5__d
0x13f2a  ldarg.0
0x13f2b  ldarg.0
0x13f2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<item>5__d
0x13f31  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x13f36  ldarg.0
0x13f37  ldc.i4.2
0x13f38  stfld    int32 <GetProperties>d__c::<>1__state
0x13f3d  ldc.i4.1
0x13f3e  stloc.0
0x13f3f  leave    loc_141F1
0x13f44  ldarg.0
0x13f45  ldc.i4.1
0x13f46  stfld    int32 <GetProperties>d__c::<>1__state
0x13f4b  ldarg.0
0x13f4c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__c::<>7__wrape
0x13f51  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13f56  brtrue.s loc_13F19
0x13f58  ldarg.0
0x13f59  call     instance void <GetProperties>d__c::<>m__Finallyf()
0x13f5e  ldarg.0
0x13f5f  ldarg.0
0x13f60  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x13f65  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13f6a  ldarg.0
0x13f6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13f70  ldstr    aDescription// "Description"
0x13f75  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x13f7a  ldarg.0
0x13f7b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13f80  ldc.i4.0
0x13f81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x13f86  ldarg.0
0x13f87  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13f8c  ldc.i4.1
0x13f8d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13f92  ldarg.0
0x13f93  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13f98  ldc.i4.0
0x13f99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x13f9e  ldarg.0
0x13f9f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fa4  ldtoken  [mscorlib]System.String
0x13fa9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13fae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x13fb3  ldarg.0
0x13fb4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fb9  ldc.i4.0
0x13fba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x13fbf  ldarg.0
0x13fc0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fc5  ldc.i4.1
0x13fc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x13fcb  ldarg.0
0x13fcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fd1  ldnull
0x13fd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x13fd7  ldarg.0
0x13fd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fdd  ldstr    aDescription// "Description"
0x13fe2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x13fe7  ldarg.0
0x13fe8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13fed  ldnull
0x13fee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x13ff3  ldarg.0
0x13ff4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x13ff9  ldc.i4.0
0x13ffa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13fff  ldarg.0
0x14000  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x14005  ldc.i4.0
0x14006  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x1400b  ldarg.0
0x1400c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x14011  ldc.i4.0
0x14012  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x14017  ldarg.0
0x14018  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocal9
0x1401d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x14022  ldarg.0
0x14023  ldc.i4.3
0x14024  stfld    int32 <GetProperties>d__c::<>1__state
0x14029  ldc.i4.1
0x1402a  stloc.0
0x1402b  leave    loc_141F1
0x14030  ldarg.0
0x14031  ldc.i4.m1
0x14032  stfld    int32 <GetProperties>d__c::<>1__state
0x14037  ldarg.0
0x14038  ldarg.0
0x14039  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x1403e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14043  ldarg.0
0x14044  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14049  ldstr    aMarkup// "Markup"
0x1404e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x14053  ldarg.0
0x14054  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14059  ldc.i4.0
0x1405a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x1405f  ldarg.0
0x14060  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14065  ldc.i4.1
0x14066  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1406b  ldarg.0
0x1406c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14071  ldc.i4.0
0x14072  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14077  ldarg.0
0x14078  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x1407d  ldtoken  [mscorlib]System.String
0x14082  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14087  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1408c  ldarg.0
0x1408d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x14092  ldc.i4.0
0x14093  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14098  ldarg.0
0x14099  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x1409e  ldc.i4.1
0x1409f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x140a4  ldarg.0
0x140a5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140aa  ldnull
0x140ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x140b0  ldarg.0
0x140b1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140b6  ldstr    aMarkup// "Markup"
0x140bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x140c0  ldarg.0
0x140c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140c6  ldnull
0x140c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x140cc  ldarg.0
0x140cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140d2  ldc.i4.0
0x140d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x140d8  ldarg.0
0x140d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140de  ldc.i4.0
0x140df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x140e4  ldarg.0
0x140e5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140ea  ldc.i4.0
0x140eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x140f0  ldarg.0
0x140f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocala
0x140f6  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x140fb  ldarg.0
0x140fc  ldc.i4.4
0x140fd  stfld    int32 <GetProperties>d__c::<>1__state
0x14102  ldc.i4.1
0x14103  stloc.0
0x14104  leave    loc_141F1
0x14109  ldarg.0
0x1410a  ldc.i4.m1
0x1410b  stfld    int32 <GetProperties>d__c::<>1__state
0x14110  ldarg.0
0x14111  ldarg.0
0x14112  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x14117  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1411c  ldarg.0
0x1411d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x14122  ldstr    aTitle// "Title"
0x14127  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x1412c  ldarg.0
0x1412d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x14132  ldc.i4.0
0x14133  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x14138  ldarg.0
0x14139  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1413e  ldc.i4.1
0x1413f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x14144  ldarg.0
0x14145  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1414a  ldc.i4.0
0x1414b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x14150  ldarg.0
0x14151  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x14156  ldtoken  [mscorlib]System.String
0x1415b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14160  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x14165  ldarg.0
0x14166  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1416b  ldc.i4.0
0x1416c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x14171  ldarg.0
0x14172  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x14177  ldc.i4.1
0x14178  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1417d  ldarg.0
0x1417e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x14183  ldnull
0x14184  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x14189  ldarg.0
0x1418a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1418f  ldstr    aTitle// "Title"
0x14194  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x14199  ldarg.0
0x1419a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x1419f  ldnull
0x141a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x141a5  ldarg.0
0x141a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x141ab  ldc.i4.0
0x141ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x141b1  ldarg.0
0x141b2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x141b7  ldc.i4.0
0x141b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x141bd  ldarg.0
0x141be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x141c3  ldc.i4.0
0x141c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x141c9  ldarg.0
0x141ca  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>g__initLocalb
0x141cf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__c::<>2__current
0x141d4  ldarg.0
0x141d5  ldc.i4.5
0x141d6  stfld    int32 <GetProperties>d__c::<>1__state
0x141db  ldc.i4.1
0x141dc  stloc.0
0x141dd  leave.s  loc_141F1
0x141df  ldarg.0
0x141e0  ldc.i4.m1
0x141e1  stfld    int32 <GetProperties>d__c::<>1__state
0x141e6  ldc.i4.0
0x141e7  stloc.0
0x141e8  leave.s  loc_141F1
0x141ea  ldarg.0
0x141eb  call     instance void <GetProperties>d__c::System.IDisposable.Dispose()
0x141f0  endfinally
0x141f1  ldloc.0
0x141f2  ret
```
