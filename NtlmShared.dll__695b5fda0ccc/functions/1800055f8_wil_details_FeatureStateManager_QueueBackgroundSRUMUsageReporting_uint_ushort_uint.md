# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800055f8`
- end: `0x180005780`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007710`

## callees

- `0x1800055f8`
- `0x180007cdc`
- `0x18000c560`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800056a6`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x1800056a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005760`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005760`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005656`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000571b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000571b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005728`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000574e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000574e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800056d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800056d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000570a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000570a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005713`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005713`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x1800055f8  push    rbx
0x1800055fa  push    rbp
0x1800055fb  push    rsi
0x1800055fc  push    rdi
0x1800055fd  push    r14
0x1800055ff  push    r15
0x180005601  sub     rsp, 48h
0x180005605  mov     rax, cs:__security_cookie
0x18000560c  xor     rax, rsp
0x18000560f  mov     [rsp+78h+var_40], rax
0x180005614  cmp     byte ptr [rcx], 0
0x180005617  mov     r14d, r9d
0x18000561a  movzx   ebp, r8w
0x18000561e  mov     ebx, edx
0x180005620  mov     rdi, rcx
0x180005623  jz      loc_180005766
0x180005629  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005630  jnz     loc_180005766
0x180005636  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000563d  test    rax, rax
0x180005640  jz      short loc_18000564F
0x180005642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005647  test    al, al
0x180005649  jnz     loc_180005766
0x18000564f  lea     rsi, [rdi+28h]
0x180005653  mov     rcx, rsi; SRWLock
0x180005656  call    cs:__imp_AcquireSRWLockExclusive
0x18000565c  xor     eax, eax
0x18000565e  mov     [rsp+78h+Source], ebx
0x180005662  mov     [rsp+78h+var_4C], bp
0x180005667  lea     rbx, [rdi+0E8h]
0x18000566e  mov     rcx, rbx; this
0x180005671  mov     [rsp+78h+var_4A], ax
0x180005676  mov     [rsp+78h+var_48], r14d
0x18000567b  lea     ebp, [rax+0Ch]
0x18000567e  mov     edx, ebp; unsigned __int64
0x180005680  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005685  test    al, al
0x180005687  jz      short loc_1800056B0
0x180005689  mov     rcx, [rbx+8]; Destination
0x18000568d  lea     r8, [rsp+78h+Source]; Source
0x180005692  mov     rax, [rbx+10h]
0x180005696  mov     r9d, ebp; SourceSize
0x180005699  sub     rax, rcx
0x18000569c  cmp     rcx, [rbx+10h]
0x1800056a0  sbb     rdx, rdx
0x1800056a3  and     rdx, rax; DestinationSize
0x1800056a6  call    cs:__imp_memcpy_s
0x1800056ac  add     [rbx+8], rbp
0x1800056b0  cmp     byte ptr [rdi+40h], 0
0x1800056b4  jnz     loc_180005758
0x1800056ba  cmp     qword ptr [rdi+38h], 0
0x1800056bf  jnz     short loc_18000572E
0x1800056c1  call    cs:__imp_GetLastError
0x1800056c7  xor     r8d, r8d; pcbe
0x1800056ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800056d1  mov     rdx, rdi; pv
0x1800056d4  mov     r14d, eax
0x1800056d7  call    cs:__imp_CreateThreadpoolTimer
0x1800056dd  mov     rbp, [rdi+38h]
0x1800056e1  mov     r15, rax
0x1800056e4  test    rbp, rbp
0x1800056e7  jz      short loc_180005721
0x1800056e9  call    cs:__imp_GetLastError
0x1800056ef  xor     r9d, r9d; msWindowLength
0x1800056f2  xor     r8d, r8d; msPeriod
0x1800056f5  xor     edx, edx; pftDueTime
0x1800056f7  mov     rcx, rbp; pti
0x1800056fa  mov     ebx, eax
0x1800056fc  call    cs:__imp_SetThreadpoolTimer
0x180005702  mov     edx, 1; fCancelPendingCallbacks
0x180005707  mov     rcx, rbp; pti
0x18000570a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005710  mov     rcx, rbp; pti
0x180005713  call    cs:__imp_CloseThreadpoolTimer
0x180005719  mov     ecx, ebx; dwErrCode
0x18000571b  call    cs:__imp_SetLastError
0x180005721  mov     ecx, r14d; dwErrCode
0x180005724  mov     [rdi+38h], r15
0x180005728  call    cs:__imp_SetLastError
0x18000572e  mov     rcx, [rdi+38h]; pti
0x180005732  test    rcx, rcx
0x180005735  jz      short loc_180005758
0x180005737  mov     r9d, 4E2h; msWindowLength
0x18000573d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005746  xor     r8d, r8d; msPeriod
0x180005749  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000574e  call    cs:__imp_SetThreadpoolTimer
0x180005754  mov     byte ptr [rdi+40h], 1
0x180005758  test    rsi, rsi
0x18000575b  jz      short loc_180005766
0x18000575d  mov     rcx, rsi; SRWLock
0x180005760  call    cs:__imp_ReleaseSRWLockExclusive
0x180005766  mov     rcx, [rsp+78h+var_40]
0x18000576b  xor     rcx, rsp; StackCookie
0x18000576e  call    __security_check_cookie
0x180005773  add     rsp, 48h
0x180005777  pop     r15
0x180005779  pop     r14
0x18000577b  pop     rdi
0x18000577c  pop     rsi
0x18000577d  pop     rbp
0x18000577e  pop     rbx
0x18000577f  retn
```
