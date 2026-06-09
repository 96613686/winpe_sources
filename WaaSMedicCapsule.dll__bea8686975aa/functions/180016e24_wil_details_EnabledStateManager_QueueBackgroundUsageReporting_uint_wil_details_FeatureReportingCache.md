# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180016e24`
- end: `0x180016f91`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `365`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001763c`

## callees

- `0x180016e24`
- `0x180017ae4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016f7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016f7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016e70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016f32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016f3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016f32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016f3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016eee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180016eee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016f2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016f2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016f13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016f6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016f13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016f6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016f21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016f21`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Src[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
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
      Src[0] = a2;
      Src[1] = 0;
      v12 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Src, 0x10u);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
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
0x180016e24  push    rbx
0x180016e26  push    rbp
0x180016e27  push    rsi
0x180016e28  push    rdi
0x180016e29  push    r14
0x180016e2b  push    r15
0x180016e2d  sub     rsp, 38h
0x180016e31  mov     rbx, r8
0x180016e34  mov     ebp, edx
0x180016e36  mov     rdi, rcx
0x180016e39  mov     eax, [rcx]
0x180016e3b  test    eax, eax
0x180016e3d  jz      loc_180016F84
0x180016e43  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016e4a  jnz     loc_180016F84
0x180016e50  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016e57  test    rax, rax
0x180016e5a  jz      short loc_180016E69
0x180016e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e61  test    al, al
0x180016e63  jnz     loc_180016F84
0x180016e69  lea     rsi, [rdi+8]
0x180016e6d  mov     rcx, rsi; SRWLock
0x180016e70  call    cs:__imp_AcquireSRWLockExclusive
0x180016e76  mov     eax, [rdi]
0x180016e78  test    eax, eax
0x180016e7a  jz      loc_180016F75
0x180016e80  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016e87  jnz     loc_180016F75
0x180016e8d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016e94  test    rax, rax
0x180016e97  jz      short loc_180016EA6
0x180016e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e9e  test    al, al
0x180016ea0  jnz     loc_180016F75
0x180016ea6  mov     [rsp+68h+Src], ebp
0x180016eaa  xor     eax, eax
0x180016eac  mov     [rsp+68h+var_44], eax
0x180016eb0  mov     [rsp+68h+var_40], rbx
0x180016eb5  lea     rcx, [rdi+20h]; this
0x180016eb9  lea     r8d, [rax+10h]; Size
0x180016ebd  lea     rdx, [rsp+68h+Src]; Src
0x180016ec2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016ec7  cmp     byte ptr [rdi+18h], 0
0x180016ecb  jnz     loc_180016F75
0x180016ed1  cmp     qword ptr [rdi+10h], 0
0x180016ed6  jnz     short loc_180016F45
0x180016ed8  call    cs:__imp_GetLastError
0x180016ede  mov     r14d, eax
0x180016ee1  xor     r8d, r8d; pcbe
0x180016ee4  mov     rdx, rdi; pv
0x180016ee7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016eee  call    cs:__imp_CreateThreadpoolTimer
0x180016ef4  mov     r15, rax
0x180016ef7  mov     rbp, [rdi+10h]
0x180016efb  test    rbp, rbp
0x180016efe  jz      short loc_180016F38
0x180016f00  call    cs:__imp_GetLastError
0x180016f06  mov     ebx, eax
0x180016f08  xor     r9d, r9d; msWindowLength
0x180016f0b  xor     r8d, r8d; msPeriod
0x180016f0e  xor     edx, edx; pftDueTime
0x180016f10  mov     rcx, rbp; pti
0x180016f13  call    cs:__imp_SetThreadpoolTimer
0x180016f19  mov     edx, 1; fCancelPendingCallbacks
0x180016f1e  mov     rcx, rbp; pti
0x180016f21  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016f27  mov     rcx, rbp; pti
0x180016f2a  call    cs:__imp_CloseThreadpoolTimer
0x180016f30  mov     ecx, ebx; dwErrCode
0x180016f32  call    cs:__imp_SetLastError
0x180016f38  mov     [rdi+10h], r15
0x180016f3c  mov     ecx, r14d; dwErrCode
0x180016f3f  call    cs:__imp_SetLastError
0x180016f45  mov     rcx, [rdi+10h]; pti
0x180016f49  test    rcx, rcx
0x180016f4c  jz      short loc_180016F75
0x180016f4e  mov     rax, 0FFFFFFFF4D2FA200h
0x180016f58  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180016f5d  mov     r9d, 124F8h; msWindowLength
0x180016f63  xor     r8d, r8d; msPeriod
0x180016f66  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180016f6b  call    cs:__imp_SetThreadpoolTimer
0x180016f71  mov     byte ptr [rdi+18h], 1
0x180016f75  test    rsi, rsi
0x180016f78  jz      short loc_180016F84
0x180016f7a  mov     rcx, rsi; SRWLock
0x180016f7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180016f83  nop
0x180016f84  add     rsp, 38h
0x180016f88  pop     r15
0x180016f8a  pop     r14
0x180016f8c  pop     rdi
0x180016f8d  pop     rsi
0x180016f8e  pop     rbp
0x180016f8f  pop     rbx
0x180016f90  retn
```
