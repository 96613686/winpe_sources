# Microsoft.ReportingServices.Library.JsonContentCacheManager::.ctor

- ea: `0x1fd00`
- end: `0x1fd92`
- name: `Microsoft.ReportingServices.Library.JsonContentCacheManager::.ctor`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1fb40`

## callees

- `0x1fd00`

## string_xrefs

- `0x1fd26`: `data set path`
- `0x1fd43`: `rs service`

## pseudocode

```c

```

## disassembly

```asm
0x1fd00  ldarg.0
0x1fd01  call     instance void [mscorlib]System.Object::.ctor()
0x1fd06  ldarg.1
0x1fd07  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1fd0c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1fd11  brfalse.s loc_1FD1E
0x1fd13  ldstr    aDataSetId// "data set id"
0x1fd18  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1fd1d  throw
0x1fd1e  ldarg.2
0x1fd1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fd24  brfalse.s loc_1FD31
0x1fd26  ldstr    aDataSetPath// "data set path"
0x1fd2b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fd30  throw
0x1fd31  ldarg.3
0x1fd32  brtrue.s loc_1FD3F
0x1fd34  ldstr    aParameters_1// "parameters"
0x1fd39  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fd3e  throw
0x1fd3f  ldarg.s  5
0x1fd41  brtrue.s loc_1FD4E
0x1fd43  ldstr    aRsService// "rs service"
0x1fd48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fd4d  throw
0x1fd4e  ldarg.0
0x1fd4f  ldarg.1
0x1fd50  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetId
0x1fd55  ldarg.0
0x1fd56  ldarg.2
0x1fd57  stfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetPath
0x1fd5c  ldarg.0
0x1fd5d  ldarg.3
0x1fd5e  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParameters
0x1fd63  ldarg.0
0x1fd64  ldarg.s  4
0x1fd66  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters Microsoft.ReportingServices.Library.JsonContentCacheManager::m_requestParameters
0x1fd6b  ldarg.0
0x1fd6c  ldarg.s  5
0x1fd6e  stfld    class Microsoft.ReportingServices.Library.IRSService Microsoft.ReportingServices.Library.JsonContentCacheManager::m_service
0x1fd73  ldarg.0
0x1fd74  ldarg.3
0x1fd75  ldc.i4.1
0x1fd76  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToXml(bool)
0x1fd7b  stfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParametersString
0x1fd80  ldarg.0
0x1fd81  ldarg.0
0x1fd82  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParametersString
0x1fd87  call     T0x2B000002
0x1fd8c  stfld    int32 Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParametersHash
0x1fd91  ret
```
