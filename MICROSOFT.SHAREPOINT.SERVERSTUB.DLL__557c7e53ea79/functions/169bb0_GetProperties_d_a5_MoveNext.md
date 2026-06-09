# <GetProperties>d__a5::MoveNext

- ea: `0x169bb0`
- end: `0x16d068`
- name: `<GetProperties>d__a5::MoveNext`
- size: `13496`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x84250`
- `0x169bb0`
- `0x16d090`
- `0x16d0f0`

## string_xrefs

- `0x16aa51`: `CurrentChangeToken`
- `0x16aabe`: `CurrentChangeToken`
- `0x16bff9`: `ServerRelativePath`
- `0x16c066`: `ServerRelativePath`
- `0x16bad3`: `ReadOnly`
- `0x16bb45`: `ReadOnly`
- `0x16b91f`: `ResourcePath`
- `0x16c28c`: `ShareByLinkEnabled`
- `0x16c2fe`: `ShareByLinkEnabled`
- `0x169d50`: `AllowCreateDeclarativeWorkflow`
- `0x169dc2`: `AllowCreateDeclarativeWorkflow`
- `0x16a0c8`: `AllowRevertFromTemplate`
- `0x16a13a`: `AllowRevertFromTemplate`
- `0x16a1a6`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x16a218`: `AllowSaveDeclarativeWorkflowAsTemplate`
- `0x16a363`: `AllowSelfServiceUpgrade`
- `0x16a3d5`: `AllowSelfServiceUpgrade`
- `0x16a442`: `AllowSelfServiceUpgradeEvaluation`
- `0x16a4b4`: `AllowSelfServiceUpgradeEvaluation`
- `0x16a893`: `CommentsOnSitePagesDisabled`
- `0x16a905`: `CommentsOnSitePagesDisabled`
- `0x16a972`: `CompatibilityLevel`
- `0x16a9e4`: `CompatibilityLevel`
- `0x16ace4`: `DisableCompanyWideSharingLinks`
- `0x16ad56`: `DisableCompanyWideSharingLinks`
- `0x16b9f9`: `PrimaryUri`
- `0x16ba66`: `PrimaryUri`
- `0x16c529`: `StatusBarLink`
- `0x16c596`: `StatusBarLink`
- `0x16c89b`: `UIVersionConfigurationEnabled`
- `0x16c90d`: `UIVersionConfigurationEnabled`
- `0x16cb3c`: `UpgradeScheduled`
- `0x16cbae`: `UpgradeScheduled`
- `0x16cc1b`: `UpgradeScheduledDate`
- `0x16cc96`: `UpgradeScheduledDate`

## pseudocode

```c

```

## disassembly

