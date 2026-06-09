# UQIService::EnsureInitialized(void)

- ea: `0x18001b234`
- end: `0x18001b87b`
- name: `?EnsureInitialized@UQIService@@QEAAXXZ`
- size: `1607`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *pv)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ba58`
- `0x18001c060`

## callees

- `0x1800038b8`
- `0x180007804`
- `0x18000b420`
- `0x1800107b0`
- `0x180010920`
- `0x180013c48`
- `0x1800149fc`
- `0x180016628`
- `0x180016b2c`
- `0x180016cac`
- `0x180016cec`
- `0x180016dcc`
- `0x18001ab5c`
- `0x18001ac5c`
- `0x18001b234`
- `0x18001c53c`
- `0x18001f488`
- `0x180022c20`
- `0x180034de4`
- `0x1800e55e8`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b7f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b7f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b85b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001b3ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001b3ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b251`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b7c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b251`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b554`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b584`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b57c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b57c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b567`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b7a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b567`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b7a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b542`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b542`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b573`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b822`

## string_xrefs

- `0x18001b868`: `onecore\base\usageandqualityinsights\service\lib\serviceobj\serviceobj.cpp`
- `0x18001b529`: `Starting Background Maintenance Tasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall UQIService::EnsureInitialized(struct _RTL_CRITICAL_SECTION *pv)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  char v2; // r12
  UsageAndQualityInsights::Utilities *v3; // rcx
  _DWORD *v4; // rsi
  volatile signed __int32 *LockSemaphore; // rbx
  RTL_SRWLOCK *v6; // r14
  volatile signed __int32 *v7; // rbx
  char *v8; // r14
  _QWORD *v9; // rax
  volatile signed __int32 *DebugInfo; // rbx
  void **v11; // rax
  void *v12; // rcx
  void *v13; // rdx
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *SpinCount; // r14
  DWORD LastError; // ebx
  unsigned int v19; // r15d
  int FeatureVariant; // ebx
  int v21; // r14d
  unsigned int v22; // ebx
  int v23; // r8d
  unsigned __int64 v24; // r10
  char v25; // r11
  __int64 v26; // r9
  unsigned int v27; // ebx
  int v28; // ecx
  unsigned int v29; // edx
  bool v30; // zf
  unsigned __int64 v31; // rax
  _DWORD *v32; // rbx
  struct _RTL_CRITICAL_SECTION *v33; // r14
  void *v34; // rbx
  const char *v35; // rax
  int v36; // [rsp+20h] [rbp-C8h]
  __int64 v37; // [rsp+30h] [rbp-B8h]
  signed __int64 v38; // [rsp+30h] [rbp-B8h]
  unsigned int v39; // [rsp+38h] [rbp-B0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-A8h] BYREF
  volatile signed __int32 *v41; // [rsp+48h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+50h] [rbp-98h]
  const wil::ResultException *v43; // [rsp+58h] [rbp-90h] BYREF
  const std::exception *v44; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v45[8]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v46[48]; // [rsp+78h] [rbp-70h] BYREF
  LPVOID pva; // [rsp+A8h] [rbp-40h]
  wil::details *retaddr; // [rsp+E8h] [rbp+0h]
  unsigned __int64 v50; // [rsp+F8h] [rbp+10h] BYREF
  char *v51; // [rsp+100h] [rbp+18h] BYREF
  int v52; // [rsp+108h] [rbp+20h] BYREF

  v1 = pv;
  v2 = 0;
  EnterCriticalSection(pv);
  v42 = v1;
  if ( LOBYTE(v1[2].LockCount)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl)
    || UsageAndQualityInsights::Utilities::IsPolicyRestricted(v3) )
  {
    goto LABEL_68;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>>>(v45);
    v4 = operator new(0x78u);
    v50 = (unsigned __int64)v4;
    v4[2] = 1;
    v4[3] = 1;
    *(_QWORD *)v4 = &std::_Ref_count_obj2<UsageAndQualityInsights::Database::UQIDatabaseManager>::`vftable';
    UsageAndQualityInsights::Database::UQIDatabaseManager::UQIDatabaseManager((UsageAndQualityInsights::Database::UQIDatabaseManager *)(v4 + 4));
    v1[1].OwningThread = v4 + 4;
    LockSemaphore = (volatile signed __int32 *)v1[1].LockSemaphore;
    v1[1].LockSemaphore = v4;
    if ( LockSemaphore )
    {
      if ( _InterlockedExchangeAdd(LockSemaphore + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))LockSemaphore)(LockSemaphore);
        if ( _InterlockedExchangeAdd(LockSemaphore + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)LockSemaphore + 8LL))(LockSemaphore);
      }
    }
    v6 = (RTL_SRWLOCK *)operator new(0xD0u);
    v50 = (unsigned __int64)v6;
    LODWORD(v6[1].Ptr) = 1;
    HIDWORD(v6[1].Ptr) = 1;
    v6->Ptr = &std::_Ref_count_obj2<UsageAndQualityInsights::Configuration::ConfigStore>::`vftable';
    UsageAndQualityInsights::Configuration::ConfigStore::ConfigStore(v6 + 2);
    v1[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&v6[2];
    v7 = *(volatile signed __int32 **)&v1[1].LockCount;
    *(_QWORD *)&v1[1].LockCount = v6;
    if ( v7 )
    {
      if ( !_InterlockedDecrement(v7 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( !_InterlockedDecrement(v7 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl'::`2'::impl) )
    {
      v8 = (char *)operator new(0x48u);
      v50 = (unsigned __int64)v8;
      *((_DWORD *)v8 + 2) = 1;
      *((_DWORD *)v8 + 3) = 1;
      *(_QWORD *)v8 = &std::_Ref_count_obj2<UsageAndQualityInsights::Facts::FactStoreManager>::`vftable';
      v51 = v8 + 16;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 8) = 0;
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 16), 0, 0);
      *((_QWORD *)v8 + 7) = 0;
      *((_QWORD *)v8 + 8) = 0;
      v9 = operator new(0x50u);
      *v9 = v9;
      v9[1] = v9;
      v9[2] = v9;
      *((_WORD *)v9 + 12) = 257;
      *((_QWORD *)v8 + 7) = v9;
      v1[1].SpinCount = (ULONG_PTR)(v8 + 16);
      DebugInfo = (volatile signed __int32 *)v1[2].DebugInfo;
      v1[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v8;
      if ( DebugInfo )
      {
        if ( !_InterlockedDecrement(DebugInfo + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))DebugInfo)(DebugInfo);
          if ( !_InterlockedDecrement(DebugInfo + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)DebugInfo + 8LL))(DebugInfo);
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57896588>::GetImpl'::`2'::impl) )
    {
      v11 = (void **)std::make_shared<UsageAndQualityInsights::Signals::ExpIdSubscription,>(&pftDueTime);
      v12 = *v11;
      v13 = v11[1];
      *v11 = 0;
      v11[1] = 0;
      v1[2].OwningThread = v12;
      v14 = (volatile signed __int32 *)v1[2].LockSemaphore;
      v1[2].LockSemaphore = v13;
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      v15 = v41;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      UsageAndQualityInsights::Signals::ExpIdSubscription::Initialize((UsageAndQualityInsights::Signals::ExpIdSubscription *)v1[2].OwningThread);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59301394>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59301394>::GetImpl'::`2'::impl) )
      goto LABEL_55;
    UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("Starting Background Maintenance Tasks");
    ThreadpoolTimer = CreateThreadpoolTimer(UQIService::TimerCallback, v1, 0);
    SpinCount = (struct _TP_TIMER *)v1[2].SpinCount;
    if ( SpinCount )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(SpinCount, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(SpinCount, 1);
      CloseThreadpoolTimer(SpinCount);
      SetLastError(LastError);
    }
    v1[2].SpinCount = (ULONG_PTR)ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\serviceobj\\serviceobj.cpp",
        (const char *)0x8000FFFFLL,
        v36);
    v37 = *Feature_59301394__descriptor;
    v19 = *Feature_59301394__descriptor;
    if ( (*Feature_59301394__descriptor & 0xC) == 0xC )
    {
      v27 = HIDWORD(*Feature_59301394__descriptor);
LABEL_54:
      pftDueTime = (struct _FILETIME)(-10000000LL * v27);
      SetThreadpoolTimer((PTP_TIMER)v1[2].SpinCount, &pftDueTime, 0, 0);
LABEL_55:
      v32 = pva;
      v33 = (struct _RTL_CRITICAL_SECTION *)((char *)pva + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pva + 5);
      v32[18] |= 0x300u;
      if ( *((_QWORD *)v32 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v32 + 2, 2);
      if ( v33 )
        LeaveCriticalSection(v33);
      LOBYTE(v1[2].LockCount) = 1;
      v34 = pva;
      if ( pva && _InterlockedExchangeAdd((volatile signed __int32 *)pva + 68, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v34);
        CoTaskMemFree(v34);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v46);
      goto LABEL_68;
    }
    v52 = 0;
    v39 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(retaddr);
    LODWORD(v50) = 0;
    LODWORD(v51) = 0;
    if ( g_wil_details_internalGetFeatureVariant )
    {
      FeatureVariant = g_wil_details_internalGetFeatureVariant(59301394, 1, &v51, &v50, &v52);
    }
    else
    {
      if ( !g_wil_details_apiGetFeatureVariant )
      {
        FeatureVariant = 0;
        goto LABEL_40;
      }
      FeatureVariant = g_wil_details_apiGetFeatureVariant(59301394, 1, &v51, &v50, &v52);
    }
    if ( (FeatureVariant & 0x100) != 0 )
      v2 = 1;
LABEL_40:
    v21 = ((_DWORD)v50 != 0 ? 0x400 : 0) | (16 * (FeatureVariant & 0x80));
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl'::`2'::impl) )
    {
      v22 = FeatureVariant & 0xFFFFFE7F;
      if ( v22 )
      {
        v21 ^= (v21 ^ (v22 << 12)) & 0x3F000;
        v23 = (int)v51;
        if ( v2 )
          goto LABEL_45;
      }
      else
      {
        v21 |= 0x1000u;
      }
    }
    v23 = 15;
LABEL_45:
    LODWORD(v24) = HIDWORD(v37);
    while ( 1 )
    {
      v25 = v19;
      v26 = v19;
      v38 = __PAIR64__(v24, v19);
      v27 = v24;
      if ( (v19 & 8) == 0 )
      {
        v27 = v23;
        HIDWORD(v38) = v23;
        v28 = v52 != 0 ? 8 : 0;
        v29 = (v19 ^ (v21 ^ v19) & 0x3F000) & 0xFFFFF7F7;
        v26 = v28 | v29 | v21 & 0x800;
        LODWORD(v38) = v28 | v29 | v21 & 0x800;
      }
      if ( (v19 & 4) == 0 )
        LODWORD(v38) = v26 ^ ((unsigned __int16)v21 ^ (unsigned __int16)v26) & 0x400 | 4;
      v50 = __PAIR64__(v24, v19);
      v31 = _InterlockedCompareExchange64(Feature_59301394__descriptor, v38, __SPAIR64__(v24, v19));
      v30 = __PAIR64__(v24, v19) == v31;
      v19 = v31;
      if ( v30 )
        break;
      v24 = HIDWORD(v31);
    }
    if ( (v25 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_59301394__descriptor, 1, v39, v26);
    goto LABEL_54;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v43) )
    {
      UsageAndQualityInsightsCoreLogging::TraceLoggingError(
        "Service initialization failed, error: 0x%08X",
        *((_DWORD *)v43 + 8));
      v1 = pv;
      __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18001B83E);
      goto LABEL_68;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v44) )
    {
      v35 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v44 + 8LL))(v44);
      UsageAndQualityInsightsCoreLogging::TraceLoggingError("Service initialization failed, exception: %s", v35);
      v1 = pv;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18001B83E);
    }
  }
