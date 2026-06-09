# Microsoft.ReportingServices.Diagnostics.RSConfiguration::Validate

- ea: `0x4bd0`
- end: `0x5e11`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::Validate`
- size: `4673`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x7280`
- `0x7340`

## callees

- `0x1530`
- `0x1570`
- `0x1590`
- `0x15a0`
- `0x17c0`
- `0x17d0`
- `0x17e0`
- `0x1980`
- `0x1ac0`
- `0x1c40`
- `0x2c20`
- `0x4bd0`
- `0x5e20`
- `0x93e0`
- `0x9450`

## string_xrefs

- `0x4f45`: `ProcessTimeout is {0} and is less than recommended minimum of {1}. Increasing ProcessTimeout to {1}.`
- `0x4fa3`: `ProcessTimeoutGcExtension`
- `0x514d`: `AlertingDataCleanupMinutes`
- `0x53b3`: `DisplayErrorLink`
- `0x53e8`: `WebServiceUseFileShareStorage`
- `0x541a`: `IsSchedulingService`
- `0x544a`: `IsAlertingService`
- `0x547a`: `WindowsServiceUseFileShareStorage`
- `0x54ac`: `IsNotificationService`
- `0x5509`: `IsEventService`
- `0x571c`: `MaxQueueThreads`
- `0x5724`: `thread(s)`
- `0x5778`: `IsWebServiceEnabled`
- `0x57a8`: `IsReportBuilderAnonymousAccessEnabled`
- `0x5b08`: `AuthTokenCacheMaxSize`
- `0x5b4f`: `AuthTokenCacheMaintenanceInterval`
- `0x5b96`: `AuthTokenCacheLogonTimeout`
- `0x5bdd`: `AuthTokenCacheEntryTimeout`
- `0x5d4a`: `UsernameSIDRefreshMinutes`
- `0x5d83`: `UpdatePoliciesSeconds`
- `0x5dbc`: `UpdatePoliciesChunkSize`

## pseudocode

```c

```

## disassembly

