# <GetMethods>d__35::MoveNext

- ea: `0x1aaa0`
- end: `0x1ba72`
- name: `<GetMethods>d__35::MoveNext`
- size: `4050`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x78c0`
- `0x1aaa0`
- `0x1baa0`
- `0x1bb00`

## string_xrefs

- `0x1ab84`: `DeleteObject`
- `0x1abb8`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x1aaa0  ldarg.0
0x1aaa1  ldfld    int32 <GetMethods>d__35::<>1__state
0x1aaa6  stloc.1
0x1aaa7  ldloc.1
0x1aaa8  switch   loc_1AAEE, loc_1BA65, loc_1AB58, loc_1AC44, loc_1AD1D, loc_1AE70, loc_1B03D, loc_1B284, loc_1B35D, loc_1B52B, loc_1B605, loc_1B6DF, loc_1B7B9, loc_1B90D, loc_1BA5E
0x1aae9  br       loc_1BA65
0x1aaee  ldarg.0
0x1aaef  ldc.i4.m1
0x1aaf0  stfld    int32 <GetMethods>d__35::<>1__state
0x1aaf5  ldarg.0
0x1aaf6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__35::proxyContext
0x1aafb  brtrue.s loc_1AB08
0x1aafd  ldstr    aProxycontext// "proxyContext"
0x1ab02  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ab07  throw
0x1ab08  ldarg.0
0x1ab09  ldarg.0
0x1ab0a  ldfld    class Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub <GetMethods>d__35::<>4__this
0x1ab0f  ldarg.0
0x1ab10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__35::proxyContext
0x1ab15  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.Navigation.NavigationTermServerStub::<>n__FabricatedMethod3a(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x1ab1a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x1ab1f  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__35::<>7__wrap38
0x1ab24  ldarg.0
0x1ab25  ldc.i4.1
0x1ab26  stfld    int32 <GetMethods>d__35::<>1__state
0x1ab2b  br.s     loc_1AB5F
0x1ab2d  ldarg.0
0x1ab2e  ldarg.0
0x1ab2f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__35::<>7__wrap38
0x1ab34  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x1ab39  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<itemBase>5__36
0x1ab3e  ldarg.0
0x1ab3f  ldarg.0
0x1ab40  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<itemBase>5__36
0x1ab45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>2__current
0x1ab4a  ldarg.0
0x1ab4b  ldc.i4.2
0x1ab4c  stfld    int32 <GetMethods>d__35::<>1__state
0x1ab51  ldc.i4.1
0x1ab52  stloc.0
0x1ab53  leave    loc_1BA70
0x1ab58  ldarg.0
0x1ab59  ldc.i4.1
0x1ab5a  stfld    int32 <GetMethods>d__35::<>1__state
0x1ab5f  ldarg.0
0x1ab60  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__35::<>7__wrap38
0x1ab65  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ab6a  brtrue.s loc_1AB2D
0x1ab6c  ldarg.0
0x1ab6d  call     instance void <GetMethods>d__35::<>m__Finally39()
0x1ab72  ldarg.0
0x1ab73  ldarg.0
0x1ab74  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ab79  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ab7e  ldarg.0
0x1ab7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ab84  ldstr    aDeleteobject// "DeleteObject"
0x1ab89  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ab8e  ldarg.0
0x1ab8f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ab94  ldc.i4.0
0x1ab95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ab9a  ldarg.0
0x1ab9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1aba0  ldc.i4.0
0x1aba1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1aba6  ldarg.0
0x1aba7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abac  ldc.i4.7
0x1abad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1abb2  ldarg.0
0x1abb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abb8  ldstr    aDelete// "Delete"
0x1abbd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1abc2  ldarg.0
0x1abc3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abc8  ldc.i4.0
0x1abc9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1abce  ldarg.0
0x1abcf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abd4  ldtoken  [mscorlib]System.Void
0x1abd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1abde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1abe3  ldarg.0
0x1abe4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abe9  ldc.i4.0
0x1abea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1abef  ldarg.0
0x1abf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1abf5  ldc.i4.0
0x1abf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1abfb  ldarg.0
0x1abfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ac01  ldc.i4.0
0x1ac02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ac07  ldarg.0
0x1ac08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ac0d  ldc.i4.0
0x1ac0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1ac13  ldarg.0
0x1ac14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ac19  ldc.i4.0
0x1ac1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1ac1f  ldarg.0
0x1ac20  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal1f
0x1ac25  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ac2a  ldarg.0
0x1ac2b  ldarg.0
0x1ac2c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ac31  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>2__current
0x1ac36  ldarg.0
0x1ac37  ldc.i4.3
0x1ac38  stfld    int32 <GetMethods>d__35::<>1__state
0x1ac3d  ldc.i4.1
0x1ac3e  stloc.0
0x1ac3f  leave    loc_1BA70
0x1ac44  ldarg.0
0x1ac45  ldc.i4.m1
0x1ac46  stfld    int32 <GetMethods>d__35::<>1__state
0x1ac4b  ldarg.0
0x1ac4c  ldarg.0
0x1ac4d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ac52  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac57  ldarg.0
0x1ac58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac5d  ldstr    aGetallparentte// "GetAllParentTerms"
0x1ac62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ac67  ldarg.0
0x1ac68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac6d  ldc.i4.0
0x1ac6e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ac73  ldarg.0
0x1ac74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac79  ldc.i4.0
0x1ac7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ac7f  ldarg.0
0x1ac80  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac85  ldc.i4.7
0x1ac86  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ac8b  ldarg.0
0x1ac8c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ac91  ldstr    aGetallparentte// "GetAllParentTerms"
0x1ac96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ac9b  ldarg.0
0x1ac9c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1aca1  ldc.i4.0
0x1aca2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1aca7  ldarg.0
0x1aca8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acad  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermCollectionCsom
0x1acb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1acb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1acbc  ldarg.0
0x1acbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acc2  ldc.i4.5
0x1acc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1acc8  ldarg.0
0x1acc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acce  ldc.i4.0
0x1accf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1acd4  ldarg.0
0x1acd5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acda  ldc.i4.0
0x1acdb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1ace0  ldarg.0
0x1ace1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1ace6  ldc.i4.0
0x1ace7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1acec  ldarg.0
0x1aced  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acf2  ldc.i4.0
0x1acf3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1acf8  ldarg.0
0x1acf9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal20
0x1acfe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ad03  ldarg.0
0x1ad04  ldarg.0
0x1ad05  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ad0a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>2__current
0x1ad0f  ldarg.0
0x1ad10  ldc.i4.4
0x1ad11  stfld    int32 <GetMethods>d__35::<>1__state
0x1ad16  ldc.i4.1
0x1ad17  stloc.0
0x1ad18  leave    loc_1BA70
0x1ad1d  ldarg.0
0x1ad1e  ldc.i4.m1
0x1ad1f  stfld    int32 <GetMethods>d__35::<>1__state
0x1ad24  ldarg.0
0x1ad25  ldarg.0
0x1ad26  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ad2b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad30  ldarg.0
0x1ad31  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad36  ldstr    aGetaseditable// "GetAsEditable"
0x1ad3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1ad40  ldarg.0
0x1ad41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad46  ldc.i4.0
0x1ad47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1ad4c  ldarg.0
0x1ad4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad52  ldc.i4.0
0x1ad53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1ad58  ldarg.0
0x1ad59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad5e  ldc.i4.7
0x1ad5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1ad64  ldarg.0
0x1ad65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad6a  ldstr    aGetaseditable// "GetAsEditable"
0x1ad6f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1ad74  ldarg.0
0x1ad75  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad7a  ldc.i4.0
0x1ad7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1ad80  ldarg.0
0x1ad81  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad86  ldtoken  [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm
0x1ad8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1ad95  ldarg.0
0x1ad96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ad9b  ldc.i4.4
0x1ad9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ada1  ldarg.0
0x1ada2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1ada7  ldc.i4.0
0x1ada8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1adad  ldarg.0
0x1adae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1adb3  ldc.i4.0
0x1adb4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1adb9  ldarg.0
0x1adba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1adbf  ldc.i4.0
0x1adc0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x1adc5  ldarg.0
0x1adc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1adcb  ldc.i4.0
0x1adcc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x1add1  ldarg.0
0x1add2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal21
0x1add7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1addc  ldarg.0
0x1addd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ade2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1ade7  ldarg.0
0x1ade8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1aded  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1adf2  ldarg.0
0x1adf3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1adf8  ldstr    aTaxonomysessio// "taxonomySession"
0x1adfd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1ae02  ldarg.0
0x1ae03  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae08  ldc.i4.0
0x1ae09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1ae0e  ldarg.0
0x1ae0f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae14  ldtoken  [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.TaxonomySession
0x1ae19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ae1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1ae23  ldarg.0
0x1ae24  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae29  ldc.i4.0
0x1ae2a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1ae2f  ldarg.0
0x1ae30  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae35  ldc.i4.0
0x1ae36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1ae3b  ldarg.0
0x1ae3c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae41  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1ae46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x1ae4b  ldarg.0
0x1ae4c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__35::<>g__initLocal22
0x1ae51  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x1ae56  ldarg.0
0x1ae57  ldarg.0
0x1ae58  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<item>5__37
0x1ae5d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>2__current
0x1ae62  ldarg.0
0x1ae63  ldc.i4.5
0x1ae64  stfld    int32 <GetMethods>d__35::<>1__state
0x1ae69  ldc.i4.1
0x1ae6a  stloc.0
0x1ae6b  leave    loc_1BA70
0x1ae70  ldarg.0
0x1ae71  ldc.i4.m1
0x1ae72  stfld    int32 <GetMethods>d__35::<>1__state
0x1ae77  ldarg.0
0x1ae78  ldarg.0
0x1ae79  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1ae7e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal23
0x1ae83  ldarg.0
0x1ae84  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__35::<>g__initLocal23
0x1ae89  ldstr    aGetasresolvedb_0// "GetAsResolvedByView"
0x1ae8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
  ... truncated ...
```
