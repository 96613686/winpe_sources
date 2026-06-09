# Windows::Compat::Appraiser::WicaEngine::RunComponents(void)

- ea: `0x18002d884`
- end: `0x18002e4e9`
- name: `?RunComponents@WicaEngine@Appraiser@Compat@Windows@@QEAAJXZ`
- size: `3173`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::WicaEngine *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b894`

## callees

- `0x1800011d0`
- `0x180001730`
- `0x1800018a0`
- `0x180008570`
- `0x1800092dc`
- `0x180013c7c`
- `0x1800151f4`
- `0x180026fd0`
- `0x180029258`
- `0x18002b1f8`
- `0x18002b728`
- `0x18002d154`
- `0x18002d4fc`
- `0x18002d808`
- `0x18002d884`
- `0x18002e7b0`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18011562c`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x18002db95`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002e354`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002db95`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002e354`
- `KERNEL32!CloseThreadpool` at `0x18002e3ac`
- `KERNEL32!CloseThreadpool` at `0x18002e3ac`
- `KERNEL32!QueryThreadpoolStackInformation` at `0x18002e1a3`
- `KERNEL32!QueryThreadpoolStackInformation` at `0x18002e1a3`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x18002dba7`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x18002dba7`
- `KERNEL32!CreateThreadpool` at `0x18002db26`
- `KERNEL32!CreateThreadpool` at `0x18002db26`
- `KERNEL32!GetTickCount64` at `0x18002daea`
- `KERNEL32!GetTickCount64` at `0x18002e25c`
- `KERNEL32!GetTickCount64` at `0x18002daea`
- `KERNEL32!GetTickCount64` at `0x18002e25c`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002e1bf`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x18002e1bf`
- `KERNEL32!GetCurrentProcess` at `0x18002e1a9`
- `KERNEL32!GetCurrentProcess` at `0x18002e1a9`
- `KERNEL32!GetSystemTime` at `0x18002d9a4`
- `KERNEL32!GetSystemTime` at `0x18002dcc0`
- `KERNEL32!GetSystemTime` at `0x18002de1f`
- `KERNEL32!GetSystemTime` at `0x18002df7e`
- `KERNEL32!GetSystemTime` at `0x18002e0dd`
- `KERNEL32!GetSystemTime` at `0x18002e2b7`
- `KERNEL32!GetSystemTime` at `0x18002e457`
- `KERNEL32!GetSystemTime` at `0x18002d9a4`
- `KERNEL32!GetSystemTime` at `0x18002dcc0`
- `KERNEL32!GetSystemTime` at `0x18002de1f`
- `KERNEL32!GetSystemTime` at `0x18002df7e`
- `KERNEL32!GetSystemTime` at `0x18002e0dd`
- `KERNEL32!GetSystemTime` at `0x18002e2b7`
- `KERNEL32!GetSystemTime` at `0x18002e457`

## string_xrefs

