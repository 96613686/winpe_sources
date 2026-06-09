# Microsoft.ReportingServices.Library.SystemProperties::.ctor_0

- ea: `0x141f0`
- end: `0x14354`
- name: `Microsoft.ReportingServices.Library.SystemProperties::.ctor_0`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x21a30`

## callees

- `0x141f0`
- `0x14390`
- `0x143b0`
- `0x143c0`
- `0x143d0`
- `0x143e0`
- `0x143f0`
- `0x14400`
- `0x14410`
- `0x14420`
- `0x14430`
- `0x14440`
- `0x14460`
- `0x14470`
- `0x14480`
- `0x14490`
- `0x14910`
- `0x14b20`
- `0x14b80`
- `0x14bb0`
- `0x14c60`
- `0x14c70`
- `0x14c90`

## string_xrefs

- `0x142b3`: `SessionAccessTimeout`
- `0x142fb`: `EditSessionCacheLimit`

## pseudocode

```c

```

## disassembly

```asm
0x141f0  ldarg.0
0x141f1  ldarg.1
0x141f2  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::.ctor(class Microsoft.ReportingServices.Library.Soap.Property[] properties)
0x141f7  ldc.i4.0
0x141f8  stloc.1
0x141f9  br.s     loc_14224
0x141fb  ldarg.0
0x141fc  ldloc.1
0x141fd  call     instance string Microsoft.ReportingServices.Library.PropertyCollection::GetName(int32 i)
0x14202  stloc.2
0x14203  ldarg.0
0x14204  ldloc.1
0x14205  call     instance string Microsoft.ReportingServices.Library.PropertyCollection::GetValue(int32 i)
0x1420a  brtrue.s loc_14220
0x1420c  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNonNullableProperties
0x14211  ldloc.2
0x14212  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x14217  brfalse.s loc_14220
0x14219  ldloc.2
0x1421a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x1421f  throw
0x14220  ldloc.1
0x14221  ldc.i4.1
0x14222  add
0x14223  stloc.1
0x14224  ldloc.1
0x14225  ldarg.0
0x14226  call     instance int32 Microsoft.ReportingServices.Library.PropertyCollection::get_Count()
0x1422b  blt.s    loc_141FB
0x1422d  ldarg.0
0x1422e  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_SiteName()
0x14233  stloc.0
0x14234  ldloc.0
0x14235  brfalse.s loc_1424C
0x14237  ldloc.0
0x14238  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1423d  ldc.i4.s 0x64
0x1423f  ble.s    loc_1424C
0x14241  ldstr    aSitename// "SiteName"
0x14246  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x1424b  throw
0x1424c  ldarg.0
0x1424d  ldstr    aSystemreportti// "SystemReportTimeout"
0x14252  ldc.i4.0
0x14253  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateReportTimeoutIfPresent(string timeoutPropertyName, valuetype Microsoft.ReportingServices.Library.ItemType itemType)
0x14258  ldarg.0
0x14259  ldstr    aEnableexecutio// "EnableExecutionLogging"
0x1425e  ldarg.0
0x1425f  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_EnableExecutionLogging()
0x14264  ldc.i4.0
0x14265  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateBooleanProperty(string name, string val, bool throwIfNull)
0x1426a  ldarg.0
0x1426b  ldstr    aExecutionlogda// "ExecutionLogDaysKept"
0x14270  ldarg.0
0x14271  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_ExecutionLogDaysKept()
0x14276  ldc.i4.0
0x14277  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x1427c  ldarg.0
0x1427d  ldstr    aUsesessioncook// "UseSessionCookies"
0x14282  ldarg.0
0x14283  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_UseSessionCookies()
0x14288  ldc.i4.0
0x14289  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateBooleanProperty(string name, string val, bool throwIfNull)
0x1428e  ldarg.0
0x1428f  ldstr    aSessiontimeout// "SessionTimeout"
0x14294  ldarg.0
0x14295  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_SessionTimeout()
0x1429a  ldc.i4.0
0x1429b  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142a0  ldarg.0
0x142a1  ldstr    aRdlxreporttime// "RDLXReportTimeout"
0x142a6  ldarg.0
0x142a7  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_RdlxReportTimeout()
0x142ac  ldc.i4.0
0x142ad  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142b2  ldarg.0
0x142b3  ldstr    aSessionaccesst// "SessionAccessTimeout"
0x142b8  ldarg.0
0x142b9  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_SessionAccessTimeout()
0x142be  ldc.i4.0
0x142bf  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142c4  ldarg.0
0x142c5  ldstr    aResponsebuffer// "ResponseBufferSizeKb"
0x142ca  ldarg.0
0x142cb  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_ResponseBufferSizeKb()
0x142d0  ldc.i4.0
0x142d1  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142d6  ldarg.0
0x142d7  ldstr    aSqlstreamingbu// "SqlStreamingBufferSize"
0x142dc  ldarg.0
0x142dd  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_SqlStreamingBufferSize()
0x142e2  ldc.i4.0
0x142e3  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142e8  ldarg.0
0x142e9  ldstr    aEditsessiontim_0// "EditSessionTimeout"
0x142ee  ldarg.0
0x142ef  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_EditSessionTimeout()
0x142f4  ldc.i4.0
0x142f5  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x142fa  ldarg.0
0x142fb  ldstr    aEditsessioncac// "EditSessionCacheLimit"
0x14300  ldarg.0
0x14301  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_EditSessionCacheLimit()
0x14306  ldc.i4.0
0x14307  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x1430c  ldarg.0
0x1430d  ldstr    aMaxfilesizemb// "MaxFileSizeMb"
0x14312  ldarg.0
0x14313  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_MaxFileSizeMb()
0x14318  ldc.i4.0
0x14319  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateIntegerProperty(string name, string val, bool throwIfNull)
0x1431e  ldarg.0
0x1431f  ldstr    aEnableclientpr// "EnableClientPrinting"
0x14324  ldarg.0
0x14325  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_EnableClientPrinting()
0x1432a  ldc.i4.0
0x1432b  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateBooleanProperty(string name, string val, bool throwIfNull)
0x14330  ldarg.0
0x14331  ldstr    aEnabletestconn// "EnableTestConnectionDetailedErrors"
0x14336  ldarg.0
0x14337  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_EnableTestConnectionDetailedErrors()
0x1433c  ldc.i4.0
0x1433d  call     instance void Microsoft.ReportingServices.Library.PropertyCollection::ValidateBooleanProperty(string name, string val, bool throwIfNull)
0x14342  ldarg.0
0x14343  ldstr    aExecutionlogle// "ExecutionLogLevel"
0x14348  ldarg.0
0x14349  call     instance string Microsoft.ReportingServices.Library.SystemProperties::get_ExecutionLogLevel()
0x1434e  call     T0x2B00000F
0x14353  ret
```
