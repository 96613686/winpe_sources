# <GetProperties>d__10c::MoveNext

- ea: `0xc0280`
- end: `0xc5186`
- name: `<GetProperties>d__10c::MoveNext`
- size: `20230`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x87b0`
- `0xc0280`
- `0xc51b0`
- `0xc5210`

## string_xrefs

- `0xc072d`: `BaseTemplate`
- `0xc0d39`: `Created`
- `0xc0db3`: `Created`
- `0xc0e20`: `CurrentChangeToken`
- `0xc0e8d`: `CurrentChangeToken`
- `0xc1349`: `DefaultItemOpenUseListSetting`
- `0xc13bb`: `DefaultItemOpenUseListSetting`
- `0xc15dc`: `DefaultViewPath`
- `0xc1649`: `DefaultViewPath`
- `0xc1a1e`: `DocumentTemplateUrl`
- `0xc2c4f`: `ImagePath`
- `0xc2cbc`: `ImagePath`
- `0xc386d`: `LastItemDeletedDate`
- `0xc38e8`: `LastItemDeletedDate`
- `0xc42f2`: `ParentWebPath`
- `0xc435f`: `ParentWebPath`
- `0xc4585`: `ReadSecurity`
- `0xc45f7`: `ReadSecurity`
- `0xc473e`: `SchemaXml`
- `0xc47ab`: `SchemaXml`
- `0xc4818`: `ServerTemplateCanCreateFolders`
- `0xc488a`: `ServerTemplateCanCreateFolders`
- `0xc49d1`: `TemplateFeatureId`
- `0xc4a4c`: `TemplateFeatureId`
- `0xc50af`: `WriteSecurity`
- `0xc5121`: `WriteSecurity`
- `0xc079f`: `BaseTemplate_Client`
- `0xc1a8b`: `DocumentTemplateUrl_Client`

## pseudocode

```c

