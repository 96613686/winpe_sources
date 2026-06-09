# Microsoft.ReportingServices.Library.JsonContentCacheManager::CreateOrUpdateCacheInternal

- ea: `0x1fdf0`
- end: `0x1feff`
- name: `Microsoft.ReportingServices.Library.JsonContentCacheManager::CreateOrUpdateCacheInternal`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1fde0`
- `0x1ff00`

## callees

- `0xcd70`
- `0xe160`
- `0x1fb60`
- `0x1fbd0`
- `0x1fdf0`

## string_xrefs

- `0x1fdf6`: `Starting JSON Cache creation for Data Set ID: {0} and Path: {1}.`
- `0x1fe9a`: `JSON Cache creation completed for Data Set ID: {0} and Path: {1}.`
- `0x1fecb`: `Error while creating JSON Cache for Data Set ID: {0} and Path: {1}. Exception: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1fdf0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningJobsTrace()
0x1fdf5  ldc.i4.4
0x1fdf6  ldstr    aStartingJsonCa// "Starting JSON Cache creation for Data S"...
0x1fdfb  ldc.i4.2
0x1fdfc  newarr   [mscorlib]System.Object
0x1fe01  dup
0x1fe02  ldc.i4.0
0x1fe03  ldarg.0
0x1fe04  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetId
0x1fe09  box      [mscorlib]System.Guid
0x1fe0e  stelem.ref
0x1fe0f  dup
0x1fe10  ldc.i4.1
0x1fe11  ldarg.0
0x1fe12  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetPath
0x1fe17  stelem.ref
0x1fe18  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1fe1d  ldarg.0
0x1fe1e  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetPath
0x1fe23  ldarg.0
0x1fe24  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParameters
0x1fe29  call     unsigned int8[] Microsoft.ReportingServices.Library.JsonContentCacheManager::LoadJsonSharedDataSetBytes(string dataSetPath, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection queryParameters)
0x1fe2e  stloc.0
0x1fe2f  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1fe34  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetPreamble()
0x1fe39  stloc.1
0x1fe3a  ldloc.0
0x1fe3b  ldlen
0x1fe3c  conv.i4
0x1fe3d  ldloc.1
0x1fe3e  ldlen
0x1fe3f  conv.i4
0x1fe40  blt.s    loc_1FE53
0x1fe42  ldloc.0
0x1fe43  ldloc.1
0x1fe44  ldlen
0x1fe45  conv.i4
0x1fe46  call     T0x2B000019
0x1fe4b  ldloc.1
0x1fe4c  call     T0x2B00001A
0x1fe51  brtrue.s loc_1FE56
0x1fe53  ldc.i4.0
0x1fe54  br.s     loc_1FE59
0x1fe56  ldloc.1
0x1fe57  ldlen
0x1fe58  conv.i4
0x1fe59  stloc.2
0x1fe5a  ldarg.0
0x1fe5b  ldloc.0
0x1fe5c  ldloc.2
0x1fe5d  call     instance class [mscorlib]System.IO.MemoryStream Microsoft.ReportingServices.Library.JsonContentCacheManager::CompressBytes(unsigned int8[] bytes, int32 offset)
0x1fe62  stloc.3
0x1fe63  ldarg.0
0x1fe64  ldfld    class Microsoft.ReportingServices.Library.IRSService Microsoft.ReportingServices.Library.JsonContentCacheManager::m_service
0x1fe69  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.IRSService::get_Storage()
0x1fe6e  ldarg.0
0x1fe6f  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetId
0x1fe74  ldarg.0
0x1fe75  ldfld    int32 Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParametersHash
0x1fe7a  ldarg.0
0x1fe7b  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_queryParametersString
0x1fe80  ldc.i4.0
0x1fe81  ldc.i4.1
0x1fe82  ldloc.3
0x1fe83  callvirt instance void Microsoft.ReportingServices.Library.IDBInterface::CreateOrUpdateContentCache(valuetype [mscorlib]System.Guid catalogItemID, int32 paramsHash, string effectiveParams, valuetype ContentCacheTypes contentType, int32 version, class [mscorlib]System.IO.Stream content)
0x1fe88  leave.s  loc_1FE94
0x1fe8a  ldloc.3
0x1fe8b  brfalse.s loc_1FE93
0x1fe8d  ldloc.3
0x1fe8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fe93  endfinally
0x1fe94  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningJobsTrace()
0x1fe99  ldc.i4.4
0x1fe9a  ldstr    aJsonCacheCreat// "JSON Cache creation completed for Data "...
0x1fe9f  ldc.i4.2
0x1fea0  newarr   [mscorlib]System.Object
0x1fea5  dup
0x1fea6  ldc.i4.0
0x1fea7  ldarg.0
0x1fea8  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetId
0x1fead  box      [mscorlib]System.Guid
0x1feb2  stelem.ref
0x1feb3  dup
0x1feb4  ldc.i4.1
0x1feb5  ldarg.0
0x1feb6  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetPath
0x1febb  stelem.ref
0x1febc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1fec1  leave.s  loc_1FEFE
0x1fec3  stloc.s  4
0x1fec5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningJobsTrace()
0x1feca  ldc.i4.1
0x1fecb  ldstr    aErrorWhileCrea// "Error while creating JSON Cache for Dat"...
0x1fed0  ldc.i4.3
0x1fed1  newarr   [mscorlib]System.Object
0x1fed6  dup
0x1fed7  ldc.i4.0
0x1fed8  ldarg.0
0x1fed9  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetId
0x1fede  box      [mscorlib]System.Guid
0x1fee3  stelem.ref
0x1fee4  dup
0x1fee5  ldc.i4.1
0x1fee6  ldarg.0
0x1fee7  ldfld    string Microsoft.ReportingServices.Library.JsonContentCacheManager::m_dataSetPath
0x1feec  stelem.ref
0x1feed  dup
0x1feee  ldc.i4.2
0x1feef  ldloc.s  4
0x1fef1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1fef6  stelem.ref
0x1fef7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1fefc  leave.s  loc_1FEFE
0x1fefe  ret
```