```asm
0x4bd0  ldarg.1
0x4bd1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x4bd6  stloc.s  4
0x4bd8  br       loc_5DED
0x4bdd  ldloca.s 4
0x4bdf  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x4be4  stloc.s  5
0x4be6  ldloca.s 5
0x4be8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x4bed  stloc.s  6
0x4bef  ldloc.s  6
0x4bf1  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x4bf6  stloc.s  7
0x4bf8  ldloca.s 5
0x4bfa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x4bff  stloc.s  8
0x4c01  ldloc.s  8
0x4c03  ldc.i4.3
0x4c04  sub
0x4c05  switch   loc_58FF, loc_59A8, loc_59E6, loc_59E6, loc_5A00, loc_5A30, loc_5A77, loc_5ABE, loc_5849, loc_5872, loc_5DED, loc_5B02, loc_5B49, loc_5B90, loc_5BD7, loc_5DED, loc_5DED, loc_5C65, loc_57D2, loc_57D2, loc_521C, loc_5DED, loc_5DED, loc_5716, loc_5DED, loc_4E49, loc_4E49, loc_4E49, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5DED, loc_5692, loc_56D4, loc_5638, loc_5638, loc_55B8, loc_55F8, loc_50B9, loc_5258, loc_5100, loc_5147, loc_518E, loc_51D5, loc_4FE4, loc_502B, loc_5072, loc_4E63, loc_5533, loc_5DED, loc_5DED \
0x4dd6  br       loc_5DED
0x4ddb  ldloc.s  7
0x4ddd  stloc.s  9
0x4ddf  ldtoken  CatalogConnectionType
0x4de4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4de9  ldloc.s  9
0x4deb  ldc.i4.1
0x4dec  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x4df1  unbox.any CatalogConnectionType
0x4df6  stloc.s  0xD
0x4df8  ldloca.s 0xD
0x4dfa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dff  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4e04  stloc.s  9
0x4e06  leave.s  loc_4E0B
0x4e08  pop
0x4e09  leave.s  loc_4E0B
0x4e0b  ldarg.0
0x4e0c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4e11  ldstr    aConnectiontype// "ConnectionType"
0x4e16  ldloc.s  9
0x4e18  ldc.i4.0
0x4e19  ldstr    asc_126C2// ""
0x4e1e  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x4e23  stloc.0
0x4e24  ldloc.0
0x4e25  ldc.i4.0
0x4e26  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x4e2b  ldloc.0
0x4e2c  ldc.i4.1
0x4e2d  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x4e32  ldloc.s  6
0x4e34  ldloc.0
0x4e35  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4e3a  box      CatalogConnectionType
0x4e3f  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4e44  br       loc_5DED
0x4e49  ldloc.s  7
0x4e4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e50  brtrue   loc_5DED
0x4e55  ldloc.s  6
0x4e57  ldloc.s  7
0x4e59  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4e5e  br       loc_5DED
0x4e63  ldarg.0
0x4e64  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4e69  ldstr    aMaxschedulewai// "MaxScheduleWait"
0x4e6e  ldloc.s  7
0x4e70  ldarg.0
0x4e71  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxScheduleWait
0x4e76  ldstr    aSecondS// "second(s)"
0x4e7b  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x4e80  stloc.0
0x4e81  ldloc.0
0x4e82  ldc.i4.1
0x4e83  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x4e88  ldloc.0
0x4e89  ldc.i4.s 0x3C
0x4e8b  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x4e90  ldloc.s  6
0x4e92  ldloc.0
0x4e93  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4e98  box      [mscorlib]System.Int32
0x4e9d  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4ea2  br       loc_5DED
0x4ea7  ldarg.0
0x4ea8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4ead  ldstr    aDatabasequeryt// "DatabaseQueryTimeout"
0x4eb2  ldloc.s  7
0x4eb4  ldarg.0
0x4eb5  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBQueryTimeout
0x4eba  ldstr    aSecondS// "second(s)"
0x4ebf  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x4ec4  stloc.0
0x4ec5  ldloc.0
0x4ec6  ldc.i4.0
0x4ec7  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x4ecc  ldloc.0
0x4ecd  ldc.i4   0x7FFFFFFF
0x4ed2  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x4ed7  ldloc.s  6
0x4ed9  ldloc.0
0x4eda  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4edf  box      [mscorlib]System.Int32
0x4ee4  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4ee9  br       loc_5DED
0x4eee  ldarg.0
0x4eef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4ef4  ldstr    aProcesstimeout// "ProcessTimeout"
0x4ef9  ldloc.s  7
0x4efb  ldarg.0
0x4efc  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeout
0x4f01  ldstr    aSecondS// "second(s)"
0x4f06  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x4f0b  stloc.0
0x4f0c  ldloc.0
0x4f0d  ldc.i4.0
0x4f0e  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x4f13  ldloc.0
0x4f14  ldc.i4   0x7FFFFFFF
0x4f19  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x4f1e  ldloc.0
0x4f1f  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4f24  brfalse.s loc_4F86
0x4f26  ldloc.0
0x4f27  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4f2c  ldc.i4   0x96
0x4f31  bge.s    loc_4F86
0x4f33  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4f38  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x4f3d  brfalse.s loc_4F70
0x4f3f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4f44  ldc.i4.2
0x4f45  ldstr    aProcesstimeout_0// "ProcessTimeout is {0} and is less than "...
0x4f4a  ldc.i4.2
0x4f4b  newarr   [mscorlib]System.Object
0x4f50  dup
0x4f51  ldc.i4.0
0x4f52  ldloc.0
0x4f53  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4f58  box      [mscorlib]System.Int32
0x4f5d  stelem.ref
0x4f5e  dup
0x4f5f  ldc.i4.1
0x4f60  ldc.i4   0x96
0x4f65  box      [mscorlib]System.Int32
0x4f6a  stelem.ref
0x4f6b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4f70  ldloc.s  6
0x4f72  ldc.i4   0x96
0x4f77  box      [mscorlib]System.Int32
0x4f7c  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4f81  br       loc_5DED
0x4f86  ldloc.s  6
0x4f88  ldloc.0
0x4f89  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4f8e  box      [mscorlib]System.Int32
0x4f93  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4f98  br       loc_5DED
0x4f9d  ldarg.0
0x4f9e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4fa3  ldstr    aProcesstimeout_1// "ProcessTimeoutGcExtension"
0x4fa8  ldloc.s  7
0x4faa  ldarg.0
0x4fab  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeoutGcExtension
0x4fb0  ldstr    aSecondS// "second(s)"
0x4fb5  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x4fba  stloc.0
0x4fbb  ldloc.0
0x4fbc  ldc.i4.0
0x4fbd  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x4fc2  ldloc.0
0x4fc3  ldc.i4   0x7FFFFFFF
0x4fc8  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x4fcd  ldloc.s  6
0x4fcf  ldloc.0
0x4fd0  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x4fd5  box      [mscorlib]System.Int32
0x4fda  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x4fdf  br       loc_5DED
0x4fe4  ldarg.0
0x4fe5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4fea  ldstr    aRunningrequest// "RunningRequestsScavengerCycle"
0x4fef  ldloc.s  7
0x4ff1  ldarg.0
0x4ff2  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsScavengerCycleParam
0x4ff7  ldstr    aSecondS// "second(s)"
0x4ffc  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x5001  stloc.0
0x5002  ldloc.0
0x5003  ldc.i4.1
0x5004  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x5009  ldloc.0
0x500a  ldc.i4   0x7FFFFFFF
0x500f  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x5014  ldloc.s  6
0x5016  ldloc.0
0x5017  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x501c  box      [mscorlib]System.Int32
0x5021  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x5026  br       loc_5DED
0x502b  ldarg.0
0x502c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x5031  ldstr    aRunningrequest_0// "RunningRequestsDbCycle"
0x5036  ldloc.s  7
0x5038  ldarg.0
0x5039  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsDBCycleParam
0x503e  ldstr    aSecondS// "second(s)"
0x5043  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x5048  stloc.0
0x5049  ldloc.0
0x504a  ldc.i4.1
0x504b  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x5050  ldloc.0
0x5051  ldc.i4   0x7FFFFFFF
0x5056  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x505b  ldloc.s  6
0x505d  ldloc.0
0x505e  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x5063  box      [mscorlib]System.Int32
0x5068  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x506d  br       loc_5DED
0x5072  ldarg.0
0x5073  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x5078  ldstr    aRunningrequest_1// "RunningRequestsAge"
0x507d  ldloc.s  7
0x507f  ldarg.0
0x5080  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsAgeParam
0x5085  ldstr    aSecondS// "second(s)"
0x508a  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x508f  stloc.0
0x5090  ldloc.0
0x5091  ldc.i4.1
0x5092  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x5097  ldloc.0
0x5098  ldc.i4   0x7FFFFFFF
0x509d  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x50a2  ldloc.s  6
0x50a4  ldloc.0
0x50a5  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x50aa  box      [mscorlib]System.Int32
0x50af  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x50b4  br       loc_5DED
0x50b9  ldarg.0
0x50ba  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x50bf  ldstr    aCleanupcyclemi// "CleanupCycleMinutes"
0x50c4  ldloc.s  7
0x50c6  ldarg.0
0x50c7  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_CleanupCycleMinutesParam
0x50cc  ldstr    aMinuteS// "minute(s)"
0x50d1  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x50d6  stloc.0
0x50d7  ldloc.0
0x50d8  ldc.i4.1
0x50d9  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x50de  ldloc.0
0x50df  ldc.i4   0x7FFFFFFF
0x50e4  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x50e9  ldloc.s  6
0x50eb  ldloc.0
0x50ec  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x50f1  box      [mscorlib]System.Int32
0x50f6  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x50fb  br       loc_5DED
0x5100  ldarg.0
0x5101  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AlertingRuntimeTracer()
0x5106  ldstr    aAlertingcleanu// "AlertingCleanupCycleMinutes"
0x510b  ldloc.s  7
0x510d  ldarg.0
0x510e  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingCleanupCycleMinutesParam
0x5113  ldstr    aMinuteS// "minute(s)"
0x5118  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x511d  stloc.0
0x511e  ldloc.0
0x511f  ldc.i4.1
0x5120  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x5125  ldloc.0
0x5126  ldc.i4   0x7FFFFFFF
0x512b  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x5130  ldloc.s  6
0x5132  ldloc.0
0x5133  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x5138  box      [mscorlib]System.Int32
0x513d  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x5142  br       loc_5DED
0x5147  ldarg.0
0x5148  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AlertingRuntimeTracer()
0x514d  ldstr    aAlertingdatacl// "AlertingDataCleanupMinutes"
0x5152  ldloc.s  7
0x5154  ldarg.0
0x5155  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingDataCleanupMinutesParam
0x515a  ldstr    aMinuteS// "minute(s)"
0x515f  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x5164  stloc.0
0x5165  ldloc.0
0x5166  ldc.i4.1
0x5167  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x516c  ldloc.0
0x516d  ldc.i4   0x7FFFFFFF
0x5172  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
  ... truncated ...
```
