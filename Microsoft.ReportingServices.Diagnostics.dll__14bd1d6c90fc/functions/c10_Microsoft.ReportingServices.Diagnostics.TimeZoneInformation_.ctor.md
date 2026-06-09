# Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::.ctor

- ea: `0xc10`
- end: `0xd2e`
- name: `Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::.ctor`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd40`

## callees

- `0xd80`
- `0x101a0`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldarg.0
0xc11  call     instance void [mscorlib]System.Object::.ctor()
0xc16  ldloca.s 0
0xc18  initobj  Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp
0xc1e  ldloca.s 0
0xc20  call     void Microsoft.ReportingServices.Diagnostics.TimeZoneUtil::GetTimeZoneInformation(valuetype Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp& st)
0xc25  ldarg.0
0xc26  ldloc.0
0xc27  ldfld    int32 Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp::bias
0xc2c  stfld    int32 Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::m_bias
0xc31  ldloc.0
0xc32  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp::standardDate
0xc37  stloc.1
0xc38  ldarg.0
0xc39  newobj   instance void SYSTEMTIME::.ctor()
0xc3e  dup
0xc3f  ldloc.1
0xc40  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::year
0xc45  stfld    int16 SYSTEMTIME::year
0xc4a  dup
0xc4b  ldloc.1
0xc4c  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::month
0xc51  stfld    int16 SYSTEMTIME::month
0xc56  dup
0xc57  ldloc.1
0xc58  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::dayOfWeek
0xc5d  stfld    int16 SYSTEMTIME::dayOfWeek
0xc62  dup
0xc63  ldloc.1
0xc64  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::day
0xc69  stfld    int16 SYSTEMTIME::day
0xc6e  dup
0xc6f  ldloc.1
0xc70  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::hour
0xc75  stfld    int16 SYSTEMTIME::hour
0xc7a  dup
0xc7b  ldloc.1
0xc7c  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::minute
0xc81  stfld    int16 SYSTEMTIME::minute
0xc86  dup
0xc87  ldloc.1
0xc88  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::second
0xc8d  stfld    int16 SYSTEMTIME::second
0xc92  dup
0xc93  ldloc.1
0xc94  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::milliseconds
0xc99  stfld    int16 SYSTEMTIME::milliseconds
0xc9e  stfld    class SYSTEMTIME Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::m_standardDate
0xca3  ldloc.0
0xca4  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp::daylightDate
0xca9  stloc.1
0xcaa  ldarg.0
0xcab  newobj   instance void SYSTEMTIME::.ctor()
0xcb0  dup
0xcb1  ldloc.1
0xcb2  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::year
0xcb7  stfld    int16 SYSTEMTIME::year
0xcbc  dup
0xcbd  ldloc.1
0xcbe  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::month
0xcc3  stfld    int16 SYSTEMTIME::month
0xcc8  dup
0xcc9  ldloc.1
0xcca  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::dayOfWeek
0xccf  stfld    int16 SYSTEMTIME::dayOfWeek
0xcd4  dup
0xcd5  ldloc.1
0xcd6  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::day
0xcdb  stfld    int16 SYSTEMTIME::day
0xce0  dup
0xce1  ldloc.1
0xce2  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::hour
0xce7  stfld    int16 SYSTEMTIME::hour
0xcec  dup
0xced  ldloc.1
0xcee  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::minute
0xcf3  stfld    int16 SYSTEMTIME::minute
0xcf8  dup
0xcf9  ldloc.1
0xcfa  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::second
0xcff  stfld    int16 SYSTEMTIME::second
0xd04  dup
0xd05  ldloc.1
0xd06  ldfld    int16 Microsoft.ReportingServices.Diagnostics.SYSTEMTIME_Introp::milliseconds
0xd0b  stfld    int16 SYSTEMTIME::milliseconds
0xd10  stfld    class SYSTEMTIME Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::m_daylightDate
0xd15  ldarg.0
0xd16  ldloc.0
0xd17  ldfld    int32 Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp::standardBias
0xd1c  stfld    int32 Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::m_standardBias
0xd21  ldarg.0
0xd22  ldloc.0
0xd23  ldfld    int32 Microsoft.ReportingServices.Diagnostics.TIME_ZONE_INFORMATION_Introp::daylightBias
0xd28  stfld    int32 Microsoft.ReportingServices.Diagnostics.TimeZoneInformation::m_daylightBias
0xd2d  ret
```