- `0x18002dad1`: `onecore\base\appcompat\appraiser\engine\engine.cpp`
- `0x18002daca`: `Windows::Compat::Appraiser::WicaEngine::RunComponents`
- `0x18002dd0a`: `Tier complete: Inventory.`
- `0x18002de69`: `Tier complete: Data Source.`
- `0x18002dfc8`: `Tier complete: Decision Maker.`
- `0x18002e127`: `Tier complete: Decision Aggregator.`
- `0x18002db3b`: `MaxThreadCount`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WicaEngine::RunComponents(Windows::Compat::Appraiser::WicaEngine *this)
{
  volatile signed __int64 *v2; // rcx
  void **v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rax
  ULONGLONG TickCount64; // rax
  ULONGLONG v7; // r14
  Windows::Compat::Inventory::InventoryWatchdog *v8; // rcx
  struct _TP_POOL *Threadpool; // rsi
  HKEY v10; // r9
  DWORD v11; // edx
  int Decisions; // ebx
  const char *v13; // r9
  char v14; // dl
  volatile signed __int64 *v15; // rcx
  void **v16; // rdx
  int v17; // ebx
  int v18; // r8d
  int v19; // r9d
  Windows::Compat::Inventory::InventoryWatchdog *v20; // rcx
  volatile signed __int64 *v21; // rcx
  void **v22; // rdx
  int v23; // ebx
  int v24; // r8d
  int v25; // r9d
  Windows::Compat::Inventory::InventoryWatchdog *v26; // rcx
  volatile signed __int64 *v27; // rcx
  void **v28; // rdx
  int v29; // ebx
  int v30; // r8d
  int v31; // r9d
  Windows::Compat::Inventory::InventoryWatchdog *v32; // rcx
  volatile signed __int64 *v33; // rcx
  void **v34; // rdx
  int v35; // ebx
  int v36; // r8d
  int v37; // r9d
  Windows::Compat::Inventory::InventoryWatchdog *v38; // rcx
  HANDLE CurrentProcess; // rax
  volatile signed __int64 *v40; // rcx
  void **v41; // rdx
  int v42; // edi
  int v43; // r8d
  int v44; // r9d
  volatile signed __int64 *v45; // rcx
  void **v46; // rdx
  int v47; // edi
  int v48; // r8d
  int v49; // r9d
  char *v51; // [rsp+20h] [rbp-E0h]
  char *v52; // [rsp+30h] [rbp-D0h]
  char *v53; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v54; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h] BYREF
  const size_t *v56; // [rsp+90h] [rbp-70h] BYREF
  char v57[8]; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T pvData; // [rsp+B0h] [rbp-50h] BYREF
  ULONGLONG v60; // [rsp+B8h] [rbp-48h] BYREF
  struct _SYSTEMTIME *StackCommit; // [rsp+C0h] [rbp-40h] BYREF
  const size_t *StackReserve; // [rsp+C8h] [rbp-38h] BYREF
  char v63[8]; // [rsp+D0h] [rbp-30h] BYREF
  SIZE_T PeakWorkingSetSize; // [rsp+D8h] [rbp-28h] BYREF
  struct _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+E0h] [rbp-20h] BYREF
  struct _SYSTEMTIME v66; // [rsp+130h] [rbp+30h] BYREF
  _TP_POOL_STACK_INFORMATION ptpsi; // [rsp+140h] [rbp+40h] BYREF
  struct _SYSTEMTIME v68; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v69[144]; // [rsp+160h] [rbp+60h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+1F0h] [rbp+F0h] BYREF
  char v71[32]; // [rsp+240h] [rbp+140h] BYREF
  struct _SYSTEMTIME *v72; // [rsp+260h] [rbp+160h]
  __int64 v73; // [rsp+268h] [rbp+168h]
  const size_t *v74; // [rsp+270h] [rbp+170h]
  __int64 v75; // [rsp+278h] [rbp+178h]
  char *v76; // [rsp+280h] [rbp+180h]
  __int64 v77; // [rsp+288h] [rbp+188h]
  const size_t **v78; // [rsp+290h] [rbp+190h]
  __int64 v79; // [rsp+298h] [rbp+198h]
  __int64 *v80; // [rsp+2A0h] [rbp+1A0h]
  __int64 v81; // [rsp+2A8h] [rbp+1A8h]
  ULONGLONG *v82; // [rsp+2B0h] [rbp+1B0h]
  __int64 v83; // [rsp+2B8h] [rbp+1B8h]
  SIZE_T *p_pvData; // [rsp+2C0h] [rbp+1C0h]
  __int64 v85; // [rsp+2C8h] [rbp+1C8h]
  unsigned __int64 *v86; // [rsp+2D0h] [rbp+1D0h]
  __int64 v87; // [rsp+2D8h] [rbp+1D8h]
  char *v88; // [rsp+2E0h] [rbp+1E0h]
  int v89; // [rsp+2E8h] [rbp+1E8h]
  int v90; // [rsp+2ECh] [rbp+1ECh]
  char v91[144]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(&pcbe, 0, sizeof(pcbe));
  ptpsi = 0;
  memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v2 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v2 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v2,
    _InterlockedExchangeAdd64(v2 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v3);
  v4 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    LODWORD(pvData) = *((_DWORD *)this + 33);
    LODWORD(v60) = *((_DWORD *)this + 32);
    LODWORD(v55) = *((_DWORD *)this + 31);
    LODWORD(v56) = *((_DWORD *)this + 30);
    *(_DWORD *)v57 = *((_DWORD *)this + 29);
    v54 = 0x1000000;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v66 = SystemTime;
    v5 = -1;
    do
      ++v5;
    while ( v91[v5] );
    v90 = 0;
    v89 = v5 + 1;
    v88 = v91;
    v86 = &v54;
    v87 = 8;
    p_pvData = &pvData;
    v85 = 4;
    v82 = &v60;
    v83 = 4;
    v80 = &v55;
    v81 = 4;
    v78 = &v56;
    v76 = v57;
    v72 = &v66;
    v79 = 4;
    v77 = 4;
    v74 = &szValueBuf;
    v75 = 2;
    v73 = 16;
    tlgWriteTransfer_EventWriteTransfer(v4, &unk_18029D2FE, 0, 0, 11, v71);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    80,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Engine starting.",
    v52);
  TickCount64 = GetTickCount64();
  pcbe.Version = 3;
  v7 = TickCount64;
  memset(&pcbe.Pool, 0, 52);
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  Threadpool = CreateThreadpool(0);
  if ( Threadpool )
  {
    LODWORD(pvData) = 0;
    v54 = 4;
    if ( (unsigned int)Windows::Compat::Shared::Registry::ReadValue(
                         &pvData,
                         &v54,
                         0x10u,
                         v10,
                         Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
                         L"MaxThreadCount") == -2147024894 )
    {
      v11 = 0;
      LODWORD(pvData) = 0;
    }
    else
    {
      v11 = pvData;
    }
    if ( !v11 )
    {
      InitOnceExecuteOnce(
        &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
        Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
        0,
        0);
      v11 = Windows::Compat::Appraiser::AppraiserSettings::SettingMaximumThreadCount;
      LODWORD(pvData) = Windows::Compat::Appraiser::AppraiserSettings::SettingMaximumThreadCount;
    }
    SetThreadpoolThreadMaximum(Threadpool, v11);
    pcbe.Pool = Threadpool;
  }
  Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v8);
  Decisions = Windows::Compat::Appraiser::WicaEngine::CollectInventories(this, &pcbe);
  if ( Decisions < 0 )
  {
    v13 = "CollectInventories Failed: [0x%x].";
    v14 = 95;
LABEL_20:
    LODWORD(v53) = Decisions;
    LODWORD(v51) = Decisions;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v14,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      v51,
      (int)v13,
      v53);
    goto LABEL_86;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x55Fu,
      "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      "CollectInventories Failed: [0x%x].",
      Decisions);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v15 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v15 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v15,
    _InterlockedExchangeAdd64(v15 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v16);
  v17 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v57 = 0x1000000;
    v54 = (unsigned __int64)v91;
    v56 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v55 = (__int64)&v66;
    v66 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)&unk_18029D1C2,
      v18,
      v19,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)v57,
      (__int64)&v54);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    97,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Tier complete: Inventory.",
    v53);
  Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v20);
  Decisions = Windows::Compat::Appraiser::WicaEngine::RunDataSources(this, &pcbe);
  if ( Decisions < 0 )
  {
    v13 = "RunDataSources Failed: [0x%x].";
    v14 = 101;
    goto LABEL_20;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x565u,
      "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      "RunDataSources Failed: [0x%x].",
      Decisions);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v21 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v21 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v21,
    _InterlockedExchangeAdd64(v21 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v22);
  v23 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v57 = 0x1000000;
    v54 = (unsigned __int64)v91;
    v56 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v55 = (__int64)&v66;
    v66 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)&unk_18029D210,
      v24,
      v25,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)v57,
      (__int64)&v54);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    103,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Tier complete: Data Source.",
    v53);
  Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v26);
  Decisions = Windows::Compat::Appraiser::WicaEngine::MakeDecisions(this, &pcbe);
  if ( Decisions < 0 )
  {
    v13 = "MakeDecisions Failed: [0x%x].";
    v14 = 107;
    goto LABEL_20;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x56Bu,
      "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      "MakeDecisions Failed: [0x%x].",
      Decisions);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v27 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v27 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v27,
    _InterlockedExchangeAdd64(v27 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v28);
  v29 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v57 = 0x1000000;
    v54 = (unsigned __int64)v91;
    v56 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v55 = (__int64)&v66;
    v66 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v29,
      (unsigned int)&unk_18029D117,
      v30,
      v31,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)v57,
      (__int64)&v54);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    109,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Tier complete: Decision Maker.",
    v53);
  Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v32);
  Decisions = Windows::Compat::Appraiser::WicaEngine::MakeAggregateDecisions(this, &pcbe);
  if ( Decisions < 0 )
  {
    v13 = "MakeAggregateDecisions Failed: [0x%x].";
    v14 = 113;
    goto LABEL_20;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x571u,
      "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      "MakeAggregateDecisions Failed: [0x%x].",
      Decisions);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v33 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v33 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v33,
    _InterlockedExchangeAdd64(v33 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v34);
  v35 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v57 = 0x1000000;
    v54 = (unsigned __int64)v91;
    v56 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v55 = (__int64)&v66;
    v66 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v35,
      (unsigned int)&unk_18029D16A,
      v36,
      v37,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)v57,
      (__int64)&v54);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    115,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Tier complete: Decision Aggregator.",
    v53);
  Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(v38);
  Decisions = Windows::Compat::Appraiser::WicaEngine::DoOutput(this, &pcbe);
  if ( Decisions < 0 )
  {
    v13 = "DoOutput Failed: [0x%x].";
    v14 = 119;
    goto LABEL_20;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x577u,
      "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
      "Windows::Compat::Appraiser::WicaEngine::RunComponents",
      "DoOutput Failed: [0x%x].",
      Decisions);
  if ( Threadpool )
    QueryThreadpoolStackInformation(Threadpool, &ptpsi);
  CurrentProcess = GetCurrentProcess();
  K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v40 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v40 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v40,
    _InterlockedExchangeAdd64(v40 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v41);
  v42 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v55 = 0x1000000;
    v54 = (unsigned __int64)v91;
    v60 = GetTickCount64() - v7;
    pvData = ppsmemCounters.QuotaPeakPagedPoolUsage;
    PeakWorkingSetSize = ppsmemCounters.PeakWorkingSetSize;
    *(_DWORD *)v57 = ppsmemCounters.PageFaultCount;
    LODWORD(v56) = Windows::Compat::Appraiser::WicaEngine::MaxConcurrentThreadCount;
    StackCommit = (struct _SYSTEMTIME *)ptpsi.StackCommit;
    StackReserve = (const size_t *)ptpsi.StackReserve;
    *(_QWORD *)v63 = &szValueBuf;
    v66 = 0;
    GetSystemTime(&v66);
    *(_QWORD *)&SystemTime.wYear = &v68;
    v68 = v66;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v42,
      (unsigned int)&unk_18029D061,
      v43,
      v44,
      (__int64)&SystemTime,
      (__int64)v63,
      (__int64)&StackReserve,
      (__int64)&StackCommit,
      (__int64)&v56,
      (__int64)v57,
      (__int64)&PeakWorkingSetSize,
      (__int64)&pvData,
      (__int64)&v60,
      (__int64)&v55,
      (__int64)&v54);
  }
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookValidateComponentProducesAndConsumes )
  {
    Decisions = Windows::Compat::Appraiser::ProducesConsumesFactory::ValidateLayerProducesConsumes();
    if ( Decisions < 0 )
    {
      v13 = "Failed to ValidateLayerProducesConsumes [0x%x].";
      v14 = -116;
      goto LABEL_20;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x58Cu,
        "onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
        "Windows::Compat::Appraiser::WicaEngine::RunComponents",
        "Failed to ValidateLayerProducesConsumes [0x%x].",
        Decisions);
  }
