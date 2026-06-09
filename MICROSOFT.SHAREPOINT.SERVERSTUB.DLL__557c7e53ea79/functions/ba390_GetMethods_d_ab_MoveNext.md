# <GetMethods>d__ab::MoveNext

- ea: `0xba390`
- end: `0xc0107`
- name: `<GetMethods>d__ab::MoveNext`
- size: `23927`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x87a0`
- `0xba390`
- `0xc0130`
- `0xc0190`

## string_xrefs

- `0xbae12`: `copyRoleAssignments`
- `0xbfed9`: `Update`
- `0xbff11`: `Update`
- `0xbc532`: `DeleteObject`
- `0xbc360`: `CreateMappedView`
- `0xbc398`: `CreateMappedView`
- `0xbfbb3`: `SyncFlowTemplates`
- `0xbfbeb`: `SyncFlowTemplates`
- `0xbb4a4`: `CreateDocumentAndGetEditLink`
- `0xbb4dc`: `CreateDocumentAndGetEditLink`
- `0xbc18e`: `CreateDocumentWithDefaultName`
- `0xbc1c6`: `CreateDocumentWithDefaultName`
- `0xbb258`: `CreateDocument`
- `0xbb290`: `CreateDocument`
- `0xbb7a2`: `CreateDocument`
- `0xbb9ee`: `CreateDocument`
- `0xbbcb4`: `CreateDocument`
- `0xbbf7a`: `CreateDocument`
- `0xbbc7c`: `CreateDocumentFromTemplateStream`
- `0xbb9b6`: `CreateDocumentFromTemplateBytes`
- `0xbb76a`: `CreateDocumentFromTemplate`
- `0xbbf42`: `CreateDocumentFromTemplateUsingPath`
- `0xbf407`: `SaveAsTemplate`
- `0xbf43f`: `SaveAsTemplate`
- `0xbaf1d`: `BulkValidateUpdateListItems`
- `0xbd4e5`: `GetListItemChangesSinceToken`
- `0xbd519`: `GetListItemChangesSinceToken`
- `0xba673`: `AddItemUsingPath`
- `0xba6ab`: `AddItemUsingPath`
- `0xba7ca`: `AddValidateUpdateItem`
- `0xba7fe`: `AddValidateUpdateItem`
- `0xbaabf`: `AddValidateUpdateItem`
- `0xbaa8b`: `AddValidateUpdateItemUsingPath`
- `0xba88c`: `listItemCreateInfo`
- `0xbab4d`: `listItemCreateInfo`
- `0xba980`: `bNewDocumentUpdate`
- `0xbac41`: `bNewDocumentUpdate`
- `0xbb0d3`: `bNewDocumentUpdate`
- `0xba9fa`: `checkInComment`
- `0xbacbb`: `checkInComment`
- `0xbb14d`: `checkInComment`
- `0xbaf51`: `BulkValidateUpdateListItems_Client`
- `0xbb1c7`: `folderPath`
- `0xbb5e4`: `folderPath`
- `0xbc254`: `folderPath`
- `0xbb412`: `templateType`
- `0xbb65e`: `documentTemplateType`
- `0xbb6d8`: `templateUrl`
- `0xbb924`: `templateUrl`
- `0xbbb70`: `templateBytes`
- `0xbbbea`: `extension`
- `0xbbe36`: `extension`
- `0xbc2ce`: `extension`
- `0xbbeb0`: `templateStream`
- `0xbc008`: `filePath`
- `0xbc0fc`: `templatePath`
- `0xbc56a`: `Delete`
- `0xbdc5b`: `bForceCreate`
- `0xbe97d`: `viewXml`

## pseudocode

```c

