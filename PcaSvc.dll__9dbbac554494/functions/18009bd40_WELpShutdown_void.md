# WELpShutdown(void)

- ea: `0x18009bd40`
- end: `0x18009bea4`
- name: `?WELpShutdown@@YAXXZ`
- size: `356`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009bc80`

## callees

- `0x1800010e8`
- `0x180012920`
- `0x18009bd40`
- `0x18009c2fc`
- `0x18009c730`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bd92`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bdaf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bdcc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bde9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009be16`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bd92`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bdaf`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bdcc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009bde9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18009be16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009be9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bd4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bd4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009be4d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009be4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18009be5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18009be5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009be3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009be3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009bd5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009bd5e`

## pseudocode

```c
void WELpShutdown(void)
{
  PTP_TIMER v0; // rcx
  DWORD CurrentProcessId; // [rsp+20h] [rbp-18h]

  EnterCriticalSection(&g_WELpLock);
  if ( g_WELpInitialized )
  {
    CurrentProcessId = GetCurrentProcessId();
    AslLogCallPrintf(
      3,
      (unsigned int)"WELpShutdown",
      690,
      (unsigned int)"WEL: Uninitializing WNF listener %d",
      CurrentProcessId);
    if ( WELpWnfBlockedAppSubscription )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      WELpWnfBlockedAppSubscription = 0;
    }
    if ( WELpWnfPplBlockSubscription )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      WELpWnfPplBlockSubscription = 0;
    }
    if ( WELpWnfBlockedDriverSubscription )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      WELpWnfBlockedDriverSubscription = 0;
    }
    if ( WELpWnfCiImageIncompatibleSubscription )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      WELpWnfCiImageIncompatibleSubscription = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::GetImpl'::`2'::impl) )
    {
      if ( WELpWnfCiBlockedDriverWhqlOnlySubscription )
      {
        RtlUnsubscribeWnfNotificationWaitForCompletion();
        WELpWnfCiBlockedDriverWhqlOnlySubscription = 0;
      }
      v0 = qword_180159928;
      if ( qword_180159928 )
      {
        SetThreadpoolTimer(qword_180159928, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(qword_180159928, 1);
        CloseThreadpoolTimer(qword_180159928);
        qword_180159928 = 0;
      }
      if ( qword_180159788 )
        std::unique_ptr<std::map<std::wstring,unsigned __int64>>::reset(v0, 0);
    }
    TraceLoggingUnregister_EventUnregister(&dword_180155A90);
    g_WELpInitialized = 0;
  }
  LeaveCriticalSection(&g_WELpLock);
}

```

## disassembly

```asm
0x18009bd40  sub     rsp, 38h
0x18009bd44  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009bd4b  call    cs:__imp_EnterCriticalSection
0x18009bd51  cmp     cs:?g_WELpInitialized@@3HA, 0; int g_WELpInitialized
0x18009bd58  jz      loc_18009BE92
0x18009bd5e  call    cs:__imp_GetCurrentProcessId
0x18009bd64  lea     r9, aWelUninitializ; "WEL: Uninitializing WNF listener %d"
0x18009bd6b  mov     r8d, 2B2h
0x18009bd71  lea     rdx, aWelpshutdown; "WELpShutdown"
0x18009bd78  mov     [rsp+38h+var_18], eax
0x18009bd7c  mov     ecx, 3
0x18009bd81  call    AslLogCallPrintf
0x18009bd86  mov     rcx, cs:?WELpWnfBlockedAppSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedAppSubscription
0x18009bd8d  test    rcx, rcx
0x18009bd90  jz      short loc_18009BDA3
0x18009bd92  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18009bd98  mov     cs:?WELpWnfBlockedAppSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedAppSubscription
0x18009bda3  mov     rcx, cs:?WELpWnfPplBlockSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfPplBlockSubscription
0x18009bdaa  test    rcx, rcx
0x18009bdad  jz      short loc_18009BDC0
0x18009bdaf  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18009bdb5  mov     cs:?WELpWnfPplBlockSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * WELpWnfPplBlockSubscription
0x18009bdc0  mov     rcx, cs:?WELpWnfBlockedDriverSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedDriverSubscription
0x18009bdc7  test    rcx, rcx
0x18009bdca  jz      short loc_18009BDDD
0x18009bdcc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18009bdd2  mov     cs:?WELpWnfBlockedDriverSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * WELpWnfBlockedDriverSubscription
0x18009bddd  mov     rcx, cs:?WELpWnfCiImageIncompatibleSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfCiImageIncompatibleSubscription
0x18009bde4  test    rcx, rcx
0x18009bde7  jz      short loc_18009BDFA
0x18009bde9  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18009bdef  mov     cs:?WELpWnfCiImageIncompatibleSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * WELpWnfCiImageIncompatibleSubscription
0x18009bdfa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::GetImpl(void)'::`2'::impl
0x18009be01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WhqlOnlyAllowBlockToasts>::__private_IsEnabled(void)
0x18009be06  test    al, al
0x18009be08  jz      short loc_18009BE7C
0x18009be0a  mov     rcx, cs:?WELpWnfCiBlockedDriverWhqlOnlySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * WELpWnfCiBlockedDriverWhqlOnlySubscription
0x18009be11  test    rcx, rcx
0x18009be14  jz      short loc_18009BE27
0x18009be16  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18009be1c  mov     cs:?WELpWnfCiBlockedDriverWhqlOnlySubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * WELpWnfCiBlockedDriverWhqlOnlySubscription
0x18009be27  mov     rcx, cs:qword_180159928; pti
0x18009be2e  test    rcx, rcx
0x18009be31  jz      short loc_18009BE6B
0x18009be33  xor     r9d, r9d; msWindowLength
0x18009be36  xor     r8d, r8d; msPeriod
0x18009be39  xor     edx, edx; pftDueTime
0x18009be3b  call    cs:__imp_SetThreadpoolTimer
0x18009be41  mov     rcx, cs:qword_180159928; pti
0x18009be48  mov     edx, 1; fCancelPendingCallbacks
0x18009be4d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18009be53  mov     rcx, cs:qword_180159928; pti
0x18009be5a  call    cs:__imp_CloseThreadpoolTimer
0x18009be60  mov     cs:qword_180159928, 0
0x18009be6b  cmp     cs:qword_180159788, 0
0x18009be73  jz      short loc_18009BE7C
0x18009be75  xor     edx, edx
0x18009be77  call    ?reset@?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@@2@@std@@QEAAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@Z; std::unique_ptr<std::map<std::wstring,unsigned __int64>>::reset(std::map<std::wstring,unsigned __int64> *)
0x18009be7c  lea     rcx, dword_180155A90
0x18009be83  call    TraceLoggingUnregister_EventUnregister
0x18009be88  mov     cs:?g_WELpInitialized@@3HA, 0; int g_WELpInitialized
0x18009be92  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_WELpLock
0x18009be99  add     rsp, 38h
0x18009be9d  jmp     cs:__imp_LeaveCriticalSection
```