LABEL_86:
  if ( Threadpool )
    CloseThreadpool(Threadpool);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v69);
  v45 = (volatile signed __int64 *)v69;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v45 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v45,
    _InterlockedExchangeAdd64(v45 + 17, 0),
    v91);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v46);
  v47 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000001LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000001LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v63 = 0x1000000;
    *(_QWORD *)&SystemTime.wYear = v91;
    StackReserve = &szValueBuf;
    v66 = 0;
    GetSystemTime(&v66);
    StackCommit = &v68;
    v68 = v66;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v47,
      (unsigned int)&unk_18029D01E,
      v48,
      v49,
      (__int64)&StackCommit,
      (__int64)&StackReserve,
      (__int64)v63,
      (__int64)&SystemTime);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    149,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\engine\\engine.cpp",
    "Windows::Compat::Appraiser::WicaEngine::RunComponents",
    0,
    (int)"Engine finished.",
    v53);
  return (unsigned int)Decisions;
}

```

## disassembly

```asm
0x18002d884  push    rbp
0x18002d886  push    rbx
0x18002d887  push    rsi
0x18002d888  push    rdi
0x18002d889  push    r12
0x18002d88b  push    r13
0x18002d88d  push    r14
0x18002d88f  push    r15
0x18002d891  lea     rbp, [rsp-298h]
0x18002d899  sub     rsp, 398h
0x18002d8a0  mov     rax, cs:__security_cookie
0x18002d8a7  xor     rax, rsp
0x18002d8aa  mov     [rbp+2D0h+var_50], rax
0x18002d8b1  mov     rdi, rcx
0x18002d8b4  mov     ebx, 48h ; 'H'
0x18002d8b9  mov     r8d, ebx; Size
0x18002d8bc  lea     rcx, [rbp+2D0h+pcbe]; void *
0x18002d8c0  xor     edx, edx; Val
0x18002d8c2  call    memset_0
0x18002d8c7  xorps   xmm0, xmm0
0x18002d8ca  lea     rcx, [rbp+2D0h+ppsmemCounters]; void *
0x18002d8d1  mov     r8d, ebx; Size
0x18002d8d4  xor     edx, edx; Val
0x18002d8d6  movups  xmmword ptr [rbp+2D0h+ptpsi.StackReserve], xmm0
0x18002d8da  call    memset_0
0x18002d8df  lea     rcx, [rbp+2D0h+var_270]; this
0x18002d8e3  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18002d8e8  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18002d8ef  lea     rcx, [rbp+2D0h+var_270]
0x18002d8f3  xor     r15d, r15d
0x18002d8f6  test    rax, rax
0x18002d8f9  mov     edx, r15d
0x18002d8fc  cmovnz  rcx, rax; this
0x18002d900  lock xadd [rcx+88h], rdx; unsigned __int64
0x18002d909  lea     r8, [rbp+2D0h+var_E0]; char *
0x18002d910  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002d915  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r15b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18002d91c  jz      short loc_18002D92A
0x18002d91e  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18002d925  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18002d92a  mov     rbx, cs:qword_1802C9628
0x18002d931  lea     r14, szValueBuf
0x18002d938  mov     rdx, 200000000001h
0x18002d942  mov     eax, [rbx]
0x18002d944  cmp     eax, 5
0x18002d947  jbe     loc_18002DAB9
0x18002d94d  mov     rcx, [rbx+18h]
0x18002d951  mov     rax, [rbx+10h]
0x18002d955  test    rdx, rax
0x18002d958  jz      loc_18002DAB9
0x18002d95e  mov     rax, rcx
0x18002d961  and     rax, rdx
0x18002d964  cmp     rax, rcx
0x18002d967  jnz     loc_18002DAB9
0x18002d96d  mov     eax, [rdi+84h]
0x18002d973  lea     rcx, [rbp+2D0h+SystemTime]; lpSystemTime
0x18002d977  mov     dword ptr [rbp+2D0h+pvData], eax
0x18002d97a  xorps   xmm0, xmm0
0x18002d97d  mov     eax, [rdi+80h]
0x18002d983  mov     dword ptr [rbp+2D0h+var_318], eax
0x18002d986  mov     eax, [rdi+7Ch]
0x18002d989  mov     dword ptr [rbp+2D0h+var_348], eax
0x18002d98c  mov     eax, [rdi+78h]
0x18002d98f  mov     dword ptr [rbp+2D0h+var_340], eax
0x18002d992  mov     eax, [rdi+74h]
0x18002d995  mov     dword ptr [rbp+2D0h+var_338], eax
0x18002d998  mov     [rbp+2D0h+var_350], 1000000h
0x18002d9a0  movups  xmmword ptr [rbp+2D0h+SystemTime.wYear], xmm0
0x18002d9a4  call    cs:__imp_GetSystemTime
0x18002d9aa  movaps  xmm0, xmmword ptr [rbp+2D0h+SystemTime.wYear]
0x18002d9ae  lea     rcx, [rbp+2D0h+var_E0]
0x18002d9b5  movdqa  xmmword ptr [rbp+2D0h+var_2A0.wYear], xmm0
0x18002d9ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d9be  inc     rax
0x18002d9c1  cmp     [rcx+rax], r15b
0x18002d9c5  jnz     short loc_18002D9BE
0x18002d9c7  inc     eax
0x18002d9c9  mov     [rbp+2D0h+var_E4], r15d
0x18002d9d0  mov     [rbp+2D0h+var_E8], eax
0x18002d9d6  lea     rcx, [rbp+2D0h+var_E0]
0x18002d9dd  lea     rax, [rbp+2D0h+var_350]
0x18002d9e1  mov     [rbp+2D0h+var_F0], rcx
0x18002d9e8  mov     [rbp+2D0h+var_100], rax
0x18002d9ef  lea     rdx, unk_18029D2FE
0x18002d9f6  lea     rax, [rbp+2D0h+pvData]
0x18002d9fa  mov     [rbp+2D0h+var_F8], 8
0x18002da05  mov     [rbp+2D0h+var_110], rax
0x18002da0c  xor     r9d, r9d
0x18002da0f  lea     rax, [rbp+2D0h+var_318]
0x18002da13  mov     [rbp+2D0h+var_108], 4
0x18002da1e  mov     [rbp+2D0h+var_120], rax
0x18002da25  xor     r8d, r8d
0x18002da28  lea     rax, [rbp+2D0h+var_348]
0x18002da2c  mov     [rbp+2D0h+var_118], 4
0x18002da37  mov     [rbp+2D0h+var_130], rax
0x18002da3e  mov     rcx, rbx
0x18002da41  lea     rax, [rbp+2D0h+var_340]
0x18002da45  mov     [rbp+2D0h+var_128], 4
0x18002da50  mov     [rbp+2D0h+var_140], rax
0x18002da57  lea     rax, [rbp+2D0h+var_338]
0x18002da5b  mov     [rbp+2D0h+var_150], rax
0x18002da62  lea     rax, [rbp+2D0h+var_2A0]
0x18002da66  mov     [rbp+2D0h+var_170], rax
0x18002da6d  lea     rax, [rbp+2D0h+var_190]
0x18002da74  mov     [rsp+3D0h+var_3A8], rax
0x18002da79  mov     dword ptr [rsp+3D0h+var_3B0], 0Bh
0x18002da81  mov     [rbp+2D0h+var_138], 4
0x18002da8c  mov     [rbp+2D0h+var_148], 4
0x18002da97  mov     [rbp+2D0h+var_160], r14
0x18002da9e  mov     [rbp+2D0h+var_158], 2
0x18002daa9  mov     [rbp+2D0h+var_168], 10h
0x18002dab4  call    _tlgWriteTransfer_EventWriteTransfer
0x18002dab9  lea     rax, aEngineStarting; "Engine starting."
0x18002dac0  mov     edx, 550h; bool
0x18002dac5  mov     [rsp+3D0h+var_3A8], rax; int
0x18002daca  lea     r12, aWindowsCompatA_130; "Windows::Compat::Appraiser::WicaEngine:"...
0x18002dad1  lea     r13, aOnecoreBaseApp_105; "onecore\\base\\appcompat\\appraiser\\en"...
0x18002dad8  mov     [rsp+3D0h+var_3B0], r15; char *
0x18002dadd  mov     r9, r12; char *
0x18002dae0  mov     r8, r13; unsigned int
0x18002dae3  xor     ecx, ecx; this
0x18002dae5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18002daea  call    cs:__imp_GetTickCount64
0x18002daf0  xorps   xmm0, xmm0
0x18002daf3  mov     [rbp+2D0h+pcbe.Version], 3
0x18002dafa  xor     ecx, ecx; reserved
0x18002dafc  movdqa  xmmword ptr [rbp+2D0h+pcbe.RaceDll], xmm0
0x18002db01  mov     r14, rax
0x18002db04  mov     [rbp+2D0h+pcbe.Pool], r15
0x18002db08  mov     [rbp+2D0h+pcbe.CleanupGroup], r15
0x18002db0c  mov     [rbp+2D0h+pcbe.CleanupGroupCancelCallback], r15
0x18002db10  mov     [rbp+2D0h+pcbe.FinalizationCallback], r15
0x18002db14  mov     dword ptr [rbp+2D0h+pcbe.u], r15d
0x18002db18  mov     [rbp+2D0h+pcbe.CallbackPriority], 1
0x18002db1f  mov     [rbp+2D0h+pcbe.Size], 48h ; 'H'
0x18002db26  call    cs:__imp_CreateThreadpool
0x18002db2c  mov     rsi, rax
0x18002db2f  test    rax, rax
0x18002db32  jz      short loc_18002DBB1
0x18002db34  mov     rcx, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x18002db3b  lea     rax, aMaxthreadcount; "MaxThreadCount"
0x18002db42  mov     [rsp+3D0h+var_3A8], rax; unsigned __int16 *
0x18002db47  lea     rdx, [rbp+2D0h+var_350]; unsigned __int64 *
0x18002db4b  mov     [rsp+3D0h+var_3B0], rcx; unsigned __int16 *
0x18002db50  mov     r8d, 10h; unsigned int
0x18002db56  lea     rcx, [rbp+2D0h+pvData]; pvData
0x18002db5a  mov     dword ptr [rbp+2D0h+pvData], r15d
0x18002db5e  mov     [rbp+2D0h+var_350], 4
0x18002db66  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18002db6b  cmp     eax, 80070002h
0x18002db70  jnz     short loc_18002DB7A
0x18002db72  mov     edx, r15d
0x18002db75  mov     dword ptr [rbp+2D0h+pvData], edx
0x18002db78  jmp     short loc_18002DB7D
0x18002db7a  mov     edx, dword ptr [rbp+2D0h+pvData]
0x18002db7d  test    edx, edx
0x18002db7f  jnz     short loc_18002DBA4
0x18002db81  xor     r9d, r9d; Context
0x18002db84  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002db8b  xor     r8d, r8d; Parameter
0x18002db8e  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18002db95  call    cs:__imp_InitOnceExecuteOnce
0x18002db9b  mov     edx, cs:?SettingMaximumThreadCount@AppraiserSettings@Appraiser@Compat@Windows@@0KA; cthrdMost
0x18002dba1  mov     dword ptr [rbp+2D0h+pvData], edx
0x18002dba4  mov     rcx, rsi; ptpp
0x18002dba7  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002dbad  mov     [rbp+2D0h+pcbe.Pool], rsi
0x18002dbb1  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x18002dbb6  lea     rdx, [rbp+2D0h+pcbe]; pcbe
0x18002dbba  mov     rcx, rdi; this
0x18002dbbd  call    ?CollectInventories@WicaEngine@Appraiser@Compat@Windows@@AEAAJPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; Windows::Compat::Appraiser::WicaEngine::CollectInventories(_TP_CALLBACK_ENVIRON_V3 *)
0x18002dbc2  mov     ebx, eax
0x18002dbc4  test    eax, eax
0x18002dbc6  jns     short loc_18002DBF6
0x18002dbc8  lea     r9, aCollectinvento; "CollectInventories Failed: [0x%x]."
0x18002dbcf  mov     edx, 55Fh; bool
0x18002dbd4  mov     dword ptr [rsp+3D0h+var_3A0], ebx; char *
0x18002dbd8  mov     r8, r13; unsigned int
0x18002dbdb  mov     [rsp+3D0h+var_3A8], r9; int
0x18002dbe0  mov     ecx, 1; this
0x18002dbe5  mov     r9, r12; char *
0x18002dbe8  mov     dword ptr [rsp+3D0h+var_3B0], ebx; char *
0x18002dbec  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18002dbf1  jmp     loc_18002E3A4
0x18002dbf6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18002dbfc  test    al, 1
0x18002dbfe  jz      short loc_18002DC1B
0x18002dc00  lea     r9, aCollectinvento; "CollectInventories Failed: [0x%x]."
0x18002dc07  mov     dword ptr [rsp+3D0h+var_3B0], ebx
0x18002dc0b  mov     r8, r12; char *
0x18002dc0e  mov     rdx, r13; char *
0x18002dc11  mov     ecx, 55Fh; unsigned int
0x18002dc16  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18002dc1b  lea     rcx, [rbp+2D0h+var_270]; this
0x18002dc1f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18002dc24  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18002dc2b  lea     rcx, [rbp+2D0h+var_270]
0x18002dc2f  test    rax, rax
0x18002dc32  mov     rdx, r15
0x18002dc35  cmovnz  rcx, rax; this
0x18002dc39  lock xadd [rcx+88h], rdx; unsigned __int64
0x18002dc42  lea     r8, [rbp+2D0h+var_E0]; char *
0x18002dc49  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002dc4e  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r15b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18002dc55  jz      short loc_18002DC63
0x18002dc57  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18002dc5e  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18002dc63  mov     rbx, cs:qword_1802C9628
0x18002dc6a  mov     eax, [rbx]
0x18002dc6c  cmp     eax, 5
0x18002dc6f  jbe     loc_18002DD0A
0x18002dc75  mov     rcx, [rbx+18h]
0x18002dc79  mov     rdx, 200000000001h
0x18002dc83  mov     rax, [rbx+10h]
0x18002dc87  test    rdx, rax
0x18002dc8a  jz      short loc_18002DD0A
0x18002dc8c  mov     rax, rcx
0x18002dc8f  and     rax, rdx
0x18002dc92  cmp     rax, rcx
0x18002dc95  jnz     short loc_18002DD0A
0x18002dc97  lea     rax, [rbp+2D0h+var_E0]
0x18002dc9e  mov     qword ptr [rbp+2D0h+var_338], 1000000h
0x18002dca6  mov     [rbp+2D0h+var_350], rax
0x18002dcaa  lea     rcx, [rbp+2D0h+SystemTime]; lpSystemTime
0x18002dcae  lea     rax, szValueBuf
0x18002dcb5  xorps   xmm0, xmm0
0x18002dcb8  mov     [rbp+2D0h+var_340], rax
0x18002dcbc  movups  xmmword ptr [rbp+2D0h+SystemTime.wYear], xmm0
0x18002dcc0  call    cs:__imp_GetSystemTime
0x18002dcc6  movaps  xmm0, xmmword ptr [rbp+2D0h+SystemTime.wYear]
0x18002dcca  lea     rax, [rbp+2D0h+var_2A0]
0x18002dcce  mov     [rbp+2D0h+var_348], rax
0x18002dcd2  lea     rdx, unk_18029D1C2
0x18002dcd9  lea     rax, [rbp+2D0h+var_350]
0x18002dcdd  movdqa  xmmword ptr [rbp+2D0h+var_2A0.wYear], xmm0
0x18002dce2  mov     [rsp+3D0h+var_398], rax
0x18002dce7  mov     rcx, rbx
0x18002dcea  lea     rax, [rbp+2D0h+var_338]
0x18002dcee  mov     [rsp+3D0h+var_3A0], rax; char *
0x18002dcf3  lea     rax, [rbp+2D0h+var_340]
0x18002dcf7  mov     [rsp+3D0h+var_3A8], rax
0x18002dcfc  lea     rax, [rbp+2D0h+var_348]
0x18002dd00  mov     [rsp+3D0h+var_3B0], rax
0x18002dd05  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18002dd0a  lea     rax, aTierCompleteIn; "Tier complete: Inventory."
0x18002dd11  mov     r9, r12; char *
0x18002dd14  mov     [rsp+3D0h+var_3A8], rax; int
0x18002dd19  mov     r8, r13; unsigned int
0x18002dd1c  mov     edx, 561h; bool
0x18002dd21  mov     [rsp+3D0h+var_3B0], r15; char *
0x18002dd26  xor     ecx, ecx; this
0x18002dd28  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18002dd2d  call    ?RenewTimer@InventoryWatchdog@Inventory@Compat@Windows@@QEAA_NXZ; Windows::Compat::Inventory::InventoryWatchdog::RenewTimer(void)
0x18002dd32  lea     rdx, [rbp+2D0h+pcbe]; struct _TP_CALLBACK_ENVIRON_V3 *
0x18002dd36  mov     rcx, rdi; this
0x18002dd39  call    ?RunDataSources@WicaEngine@Appraiser@Compat@Windows@@AEAAJPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; Windows::Compat::Appraiser::WicaEngine::RunDataSources(_TP_CALLBACK_ENVIRON_V3 *)
0x18002dd3e  mov     ebx, eax
0x18002dd40  test    eax, eax
0x18002dd42  jns     short loc_18002DD55
0x18002dd44  lea     r9, aRundatasources; "RunDataSources Failed: [0x%x]."
0x18002dd4b  mov     edx, 565h
0x18002dd50  jmp     loc_18002DBD4
0x18002dd55  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18002dd5b  test    al, 1
0x18002dd5d  jz      short loc_18002DD7A
0x18002dd5f  lea     r9, aRundatasources; "RunDataSources Failed: [0x%x]."
0x18002dd66  mov     dword ptr [rsp+3D0h+var_3B0], ebx
0x18002dd6a  mov     r8, r12; char *
0x18002dd6d  mov     rdx, r13; char *
0x18002dd70  mov     ecx, 565h; unsigned int
0x18002dd75  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18002dd7a  lea     rcx, [rbp+2D0h+var_270]; this
0x18002dd7e  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18002dd83  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18002dd8a  lea     rcx, [rbp+2D0h+var_270]
0x18002dd8e  test    rax, rax
0x18002dd91  mov     rdx, r15
0x18002dd94  cmovnz  rcx, rax; this
0x18002dd98  lock xadd [rcx+88h], rdx; unsigned __int64
0x18002dda1  lea     r8, [rbp+2D0h+var_E0]; char *
0x18002dda8  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002ddad  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r15b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18002ddb4  jz      short loc_18002DDC2
0x18002ddb6  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18002ddbd  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18002ddc2  mov     rbx, cs:qword_1802C9628
0x18002ddc9  mov     eax, [rbx]
0x18002ddcb  cmp     eax, 5
0x18002ddce  jbe     loc_18002DE69
0x18002ddd4  mov     rcx, [rbx+18h]
0x18002ddd8  mov     rdx, 200000000001h
0x18002dde2  mov     rax, [rbx+10h]
0x18002dde6  test    rdx, rax
0x18002dde9  jz      short loc_18002DE69
0x18002ddeb  mov     rax, rcx
0x18002ddee  and     rax, rdx
0x18002ddf1  cmp     rax, rcx
0x18002ddf4  jnz     short loc_18002DE69
0x18002ddf6  lea     rax, [rbp+2D0h+var_E0]
0x18002ddfd  mov     qword ptr [rbp+2D0h+var_338], 1000000h
  ... truncated ...
```
