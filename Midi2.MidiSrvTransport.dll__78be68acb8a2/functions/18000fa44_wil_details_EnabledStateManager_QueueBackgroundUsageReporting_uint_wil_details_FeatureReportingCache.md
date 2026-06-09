# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000fa44`
- end: `0x18000fbad`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000feec`

## callees

- `0x18000fa44`
- `0x18001162c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fa90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fa90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fb3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fb3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fb46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fb46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fb0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fb0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb87`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  unsigned __int64 v6; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD v12[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      v12[0] = a2;
      v12[1] = 0;
      v13 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v12, v6);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18000fa44  push    rbx
0x18000fa46  push    rbp
0x18000fa47  push    rsi
0x18000fa48  push    rdi
0x18000fa49  push    r14
0x18000fa4b  push    r15
0x18000fa4d  sub     rsp, 38h
0x18000fa51  mov     rbx, r8
0x18000fa54  mov     ebp, edx
0x18000fa56  mov     rdi, rcx
0x18000fa59  mov     eax, [rcx]
0x18000fa5b  test    eax, eax
0x18000fa5d  jz      loc_18000FBA0
0x18000fa63  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fa6a  jnz     loc_18000FBA0
0x18000fa70  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fa77  test    rax, rax
0x18000fa7a  jz      short loc_18000FA89
0x18000fa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa81  test    al, al
0x18000fa83  jnz     loc_18000FBA0
0x18000fa89  lea     rsi, [rdi+8]
0x18000fa8d  mov     rcx, rsi; SRWLock
0x18000fa90  call    cs:__imp_AcquireSRWLockExclusive
0x18000fa96  mov     eax, [rdi]
0x18000fa98  test    eax, eax
0x18000fa9a  jz      loc_18000FB91
0x18000faa0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000faa7  jnz     loc_18000FB91
0x18000faad  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fab4  test    rax, rax
0x18000fab7  jz      short loc_18000FAC6
0x18000fab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fabe  test    al, al
0x18000fac0  jnz     loc_18000FB91
0x18000fac6  mov     [rsp+68h+var_48], ebp
0x18000faca  xor     eax, eax
0x18000facc  mov     [rsp+68h+var_44], eax
0x18000fad0  mov     [rsp+68h+var_40], rbx
0x18000fad5  lea     rcx, [rdi+20h]; this
0x18000fad9  lea     rdx, [rsp+68h+var_48]; void *
0x18000fade  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000fae3  cmp     byte ptr [rdi+18h], 0
0x18000fae7  jnz     loc_18000FB91
0x18000faed  cmp     qword ptr [rdi+10h], 0
0x18000faf2  jnz     short loc_18000FB61
0x18000faf4  call    cs:__imp_GetLastError
0x18000fafa  mov     r14d, eax
0x18000fafd  xor     r8d, r8d; pcbe
0x18000fb00  mov     rdx, rdi; pv
0x18000fb03  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000fb0a  call    cs:__imp_CreateThreadpoolTimer
0x18000fb10  mov     r15, rax
0x18000fb13  mov     rbp, [rdi+10h]
0x18000fb17  test    rbp, rbp
0x18000fb1a  jz      short loc_18000FB54
0x18000fb1c  call    cs:__imp_GetLastError
0x18000fb22  mov     ebx, eax
0x18000fb24  xor     r9d, r9d; msWindowLength
0x18000fb27  xor     r8d, r8d; msPeriod
0x18000fb2a  xor     edx, edx; pftDueTime
0x18000fb2c  mov     rcx, rbp; pti
0x18000fb2f  call    cs:__imp_SetThreadpoolTimer
0x18000fb35  mov     edx, 1; fCancelPendingCallbacks
0x18000fb3a  mov     rcx, rbp; pti
0x18000fb3d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000fb43  mov     rcx, rbp; pti
0x18000fb46  call    cs:__imp_CloseThreadpoolTimer
0x18000fb4c  mov     ecx, ebx; dwErrCode
0x18000fb4e  call    cs:__imp_SetLastError
0x18000fb54  mov     [rdi+10h], r15
0x18000fb58  mov     ecx, r14d; dwErrCode
0x18000fb5b  call    cs:__imp_SetLastError
0x18000fb61  mov     rcx, [rdi+10h]; pti
0x18000fb65  test    rcx, rcx
0x18000fb68  jz      short loc_18000FB91
0x18000fb6a  mov     rax, 0FFFFFFFF4D2FA200h
0x18000fb74  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000fb79  mov     r9d, 124F8h; msWindowLength
0x18000fb7f  xor     r8d, r8d; msPeriod
0x18000fb82  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000fb87  call    cs:__imp_SetThreadpoolTimer
0x18000fb8d  mov     byte ptr [rdi+18h], 1
0x18000fb91  test    rsi, rsi
0x18000fb94  jz      short loc_18000FBA0
0x18000fb96  mov     rcx, rsi; SRWLock
0x18000fb99  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fb9f  nop
0x18000fba0  add     rsp, 38h
0x18000fba4  pop     r15
0x18000fba6  pop     r14
0x18000fba8  pop     rdi
0x18000fba9  pop     rsi
0x18000fbaa  pop     rbp
0x18000fbab  pop     rbx
0x18000fbac  retn
```
