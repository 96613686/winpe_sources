# <GetProperties>d__4::MoveNext_1

- ea: `0x2ab90`
- end: `0x2afb0`
- name: `<GetProperties>d__4::MoveNext_1`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x12240`
- `0x2ab90`
- `0x2afd0`
- `0x2b030`

## pseudocode

```c

```

## disassembly

```asm
0x2ab90  ldarg.0
0x2ab91  ldfld    int32 <GetProperties>d__4::<>1__state
0x2ab96  stloc.1
0x2ab97  ldloc.1
0x2ab98  switch   loc_2ABBE, loc_2AFA3, loc_2AC28, loc_2AD14, loc_2ADED, loc_2AEC6, loc_2AF9C
0x2abb9  br       loc_2AFA3
0x2abbe  ldarg.0
0x2abbf  ldc.i4.m1
0x2abc0  stfld    int32 <GetProperties>d__4::<>1__state
0x2abc5  ldarg.0
0x2abc6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x2abcb  brtrue.s loc_2ABD8
0x2abcd  ldstr    aProxycontext// "proxyContext"
0x2abd2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2abd7  throw
0x2abd8  ldarg.0
0x2abd9  ldarg.0
0x2abda  ldfld    class Microsoft.SharePoint.Publishing.SiteSharingEmailContextValueTypeConverter <GetProperties>d__4::<>4__this
0x2abdf  ldarg.0
0x2abe0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__4::proxyContext
0x2abe5  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.Publishing.SiteSharingEmailContextValueTypeConverter::<>n__FabricatedMethod8(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x2abea  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x2abef  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2abf4  ldarg.0
0x2abf5  ldc.i4.1
0x2abf6  stfld    int32 <GetProperties>d__4::<>1__state
0x2abfb  br.s     loc_2AC2F
0x2abfd  ldarg.0
0x2abfe  ldarg.0
0x2abff  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2ac04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x2ac09  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x2ac0e  ldarg.0
0x2ac0f  ldarg.0
0x2ac10  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<item>5__5
0x2ac15  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2ac1a  ldarg.0
0x2ac1b  ldc.i4.2
0x2ac1c  stfld    int32 <GetProperties>d__4::<>1__state
0x2ac21  ldc.i4.1
0x2ac22  stloc.0
0x2ac23  leave    loc_2AFAE
0x2ac28  ldarg.0
0x2ac29  ldc.i4.1
0x2ac2a  stfld    int32 <GetProperties>d__4::<>1__state
0x2ac2f  ldarg.0
0x2ac30  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__4::<>7__wrap6
0x2ac35  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ac3a  brtrue.s loc_2ABFD
0x2ac3c  ldarg.0
0x2ac3d  call     instance void <GetProperties>d__4::<>m__Finally7()
0x2ac42  ldarg.0
0x2ac43  ldarg.0
0x2ac44  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2ac49  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac4e  ldarg.0
0x2ac4f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac54  ldstr    aCustomdescript// "CustomDescription"
0x2ac59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2ac5e  ldarg.0
0x2ac5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac64  ldc.i4.0
0x2ac65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2ac6a  ldarg.0
0x2ac6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac70  ldc.i4.1
0x2ac71  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2ac76  ldarg.0
0x2ac77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac7c  ldc.i4.0
0x2ac7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2ac82  ldarg.0
0x2ac83  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac88  ldtoken  [mscorlib]System.String
0x2ac8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ac92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2ac97  ldarg.0
0x2ac98  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ac9d  ldc.i4.0
0x2ac9e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2aca3  ldarg.0
0x2aca4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2aca9  ldc.i4.1
0x2acaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2acaf  ldarg.0
0x2acb0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2acb5  ldnull
0x2acb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2acbb  ldarg.0
0x2acbc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2acc1  ldstr    aCustomdescript// "CustomDescription"
0x2acc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2accb  ldarg.0
0x2accc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2acd1  ldnull
0x2acd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2acd7  ldarg.0
0x2acd8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2acdd  ldc.i4.0
0x2acde  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2ace3  ldarg.0
0x2ace4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ace9  ldc.i4.1
0x2acea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2acef  ldarg.0
0x2acf0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2acf5  ldc.i4.0
0x2acf6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2acfb  ldarg.0
0x2acfc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal0
0x2ad01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2ad06  ldarg.0
0x2ad07  ldc.i4.3
0x2ad08  stfld    int32 <GetProperties>d__4::<>1__state
0x2ad0d  ldc.i4.1
0x2ad0e  stloc.0
0x2ad0f  leave    loc_2AFAE
0x2ad14  ldarg.0
0x2ad15  ldc.i4.m1
0x2ad16  stfld    int32 <GetProperties>d__4::<>1__state
0x2ad1b  ldarg.0
0x2ad1c  ldarg.0
0x2ad1d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2ad22  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad27  ldarg.0
0x2ad28  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad2d  ldstr    aCustomtitle// "CustomTitle"
0x2ad32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2ad37  ldarg.0
0x2ad38  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad3d  ldc.i4.0
0x2ad3e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2ad43  ldarg.0
0x2ad44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad49  ldc.i4.1
0x2ad4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2ad4f  ldarg.0
0x2ad50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad55  ldc.i4.0
0x2ad56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2ad5b  ldarg.0
0x2ad5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad61  ldtoken  [mscorlib]System.String
0x2ad66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ad6b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2ad70  ldarg.0
0x2ad71  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad76  ldc.i4.0
0x2ad77  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2ad7c  ldarg.0
0x2ad7d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad82  ldc.i4.1
0x2ad83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2ad88  ldarg.0
0x2ad89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad8e  ldnull
0x2ad8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2ad94  ldarg.0
0x2ad95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2ad9a  ldstr    aCustomtitle// "CustomTitle"
0x2ad9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2ada4  ldarg.0
0x2ada5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2adaa  ldnull
0x2adab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2adb0  ldarg.0
0x2adb1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2adb6  ldc.i4.0
0x2adb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2adbc  ldarg.0
0x2adbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2adc2  ldc.i4.1
0x2adc3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2adc8  ldarg.0
0x2adc9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2adce  ldc.i4.0
0x2adcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2add4  ldarg.0
0x2add5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal1
0x2adda  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2addf  ldarg.0
0x2ade0  ldc.i4.4
0x2ade1  stfld    int32 <GetProperties>d__4::<>1__state
0x2ade6  ldc.i4.1
0x2ade7  stloc.0
0x2ade8  leave    loc_2AFAE
0x2aded  ldarg.0
0x2adee  ldc.i4.m1
0x2adef  stfld    int32 <GetProperties>d__4::<>1__state
0x2adf4  ldarg.0
0x2adf5  ldarg.0
0x2adf6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2adfb  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae00  ldarg.0
0x2ae01  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae06  ldstr    aMessage_0// "Message"
0x2ae0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2ae10  ldarg.0
0x2ae11  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae16  ldc.i4.0
0x2ae17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2ae1c  ldarg.0
0x2ae1d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae22  ldc.i4.1
0x2ae23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2ae28  ldarg.0
0x2ae29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae2e  ldc.i4.0
0x2ae2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2ae34  ldarg.0
0x2ae35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae3a  ldtoken  [mscorlib]System.String
0x2ae3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae44  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2ae49  ldarg.0
0x2ae4a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae4f  ldc.i4.0
0x2ae50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2ae55  ldarg.0
0x2ae56  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae5b  ldc.i4.1
0x2ae5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2ae61  ldarg.0
0x2ae62  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae67  ldnull
0x2ae68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2ae6d  ldarg.0
0x2ae6e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae73  ldstr    aMessage_0// "Message"
0x2ae78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2ae7d  ldarg.0
0x2ae7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae83  ldnull
0x2ae84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x2ae89  ldarg.0
0x2ae8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae8f  ldc.i4.0
0x2ae90  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x2ae95  ldarg.0
0x2ae96  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2ae9b  ldc.i4.1
0x2ae9c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x2aea1  ldarg.0
0x2aea2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2aea7  ldc.i4.0
0x2aea8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x2aead  ldarg.0
0x2aeae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal2
0x2aeb3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>2__current
0x2aeb8  ldarg.0
0x2aeb9  ldc.i4.5
0x2aeba  stfld    int32 <GetProperties>d__4::<>1__state
0x2aebf  ldc.i4.1
0x2aec0  stloc.0
0x2aec1  leave    loc_2AFAE
0x2aec6  ldarg.0
0x2aec7  ldc.i4.m1
0x2aec8  stfld    int32 <GetProperties>d__4::<>1__state
0x2aecd  ldarg.0
0x2aece  ldarg.0
0x2aecf  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x2aed4  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2aed9  ldarg.0
0x2aeda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2aedf  ldstr    aUrl// "Url"
0x2aee4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x2aee9  ldarg.0
0x2aeea  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2aeef  ldc.i4.0
0x2aef0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x2aef5  ldarg.0
0x2aef6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2aefb  ldc.i4.1
0x2aefc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x2af01  ldarg.0
0x2af02  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af07  ldc.i4.0
0x2af08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x2af0d  ldarg.0
0x2af0e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af13  ldtoken  [mscorlib]System.String
0x2af18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2af1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x2af22  ldarg.0
0x2af23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af28  ldc.i4.0
0x2af29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x2af2e  ldarg.0
0x2af2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af34  ldc.i4.1
0x2af35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x2af3a  ldarg.0
0x2af3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af40  ldnull
0x2af41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x2af46  ldarg.0
0x2af47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__4::<>g__initLocal3
0x2af4c  ldstr    aUrl// "Url"
0x2af51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x2af56  ldarg.0
  ... truncated ...
```
