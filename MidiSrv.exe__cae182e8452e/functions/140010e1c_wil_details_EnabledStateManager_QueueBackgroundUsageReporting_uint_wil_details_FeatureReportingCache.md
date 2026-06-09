# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140010e1c`
- end: `0x140010f85`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011210`

## callees

- `0x14000c89c`
- `0x140010e1c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010e68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010e68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010f71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ef4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010ee2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010ee2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010f1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010f1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010f5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010f5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010f15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010f15`

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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x140010e1c  push    rbx
0x140010e1e  push    rbp
0x140010e1f  push    rsi
0x140010e20  push    rdi
0x140010e21  push    r14
0x140010e23  push    r15
0x140010e25  sub     rsp, 38h
0x140010e29  mov     rbx, r8
0x140010e2c  mov     ebp, edx
0x140010e2e  mov     rdi, rcx
0x140010e31  mov     eax, [rcx]
0x140010e33  test    eax, eax
0x140010e35  jz      loc_140010F78
0x140010e3b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010e42  jnz     loc_140010F78
0x140010e48  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010e4f  test    rax, rax
0x140010e52  jz      short loc_140010E61
0x140010e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e59  test    al, al
0x140010e5b  jnz     loc_140010F78
0x140010e61  lea     rsi, [rdi+8]
0x140010e65  mov     rcx, rsi; SRWLock
0x140010e68  call    cs:__imp_AcquireSRWLockExclusive
0x140010e6e  mov     eax, [rdi]
0x140010e70  test    eax, eax
0x140010e72  jz      loc_140010F69
0x140010e78  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010e7f  jnz     loc_140010F69
0x140010e85  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010e8c  test    rax, rax
0x140010e8f  jz      short loc_140010E9E
0x140010e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e96  test    al, al
0x140010e98  jnz     loc_140010F69
0x140010e9e  mov     [rsp+68h+var_48], ebp
0x140010ea2  xor     eax, eax
0x140010ea4  mov     [rsp+68h+var_44], eax
0x140010ea8  mov     [rsp+68h+var_40], rbx
0x140010ead  lea     rcx, [rdi+20h]; this
0x140010eb1  lea     rdx, [rsp+68h+var_48]; void *
0x140010eb6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140010ebb  cmp     byte ptr [rdi+18h], 0
0x140010ebf  jnz     loc_140010F69
0x140010ec5  cmp     qword ptr [rdi+10h], 0
0x140010eca  jnz     short loc_140010F39
0x140010ecc  call    cs:__imp_GetLastError
0x140010ed2  mov     r14d, eax
0x140010ed5  xor     r8d, r8d; pcbe
0x140010ed8  mov     rdx, rdi; pv
0x140010edb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140010ee2  call    cs:__imp_CreateThreadpoolTimer
0x140010ee8  mov     r15, rax
0x140010eeb  mov     rbp, [rdi+10h]
0x140010eef  test    rbp, rbp
0x140010ef2  jz      short loc_140010F2C
0x140010ef4  call    cs:__imp_GetLastError
0x140010efa  mov     ebx, eax
0x140010efc  xor     r9d, r9d; msWindowLength
0x140010eff  xor     r8d, r8d; msPeriod
0x140010f02  xor     edx, edx; pftDueTime
0x140010f04  mov     rcx, rbp; pti
0x140010f07  call    cs:__imp_SetThreadpoolTimer
0x140010f0d  mov     edx, 1; fCancelPendingCallbacks
0x140010f12  mov     rcx, rbp; pti
0x140010f15  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010f1b  mov     rcx, rbp; pti
0x140010f1e  call    cs:__imp_CloseThreadpoolTimer
0x140010f24  mov     ecx, ebx; dwErrCode
0x140010f26  call    cs:__imp_SetLastError
0x140010f2c  mov     [rdi+10h], r15
0x140010f30  mov     ecx, r14d; dwErrCode
0x140010f33  call    cs:__imp_SetLastError
0x140010f39  mov     rcx, [rdi+10h]; pti
0x140010f3d  test    rcx, rcx
0x140010f40  jz      short loc_140010F69
0x140010f42  mov     rax, 0FFFFFFFF4D2FA200h
0x140010f4c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x140010f51  mov     r9d, 124F8h; msWindowLength
0x140010f57  xor     r8d, r8d; msPeriod
0x140010f5a  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140010f5f  call    cs:__imp_SetThreadpoolTimer
0x140010f65  mov     byte ptr [rdi+18h], 1
0x140010f69  test    rsi, rsi
0x140010f6c  jz      short loc_140010F78
0x140010f6e  mov     rcx, rsi; SRWLock
0x140010f71  call    cs:__imp_ReleaseSRWLockExclusive
0x140010f77  nop
0x140010f78  add     rsp, 38h
0x140010f7c  pop     r15
0x140010f7e  pop     r14
0x140010f80  pop     rdi
0x140010f81  pop     rsi
0x140010f82  pop     rbp
0x140010f83  pop     rbx
0x140010f84  retn
```