```

## disassembly

```asm
0xba390  ldarg.0
0xba391  ldfld    int32 <GetMethods>d__ab::<>1__state
0xba396  stloc.1
0xba397  ldloc.1
0xba398  switch   loc_BA486, loc_C00FA, loc_BA4F0, loc_BA65A, loc_BA7B1, loc_BAA72, loc_BAD33, loc_BAF04, loc_BB23F, loc_BB48B, loc_BB751, loc_BB99D, loc_BBC63, loc_BBF29, loc_BC175, loc_BC347, loc_BC519, loc_BC5F7, loc_BC74F, loc_BC921, loc_BCA79, loc_BCB57, loc_BCD26, loc_BCE7B, loc_BCFD3, loc_BD128, loc_BD280, loc_BD4CC, loc_BD620, loc_BD7F2, loc_BD94A, loc_BDA28, loc_BDB02, loc_BDD4E, loc_BDEA6, loc_BDFFE, loc_BE156, loc_BE328, loc_BE406, loc_BE746, loc_BE89E, loc_BE9F6, loc_BEBC8, loc_BED20, loc_BEF6C, loc_BF04A, loc_BF128, loc_BF3EE, loc_BF6B4, loc_BF80C, loc_BF964, loc_BFABC, loc_BFB9A, loc_BFCEE, loc_BFEC0 \
0xba481  br       loc_C00FA
0xba486  ldarg.0
0xba487  ldc.i4.m1
0xba488  stfld    int32 <GetMethods>d__ab::<>1__state
0xba48d  ldarg.0
0xba48e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__ab::proxyContext
0xba493  brtrue.s loc_BA4A0
0xba495  ldstr    aProxycontext// "proxyContext"
0xba49a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xba49f  throw
0xba4a0  ldarg.0
0xba4a1  ldarg.0
0xba4a2  ldfld    class Microsoft.SharePoint.ServerStub.SPListServerStub <GetMethods>d__ab::<>4__this
0xba4a7  ldarg.0
0xba4a8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__ab::proxyContext
0xba4ad  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPListServerStub::<>n__FabricatedMethodb0(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xba4b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0xba4b7  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__ab::<>7__wrapae
0xba4bc  ldarg.0
0xba4bd  ldc.i4.1
0xba4be  stfld    int32 <GetMethods>d__ab::<>1__state
0xba4c3  br.s     loc_BA4F7
0xba4c5  ldarg.0
0xba4c6  ldarg.0
0xba4c7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__ab::<>7__wrapae
0xba4cc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0xba4d1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<itemBase>5__ac
0xba4d6  ldarg.0
0xba4d7  ldarg.0
0xba4d8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<itemBase>5__ac
0xba4dd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>2__current
0xba4e2  ldarg.0
0xba4e3  ldc.i4.2
0xba4e4  stfld    int32 <GetMethods>d__ab::<>1__state
0xba4e9  ldc.i4.1
0xba4ea  stloc.0
0xba4eb  leave    loc_C0105
0xba4f0  ldarg.0
0xba4f1  ldc.i4.1
0xba4f2  stfld    int32 <GetMethods>d__ab::<>1__state
0xba4f7  ldarg.0
0xba4f8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__ab::<>7__wrapae
0xba4fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xba502  brtrue.s loc_BA4C5
0xba504  ldarg.0
0xba505  call     instance void <GetMethods>d__ab::<>m__Finallyaf()
0xba50a  ldarg.0
0xba50b  ldarg.0
0xba50c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xba511  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba516  ldarg.0
0xba517  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba51c  ldstr    aAdditem// "AddItem"
0xba521  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xba526  ldarg.0
0xba527  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba52c  ldc.i4.0
0xba52d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xba532  ldarg.0
0xba533  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba538  ldc.i4.0
0xba539  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xba53e  ldarg.0
0xba53f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba544  ldc.i4   0xFFFFFFF
0xba549  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xba54e  ldarg.0
0xba54f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba554  ldstr    aAdditem// "AddItem"
0xba559  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xba55e  ldarg.0
0xba55f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba564  ldc.i4.0
0xba565  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xba56a  ldarg.0
0xba56b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba570  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0xba575  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba57a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xba57f  ldarg.0
0xba580  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba585  ldc.i4.4
0xba586  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xba58b  ldarg.0
0xba58c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba591  ldc.i4.0
0xba592  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xba597  ldarg.0
0xba598  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba59d  ldc.i4.0
0xba59e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xba5a3  ldarg.0
0xba5a4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba5a9  ldc.i4.0
0xba5aa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xba5af  ldarg.0
0xba5b0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba5b5  ldc.i4.0
0xba5b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xba5bb  ldarg.0
0xba5bc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal16
0xba5c1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba5c6  ldarg.0
0xba5c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba5cc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xba5d1  ldarg.0
0xba5d2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xba5d7  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba5dc  ldarg.0
0xba5dd  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba5e2  ldstr    aParameters// "parameters"
0xba5e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xba5ec  ldarg.0
0xba5ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba5f2  ldc.i4.0
0xba5f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xba5f8  ldarg.0
0xba5f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba5fe  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItemCreationInformation
0xba603  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba608  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xba60d  ldarg.0
0xba60e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba613  ldc.i4.2
0xba614  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xba619  ldarg.0
0xba61a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba61f  ldc.i4.0
0xba620  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xba625  ldarg.0
0xba626  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba62b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xba630  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xba635  ldarg.0
0xba636  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal17
0xba63b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xba640  ldarg.0
0xba641  ldarg.0
0xba642  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba647  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>2__current
0xba64c  ldarg.0
0xba64d  ldc.i4.3
0xba64e  stfld    int32 <GetMethods>d__ab::<>1__state
0xba653  ldc.i4.1
0xba654  stloc.0
0xba655  leave    loc_C0105
0xba65a  ldarg.0
0xba65b  ldc.i4.m1
0xba65c  stfld    int32 <GetMethods>d__ab::<>1__state
0xba661  ldarg.0
0xba662  ldarg.0
0xba663  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xba668  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba66d  ldarg.0
0xba66e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba673  ldstr    aAdditemusingpa// "AddItemUsingPath"
0xba678  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xba67d  ldarg.0
0xba67e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba683  ldc.i4.0
0xba684  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xba689  ldarg.0
0xba68a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba68f  ldc.i4.0
0xba690  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xba695  ldarg.0
0xba696  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba69b  ldc.i4   0xFFFFFFF
0xba6a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xba6a5  ldarg.0
0xba6a6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6ab  ldstr    aAdditemusingpa// "AddItemUsingPath"
0xba6b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xba6b5  ldarg.0
0xba6b6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6bb  ldc.i4.0
0xba6bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xba6c1  ldarg.0
0xba6c2  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6c7  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0xba6cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba6d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xba6d6  ldarg.0
0xba6d7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6dc  ldc.i4.4
0xba6dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xba6e2  ldarg.0
0xba6e3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6e8  ldc.i4.0
0xba6e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xba6ee  ldarg.0
0xba6ef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba6f4  ldc.i4.0
0xba6f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0xba6fa  ldarg.0
0xba6fb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba700  ldc.i4.0
0xba701  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0xba706  ldarg.0
0xba707  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba70c  ldc.i4.1
0xba70d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0xba712  ldarg.0
0xba713  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal18
0xba718  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba71d  ldarg.0
0xba71e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba723  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0xba728  ldarg.0
0xba729  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0xba72e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba733  ldarg.0
0xba734  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba739  ldstr    aParameters// "parameters"
0xba73e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0xba743  ldarg.0
0xba744  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba749  ldc.i4.0
0xba74a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0xba74f  ldarg.0
0xba750  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba755  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.SPListItemCreationInformationUsingPath
0xba75a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba75f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0xba764  ldarg.0
0xba765  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba76a  ldc.i4.2
0xba76b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xba770  ldarg.0
0xba771  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba776  ldc.i4.0
0xba777  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0xba77c  ldarg.0
0xba77d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba782  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xba787  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0xba78c  ldarg.0
0xba78d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__ab::<>g__initLocal19
0xba792  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0xba797  ldarg.0
0xba798  ldarg.0
0xba799  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<item>5__ad
0xba79e  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>2__current
0xba7a3  ldarg.0
0xba7a4  ldc.i4.4
0xba7a5  stfld    int32 <GetMethods>d__ab::<>1__state
0xba7aa  ldc.i4.1
0xba7ab  stloc.0
0xba7ac  leave    loc_C0105
0xba7b1  ldarg.0
0xba7b2  ldc.i4.m1
0xba7b3  stfld    int32 <GetMethods>d__ab::<>1__state
0xba7b8  ldarg.0
0xba7b9  ldarg.0
0xba7ba  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0xba7bf  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7c4  ldarg.0
0xba7c5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7ca  ldstr    aAddvalidateupd// "AddValidateUpdateItem"
0xba7cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0xba7d4  ldarg.0
0xba7d5  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7da  ldc.i4.0
0xba7db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0xba7e0  ldarg.0
0xba7e1  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7e6  ldc.i4.0
0xba7e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0xba7ec  ldarg.0
0xba7ed  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7f2  ldc.i4.8
0xba7f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0xba7f8  ldarg.0
0xba7f9  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba7fe  ldstr    aAddvalidateupd// "AddValidateUpdateItem"
0xba803  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0xba808  ldarg.0
0xba809  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba80e  ldc.i4.0
0xba80f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0xba814  ldarg.0
0xba815  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba81a  ldtoken  class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItemFormUpdateValue>
0xba81f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xba824  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0xba829  ldarg.0
0xba82a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba82f  ldc.i4.3
0xba830  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0xba835  ldarg.0
0xba836  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
0xba83b  ldc.i4.0
0xba83c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0xba841  ldarg.0
0xba842  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__ab::<>g__initLocal1a
  ... truncated ...
```
