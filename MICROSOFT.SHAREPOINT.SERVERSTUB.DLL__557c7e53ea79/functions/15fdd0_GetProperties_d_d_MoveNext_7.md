# <GetProperties>d__d::MoveNext_7

- ea: `0x15fdd0`
- end: `0x1609e4`
- name: `<GetProperties>d__d::MoveNext_7`
- size: `3092`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7b980`
- `0x15fdd0`
- `0x160a10`
- `0x160a70`

## string_xrefs

- `0x160912`: `ViewXml`
- `0x16097f`: `ViewXml`
- `0x1603e7`: `ImageFieldsToTryRewriteToCdnUrls`
- `0x160454`: `ImageFieldsToTryRewriteToCdnUrls`
- `0x1604c1`: `OverrideViewXml`
- `0x16052e`: `OverrideViewXml`
- `0x160754`: `ReplaceGroup`
- `0x1607c6`: `ReplaceGroup`

## pseudocode

```c

```

## disassembly

```asm
0x15fdd0  ldarg.0
0x15fdd1  ldfld    int32 <GetProperties>d__d::<>1__state
0x15fdd6  stloc.1
0x15fdd7  ldloc.1
0x15fdd8  switch   loc_15FE22, loc_1609D7, loc_15FE8C, loc_15FF7D, loc_16005B, loc_160139, loc_160217, loc_1602F5, loc_1603CE, loc_1604A8, loc_160582, loc_16065C, loc_16073B, loc_16081A, loc_1608F9, loc_1609D0
0x15fe1d  br       loc_1609D7
0x15fe22  ldarg.0
0x15fe23  ldc.i4.m1
0x15fe24  stfld    int32 <GetProperties>d__d::<>1__state
0x15fe29  ldarg.0
0x15fe2a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x15fe2f  brtrue.s loc_15FE3C
0x15fe31  ldstr    aProxycontext// "proxyContext"
0x15fe36  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15fe3b  throw
0x15fe3c  ldarg.0
0x15fe3d  ldarg.0
0x15fe3e  ldfld    class Microsoft.SharePoint.ServerStub.SPRenderListDataParametersValueTypeConverter <GetProperties>d__d::<>4__this
0x15fe43  ldarg.0
0x15fe44  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__d::proxyContext
0x15fe49  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPRenderListDataParametersValueTypeConverter::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x15fe4e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x15fe53  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x15fe58  ldarg.0
0x15fe59  ldc.i4.1
0x15fe5a  stfld    int32 <GetProperties>d__d::<>1__state
0x15fe5f  br.s     loc_15FE93
0x15fe61  ldarg.0
0x15fe62  ldarg.0
0x15fe63  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x15fe68  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x15fe6d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x15fe72  ldarg.0
0x15fe73  ldarg.0
0x15fe74  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<item>5__e
0x15fe79  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x15fe7e  ldarg.0
0x15fe7f  ldc.i4.2
0x15fe80  stfld    int32 <GetProperties>d__d::<>1__state
0x15fe85  ldc.i4.1
0x15fe86  stloc.0
0x15fe87  leave    loc_1609E2
0x15fe8c  ldarg.0
0x15fe8d  ldc.i4.1
0x15fe8e  stfld    int32 <GetProperties>d__d::<>1__state
0x15fe93  ldarg.0
0x15fe94  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__d::<>7__wrapf
0x15fe99  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15fe9e  brtrue.s loc_15FE61
0x15fea0  ldarg.0
0x15fea1  call     instance void <GetProperties>d__d::<>m__Finally10()
0x15fea6  ldarg.0
0x15fea7  ldarg.0
0x15fea8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15fead  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15feb2  ldarg.0
0x15feb3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15feb8  ldstr    aAddrequiredfie// "AddRequiredFields"
0x15febd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x15fec2  ldarg.0
0x15fec3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15fec8  ldc.i4.0
0x15fec9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15fece  ldarg.0
0x15fecf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15fed4  ldc.i4.1
0x15fed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15feda  ldarg.0
0x15fedb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15fee0  ldc.i4.0
0x15fee1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15fee6  ldarg.0
0x15fee7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15feec  ldtoken  [mscorlib]System.Boolean
0x15fef1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15fef6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15fefb  ldarg.0
0x15fefc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff01  ldc.i4.0
0x15ff02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15ff07  ldarg.0
0x15ff08  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff0d  ldc.i4.1
0x15ff0e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x15ff13  ldarg.0
0x15ff14  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff19  ldc.i4.0
0x15ff1a  box      [mscorlib]System.Boolean
0x15ff1f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x15ff24  ldarg.0
0x15ff25  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff2a  ldstr    aAddrequiredfie// "AddRequiredFields"
0x15ff2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x15ff34  ldarg.0
0x15ff35  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff3a  ldnull
0x15ff3b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x15ff40  ldarg.0
0x15ff41  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff46  ldc.i4.0
0x15ff47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x15ff4c  ldarg.0
0x15ff4d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff52  ldc.i4.1
0x15ff53  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x15ff58  ldarg.0
0x15ff59  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff5e  ldc.i4.0
0x15ff5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x15ff64  ldarg.0
0x15ff65  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal0
0x15ff6a  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x15ff6f  ldarg.0
0x15ff70  ldc.i4.3
0x15ff71  stfld    int32 <GetProperties>d__d::<>1__state
0x15ff76  ldc.i4.1
0x15ff77  stloc.0
0x15ff78  leave    loc_1609E2
0x15ff7d  ldarg.0
0x15ff7e  ldc.i4.m1
0x15ff7f  stfld    int32 <GetProperties>d__d::<>1__state
0x15ff84  ldarg.0
0x15ff85  ldarg.0
0x15ff86  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x15ff8b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ff90  ldarg.0
0x15ff91  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ff96  ldstr    aAllowmultiplev_0// "AllowMultipleValueFilterForTaxonomyFiel"...
0x15ff9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x15ffa0  ldarg.0
0x15ffa1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffa6  ldc.i4.0
0x15ffa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x15ffac  ldarg.0
0x15ffad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffb2  ldc.i4.1
0x15ffb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x15ffb8  ldarg.0
0x15ffb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffbe  ldc.i4.0
0x15ffbf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x15ffc4  ldarg.0
0x15ffc5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffca  ldtoken  [mscorlib]System.Boolean
0x15ffcf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ffd4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x15ffd9  ldarg.0
0x15ffda  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffdf  ldc.i4.0
0x15ffe0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x15ffe5  ldarg.0
0x15ffe6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15ffeb  ldc.i4.1
0x15ffec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x15fff1  ldarg.0
0x15fff2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x15fff7  ldc.i4.0
0x15fff8  box      [mscorlib]System.Boolean
0x15fffd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x160002  ldarg.0
0x160003  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x160008  ldstr    aAllowmultiplev_0// "AllowMultipleValueFilterForTaxonomyFiel"...
0x16000d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x160012  ldarg.0
0x160013  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x160018  ldnull
0x160019  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x16001e  ldarg.0
0x16001f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x160024  ldc.i4.0
0x160025  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x16002a  ldarg.0
0x16002b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x160030  ldc.i4.0
0x160031  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x160036  ldarg.0
0x160037  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x16003c  ldc.i4.0
0x16003d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x160042  ldarg.0
0x160043  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal1
0x160048  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x16004d  ldarg.0
0x16004e  ldc.i4.4
0x16004f  stfld    int32 <GetProperties>d__d::<>1__state
0x160054  ldc.i4.1
0x160055  stloc.0
0x160056  leave    loc_1609E2
0x16005b  ldarg.0
0x16005c  ldc.i4.m1
0x16005d  stfld    int32 <GetProperties>d__d::<>1__state
0x160062  ldarg.0
0x160063  ldarg.0
0x160064  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x160069  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x16006e  ldarg.0
0x16006f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x160074  ldstr    aDatesinutc// "DatesInUtc"
0x160079  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x16007e  ldarg.0
0x16007f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x160084  ldc.i4.0
0x160085  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x16008a  ldarg.0
0x16008b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x160090  ldc.i4.1
0x160091  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x160096  ldarg.0
0x160097  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x16009c  ldc.i4.0
0x16009d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x1600a2  ldarg.0
0x1600a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600a8  ldtoken  [mscorlib]System.Boolean
0x1600ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x1600b7  ldarg.0
0x1600b8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600bd  ldc.i4.0
0x1600be  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1600c3  ldarg.0
0x1600c4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600c9  ldc.i4.1
0x1600ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1600cf  ldarg.0
0x1600d0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600d5  ldc.i4.0
0x1600d6  box      [mscorlib]System.Boolean
0x1600db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1600e0  ldarg.0
0x1600e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600e6  ldstr    aDatesinutc// "DatesInUtc"
0x1600eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x1600f0  ldarg.0
0x1600f1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x1600f6  ldnull
0x1600f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x1600fc  ldarg.0
0x1600fd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x160102  ldc.i4.0
0x160103  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x160108  ldarg.0
0x160109  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x16010e  ldc.i4.0
0x16010f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x160114  ldarg.0
0x160115  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x16011a  ldc.i4.0
0x16011b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x160120  ldarg.0
0x160121  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal2
0x160126  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>2__current
0x16012b  ldarg.0
0x16012c  ldc.i4.5
0x16012d  stfld    int32 <GetProperties>d__d::<>1__state
0x160132  ldc.i4.1
0x160133  stloc.0
0x160134  leave    loc_1609E2
0x160139  ldarg.0
0x16013a  ldc.i4.m1
0x16013b  stfld    int32 <GetProperties>d__d::<>1__state
0x160140  ldarg.0
0x160141  ldarg.0
0x160142  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x160147  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x16014c  ldarg.0
0x16014d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x160152  ldstr    aExpandgroups// "ExpandGroups"
0x160157  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x16015c  ldarg.0
0x16015d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x160162  ldc.i4.0
0x160163  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x160168  ldarg.0
0x160169  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x16016e  ldc.i4.1
0x16016f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x160174  ldarg.0
0x160175  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x16017a  ldc.i4.0
0x16017b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x160180  ldarg.0
0x160181  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x160186  ldtoken  [mscorlib]System.Boolean
0x16018b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160190  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x160195  ldarg.0
0x160196  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x16019b  ldc.i4.0
0x16019c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x1601a1  ldarg.0
0x1601a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x1601a7  ldc.i4.1
0x1601a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x1601ad  ldarg.0
0x1601ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__d::<>g__initLocal3
0x1601b3  ldc.i4.0
0x1601b4  box      [mscorlib]System.Boolean
0x1601b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x1601be  ldarg.0
  ... truncated ...
```
