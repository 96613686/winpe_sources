# Microsoft.ReportingServices.Diagnostics.RSConfiguration::.ctor

- ea: `0x36e0`
- end: `0x3751`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::.ctor`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7210`
- `0x7280`

## callees

- `0x3500`
- `0x3760`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  ldarg.0
0x36e1  ldc.i4.1
0x36e2  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enableReportDesignClientButton
0x36e7  ldarg.0
0x36e8  ldc.i4.s 0x3C
0x36ea  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_postbackTimeout
0x36ef  ldarg.0
0x36f0  ldc.i4.3
0x36f1  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.LogonMethod Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_logonMethod
0x36f6  ldarg.0
0x36f7  ldc.i4.1
0x36f8  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authPersistence
0x36fd  ldarg.0
0x36fe  ldc.i4.s 0x32
0x3700  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxUnauthenticatedRequests
0x3705  ldarg.0
0x3706  ldc.i4.s 0xA
0x3708  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_unauthenticatedRequestWindow
0x370d  ldarg.0
0x370e  ldc.i4.s 0x3C
0x3710  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_unauthenticatedRequestLockoutTime
0x3715  ldarg.0
0x3716  ldc.i4   0x258
0x371b  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheMaxSize
0x3720  ldarg.0
0x3721  ldc.i4   0x258
0x3726  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheMaintenanceInterval
0x372b  ldarg.0
0x372c  ldc.i4   0x21C
0x3731  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheEntryTimeout
0x3736  ldarg.0
0x3737  call     instance void Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::.ctor()
0x373c  ldarg.0
0x373d  ldarg.1
0x373e  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_configFileName
0x3743  ldarg.0
0x3744  ldarg.2
0x3745  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_configLocation
0x374a  ldarg.0
0x374b  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Init()
0x3750  ret
```
