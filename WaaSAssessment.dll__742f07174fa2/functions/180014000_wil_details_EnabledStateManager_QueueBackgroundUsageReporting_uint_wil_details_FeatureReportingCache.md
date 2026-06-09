# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014000`
- end: `0x180014194`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015674`

## callees

- `0x180014000`
- `0x1800162c4`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800140c0`
- `msvcrt!memcpy_s` at `0x1800140c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014180`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014180`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001404c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001404c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014142`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014103`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014124`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014124`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001412d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001412d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800140f1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800140f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014116`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001416e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014116`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001416e`

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
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
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
      Source[0] = a2;
      Source[1] = 0;
      v12 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
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
0x180014000  push    rbx
0x180014002  push    rbp
0x180014003  push    rsi
0x180014004  push    rdi
0x180014005  push    r14
0x180014007  push    r15
0x180014009  sub     rsp, 38h
0x18001400d  mov     rbx, r8
0x180014010  mov     ebp, edx
0x180014012  mov     rdi, rcx
0x180014015  mov     eax, [rcx]
0x180014017  test    eax, eax
0x180014019  jz      loc_180014187
0x18001401f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014026  jnz     loc_180014187
0x18001402c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014033  test    rax, rax
0x180014036  jz      short loc_180014045
0x180014038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001403d  test    al, al
0x18001403f  jnz     loc_180014187
0x180014045  lea     rsi, [rdi+8]
0x180014049  mov     rcx, rsi; SRWLock
0x18001404c  call    cs:__imp_AcquireSRWLockExclusive
0x180014052  mov     eax, [rdi]
0x180014054  test    eax, eax
0x180014056  jz      loc_180014178
0x18001405c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014063  jnz     loc_180014178
0x180014069  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014070  test    rax, rax
0x180014073  jz      short loc_180014082
0x180014075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001407a  test    al, al
0x18001407c  jnz     loc_180014178
0x180014082  mov     [rsp+68h+Source], ebp
0x180014086  xor     eax, eax
0x180014088  mov     [rsp+68h+var_44], eax
0x18001408c  mov     [rsp+68h+var_40], rbx
0x180014091  lea     ebp, [rax+10h]
0x180014094  mov     edx, ebp; unsigned __int64
0x180014096  lea     rcx, [rdi+20h]; this
0x18001409a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001409f  test    al, al
0x1800140a1  jz      short loc_1800140CA
0x1800140a3  mov     rcx, [rdi+28h]; Destination
0x1800140a7  mov     rax, [rdi+30h]
0x1800140ab  sub     rax, rcx
0x1800140ae  cmp     rcx, [rdi+30h]
0x1800140b2  sbb     rdx, rdx
0x1800140b5  and     rdx, rax; DestinationSize
0x1800140b8  mov     r9d, ebp; SourceSize
0x1800140bb  lea     r8, [rsp+68h+Source]; Source
0x1800140c0  call    cs:__imp_memcpy_s
0x1800140c6  add     [rdi+28h], rbp
0x1800140ca  cmp     byte ptr [rdi+18h], 0
0x1800140ce  jnz     loc_180014178
0x1800140d4  cmp     qword ptr [rdi+10h], 0
0x1800140d9  jnz     short loc_180014148
0x1800140db  call    cs:__imp_GetLastError
0x1800140e1  mov     r14d, eax
0x1800140e4  xor     r8d, r8d; pcbe
0x1800140e7  mov     rdx, rdi; pv
0x1800140ea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800140f1  call    cs:__imp_CreateThreadpoolTimer
0x1800140f7  mov     r15, rax
0x1800140fa  mov     rbp, [rdi+10h]
0x1800140fe  test    rbp, rbp
0x180014101  jz      short loc_18001413B
0x180014103  call    cs:__imp_GetLastError
0x180014109  mov     ebx, eax
0x18001410b  xor     r9d, r9d; msWindowLength
0x18001410e  xor     r8d, r8d; msPeriod
0x180014111  xor     edx, edx; pftDueTime
0x180014113  mov     rcx, rbp; pti
0x180014116  call    cs:__imp_SetThreadpoolTimer
0x18001411c  mov     edx, 1; fCancelPendingCallbacks
0x180014121  mov     rcx, rbp; pti
0x180014124  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001412a  mov     rcx, rbp; pti
0x18001412d  call    cs:__imp_CloseThreadpoolTimer
0x180014133  mov     ecx, ebx; dwErrCode
0x180014135  call    cs:__imp_SetLastError
0x18001413b  mov     [rdi+10h], r15
0x18001413f  mov     ecx, r14d; dwErrCode
0x180014142  call    cs:__imp_SetLastError
0x180014148  mov     rcx, [rdi+10h]; pti
0x18001414c  test    rcx, rcx
0x18001414f  jz      short loc_180014178
0x180014151  mov     rax, 0FFFFFFFF4D2FA200h
0x18001415b  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180014160  mov     r9d, 124F8h; msWindowLength
0x180014166  xor     r8d, r8d; msPeriod
0x180014169  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001416e  call    cs:__imp_SetThreadpoolTimer
0x180014174  mov     byte ptr [rdi+18h], 1
0x180014178  test    rsi, rsi
0x18001417b  jz      short loc_180014187
0x18001417d  mov     rcx, rsi; SRWLock
0x180014180  call    cs:__imp_ReleaseSRWLockExclusive
0x180014186  nop
0x180014187  add     rsp, 38h
0x18001418b  pop     r15
0x18001418d  pop     r14
0x18001418f  pop     rdi
0x180014190  pop     rsi
0x180014191  pop     rbp
0x180014192  pop     rbx
0x180014193  retn
```