LABEL_68:
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18001b234  mov     [rsp+arg_0], rcx
0x18001b239  push    rbx
0x18001b23a  push    rsi
0x18001b23b  push    rdi
0x18001b23c  push    r12
0x18001b23e  push    r13
0x18001b240  push    r14
0x18001b242  push    r15
0x18001b244  sub     rsp, 0B0h
0x18001b24b  mov     rdi, rcx
0x18001b24e  xor     r12d, r12d
0x18001b251  call    cs:__imp_EnterCriticalSection
0x18001b257  mov     [rsp+0E8h+var_98], rdi
0x18001b25c  cmp     [rdi+58h], r12b
0x18001b260  jnz     loc_18001B846
0x18001b266  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights> `wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl(void)'::`2'::impl
0x18001b26d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(void)
0x18001b272  test    al, al
0x18001b274  jz      loc_18001B846
0x18001b27a  call    ?IsPolicyRestricted@Utilities@UsageAndQualityInsights@@YA_NXZ; UsageAndQualityInsights::Utilities::IsPolicyRestricted(void)
0x18001b27f  test    al, al
0x18001b281  jnz     loc_18001B846
0x18001b287  lea     rcx, [rsp+0E8h+var_78]
0x18001b28c  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18001b291  nop
0x18001b292  lea     ecx, [r12+78h]; Size
0x18001b297  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b29c  mov     rsi, rax
0x18001b29f  mov     [rsp+0E8h+arg_8], rax
0x18001b2a7  lea     r13d, [r12+1]
0x18001b2ac  mov     [rax+8], r13d
0x18001b2b0  mov     [rax+0Ch], r13d
0x18001b2b4  lea     rax, ??_7?$_Ref_count_obj2@VUQIDatabaseManager@Database@UsageAndQualityInsights@@@std@@6B@; const std::_Ref_count_obj2<UsageAndQualityInsights::Database::UQIDatabaseManager>::`vftable'
0x18001b2bb  mov     [rsi], rax
0x18001b2be  lea     rbx, [rsi+10h]
0x18001b2c2  mov     rcx, rbx; this
0x18001b2c5  call    ??0UQIDatabaseManager@Database@UsageAndQualityInsights@@QEAA@XZ; UsageAndQualityInsights::Database::UQIDatabaseManager::UQIDatabaseManager(void)
0x18001b2ca  nop
0x18001b2cb  mov     [rdi+38h], rbx
0x18001b2cf  mov     rbx, [rdi+40h]
0x18001b2d3  mov     [rdi+40h], rsi
0x18001b2d7  or      esi, 0FFFFFFFFh
0x18001b2da  test    rbx, rbx
0x18001b2dd  jz      short loc_18001B312
0x18001b2df  mov     eax, esi
0x18001b2e1  lock xadd [rbx+8], eax
0x18001b2e6  add     eax, esi
0x18001b2e8  jnz     short loc_18001B312
0x18001b2ea  mov     rax, [rbx]
0x18001b2ed  mov     rcx, rbx
0x18001b2f0  mov     rax, [rax]
0x18001b2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2f8  mov     eax, esi
0x18001b2fa  lock xadd [rbx+0Ch], eax
0x18001b2ff  add     eax, esi
0x18001b301  jnz     short loc_18001B312
0x18001b303  mov     rax, [rbx]
0x18001b306  mov     rcx, rbx
0x18001b309  mov     rax, [rax+8]
0x18001b30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b312  mov     ecx, 0D0h; Size
0x18001b317  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b31c  mov     r14, rax
0x18001b31f  mov     [rsp+0E8h+arg_8], rax
0x18001b327  mov     [rax+8], r13d
0x18001b32b  mov     [rax+0Ch], r13d
0x18001b32f  lea     rax, ??_7?$_Ref_count_obj2@VConfigStore@Configuration@UsageAndQualityInsights@@@std@@6B@; const std::_Ref_count_obj2<UsageAndQualityInsights::Configuration::ConfigStore>::`vftable'
0x18001b336  mov     [r14], rax
0x18001b339  lea     rbx, [r14+10h]
0x18001b33d  mov     rcx, rbx; this
0x18001b340  call    ??0ConfigStore@Configuration@UsageAndQualityInsights@@QEAA@XZ; UsageAndQualityInsights::Configuration::ConfigStore::ConfigStore(void)
0x18001b345  nop
0x18001b346  mov     [rdi+28h], rbx
0x18001b34a  mov     rbx, [rdi+30h]
0x18001b34e  mov     [rdi+30h], r14
0x18001b352  test    rbx, rbx
0x18001b355  jz      short loc_18001B38A
0x18001b357  mov     eax, esi
0x18001b359  lock xadd [rbx+8], eax
0x18001b35e  add     eax, esi
0x18001b360  jnz     short loc_18001B38A
0x18001b362  mov     rax, [rbx]
0x18001b365  mov     rcx, rbx
0x18001b368  mov     rax, [rax]
0x18001b36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b370  mov     eax, esi
0x18001b372  lock xadd [rbx+0Ch], eax
0x18001b377  add     eax, esi
0x18001b379  jnz     short loc_18001B38A
0x18001b37b  mov     rax, [rbx]
0x18001b37e  mov     rcx, rbx
0x18001b381  mov     rax, [rax+8]
0x18001b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b38a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59192442@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442> `wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl(void)'::`2'::impl
0x18001b391  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(void)
0x18001b396  test    al, al
0x18001b398  jz      loc_18001B45F
0x18001b39e  mov     ecx, 48h ; 'H'; Size
0x18001b3a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b3a8  mov     r14, rax
0x18001b3ab  mov     [rsp+0E8h+arg_8], rax
0x18001b3b3  mov     [rax+8], r13d
0x18001b3b7  mov     [rax+0Ch], r13d
0x18001b3bb  lea     rax, ??_7?$_Ref_count_obj2@VFactStoreManager@Facts@UsageAndQualityInsights@@@std@@6B@; const std::_Ref_count_obj2<UsageAndQualityInsights::Facts::FactStoreManager>::`vftable'
0x18001b3c2  mov     [r14], rax
0x18001b3c5  lea     rbx, [r14+10h]
0x18001b3c9  mov     [rsp+0E8h+arg_10], rbx
0x18001b3d1  xorps   xmm0, xmm0
0x18001b3d4  xor     eax, eax
0x18001b3d6  movups  xmmword ptr [rbx], xmm0
0x18001b3d9  movups  xmmword ptr [rbx+10h], xmm0
0x18001b3dd  movups  xmmword ptr [rbx+20h], xmm0
0x18001b3e1  mov     [rbx+30h], rax
0x18001b3e5  xor     r8d, r8d; Flags
0x18001b3e8  xor     edx, edx; dwSpinCount
0x18001b3ea  mov     rcx, rbx; lpCriticalSection
0x18001b3ed  call    cs:__imp_InitializeCriticalSectionEx
0x18001b3f3  nop
0x18001b3f4  mov     [rbx+28h], r12
0x18001b3f8  mov     [rbx+30h], r12
0x18001b3fc  mov     ecx, 50h ; 'P'; Size
0x18001b401  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b406  mov     [rax], rax
0x18001b409  mov     [rax+8], rax
0x18001b40d  mov     [rax+10h], rax
0x18001b411  mov     word ptr [rax+18h], 101h
0x18001b417  mov     [rbx+28h], rax
0x18001b41b  mov     [rdi+48h], rbx
0x18001b41f  mov     rbx, [rdi+50h]
0x18001b423  mov     [rdi+50h], r14
0x18001b427  test    rbx, rbx
0x18001b42a  jz      short loc_18001B45F
0x18001b42c  mov     eax, esi
0x18001b42e  lock xadd [rbx+8], eax
0x18001b433  add     eax, esi
0x18001b435  jnz     short loc_18001B45F
0x18001b437  mov     rax, [rbx]
0x18001b43a  mov     rcx, rbx
0x18001b43d  mov     rax, [rax]
0x18001b440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b445  mov     eax, esi
0x18001b447  lock xadd [rbx+0Ch], eax
0x18001b44c  add     eax, esi
0x18001b44e  jnz     short loc_18001B45F
0x18001b450  mov     rax, [rbx]
0x18001b453  mov     rcx, rbx
0x18001b456  mov     rax, [rax+8]
0x18001b45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57896588@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57896588@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588> `wil::Feature<__WilFeatureTraits_Feature_57896588>::GetImpl(void)'::`2'::impl
0x18001b466  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57896588@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57896588>::__private_IsEnabled(void)
0x18001b46b  test    al, al
0x18001b46d  jz      loc_18001B515
0x18001b473  lea     rcx, [rsp+0E8h+pftDueTime]
0x18001b478  call    ??$make_shared@VExpIdSubscription@Signals@UsageAndQualityInsights@@$$V@std@@YA?AV?$shared_ptr@VExpIdSubscription@Signals@UsageAndQualityInsights@@@0@XZ; std::make_shared<UsageAndQualityInsights::Signals::ExpIdSubscription,>(void)
0x18001b47d  mov     rcx, [rax]
0x18001b480  mov     rdx, [rax+8]
0x18001b484  mov     [rax], r12
0x18001b487  mov     [rax+8], r12
0x18001b48b  mov     [rdi+60h], rcx
0x18001b48f  mov     rbx, [rdi+68h]
0x18001b493  mov     [rdi+68h], rdx
0x18001b497  test    rbx, rbx
0x18001b49a  jz      short loc_18001B4CF
0x18001b49c  mov     eax, esi
0x18001b49e  lock xadd [rbx+8], eax
0x18001b4a3  add     eax, esi
0x18001b4a5  jnz     short loc_18001B4CF
0x18001b4a7  mov     rax, [rbx]
0x18001b4aa  mov     rcx, rbx
0x18001b4ad  mov     rax, [rax]
0x18001b4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4b5  mov     eax, esi
0x18001b4b7  lock xadd [rbx+0Ch], eax
0x18001b4bc  add     eax, esi
0x18001b4be  jnz     short loc_18001B4CF
0x18001b4c0  mov     rax, [rbx]
0x18001b4c3  mov     rcx, rbx
0x18001b4c6  mov     rax, [rax+8]
0x18001b4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4cf  mov     rbx, [rsp+0E8h+var_A0]
0x18001b4d4  test    rbx, rbx
0x18001b4d7  jz      short loc_18001B50C
0x18001b4d9  mov     eax, esi
0x18001b4db  lock xadd [rbx+8], eax
0x18001b4e0  add     eax, esi
0x18001b4e2  jnz     short loc_18001B50C
0x18001b4e4  mov     rax, [rbx]
0x18001b4e7  mov     rcx, rbx
0x18001b4ea  mov     rax, [rax]
0x18001b4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4f2  mov     eax, esi
0x18001b4f4  lock xadd [rbx+0Ch], eax
0x18001b4f9  add     eax, esi
0x18001b4fb  jnz     short loc_18001B50C
0x18001b4fd  mov     rax, [rbx]
0x18001b500  mov     rcx, rbx
0x18001b503  mov     rax, [rax+8]
0x18001b507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b50c  mov     rcx, [rdi+60h]; this
0x18001b510  call    ?Initialize@ExpIdSubscription@Signals@UsageAndQualityInsights@@QEAAXXZ; UsageAndQualityInsights::Signals::ExpIdSubscription::Initialize(void)
0x18001b515  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59301394@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59301394@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59301394> `wil::Feature<__WilFeatureTraits_Feature_59301394>::GetImpl(void)'::`2'::impl
0x18001b51c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59301394@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59301394>::__private_IsEnabled(void)
0x18001b521  test    al, al
0x18001b523  jz      loc_18001B7B4
0x18001b529  lea     rcx, aStartingBackgr; "Starting Background Maintenance Tasks"
0x18001b530  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x18001b535  xor     r8d, r8d; pcbe
0x18001b538  mov     rdx, rdi; pv
0x18001b53b  lea     rcx, ?TimerCallback@UQIService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b542  call    cs:__imp_CreateThreadpoolTimer
0x18001b548  mov     r15, rax
0x18001b54b  mov     r14, [rdi+70h]
0x18001b54f  test    r14, r14
0x18001b552  jz      short loc_18001B58A
0x18001b554  call    cs:__imp_GetLastError
0x18001b55a  mov     ebx, eax
0x18001b55c  xor     r9d, r9d; msWindowLength
0x18001b55f  xor     r8d, r8d; msPeriod
0x18001b562  xor     edx, edx; pftDueTime
0x18001b564  mov     rcx, r14; pti
0x18001b567  call    cs:__imp_SetThreadpoolTimer
0x18001b56d  mov     edx, r13d; fCancelPendingCallbacks
0x18001b570  mov     rcx, r14; pti
0x18001b573  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b579  mov     rcx, r14; pti
0x18001b57c  call    cs:__imp_CloseThreadpoolTimer
0x18001b582  mov     ecx, ebx; dwErrCode
0x18001b584  call    cs:__imp_SetLastError
0x18001b58a  mov     [rdi+70h], r15
0x18001b58e  mov     rcx, [rsp+0E8h]; this
0x18001b596  test    r15, r15
0x18001b599  jz      loc_18001B862
0x18001b59f  mov     r13, cs:Feature_59301394__descriptor
0x18001b5a6  mov     rax, [r13+0]
0x18001b5aa  mov     [rsp+0E8h+var_B8], rax
0x18001b5af  mov     r15d, eax
0x18001b5b2  and     eax, 0Ch
0x18001b5b5  cmp     al, 0Ch
0x18001b5b7  jz      loc_18001B835
0x18001b5bd  mov     [rsp+0E8h+arg_18], r12d
0x18001b5c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b5ca  mov     [rsp+0E8h+var_B0], eax
0x18001b5ce  mov     dword ptr [rsp+0E8h+arg_8], r12d
0x18001b5d6  mov     dword ptr [rsp+0E8h+arg_10], r12d
0x18001b5de  mov     rax, cs:g_wil_details_internalGetFeatureVariant
0x18001b5e5  test    rax, rax
0x18001b5e8  jz      short loc_18001B61A
0x18001b5ea  lea     rcx, [rsp+0E8h+arg_18]
0x18001b5f2  mov     qword ptr [rsp+0E8h+var_C8], rcx
0x18001b5f7  lea     r9, [rsp+0E8h+arg_8]
0x18001b5ff  lea     r8, [rsp+0E8h+arg_10]
0x18001b607  mov     edx, 1
0x18001b60c  mov     ecx, 388DE12h
0x18001b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b616  mov     ebx, eax
0x18001b618  jmp     short loc_18001B654
0x18001b61a  mov     rax, cs:g_wil_details_apiGetFeatureVariant
0x18001b621  test    rax, rax
0x18001b624  jz      short loc_18001B65F
0x18001b626  lea     rcx, [rsp+0E8h+arg_18]
0x18001b62e  mov     qword ptr [rsp+0E8h+var_C8], rcx
0x18001b633  lea     r9, [rsp+0E8h+arg_8]
0x18001b63b  lea     r8, [rsp+0E8h+arg_10]
0x18001b643  mov     edx, 1
0x18001b648  mov     ecx, 388DE12h
0x18001b64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b652  mov     ebx, eax
0x18001b654  bt      ebx, 8
0x18001b658  jnb     short loc_18001B662
0x18001b65a  mov     r12b, 1
0x18001b65d  jmp     short loc_18001B662
0x18001b65f  mov     ebx, r12d
0x18001b662  mov     eax, dword ptr [rsp+0E8h+arg_8]
0x18001b669  neg     eax
0x18001b66b  sbb     edx, edx
0x18001b66d  and     edx, 400h
0x18001b673  mov     r14d, ebx
0x18001b676  and     r14d, 80h
0x18001b67d  shl     r14d, 4
0x18001b681  or      r14d, edx
0x18001b684  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights> `wil::Feature<__WilFeatureTraits_Feature_UsageAndQualityInsights>::GetImpl(void)'::`2'::impl
0x18001b68b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UsageAndQualityInsights@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UsageAndQualityInsights>::__private_IsEnabled(wil::ReportingKind)
0x18001b690  test    al, al
0x18001b692  jz      short loc_18001B6BF
0x18001b694  and     ebx, 0FFFFFE7Fh
0x18001b69a  jnz     short loc_18001B6A3
0x18001b69c  bts     r14d, 0Ch
0x18001b6a1  jmp     short loc_18001B6BF
0x18001b6a3  shl     ebx, 0Ch
0x18001b6a6  xor     ebx, r14d
0x18001b6a9  and     ebx, 3F000h
0x18001b6af  xor     r14d, ebx
0x18001b6b2  test    r12b, r12b
0x18001b6b5  mov     r8d, dword ptr [rsp+0E8h+arg_10]
0x18001b6bd  jnz     short loc_18001B6C5
0x18001b6bf  mov     r8d, 0Fh
0x18001b6c5  mov     r10d, dword ptr [rsp+0E8h+var_B8+4]
0x18001b6ca  mov     r11d, r15d
0x18001b6cd  mov     r9d, r15d
0x18001b6d0  mov     dword ptr [rsp+0E8h+var_B8], r15d
  ... truncated ...
```
