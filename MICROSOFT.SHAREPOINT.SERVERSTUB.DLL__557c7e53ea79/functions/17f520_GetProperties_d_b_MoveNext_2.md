# <GetProperties>d__b::MoveNext_2

- ea: `0x17f520`
- end: `0x17ff9e`
- name: `<GetProperties>d__b::MoveNext_2`
- size: `2686`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x925a0`
- `0x17f520`
- `0x17ffc0`
- `0x180020`

## string_xrefs

- `0x17f6de`: `Created`
- `0x17f758`: `Created`
- `0x17fded`: `WebTemplate`
- `0x17fe5a`: `WebTemplate`
- `0x17f600`: `Configuration`
- `0x17f672`: `Configuration`
- `0x17fec7`: `WebTemplateId`
- `0x17ff39`: `WebTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x17f520  ldarg.0
0x17f521  ldfld    int32 <GetProperties>d__b::<>1__state
0x17f526  stloc.1
0x17f527  ldloc.1
0x17f528  switch   loc_17F56A, loc_17FF91, loc_17F5D4, loc_17F6C5, loc_17F7AB, loc_17F884, loc_17F96A, loc_17FA51, loc_17FB38, loc_17FC20, loc_17FCFA, loc_17FDD4, loc_17FEAE, loc_17FF8A
0x17f565  br       loc_17FF91
0x17f56a  ldarg.0
0x17f56b  ldc.i4.m1
0x17f56c  stfld    int32 <GetProperties>d__b::<>1__state
0x17f571  ldarg.0
0x17f572  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__b::proxyContext
0x17f577  brtrue.s loc_17F584
0x17f579  ldstr    aProxycontext// "proxyContext"
0x17f57e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17f583  throw
0x17f584  ldarg.0
0x17f585  ldarg.0
0x17f586  ldfld    class Microsoft.SharePoint.ServerStub.SPWebInformationServerStub <GetProperties>d__b::<>4__this
0x17f58b  ldarg.0
0x17f58c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__b::proxyContext
0x17f591  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::<>n__FabricatedMethodf(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext xmlargs)
0x17f596  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x17f59b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__b::<>7__wrapd
0x17f5a0  ldarg.0
0x17f5a1  ldc.i4.1
0x17f5a2  stfld    int32 <GetProperties>d__b::<>1__state
0x17f5a7  br.s     loc_17F5DB
0x17f5a9  ldarg.0
0x17f5aa  ldarg.0
0x17f5ab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__b::<>7__wrapd
0x17f5b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x17f5b5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<item>5__c
0x17f5ba  ldarg.0
0x17f5bb  ldarg.0
0x17f5bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<item>5__c
0x17f5c1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>2__current
0x17f5c6  ldarg.0
0x17f5c7  ldc.i4.2
0x17f5c8  stfld    int32 <GetProperties>d__b::<>1__state
0x17f5cd  ldc.i4.1
0x17f5ce  stloc.0
0x17f5cf  leave    loc_17FF9C
0x17f5d4  ldarg.0
0x17f5d5  ldc.i4.1
0x17f5d6  stfld    int32 <GetProperties>d__b::<>1__state
0x17f5db  ldarg.0
0x17f5dc  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__b::<>7__wrapd
0x17f5e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17f5e6  brtrue.s loc_17F5A9
0x17f5e8  ldarg.0
0x17f5e9  call     instance void <GetProperties>d__b::<>m__Finallye()
0x17f5ee  ldarg.0
0x17f5ef  ldarg.0
0x17f5f0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17f5f5  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f5fa  ldarg.0
0x17f5fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f600  ldstr    aConfiguration// "Configuration"
0x17f605  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17f60a  ldarg.0
0x17f60b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f610  ldc.i4.0
0x17f611  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17f616  ldarg.0
0x17f617  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f61c  ldc.i4.1
0x17f61d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17f622  ldarg.0
0x17f623  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f628  ldc.i4.0
0x17f629  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17f62e  ldarg.0
0x17f62f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f634  ldtoken  [mscorlib]System.Int16
0x17f639  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f63e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17f643  ldarg.0
0x17f644  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f649  ldc.i4.1
0x17f64a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17f64f  ldarg.0
0x17f650  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f655  ldc.i4.1
0x17f656  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17f65b  ldarg.0
0x17f65c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f661  ldc.i4.0
0x17f662  box      [mscorlib]System.Int16
0x17f667  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17f66c  ldarg.0
0x17f66d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f672  ldstr    aConfiguration// "Configuration"
0x17f677  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x17f67c  ldarg.0
0x17f67d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f682  ldnull
0x17f683  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x17f688  ldarg.0
0x17f689  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f68e  ldc.i4.0
0x17f68f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17f694  ldarg.0
0x17f695  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f69a  ldc.i4.0
0x17f69b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x17f6a0  ldarg.0
0x17f6a1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f6a6  ldc.i4.0
0x17f6a7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17f6ac  ldarg.0
0x17f6ad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal0
0x17f6b2  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>2__current
0x17f6b7  ldarg.0
0x17f6b8  ldc.i4.3
0x17f6b9  stfld    int32 <GetProperties>d__b::<>1__state
0x17f6be  ldc.i4.1
0x17f6bf  stloc.0
0x17f6c0  leave    loc_17FF9C
0x17f6c5  ldarg.0
0x17f6c6  ldc.i4.m1
0x17f6c7  stfld    int32 <GetProperties>d__b::<>1__state
0x17f6cc  ldarg.0
0x17f6cd  ldarg.0
0x17f6ce  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17f6d3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f6d8  ldarg.0
0x17f6d9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f6de  ldstr    aCreated// "Created"
0x17f6e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17f6e8  ldarg.0
0x17f6e9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f6ee  ldc.i4.0
0x17f6ef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17f6f4  ldarg.0
0x17f6f5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f6fa  ldc.i4.1
0x17f6fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17f700  ldarg.0
0x17f701  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f706  ldc.i4.0
0x17f707  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17f70c  ldarg.0
0x17f70d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f712  ldtoken  [mscorlib]System.DateTime
0x17f717  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f71c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17f721  ldarg.0
0x17f722  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f727  ldc.i4.1
0x17f728  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17f72d  ldarg.0
0x17f72e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f733  ldc.i4.1
0x17f734  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17f739  ldarg.0
0x17f73a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f73f  ldloca.s 2
0x17f741  initobj  [mscorlib]System.DateTime
0x17f747  ldloc.2
0x17f748  box      [mscorlib]System.DateTime
0x17f74d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17f752  ldarg.0
0x17f753  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f758  ldstr    aCreated// "Created"
0x17f75d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x17f762  ldarg.0
0x17f763  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f768  ldnull
0x17f769  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x17f76e  ldarg.0
0x17f76f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f774  ldc.i4.0
0x17f775  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17f77a  ldarg.0
0x17f77b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f780  ldc.i4.0
0x17f781  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x17f786  ldarg.0
0x17f787  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f78c  ldc.i4.0
0x17f78d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17f792  ldarg.0
0x17f793  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal1
0x17f798  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>2__current
0x17f79d  ldarg.0
0x17f79e  ldc.i4.4
0x17f79f  stfld    int32 <GetProperties>d__b::<>1__state
0x17f7a4  ldc.i4.1
0x17f7a5  stloc.0
0x17f7a6  leave    loc_17FF9C
0x17f7ab  ldarg.0
0x17f7ac  ldc.i4.m1
0x17f7ad  stfld    int32 <GetProperties>d__b::<>1__state
0x17f7b2  ldarg.0
0x17f7b3  ldarg.0
0x17f7b4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17f7b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7be  ldarg.0
0x17f7bf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7c4  ldstr    aDescription// "Description"
0x17f7c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17f7ce  ldarg.0
0x17f7cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7d4  ldc.i4.0
0x17f7d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17f7da  ldarg.0
0x17f7db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7e0  ldc.i4.1
0x17f7e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17f7e6  ldarg.0
0x17f7e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7ec  ldc.i4.0
0x17f7ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17f7f2  ldarg.0
0x17f7f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f7f8  ldtoken  [mscorlib]System.String
0x17f7fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f802  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17f807  ldarg.0
0x17f808  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f80d  ldc.i4.1
0x17f80e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17f813  ldarg.0
0x17f814  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f819  ldc.i4.1
0x17f81a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17f81f  ldarg.0
0x17f820  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f825  ldnull
0x17f826  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x17f82b  ldarg.0
0x17f82c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f831  ldstr    aDescription// "Description"
0x17f836  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x17f83b  ldarg.0
0x17f83c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f841  ldnull
0x17f842  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x17f847  ldarg.0
0x17f848  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f84d  ldc.i4.0
0x17f84e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17f853  ldarg.0
0x17f854  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f859  ldc.i4.0
0x17f85a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x17f85f  ldarg.0
0x17f860  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f865  ldc.i4.0
0x17f866  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x17f86b  ldarg.0
0x17f86c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal2
0x17f871  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>2__current
0x17f876  ldarg.0
0x17f877  ldc.i4.5
0x17f878  stfld    int32 <GetProperties>d__b::<>1__state
0x17f87d  ldc.i4.1
0x17f87e  stloc.0
0x17f87f  leave    loc_17FF9C
0x17f884  ldarg.0
0x17f885  ldc.i4.m1
0x17f886  stfld    int32 <GetProperties>d__b::<>1__state
0x17f88b  ldarg.0
0x17f88c  ldarg.0
0x17f88d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x17f892  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f897  ldarg.0
0x17f898  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f89d  ldstr    aId_0// "Id"
0x17f8a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x17f8a7  ldarg.0
0x17f8a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8ad  ldc.i4.0
0x17f8ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x17f8b3  ldarg.0
0x17f8b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8b9  ldc.i4.1
0x17f8ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x17f8bf  ldarg.0
0x17f8c0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8c5  ldc.i4.0
0x17f8c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x17f8cb  ldarg.0
0x17f8cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8d1  ldtoken  [mscorlib]System.Guid
0x17f8d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f8db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x17f8e0  ldarg.0
0x17f8e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8e6  ldc.i4.1
0x17f8e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x17f8ec  ldarg.0
0x17f8ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8f2  ldc.i4.1
0x17f8f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x17f8f8  ldarg.0
0x17f8f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__b::<>g__initLocal3
0x17f8fe  ldloca.s 3
0x17f900  initobj  [mscorlib]System.Guid
0x17f906  ldloc.3
  ... truncated ...
```
