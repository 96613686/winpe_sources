# VAlertManager::MatchFilterAndSecurityTrim(CSubscriptionNotificationData *,CAlertEventRecord *,uint,CAlertFilter &)

- ea: `0x18001abc0`
- end: `0x18001b7b6`
- name: `?MatchFilterAndSecurityTrim@VAlertManager@@AEAAXPEAVCSubscriptionNotificationData@@PEAVCAlertEventRecord@@IAEAVCAlertFilter@@@Z`
- size: `3062`
- prototype: `void __fastcall(VAlertManager *__hidden this, struct CSubscriptionNotificationData *, struct CAlertEventRecord *, unsigned int, struct CAlertFilter *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b7c0`

## callees

- `0x1800109f0`
- `0x180010da0`
- `0x180010e10`
- `0x180011e40`
- `0x180015ef0`
- `0x180016730`
- `0x180017be0`
- `0x180019140`
- `0x180019b50`
- `0x18001a940`
- `0x18001abc0`
- `0x1801c1770`
- `0x1801c2d20`
- `0x1801c2da0`

## import_xrefs

- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18001b077`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18001b6ea`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18001b077`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18001b6ea`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x18001ac74`
- `onetutil!??0Vwstring@@QEAA@PEB_W@Z` at `0x18001ac74`
- `onetutil!?Alloc@VwstackBuffer@@IEAAXI@Z` at `0x18001ade9`
- `onetutil!?Alloc@VwstackBuffer@@IEAAXI@Z` at `0x18001ae05`
- `onetutil!?Alloc@VwstackBuffer@@IEAAXI@Z` at `0x18001ade9`
- `onetutil!?Alloc@VwstackBuffer@@IEAAXI@Z` at `0x18001ae05`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18001ae1a`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18001ae86`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18001ae1a`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18001ae86`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001af84`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b01a`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b04c`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b08e`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001af84`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b01a`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b04c`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18001b08e`
- `onetutil!?appendGuid@VwstackBuffer512@@QEAAAEAV1@PEBU_GUID@@DDD@Z` at `0x18001ac94`
- `onetutil!?appendGuid@VwstackBuffer512@@QEAAAEAV1@PEBU_GUID@@DDD@Z` at `0x18001ac94`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001af71`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b248`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b28d`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b2d6`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b30d`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001af71`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b248`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b28d`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b2d6`
- `onetutil!?Vwtoi@@YAJPEB_W@Z` at `0x18001b30d`
- `onetutil!?reallocate@VwstackBuffer512@@AEAAXI@Z` at `0x18001b0fa`
- `onetutil!?reallocate@VwstackBuffer512@@AEAAXI@Z` at `0x18001b144`
- `onetutil!?reallocate@VwstackBuffer512@@AEAAXI@Z` at `0x18001b0fa`
- `onetutil!?reallocate@VwstackBuffer512@@AEAAXI@Z` at `0x18001b144`
- `onetutil!?appendIntBase10@VwstackBuffer512@@QEAAIJ@Z` at `0x18001b124`
- `onetutil!?appendIntBase10@VwstackBuffer512@@QEAAIJ@Z` at `0x18001b124`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x18001afc4`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x18001b06c`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x18001afc4`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x18001b06c`
- `onetutil!?pop@Vint32Vvector@@QEAAJXZ` at `0x18001afd6`
- `onetutil!?pop@Vint32Vvector@@QEAAJXZ` at `0x18001b0a8`
- `onetutil!?pop@Vint32Vvector@@QEAAJXZ` at `0x18001afd6`
- `onetutil!?pop@Vint32Vvector@@QEAAJXZ` at `0x18001b0a8`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18001b03e`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18001b03e`
- `onetutil!?appendGuid@VstackBuffer512@@QEAAAEAV1@PEBU_GUID@@D@Z` at `0x18001b41f`
- `onetutil!?appendGuid@VstackBuffer512@@QEAAAEAV1@PEBU_GUID@@D@Z` at `0x18001b458`
- `onetutil!?appendGuid@VstackBuffer512@@QEAAAEAV1@PEBU_GUID@@D@Z` at `0x18001b41f`
- `onetutil!?appendGuid@VstackBuffer512@@QEAAAEAV1@PEBU_GUID@@D@Z` at `0x18001b458`
- `onetutil!?appendIntBase10@VstackBuffer512@@QEAAIJ@Z` at `0x18001b42c`
- `onetutil!?appendIntBase10@VstackBuffer512@@QEAAIJ@Z` at `0x18001b466`
- `onetutil!?appendIntBase10@VstackBuffer512@@QEAAIJ@Z` at `0x18001b42c`
- `onetutil!?appendIntBase10@VstackBuffer512@@QEAAIJ@Z` at `0x18001b466`
- `onetutil!?appendUnicode@VstackBuffer512@@QEAAKPEB_WK@Z` at `0x18001b447`
- `onetutil!?appendUnicode@VstackBuffer512@@QEAAKPEB_WK@Z` at `0x18001b447`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18001b754`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18001b754`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x18001b563`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x18001b572`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x18001b563`
- `onetutil!??4Vwstring@@QEAAAEAV0@PEB_W@Z` at `0x18001b572`
- `onetutil!?GetData@Vwstring@@AEBAPEA_WXZ` at `0x18001b436`
- `onetutil!?GetData@Vwstring@@AEBAPEA_WXZ` at `0x18001b436`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b1aa`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b1d2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b629`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b704`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b733`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b76e`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b1aa`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b1d2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b629`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b704`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b733`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18001b76e`
- `onetutil!?Vwcsstr@@YAPEB_WPEB_W0@Z` at `0x18001af94`
- `onetutil!?Vwcsstr@@YAPEB_WPEB_W0@Z` at `0x18001b187`
- `onetutil!?Vwcsstr@@YAPEB_WPEB_W0@Z` at `0x18001af94`
- `onetutil!?Vwcsstr@@YAPEB_WPEB_W0@Z` at `0x18001b187`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001ae5c`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001ae6f`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001af20`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001ae5c`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001ae6f`
- `onetutil!?Vwcslen@@YAIPEB_W@Z` at `0x18001af20`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b1b7`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b1df`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b636`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b711`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b740`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b77b`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b1b7`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b1df`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b636`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b711`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b740`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18001b77b`
- `onetutil!?Vwcsnicmp@@YAJPEB_W0I@Z` at `0x18001aecf`
- `onetutil!?Vwcsnicmp@@YAJPEB_W0I@Z` at `0x18001aef3`
- `onetutil!?Vwcsnicmp@@YAJPEB_W0I@Z` at `0x18001aecf`
- `onetutil!?Vwcsnicmp@@YAJPEB_W0I@Z` at `0x18001aef3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b1c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b1e7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b641`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b719`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b748`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b783`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b1c2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b1e7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b641`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b719`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b748`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b783`
- `onetnative!ULSShouldTrace` at `0x18001ad0f`
- `onetnative!ULSShouldTrace` at `0x18001b37e`
- `onetnative!ULSShouldTrace` at `0x18001b5a8`
- `onetnative!ULSShouldTrace` at `0x18001b65e`
- `onetnative!ULSShouldTrace` at `0x18001ad0f`
- `onetnative!ULSShouldTrace` at `0x18001b37e`
- `onetnative!ULSShouldTrace` at `0x18001b5a8`
- `onetnative!ULSShouldTrace` at `0x18001b65e`
- `onetnative!ULSSendTraceTag` at `0x18001ad74`
- `onetnative!ULSSendTraceTag` at `0x18001b3ce`
- `onetnative!ULSSendTraceTag` at `0x18001b611`
- `onetnative!ULSSendTraceTag` at `0x18001b6cc`
- `onetnative!ULSSendTraceTag` at `0x18001ad74`
- `onetnative!ULSSendTraceTag` at `0x18001b3ce`
- `onetnative!ULSSendTraceTag` at `0x18001b611`
- `onetnative!ULSSendTraceTag` at `0x18001b6cc`

## string_xrefs

- `0x18001ac5d`: `Scheduled`

## pseudocode

```c

```
