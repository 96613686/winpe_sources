# <GetMethods>d__5::MoveNext_2

- ea: `0x1fd80`
- end: `0x201ae`
- name: `<GetMethods>d__5::MoveNext_2`
- size: `1070`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0xa7b0`
- `0x1fd80`
- `0x201d0`
- `0x20230`

## string_xrefs

- `0x20063`: `Update`
- `0x20097`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x1fd80  ldarg.0
0x1fd81  ldfld    int32 <GetMethods>d__5::<>1__state
0x1fd86  stloc.1
0x1fd87  ldloc.1
0x1fd88  switch   loc_1FDAA, loc_201A1, loc_1FE14, loc_1FF71, loc_2004A, loc_2019A
0x1fda5  br       loc_201A1
0x1fdaa  ldarg.0
0x1fdab  ldc.i4.m1
0x1fdac  stfld    int32 <GetMethods>d__5::<>1__state
0x1fdb1  ldarg.0
0x1fdb2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__5::proxyContext
0x1fdb7  brtrue.s loc_1FDC4
0x1fdb9  ldstr    aProxycontext// "proxyContext"
0x1fdbe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fdc3  throw
0x1fdc4  ldarg.0
0x1fdc5  ldarg.0
0x1fdc6  ldfld    class Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub <GetMethods>d__5::<>4__this
0x1fdcb  ldarg.0
0x1fdcc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__5::proxyContext
0x1fdd1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::<>n__FabricatedMethoda(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x1fdd6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1fddb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__5::<>7__wrap8
0x1fde0  ldarg.0
0x1fde1  ldc.i4.1
0x1fde2  stfld    int32 <GetMethods>d__5::<>1__state
0x1fde7  br.s     loc_1FE1B
0x1fde9  ldarg.0
0x1fdea  ldarg.0
0x1fdeb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__5::<>7__wrap8
0x1fdf0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1fdf5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<itemBase>5__6
0x1fdfa  ldarg.0
0x1fdfb  ldarg.0
0x1fdfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<itemBase>5__6
0x1fe01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>2__current
0x1fe06  ldarg.0
0x1fe07  ldc.i4.2
0x1fe08  stfld    int32 <GetMethods>d__5::<>1__state
0x1fe0d  ldc.i4.1
0x1fe0e  stloc.0
0x1fe0f  leave    loc_201AC
0x1fe14  ldarg.0
0x1fe15  ldc.i4.1
0x1fe16  stfld    int32 <GetMethods>d__5::<>1__state
0x1fe1b  ldarg.0
0x1fe1c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__5::<>7__wrap8
0x1fe21  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fe26  brtrue.s loc_1FDE9
0x1fe28  ldarg.0
0x1fe29  call     instance void <GetMethods>d__5::<>m__Finally9()
0x1fe2e  ldarg.0
0x1fe2f  ldarg.0
0x1fe30  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1fe35  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe3a  ldarg.0
0x1fe3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe40  ldstr    aCtor// ".ctor"
0x1fe45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1fe4a  ldarg.0
0x1fe4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe50  ldc.i4.0
0x1fe51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1fe56  ldarg.0
0x1fe57  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe5c  ldc.i4.0
0x1fe5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1fe62  ldarg.0
0x1fe63  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe68  ldc.i4.7
0x1fe69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1fe6e  ldarg.0
0x1fe6f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe74  ldstr    aCtor// ".ctor"
0x1fe79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1fe7e  ldarg.0
0x1fe7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe84  ldc.i4.0
0x1fe85  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1fe8a  ldarg.0
0x1fe8b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe90  ldnull
0x1fe91  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1fe96  ldarg.0
0x1fe97  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fe9c  ldc.i4.0
0x1fe9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1fea2  ldarg.0
0x1fea3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fea8  ldc.i4.0
0x1fea9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1feae  ldarg.0
0x1feaf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1feb4  ldc.i4.0
0x1feb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1feba  ldarg.0
0x1febb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fec0  ldc.i4.0
0x1fec1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1fec6  ldarg.0
0x1fec7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fecc  ldc.i4.0
0x1fecd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1fed2  ldarg.0
0x1fed3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal0
0x1fed8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x1fedd  ldarg.0
0x1fede  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x1fee3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1fee8  ldarg.0
0x1fee9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1feee  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1fef3  ldarg.0
0x1fef4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1fef9  ldstr    aWeb// "web"
0x1fefe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ff03  ldarg.0
0x1ff04  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff09  ldc.i4.0
0x1ff0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ff0f  ldarg.0
0x1ff10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff15  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x1ff1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ff1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ff24  ldarg.0
0x1ff25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff2a  ldc.i4.0
0x1ff2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ff30  ldarg.0
0x1ff31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff36  ldc.i4.0
0x1ff37  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ff3c  ldarg.0
0x1ff3d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff42  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ff47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ff4c  ldarg.0
0x1ff4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal1
0x1ff52  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ff57  ldarg.0
0x1ff58  ldarg.0
0x1ff59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x1ff5e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>2__current
0x1ff63  ldarg.0
0x1ff64  ldc.i4.3
0x1ff65  stfld    int32 <GetMethods>d__5::<>1__state
0x1ff6a  ldc.i4.1
0x1ff6b  stloc.0
0x1ff6c  leave    loc_201AC
0x1ff71  ldarg.0
0x1ff72  ldc.i4.m1
0x1ff73  stfld    int32 <GetMethods>d__5::<>1__state
0x1ff78  ldarg.0
0x1ff79  ldarg.0
0x1ff7a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ff7f  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ff84  ldarg.0
0x1ff85  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ff8a  ldstr    aResettodefault// "ResetToDefaults"
0x1ff8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ff94  ldarg.0
0x1ff95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ff9a  ldc.i4.0
0x1ff9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ffa0  ldarg.0
0x1ffa1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffa6  ldc.i4.0
0x1ffa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ffac  ldarg.0
0x1ffad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffb2  ldc.i4.7
0x1ffb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ffb8  ldarg.0
0x1ffb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffbe  ldstr    aResettodefault// "ResetToDefaults"
0x1ffc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ffc8  ldarg.0
0x1ffc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffce  ldc.i4.0
0x1ffcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ffd4  ldarg.0
0x1ffd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffda  ldtoken  [mscorlib]System.Void
0x1ffdf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ffe4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ffe9  ldarg.0
0x1ffea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1ffef  ldc.i4.0
0x1fff0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1fff5  ldarg.0
0x1fff6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x1fffb  ldc.i4.0
0x1fffc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x20001  ldarg.0
0x20002  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x20007  ldc.i4.0
0x20008  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x2000d  ldarg.0
0x2000e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x20013  ldc.i4.0
0x20014  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x20019  ldarg.0
0x2001a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x2001f  ldc.i4.0
0x20020  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x20025  ldarg.0
0x20026  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal2
0x2002b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x20030  ldarg.0
0x20031  ldarg.0
0x20032  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x20037  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>2__current
0x2003c  ldarg.0
0x2003d  ldc.i4.4
0x2003e  stfld    int32 <GetMethods>d__5::<>1__state
0x20043  ldc.i4.1
0x20044  stloc.0
0x20045  leave    loc_201AC
0x2004a  ldarg.0
0x2004b  ldc.i4.m1
0x2004c  stfld    int32 <GetMethods>d__5::<>1__state
0x20051  ldarg.0
0x20052  ldarg.0
0x20053  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x20058  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x2005d  ldarg.0
0x2005e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x20063  ldstr    aUpdate// "Update"
0x20068  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x2006d  ldarg.0
0x2006e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x20073  ldc.i4.0
0x20074  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x20079  ldarg.0
0x2007a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x2007f  ldc.i4.0
0x20080  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x20085  ldarg.0
0x20086  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x2008b  ldc.i4.7
0x2008c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x20091  ldarg.0
0x20092  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x20097  ldstr    aUpdate// "Update"
0x2009c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x200a1  ldarg.0
0x200a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200a7  ldc.i4.0
0x200a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x200ad  ldarg.0
0x200ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200b3  ldtoken  [mscorlib]System.Void
0x200b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x200bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x200c2  ldarg.0
0x200c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200c8  ldc.i4.0
0x200c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x200ce  ldarg.0
0x200cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200d4  ldc.i4.0
0x200d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x200da  ldarg.0
0x200db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200e0  ldc.i4.0
0x200e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x200e6  ldarg.0
0x200e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200ec  ldc.i4.0
0x200ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x200f2  ldarg.0
0x200f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x200f8  ldc.i4.0
0x200f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x200fe  ldarg.0
0x200ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<>g__initLocal3
0x20104  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x20109  ldarg.0
0x2010a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__5::<item>5__7
0x2010f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x20114  ldarg.0
0x20115  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x2011a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal4
0x2011f  ldarg.0
0x20120  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal4
0x20125  ldstr    aTaxonomysessio// "taxonomySession"
0x2012a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x2012f  ldarg.0
0x20130  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal4
0x20135  ldc.i4.0
0x20136  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x2013b  ldarg.0
0x2013c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal4
0x20141  ldtoken  [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.TaxonomySession
0x20146  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2014b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x20150  ldarg.0
0x20151  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__5::<>g__initLocal4
0x20156  ldc.i4.0
  ... truncated ...
```
