# <GetMethods>d__c::MoveNext_1

- ea: `0x1794b0`
- end: `0x179d72`
- name: `<GetMethods>d__c::MoveNext_1`
- size: `2242`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x8f630`
- `0x1794b0`
- `0x179da0`
- `0x179e00`

## string_xrefs

- `0x179c9d`: `Update`
- `0x179cd5`: `Update`
- `0x1797c3`: `DeleteObject`
- `0x1796b8`: `folderPath`
- `0x1799dc`: `folderPath`
- `0x1797fb`: `Delete`
- `0x179c0c`: `viewXml`
- `0x179b4a`: `SetViewXml`
- `0x1798a0`: `RemoveFromSpotlight`
- `0x1798d4`: `RemoveFromSpotlight`
- `0x179b7e`: `SetViewXml_Client`

## pseudocode

```c

```

## disassembly

```asm
0x1794b0  ldarg.0
0x1794b1  ldfld    int32 <GetMethods>d__c::<>1__state
0x1794b6  stloc.1
0x1794b7  ldloc.1
0x1794b8  switch   loc_1794E6, loc_179D65, loc_179550, loc_1797AA, loc_179887, loc_179A54, loc_179B31, loc_179C84, loc_179D5E
0x1794e1  br       loc_179D65
0x1794e6  ldarg.0
0x1794e7  ldc.i4.m1
0x1794e8  stfld    int32 <GetMethods>d__c::<>1__state
0x1794ed  ldarg.0
0x1794ee  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__c::proxyContext
0x1794f3  brtrue.s loc_179500
0x1794f5  ldstr    aProxycontext// "proxyContext"
0x1794fa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1794ff  throw
0x179500  ldarg.0
0x179501  ldarg.0
0x179502  ldfld    class Microsoft.SharePoint.ServerStub.SPViewServerStub <GetMethods>d__c::<>4__this
0x179507  ldarg.0
0x179508  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__c::proxyContext
0x17950d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.ServerStub.SPViewServerStub::<>n__FabricatedMethod11(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext node)
0x179512  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x179517  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x17951c  ldarg.0
0x17951d  ldc.i4.1
0x17951e  stfld    int32 <GetMethods>d__c::<>1__state
0x179523  br.s     loc_179557
0x179525  ldarg.0
0x179526  ldarg.0
0x179527  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x17952c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x179531  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<itemBase>5__d
0x179536  ldarg.0
0x179537  ldarg.0
0x179538  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<itemBase>5__d
0x17953d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x179542  ldarg.0
0x179543  ldc.i4.2
0x179544  stfld    int32 <GetMethods>d__c::<>1__state
0x179549  ldc.i4.1
0x17954a  stloc.0
0x17954b  leave    loc_179D70
0x179550  ldarg.0
0x179551  ldc.i4.1
0x179552  stfld    int32 <GetMethods>d__c::<>1__state
0x179557  ldarg.0
0x179558  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__c::<>7__wrapf
0x17955d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x179562  brtrue.s loc_179525
0x179564  ldarg.0
0x179565  call     instance void <GetMethods>d__c::<>m__Finally10()
0x17956a  ldarg.0
0x17956b  ldarg.0
0x17956c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x179571  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x179576  ldarg.0
0x179577  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x17957c  ldstr    aAddtospotlight// "AddToSpotlight"
0x179581  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x179586  ldarg.0
0x179587  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x17958c  ldc.i4.0
0x17958d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x179592  ldarg.0
0x179593  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x179598  ldc.i4.0
0x179599  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x17959e  ldarg.0
0x17959f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795a4  ldc.i4.8
0x1795a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1795aa  ldarg.0
0x1795ab  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795b0  ldstr    aAddtospotlight// "AddToSpotlight"
0x1795b5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x1795ba  ldarg.0
0x1795bb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795c0  ldc.i4.0
0x1795c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x1795c6  ldarg.0
0x1795c7  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795cc  ldtoken  [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSpotlightResult
0x1795d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1795d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x1795db  ldarg.0
0x1795dc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795e1  ldc.i4.4
0x1795e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1795e7  ldarg.0
0x1795e8  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795ed  ldc.i4.0
0x1795ee  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x1795f3  ldarg.0
0x1795f4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x1795f9  ldc.i4.0
0x1795fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x1795ff  ldarg.0
0x179600  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x179605  ldc.i4.0
0x179606  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x17960b  ldarg.0
0x17960c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x179611  ldc.i4.1
0x179612  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x179617  ldarg.0
0x179618  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal0
0x17961d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x179622  ldarg.0
0x179623  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x179628  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x17962d  ldarg.0
0x17962e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x179633  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x179638  ldarg.0
0x179639  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x17963e  ldstr    aItemid// "itemId"
0x179643  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x179648  ldarg.0
0x179649  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x17964e  ldc.i4.0
0x17964f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x179654  ldarg.0
0x179655  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x17965a  ldtoken  [mscorlib]System.Int32
0x17965f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179664  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x179669  ldarg.0
0x17966a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x17966f  ldc.i4.1
0x179670  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x179675  ldarg.0
0x179676  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x17967b  ldc.i4.0
0x17967c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x179681  ldarg.0
0x179682  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x179687  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x17968c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x179691  ldarg.0
0x179692  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal1
0x179697  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x17969c  ldarg.0
0x17969d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x1796a2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x1796a7  ldarg.0
0x1796a8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x1796ad  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796b2  ldarg.0
0x1796b3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796b8  ldstr    aFolderpath// "folderPath"
0x1796bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x1796c2  ldarg.0
0x1796c3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796c8  ldc.i4.0
0x1796c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x1796ce  ldarg.0
0x1796cf  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796d4  ldtoken  [mscorlib]System.String
0x1796d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1796de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x1796e3  ldarg.0
0x1796e4  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796e9  ldc.i4.1
0x1796ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x1796ef  ldarg.0
0x1796f0  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x1796f5  ldc.i4.0
0x1796f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x1796fb  ldarg.0
0x1796fc  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x179701  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x179706  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x17970b  ldarg.0
0x17970c  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal2
0x179711  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x179716  ldarg.0
0x179717  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x17971c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x179721  ldarg.0
0x179722  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x179727  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x17972c  ldarg.0
0x17972d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x179732  ldstr    aAfteritemid// "afterItemId"
0x179737  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_Name(string)
0x17973c  ldarg.0
0x17973d  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x179742  ldc.i4.0
0x179743  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_RESTfulParameterSource(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.RESTfulParameterSource)
0x179748  ldarg.0
0x179749  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x17974e  ldtoken  [mscorlib]System.Int32
0x179753  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179758  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type)
0x17975d  ldarg.0
0x17975e  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x179763  ldc.i4.1
0x179764  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x179769  ldarg.0
0x17976a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x17976f  ldc.i4.0
0x179770  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_IsOptional(bool)
0x179775  ldarg.0
0x179776  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x17977b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x179780  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation::set_DefaultValue(object)
0x179785  ldarg.0
0x179786  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation <GetMethods>d__c::<>g__initLocal3
0x17978b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ParameterInformation>::Add(var<u1>)
0x179790  ldarg.0
0x179791  ldarg.0
0x179792  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x179797  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x17979c  ldarg.0
0x17979d  ldc.i4.3
0x17979e  stfld    int32 <GetMethods>d__c::<>1__state
0x1797a3  ldc.i4.1
0x1797a4  stloc.0
0x1797a5  leave    loc_179D70
0x1797aa  ldarg.0
0x1797ab  ldc.i4.m1
0x1797ac  stfld    int32 <GetMethods>d__c::<>1__state
0x1797b1  ldarg.0
0x1797b2  ldarg.0
0x1797b3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x1797b8  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797bd  ldarg.0
0x1797be  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797c3  ldstr    aDeleteobject// "DeleteObject"
0x1797c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1797cd  ldarg.0
0x1797ce  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797d3  ldc.i4.0
0x1797d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x1797d9  ldarg.0
0x1797da  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797df  ldc.i4.0
0x1797e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x1797e5  ldarg.0
0x1797e6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797eb  ldc.i4   0xFFFFFFF
0x1797f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x1797f5  ldarg.0
0x1797f6  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x1797fb  ldstr    aDelete// "Delete"
0x179800  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x179805  ldarg.0
0x179806  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x17980b  ldc.i4.0
0x17980c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x179811  ldarg.0
0x179812  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x179817  ldtoken  [mscorlib]System.Void
0x17981c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179821  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x179826  ldarg.0
0x179827  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x17982c  ldc.i4.0
0x17982d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x179832  ldarg.0
0x179833  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x179838  ldc.i4.0
0x179839  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x17983e  ldarg.0
0x17983f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x179844  ldc.i4.0
0x179845  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x17984a  ldarg.0
0x17984b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x179850  ldc.i4.0
0x179851  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x179856  ldarg.0
0x179857  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x17985c  ldc.i4.0
0x17985d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x179862  ldarg.0
0x179863  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal4
0x179868  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x17986d  ldarg.0
0x17986e  ldarg.0
0x17986f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<item>5__e
0x179874  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>2__current
0x179879  ldarg.0
0x17987a  ldc.i4.4
0x17987b  stfld    int32 <GetMethods>d__c::<>1__state
0x179880  ldc.i4.1
0x179881  stloc.0
0x179882  leave    loc_179D70
0x179887  ldarg.0
0x179888  ldc.i4.m1
0x179889  stfld    int32 <GetMethods>d__c::<>1__state
0x17988e  ldarg.0
0x17988f  ldarg.0
0x179890  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x179895  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal5
0x17989a  ldarg.0
0x17989b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__c::<>g__initLocal5
0x1798a0  ldstr    aRemovefromspot// "RemoveFromSpotlight"
0x1798a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x1798aa  ldarg.0
  ... truncated ...
```
