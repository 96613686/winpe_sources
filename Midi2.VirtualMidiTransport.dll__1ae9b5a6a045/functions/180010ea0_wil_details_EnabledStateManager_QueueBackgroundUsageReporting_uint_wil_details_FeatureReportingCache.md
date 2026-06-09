# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180010ea0`
- end: `0x180011009`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001133c`

## callees

- `0x180010ea0`
- `0x180011ec4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010eec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010eec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010faa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010faa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010fb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010f99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010f66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010f66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010fe3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010fe3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010fa2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010fa2`

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
0x180010ea0  push    rbx
0x180010ea2  push    rbp
0x180010ea3  push    rsi
0x180010ea4  push    rdi
0x180010ea5  push    r14
0x180010ea7  push    r15
0x180010ea9  sub     rsp, 38h
0x180010ead  mov     rbx, r8
0x180010eb0  mov     ebp, edx
0x180010eb2  mov     rdi, rcx
0x180010eb5  mov     eax, [rcx]
0x180010eb7  test    eax, eax
0x180010eb9  jz      loc_180010FFC
0x180010ebf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010ec6  jnz     loc_180010FFC
0x180010ecc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010ed3  test    rax, rax
0x180010ed6  jz      short loc_180010EE5
0x180010ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010edd  test    al, al
0x180010edf  jnz     loc_180010FFC
0x180010ee5  lea     rsi, [rdi+8]
0x180010ee9  mov     rcx, rsi; SRWLock
0x180010eec  call    cs:__imp_AcquireSRWLockExclusive
0x180010ef2  mov     eax, [rdi]
0x180010ef4  test    eax, eax
0x180010ef6  jz      loc_180010FED
0x180010efc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010f03  jnz     loc_180010FED
0x180010f09  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010f10  test    rax, rax
0x180010f13  jz      short loc_180010F22
0x180010f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f1a  test    al, al
0x180010f1c  jnz     loc_180010FED
0x180010f22  mov     [rsp+68h+var_48], ebp
0x180010f26  xor     eax, eax
0x180010f28  mov     [rsp+68h+var_44], eax
0x180010f2c  mov     [rsp+68h+var_40], rbx
0x180010f31  lea     rcx, [rdi+20h]; this
0x180010f35  lea     rdx, [rsp+68h+var_48]; void *
0x180010f3a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010f3f  cmp     byte ptr [rdi+18h], 0
0x180010f43  jnz     loc_180010FED
0x180010f49  cmp     qword ptr [rdi+10h], 0
0x180010f4e  jnz     short loc_180010FBD
0x180010f50  call    cs:__imp_GetLastError
0x180010f56  mov     r14d, eax
0x180010f59  xor     r8d, r8d; pcbe
0x180010f5c  mov     rdx, rdi; pv
0x180010f5f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010f66  call    cs:__imp_CreateThreadpoolTimer
0x180010f6c  mov     r15, rax
0x180010f6f  mov     rbp, [rdi+10h]
0x180010f73  test    rbp, rbp
0x180010f76  jz      short loc_180010FB0
0x180010f78  call    cs:__imp_GetLastError
0x180010f7e  mov     ebx, eax
0x180010f80  xor     r9d, r9d; msWindowLength
0x180010f83  xor     r8d, r8d; msPeriod
0x180010f86  xor     edx, edx; pftDueTime
0x180010f88  mov     rcx, rbp; pti
0x180010f8b  call    cs:__imp_SetThreadpoolTimer
0x180010f91  mov     edx, 1; fCancelPendingCallbacks
0x180010f96  mov     rcx, rbp; pti
0x180010f99  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010f9f  mov     rcx, rbp; pti
0x180010fa2  call    cs:__imp_CloseThreadpoolTimer
0x180010fa8  mov     ecx, ebx; dwErrCode
0x180010faa  call    cs:__imp_SetLastError
0x180010fb0  mov     [rdi+10h], r15
0x180010fb4  mov     ecx, r14d; dwErrCode
0x180010fb7  call    cs:__imp_SetLastError
0x180010fbd  mov     rcx, [rdi+10h]; pti
0x180010fc1  test    rcx, rcx
0x180010fc4  jz      short loc_180010FED
0x180010fc6  mov     rax, 0FFFFFFFF4D2FA200h
0x180010fd0  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180010fd5  mov     r9d, 124F8h; msWindowLength
0x180010fdb  xor     r8d, r8d; msPeriod
0x180010fde  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180010fe3  call    cs:__imp_SetThreadpoolTimer
0x180010fe9  mov     byte ptr [rdi+18h], 1
0x180010fed  test    rsi, rsi
0x180010ff0  jz      short loc_180010FFC
0x180010ff2  mov     rcx, rsi; SRWLock
0x180010ff5  call    cs:__imp_ReleaseSRWLockExclusive
0x180010ffb  nop
0x180010ffc  add     rsp, 38h
0x180011000  pop     r15
0x180011002  pop     r14
0x180011004  pop     rdi
0x180011005  pop     rsi
0x180011006  pop     rbp
0x180011007  pop     rbx
0x180011008  retn
```