```

## disassembly

```asm
0xc0280  ldarg.0
0xc0281  ldfld    int32 <GetProperties>d__10c::<>1__state
0xc0286  stloc.1
0xc0287  ldloc.1
0xc0288  switch   loc_C0402, loc_C5179, loc_C046C, loc_C0558, loc_C0636, loc_C0714, loc_C07F2, loc_C08D0, loc_C09AE, loc_C0A88, loc_C0B67, loc_C0C46, loc_C0D20, loc_C0E07, loc_C0EE1, loc_C0FBB, loc_C1095, loc_C117C, loc_C1256, loc_C1330, loc_C140F, loc_C14E9, loc_C15C3, loc_C169D, loc_C1777, loc_C1851, loc_C192B, loc_C1A05, loc_C1ADF, loc_C1BBE, loc_C1C98, loc_C1D72, loc_C1E51, loc_C1F30, loc_C200F, loc_C20EE, loc_C21CD, loc_C22AC, loc_C2386, loc_C2460, loc_C253F, loc_C261E, loc_C26F8, loc_C27D7, loc_C28B6, loc_C2990, loc_C2A6F, loc_C2B4E, loc_C2C36, loc_C2D10, loc_C2DEA, loc_C2EC4, loc_C2FA3, loc_C3082, loc_C3161 \
0xc03fd  br       loc_C5179
0xc0402  ldarg.0
0xc0403  ldc.i4.m1
0xc0404  stfld    int32 <GetProperties>d__10c::<>1__state
0xc0409  ldarg.0
0xc040a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__10c::proxyContext
0xc040f  brtrue.s loc_C041C
0xc0411  ldstr    aProxycontext// "proxyContext"
0xc0416  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc041b  throw
0xc041c  ldarg.0
0xc041d  ldarg.0
0xc041e  ldfld    class Microsoft.SharePoint.ServerStub.SPListServerStub <GetProperties>d__10c::<>4__this
0xc0423  ldarg.0
0xc0424  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__10c::proxyContext
0xc0429  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPListServerStub::<>n__FabricatedMethod110(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xc042e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0xc0433  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__10c::<>7__wrap10e
0xc0438  ldarg.0
0xc0439  ldc.i4.1
0xc043a  stfld    int32 <GetProperties>d__10c::<>1__state
0xc043f  br.s     loc_C0473
0xc0441  ldarg.0
0xc0442  ldarg.0
0xc0443  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__10c::<>7__wrap10e
0xc0448  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0xc044d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<item>5__10d
0xc0452  ldarg.0
0xc0453  ldarg.0
0xc0454  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<item>5__10d
0xc0459  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>2__current
0xc045e  ldarg.0
0xc045f  ldc.i4.2
0xc0460  stfld    int32 <GetProperties>d__10c::<>1__state
0xc0465  ldc.i4.1
0xc0466  stloc.0
0xc0467  leave    loc_C5184
0xc046c  ldarg.0
0xc046d  ldc.i4.1
0xc046e  stfld    int32 <GetProperties>d__10c::<>1__state
0xc0473  ldarg.0
0xc0474  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__10c::<>7__wrap10e
0xc0479  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc047e  brtrue.s loc_C0441
0xc0480  ldarg.0
0xc0481  call     instance void <GetProperties>d__10c::<>m__Finally10f()
0xc0486  ldarg.0
0xc0487  ldarg.0
0xc0488  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc048d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0492  ldarg.0
0xc0493  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0498  ldstr    aActivities// "Activities"
0xc049d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc04a2  ldarg.0
0xc04a3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04a8  ldc.i4.0
0xc04a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc04ae  ldarg.0
0xc04af  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04b4  ldc.i4.5
0xc04b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc04ba  ldarg.0
0xc04bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04c0  ldc.i4.1
0xc04c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc04c6  ldarg.0
0xc04c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04cc  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet
0xc04d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc04d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc04db  ldarg.0
0xc04dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04e1  ldc.i4.1
0xc04e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc04e7  ldarg.0
0xc04e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04ed  ldc.i4.1
0xc04ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc04f3  ldarg.0
0xc04f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc04f9  ldnull
0xc04fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc04ff  ldarg.0
0xc0500  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0505  ldstr    aActivities// "Activities"
0xc050a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc050f  ldarg.0
0xc0510  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0515  ldnull
0xc0516  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc051b  ldarg.0
0xc051c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0521  ldc.i4.0
0xc0522  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc0527  ldarg.0
0xc0528  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc052d  ldc.i4.1
0xc052e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc0533  ldarg.0
0xc0534  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0539  ldc.i4.0
0xc053a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc053f  ldarg.0
0xc0540  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb3
0xc0545  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>2__current
0xc054a  ldarg.0
0xc054b  ldc.i4.3
0xc054c  stfld    int32 <GetProperties>d__10c::<>1__state
0xc0551  ldc.i4.1
0xc0552  stloc.0
0xc0553  leave    loc_C5184
0xc0558  ldarg.0
0xc0559  ldc.i4.m1
0xc055a  stfld    int32 <GetProperties>d__10c::<>1__state
0xc055f  ldarg.0
0xc0560  ldarg.0
0xc0561  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc0566  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc056b  ldarg.0
0xc056c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc0571  ldstr    aAllowcontentty// "AllowContentTypes"
0xc0576  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc057b  ldarg.0
0xc057c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc0581  ldc.i4.0
0xc0582  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc0587  ldarg.0
0xc0588  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc058d  ldc.i4.1
0xc058e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc0593  ldarg.0
0xc0594  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc0599  ldc.i4.0
0xc059a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc059f  ldarg.0
0xc05a0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05a5  ldtoken  [mscorlib]System.Boolean
0xc05aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc05af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc05b4  ldarg.0
0xc05b5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05ba  ldc.i4.1
0xc05bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc05c0  ldarg.0
0xc05c1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05c6  ldc.i4.1
0xc05c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc05cc  ldarg.0
0xc05cd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05d2  ldc.i4.0
0xc05d3  box      [mscorlib]System.Boolean
0xc05d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc05dd  ldarg.0
0xc05de  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05e3  ldstr    aAllowcontentty// "AllowContentTypes"
0xc05e8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc05ed  ldarg.0
0xc05ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05f3  ldnull
0xc05f4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc05f9  ldarg.0
0xc05fa  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc05ff  ldc.i4.0
0xc0600  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc0605  ldarg.0
0xc0606  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc060b  ldc.i4.0
0xc060c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc0611  ldarg.0
0xc0612  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc0617  ldc.i4.0
0xc0618  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc061d  ldarg.0
0xc061e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb4
0xc0623  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>2__current
0xc0628  ldarg.0
0xc0629  ldc.i4.4
0xc062a  stfld    int32 <GetProperties>d__10c::<>1__state
0xc062f  ldc.i4.1
0xc0630  stloc.0
0xc0631  leave    loc_C5184
0xc0636  ldarg.0
0xc0637  ldc.i4.m1
0xc0638  stfld    int32 <GetProperties>d__10c::<>1__state
0xc063d  ldarg.0
0xc063e  ldarg.0
0xc063f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc0644  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc0649  ldarg.0
0xc064a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc064f  ldstr    aAllowdeletion// "AllowDeletion"
0xc0654  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc0659  ldarg.0
0xc065a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc065f  ldc.i4.0
0xc0660  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc0665  ldarg.0
0xc0666  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc066b  ldc.i4.1
0xc066c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc0671  ldarg.0
0xc0672  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc0677  ldc.i4.1
0xc0678  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc067d  ldarg.0
0xc067e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc0683  ldtoken  [mscorlib]System.Boolean
0xc0688  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc068d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc0692  ldarg.0
0xc0693  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc0698  ldc.i4.0
0xc0699  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc069e  ldarg.0
0xc069f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06a4  ldc.i4.1
0xc06a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc06aa  ldarg.0
0xc06ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06b0  ldc.i4.0
0xc06b1  box      [mscorlib]System.Boolean
0xc06b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc06bb  ldarg.0
0xc06bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06c1  ldstr    aAllowdeletion// "AllowDeletion"
0xc06c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0xc06cb  ldarg.0
0xc06cc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06d1  ldnull
0xc06d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0xc06d7  ldarg.0
0xc06d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06dd  ldc.i4.0
0xc06de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xc06e3  ldarg.0
0xc06e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06e9  ldc.i4.0
0xc06ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0xc06ef  ldarg.0
0xc06f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc06f5  ldc.i4.0
0xc06f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0xc06fb  ldarg.0
0xc06fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb5
0xc0701  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>2__current
0xc0706  ldarg.0
0xc0707  ldc.i4.5
0xc0708  stfld    int32 <GetProperties>d__10c::<>1__state
0xc070d  ldc.i4.1
0xc070e  stloc.0
0xc070f  leave    loc_C5184
0xc0714  ldarg.0
0xc0715  ldc.i4.m1
0xc0716  stfld    int32 <GetProperties>d__10c::<>1__state
0xc071b  ldarg.0
0xc071c  ldarg.0
0xc071d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0xc0722  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0727  ldarg.0
0xc0728  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc072d  ldstr    aBasetemplate// "BaseTemplate"
0xc0732  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0xc0737  ldarg.0
0xc0738  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc073d  ldc.i4.0
0xc073e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0xc0743  ldarg.0
0xc0744  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0749  ldc.i4.1
0xc074a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xc074f  ldarg.0
0xc0750  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0755  ldc.i4.0
0xc0756  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0xc075b  ldarg.0
0xc075c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0761  ldtoken  [mscorlib]System.Int32
0xc0766  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc076b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0xc0770  ldarg.0
0xc0771  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0776  ldc.i4.1
0xc0777  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0xc077c  ldarg.0
0xc077d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc0782  ldc.i4.1
0xc0783  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0xc0788  ldarg.0
0xc0789  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
0xc078e  ldc.i4.0
0xc078f  box      [mscorlib]System.Int32
0xc0794  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0xc0799  ldarg.0
0xc079a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__10c::<>g__initLocalb6
  ... truncated ...
```
