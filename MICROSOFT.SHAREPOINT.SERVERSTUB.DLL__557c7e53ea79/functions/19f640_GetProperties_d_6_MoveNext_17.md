# <GetProperties>d__6::MoveNext_17

- ea: `0x19f640`
- end: `0x19fc1a`
- name: `<GetProperties>d__6::MoveNext_17`
- size: `1498`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0xa60e0`
- `0x19f640`
- `0x19fc40`
- `0x19fca0`

## string_xrefs

- `0x19f7e5`: `ContentTypeAssociationTaskListName`
- `0x19f852`: `ContentTypeAssociationTaskListName`
- `0x19fa70`: `TaskList`
- `0x19fadd`: `TaskList`
- `0x19fb49`: `Template`
- `0x19fbb6`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x19f640  ldarg.0
0x19f641  ldfld    int32 <GetProperties>d__6::<>1__state
0x19f646  stloc.1
0x19f647  ldloc.1
0x19f648  switch   loc_19F676, loc_19FC0D, loc_19F6E0, loc_19F7CC, loc_19F8A5, loc_19F97E, loc_19FA57, loc_19FB30, loc_19FC06
0x19f671  br       loc_19FC0D
0x19f676  ldarg.0
0x19f677  ldc.i4.m1
0x19f678  stfld    int32 <GetProperties>d__6::<>1__state
0x19f67d  ldarg.0
0x19f67e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x19f683  brtrue.s loc_19F690
0x19f685  ldstr    aProxycontext// "proxyContext"
0x19f68a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x19f68f  throw
0x19f690  ldarg.0
0x19f691  ldarg.0
0x19f692  ldfld    class Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationCreationInformationValueTypeConverter <GetProperties>d__6::<>4__this
0x19f697  ldarg.0
0x19f698  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__6::proxyContext
0x19f69d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationCreationInformationValueTypeConverter::<>n__FabricatedMethoda(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x19f6a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x19f6a7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x19f6ac  ldarg.0
0x19f6ad  ldc.i4.1
0x19f6ae  stfld    int32 <GetProperties>d__6::<>1__state
0x19f6b3  br.s     loc_19F6E7
0x19f6b5  ldarg.0
0x19f6b6  ldarg.0
0x19f6b7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x19f6bc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x19f6c1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x19f6c6  ldarg.0
0x19f6c7  ldarg.0
0x19f6c8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<item>5__7
0x19f6cd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x19f6d2  ldarg.0
0x19f6d3  ldc.i4.2
0x19f6d4  stfld    int32 <GetProperties>d__6::<>1__state
0x19f6d9  ldc.i4.1
0x19f6da  stloc.0
0x19f6db  leave    loc_19FC18
0x19f6e0  ldarg.0
0x19f6e1  ldc.i4.1
0x19f6e2  stfld    int32 <GetProperties>d__6::<>1__state
0x19f6e7  ldarg.0
0x19f6e8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__6::<>7__wrap8
0x19f6ed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19f6f2  brtrue.s loc_19F6B5
0x19f6f4  ldarg.0
0x19f6f5  call     instance void <GetProperties>d__6::<>m__Finally9()
0x19f6fa  ldarg.0
0x19f6fb  ldarg.0
0x19f6fc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x19f701  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f706  ldarg.0
0x19f707  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f70c  ldstr    aContenttypeass// "ContentTypeAssociationHistoryListName"
0x19f711  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x19f716  ldarg.0
0x19f717  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f71c  ldc.i4.0
0x19f71d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x19f722  ldarg.0
0x19f723  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f728  ldc.i4.1
0x19f729  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19f72e  ldarg.0
0x19f72f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f734  ldc.i4.0
0x19f735  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x19f73a  ldarg.0
0x19f73b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f740  ldtoken  [mscorlib]System.String
0x19f745  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19f74a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x19f74f  ldarg.0
0x19f750  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f755  ldc.i4.0
0x19f756  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x19f75b  ldarg.0
0x19f75c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f761  ldc.i4.1
0x19f762  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19f767  ldarg.0
0x19f768  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f76d  ldnull
0x19f76e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19f773  ldarg.0
0x19f774  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f779  ldstr    aContenttypeass// "ContentTypeAssociationHistoryListName"
0x19f77e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x19f783  ldarg.0
0x19f784  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f789  ldnull
0x19f78a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x19f78f  ldarg.0
0x19f790  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f795  ldc.i4.0
0x19f796  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19f79b  ldarg.0
0x19f79c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f7a1  ldc.i4.0
0x19f7a2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x19f7a7  ldarg.0
0x19f7a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f7ad  ldc.i4.0
0x19f7ae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x19f7b3  ldarg.0
0x19f7b4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal0
0x19f7b9  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x19f7be  ldarg.0
0x19f7bf  ldc.i4.3
0x19f7c0  stfld    int32 <GetProperties>d__6::<>1__state
0x19f7c5  ldc.i4.1
0x19f7c6  stloc.0
0x19f7c7  leave    loc_19FC18
0x19f7cc  ldarg.0
0x19f7cd  ldc.i4.m1
0x19f7ce  stfld    int32 <GetProperties>d__6::<>1__state
0x19f7d3  ldarg.0
0x19f7d4  ldarg.0
0x19f7d5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x19f7da  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f7df  ldarg.0
0x19f7e0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f7e5  ldstr    aContenttypeass_0// "ContentTypeAssociationTaskListName"
0x19f7ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x19f7ef  ldarg.0
0x19f7f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f7f5  ldc.i4.0
0x19f7f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x19f7fb  ldarg.0
0x19f7fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f801  ldc.i4.1
0x19f802  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19f807  ldarg.0
0x19f808  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f80d  ldc.i4.0
0x19f80e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x19f813  ldarg.0
0x19f814  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f819  ldtoken  [mscorlib]System.String
0x19f81e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19f823  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x19f828  ldarg.0
0x19f829  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f82e  ldc.i4.0
0x19f82f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x19f834  ldarg.0
0x19f835  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f83a  ldc.i4.1
0x19f83b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19f840  ldarg.0
0x19f841  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f846  ldnull
0x19f847  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19f84c  ldarg.0
0x19f84d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f852  ldstr    aContenttypeass_0// "ContentTypeAssociationTaskListName"
0x19f857  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x19f85c  ldarg.0
0x19f85d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f862  ldnull
0x19f863  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x19f868  ldarg.0
0x19f869  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f86e  ldc.i4.0
0x19f86f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19f874  ldarg.0
0x19f875  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f87a  ldc.i4.0
0x19f87b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x19f880  ldarg.0
0x19f881  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f886  ldc.i4.0
0x19f887  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x19f88c  ldarg.0
0x19f88d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal1
0x19f892  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x19f897  ldarg.0
0x19f898  ldc.i4.4
0x19f899  stfld    int32 <GetProperties>d__6::<>1__state
0x19f89e  ldc.i4.1
0x19f89f  stloc.0
0x19f8a0  leave    loc_19FC18
0x19f8a5  ldarg.0
0x19f8a6  ldc.i4.m1
0x19f8a7  stfld    int32 <GetProperties>d__6::<>1__state
0x19f8ac  ldarg.0
0x19f8ad  ldarg.0
0x19f8ae  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x19f8b3  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8b8  ldarg.0
0x19f8b9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8be  ldstr    aHistorylist// "HistoryList"
0x19f8c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x19f8c8  ldarg.0
0x19f8c9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8ce  ldc.i4.0
0x19f8cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x19f8d4  ldarg.0
0x19f8d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8da  ldc.i4.4
0x19f8db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19f8e0  ldarg.0
0x19f8e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8e6  ldc.i4.0
0x19f8e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x19f8ec  ldarg.0
0x19f8ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f8f2  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x19f8f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19f8fc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x19f901  ldarg.0
0x19f902  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f907  ldc.i4.0
0x19f908  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x19f90d  ldarg.0
0x19f90e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f913  ldc.i4.1
0x19f914  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19f919  ldarg.0
0x19f91a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f91f  ldnull
0x19f920  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19f925  ldarg.0
0x19f926  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f92b  ldstr    aHistorylist// "HistoryList"
0x19f930  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x19f935  ldarg.0
0x19f936  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f93b  ldnull
0x19f93c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x19f941  ldarg.0
0x19f942  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f947  ldc.i4.0
0x19f948  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x19f94d  ldarg.0
0x19f94e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f953  ldc.i4.0
0x19f954  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x19f959  ldarg.0
0x19f95a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f95f  ldc.i4.0
0x19f960  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x19f965  ldarg.0
0x19f966  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal2
0x19f96b  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>2__current
0x19f970  ldarg.0
0x19f971  ldc.i4.5
0x19f972  stfld    int32 <GetProperties>d__6::<>1__state
0x19f977  ldc.i4.1
0x19f978  stloc.0
0x19f979  leave    loc_19FC18
0x19f97e  ldarg.0
0x19f97f  ldc.i4.m1
0x19f980  stfld    int32 <GetProperties>d__6::<>1__state
0x19f985  ldarg.0
0x19f986  ldarg.0
0x19f987  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x19f98c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f991  ldarg.0
0x19f992  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f997  ldstr    aName// "Name"
0x19f99c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x19f9a1  ldarg.0
0x19f9a2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9a7  ldc.i4.0
0x19f9a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x19f9ad  ldarg.0
0x19f9ae  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9b3  ldc.i4.1
0x19f9b4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x19f9b9  ldarg.0
0x19f9ba  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9bf  ldc.i4.0
0x19f9c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x19f9c5  ldarg.0
0x19f9c6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9cb  ldtoken  [mscorlib]System.String
0x19f9d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19f9d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x19f9da  ldarg.0
0x19f9db  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9e0  ldc.i4.0
0x19f9e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x19f9e6  ldarg.0
0x19f9e7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9ec  ldc.i4.1
0x19f9ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x19f9f2  ldarg.0
0x19f9f3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19f9f8  ldnull
0x19f9f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x19f9fe  ldarg.0
0x19f9ff  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__6::<>g__initLocal3
0x19fa04  ldstr    aName// "Name"
0x19fa09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x19fa0e  ldarg.0
  ... truncated ...
```
