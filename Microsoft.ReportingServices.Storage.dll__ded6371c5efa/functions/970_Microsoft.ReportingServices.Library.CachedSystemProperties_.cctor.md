# Microsoft.ReportingServices.Library.CachedSystemProperties::.cctor

- ea: `0x970`
- end: `0xa40`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::.cctor`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x960`

## pseudocode

```c

```

## disassembly

```asm
0x970  newobj   instance void Microsoft.ReportingServices.Library.CachedSystemProperties::.ctor()
0x975  stsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x97a  ldc.i4   0x258
0x97f  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultSessionTimeoutSeconds
0x984  ldnull
0x985  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionTimeoutSecondsParam
0x98a  ldc.i4   0x708
0x98f  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_defaultRdlxReportTimeoutSeconds
0x994  ldnull
0x995  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_rdlxReportTimeoutSecondsParam
0x99a  ldc.i4.0
0x99b  stsfld   bool Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultEnableClientPrinting
0x9a0  ldnull
0x9a1  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableClientPrintingParam
0x9a6  ldnull
0x9a7  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionAccessTimeoutParam
0x9ac  ldnull
0x9ad  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_editsessionTimeoutParam
0x9b2  ldnull
0x9b3  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_editSessionCacheLimitParam
0x9b8  ldnull
0x9b9  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableRemoteErrorsParam
0x9be  ldnull
0x9bf  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.SnapshotCompressionFlags> Microsoft.ReportingServices.Library.CachedSystemProperties::m_SnapshotCompressionSettingParam
0x9c4  ldnull
0x9c5  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableIntegratedSecurityParam
0x9ca  ldnull
0x9cb  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ExternalImagesTimeoutParam
0x9d0  ldc.i4   0x258
0x9d5  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_externalImagesTimeoutDefault
0x9da  ldc.i4   0x5DC
0x9df  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_defaultStoredParametersThreshold
0x9e4  ldnull
0x9e5  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersThreshold
0x9ea  ldc.i4   0xB4
0x9ef  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_defaultStoredParametersLifetime
0x9f4  ldnull
0x9f5  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_storedParametersLifetime
0x9fa  ldc.i4.1
0x9fb  stsfld   bool Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultSessionCookies
0xa00  ldnull
0xa01  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SessionCookiesParam
0xa06  ldc.i4.s 0x40
0xa08  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultResponseBufferSizeKb
0xa0d  ldnull
0xa0e  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ResponseBufferSizeKbParam
0xa13  ldnull
0xa14  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_MaxFileSizeMb
0xa19  ldc.i4   0xFC80
0xa1e  stsfld   int32 Microsoft.ReportingServices.Library.CachedSystemProperties::m_DefaultSqlStreamingBufferSize
0xa23  ldnull
0xa24  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_SqlStreamingBufferSizeParam
0xa29  ldnull
0xa2a  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IntParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_ChunkSegmentSizeParam
0xa2f  ldnull
0xa30  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_enableTestConnectionDetailedErrorsParam
0xa35  newobj   instance void [mscorlib]System.Object::.ctor()
0xa3a  stsfld   object Microsoft.ReportingServices.Library.CachedSystemProperties::m_lockObj
0xa3f  ret
```