```asm
0x169bb0  ldarg.0
0x169bb1  ldfld    int32 <GetProperties>d__a5::<>1__state
0x169bb6  stloc.1
0x169bb7  ldloc.1
0x169bb8  switch   loc_169CBA, loc_16D05B, loc_169D24, loc_169E15, loc_169EF3, loc_169FD1, loc_16A0AF, loc_16A18D, loc_16A26B, loc_16A34A, loc_16A429, loc_16A508, loc_16A5E2, loc_16A6C1, loc_16A7A0, loc_16A87A, loc_16A959, loc_16AA38, loc_16AB12, loc_16ABEC, loc_16ACCB, loc_16ADAA, loc_16AE89, loc_16AF63, loc_16B042, loc_16B11C, loc_16B1F6, loc_16B2DD, loc_16B3C4, loc_16B4AC, loc_16B58B, loc_16B665, loc_16B74D, loc_16B82C, loc_16B906, loc_16B9E0, loc_16BABA, loc_16BB99, loc_16BC73, loc_16BD4D, loc_16BE27, loc_16BF06, loc_16BFE0, loc_16C0BA, loc_16C194, loc_16C273, loc_16C352, loc_16C431, loc_16C510, loc_16C5EA, loc_16C6C4, loc_16C7A3, loc_16C882 \
0x169cb5  br       loc_16D05B
0x169cba  ldarg.0
0x169cbb  ldc.i4.m1
0x169cbc  stfld    int32 <GetProperties>d__a5::<>1__state
0x169cc1  ldarg.0
0x169cc2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__a5::proxyContext
0x169cc7  brtrue.s loc_169CD4
0x169cc9  ldstr    aProxycontext// "proxyContext"
0x169cce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x169cd3  throw
0x169cd4  ldarg.0
0x169cd5  ldarg.0
0x169cd6  ldfld    class Microsoft.SharePoint.ServerStub.SPSiteServerStub <GetProperties>d__a5::<>4__this
0x169cdb  ldarg.0
0x169cdc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__a5::proxyContext
0x169ce1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> Microsoft.SharePoint.ServerStub.SPSiteServerStub::<>n__FabricatedMethoda9(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x169ce6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::GetEnumerator()
0x169ceb  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a5::<>7__wrapa7
0x169cf0  ldarg.0
0x169cf1  ldc.i4.1
0x169cf2  stfld    int32 <GetProperties>d__a5::<>1__state
0x169cf7  br.s     loc_169D2B
0x169cf9  ldarg.0
0x169cfa  ldarg.0
0x169cfb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a5::<>7__wrapa7
0x169d00  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation>::get_Current()
0x169d05  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<item>5__a6
0x169d0a  ldarg.0
0x169d0b  ldarg.0
0x169d0c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<item>5__a6
0x169d11  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>2__current
0x169d16  ldarg.0
0x169d17  ldc.i4.2
0x169d18  stfld    int32 <GetProperties>d__a5::<>1__state
0x169d1d  ldc.i4.1
0x169d1e  stloc.0
0x169d1f  leave    loc_16D066
0x169d24  ldarg.0
0x169d25  ldc.i4.1
0x169d26  stfld    int32 <GetProperties>d__a5::<>1__state
0x169d2b  ldarg.0
0x169d2c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation> <GetProperties>d__a5::<>7__wrapa7
0x169d31  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x169d36  brtrue.s loc_169CF9
0x169d38  ldarg.0
0x169d39  call     instance void <GetProperties>d__a5::<>m__Finallya8()
0x169d3e  ldarg.0
0x169d3f  ldarg.0
0x169d40  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x169d45  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d4a  ldarg.0
0x169d4b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d50  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x169d55  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x169d5a  ldarg.0
0x169d5b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d60  ldc.i4.0
0x169d61  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x169d66  ldarg.0
0x169d67  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d6c  ldc.i4.1
0x169d6d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x169d72  ldarg.0
0x169d73  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d78  ldc.i4.0
0x169d79  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x169d7e  ldarg.0
0x169d7f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d84  ldtoken  [mscorlib]System.Boolean
0x169d89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x169d8e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x169d93  ldarg.0
0x169d94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169d99  ldc.i4.0
0x169d9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x169d9f  ldarg.0
0x169da0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169da5  ldc.i4.1
0x169da6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x169dab  ldarg.0
0x169dac  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169db1  ldc.i4.0
0x169db2  box      [mscorlib]System.Boolean
0x169db7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x169dbc  ldarg.0
0x169dbd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169dc2  ldstr    aAllowcreatedec// "AllowCreateDeclarativeWorkflow"
0x169dc7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x169dcc  ldarg.0
0x169dcd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169dd2  ldnull
0x169dd3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x169dd8  ldarg.0
0x169dd9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169dde  ldc.i4.0
0x169ddf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x169de4  ldarg.0
0x169de5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169dea  ldc.i4.0
0x169deb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x169df0  ldarg.0
0x169df1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169df6  ldc.i4.0
0x169df7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x169dfc  ldarg.0
0x169dfd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6a
0x169e02  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>2__current
0x169e07  ldarg.0
0x169e08  ldc.i4.3
0x169e09  stfld    int32 <GetProperties>d__a5::<>1__state
0x169e0e  ldc.i4.1
0x169e0f  stloc.0
0x169e10  leave    loc_16D066
0x169e15  ldarg.0
0x169e16  ldc.i4.m1
0x169e17  stfld    int32 <GetProperties>d__a5::<>1__state
0x169e1c  ldarg.0
0x169e1d  ldarg.0
0x169e1e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x169e23  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e28  ldarg.0
0x169e29  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e2e  ldstr    aAllowdesigner// "AllowDesigner"
0x169e33  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x169e38  ldarg.0
0x169e39  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e3e  ldc.i4.0
0x169e3f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x169e44  ldarg.0
0x169e45  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e4a  ldc.i4.1
0x169e4b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x169e50  ldarg.0
0x169e51  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e56  ldc.i4.0
0x169e57  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x169e5c  ldarg.0
0x169e5d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e62  ldtoken  [mscorlib]System.Boolean
0x169e67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x169e6c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x169e71  ldarg.0
0x169e72  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e77  ldc.i4.0
0x169e78  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x169e7d  ldarg.0
0x169e7e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e83  ldc.i4.1
0x169e84  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x169e89  ldarg.0
0x169e8a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169e8f  ldc.i4.0
0x169e90  box      [mscorlib]System.Boolean
0x169e95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x169e9a  ldarg.0
0x169e9b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169ea0  ldstr    aAllowdesigner// "AllowDesigner"
0x169ea5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x169eaa  ldarg.0
0x169eab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169eb0  ldnull
0x169eb1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x169eb6  ldarg.0
0x169eb7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169ebc  ldc.i4.0
0x169ebd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x169ec2  ldarg.0
0x169ec3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169ec8  ldc.i4.0
0x169ec9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x169ece  ldarg.0
0x169ecf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169ed4  ldc.i4.0
0x169ed5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x169eda  ldarg.0
0x169edb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6b
0x169ee0  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>2__current
0x169ee5  ldarg.0
0x169ee6  ldc.i4.4
0x169ee7  stfld    int32 <GetProperties>d__a5::<>1__state
0x169eec  ldc.i4.1
0x169eed  stloc.0
0x169eee  leave    loc_16D066
0x169ef3  ldarg.0
0x169ef4  ldc.i4.m1
0x169ef5  stfld    int32 <GetProperties>d__a5::<>1__state
0x169efa  ldarg.0
0x169efb  ldarg.0
0x169efc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x169f01  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f06  ldarg.0
0x169f07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f0c  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x169f11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x169f16  ldarg.0
0x169f17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f1c  ldc.i4.0
0x169f1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x169f22  ldarg.0
0x169f23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f28  ldc.i4.1
0x169f29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x169f2e  ldarg.0
0x169f2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f34  ldc.i4.1
0x169f35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x169f3a  ldarg.0
0x169f3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f40  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.ScriptSafeExternalEmbedding
0x169f45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x169f4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x169f4f  ldarg.0
0x169f50  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f55  ldc.i4.0
0x169f56  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x169f5b  ldarg.0
0x169f5c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f61  ldc.i4.1
0x169f62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x169f67  ldarg.0
0x169f68  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f6d  ldc.i4.0
0x169f6e  box      [Microsoft.SharePoint]Microsoft.SharePoint.ScriptSafeExternalEmbedding
0x169f73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x169f78  ldarg.0
0x169f79  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f7e  ldstr    aAllowexternale// "AllowExternalEmbeddingWrapper"
0x169f83  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_OriginalName(string)
0x169f88  ldarg.0
0x169f89  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f8e  ldnull
0x169f8f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulPropertyType(class [mscorlib]System.Type)
0x169f94  ldarg.0
0x169f95  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169f9a  ldc.i4.0
0x169f9b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x169fa0  ldarg.0
0x169fa1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169fa6  ldc.i4.1
0x169fa7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsBeta(bool)
0x169fac  ldarg.0
0x169fad  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169fb2  ldc.i4.0
0x169fb3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RESTfulUseRawQueryStringValue(bool)
0x169fb8  ldarg.0
0x169fb9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6c
0x169fbe  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>2__current
0x169fc3  ldarg.0
0x169fc4  ldc.i4.5
0x169fc5  stfld    int32 <GetProperties>d__a5::<>1__state
0x169fca  ldc.i4.1
0x169fcb  stloc.0
0x169fcc  leave    loc_16D066
0x169fd1  ldarg.0
0x169fd2  ldc.i4.m1
0x169fd3  stfld    int32 <GetProperties>d__a5::<>1__state
0x169fd8  ldarg.0
0x169fd9  ldarg.0
0x169fda  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::.ctor()
0x169fdf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x169fe4  ldarg.0
0x169fe5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x169fea  ldstr    aAllowmasterpag// "AllowMasterPageEditing"
0x169fef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_Name(string)
0x169ff4  ldarg.0
0x169ff5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x169ffa  ldc.i4.0
0x169ffb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_IsStatic(bool)
0x16a000  ldarg.0
0x16a001  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a006  ldc.i4.1
0x16a007  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x16a00c  ldarg.0
0x16a00d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a012  ldc.i4.0
0x16a013  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ExcludeFromDefaultRetrieval(bool)
0x16a018  ldarg.0
0x16a019  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a01e  ldtoken  [mscorlib]System.Boolean
0x16a023  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a028  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_PropertyType(class [mscorlib]System.Type)
0x16a02d  ldarg.0
0x16a02e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a033  ldc.i4.0
0x16a034  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_ReadOnly(bool)
0x16a039  ldarg.0
0x16a03a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a03f  ldc.i4.1
0x16a040  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_RequiredForHttpPutRequest(bool)
0x16a045  ldarg.0
0x16a046  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation <GetProperties>d__a5::<>g__initLocal6d
0x16a04b  ldc.i4.0
0x16a04c  box      [mscorlib]System.Boolean
0x16a051  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.PropertyInformation::set_DefaultValue(object)
0x16a056  ldarg.0
  ... truncated ...
```
