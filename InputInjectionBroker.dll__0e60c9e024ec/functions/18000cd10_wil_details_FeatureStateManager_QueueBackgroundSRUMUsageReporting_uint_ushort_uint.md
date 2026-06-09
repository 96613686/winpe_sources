# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000cd10`
- end: `0x18000ce99`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e610`

## callees

- `0x18000cd10`
- `0x18000ea2c`
- `0x180011460`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000cdbe`
- `msvcrt!memcpy_s` at `0x18000cdbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ce78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ce22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ce22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ce2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ce2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce66`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
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
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x18000cd10  push    rbx
0x18000cd12  push    rbp
0x18000cd13  push    rsi
0x18000cd14  push    rdi
0x18000cd15  push    r14
0x18000cd17  push    r15
0x18000cd19  sub     rsp, 48h
0x18000cd1d  mov     rax, cs:__security_cookie
0x18000cd24  xor     rax, rsp
0x18000cd27  mov     [rsp+78h+var_40], rax
0x18000cd2c  mov     r14d, r9d
0x18000cd2f  movzx   ebp, r8w
0x18000cd33  mov     ebx, edx
0x18000cd35  mov     rdi, rcx
0x18000cd38  cmp     byte ptr [rcx], 0
0x18000cd3b  jz      loc_18000CE7F
0x18000cd41  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000cd48  jnz     loc_18000CE7F
0x18000cd4e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000cd55  test    rax, rax
0x18000cd58  jz      short loc_18000CD67
0x18000cd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5f  test    al, al
0x18000cd61  jnz     loc_18000CE7F
0x18000cd67  lea     rsi, [rdi+28h]
0x18000cd6b  mov     rcx, rsi; SRWLock
0x18000cd6e  call    cs:__imp_AcquireSRWLockExclusive
0x18000cd74  xor     eax, eax
0x18000cd76  mov     [rsp+78h+var_4A], ax
0x18000cd7b  mov     [rsp+78h+Source], ebx
0x18000cd7f  mov     [rsp+78h+var_4C], bp
0x18000cd84  mov     [rsp+78h+var_48], r14d
0x18000cd89  lea     rbx, [rdi+0E8h]
0x18000cd90  lea     ebp, [rax+0Ch]
0x18000cd93  mov     edx, ebp; unsigned __int64
0x18000cd95  mov     rcx, rbx; this
0x18000cd98  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cd9d  test    al, al
0x18000cd9f  jz      short loc_18000CDC8
0x18000cda1  mov     rcx, [rbx+8]; Destination
0x18000cda5  mov     rax, [rbx+10h]
0x18000cda9  sub     rax, rcx
0x18000cdac  cmp     rcx, [rbx+10h]
0x18000cdb0  sbb     rdx, rdx
0x18000cdb3  and     rdx, rax; DestinationSize
0x18000cdb6  mov     r9d, ebp; SourceSize
0x18000cdb9  lea     r8, [rsp+78h+Source]; Source
0x18000cdbe  call    cs:__imp_memcpy_s
0x18000cdc4  add     [rbx+8], rbp
0x18000cdc8  cmp     byte ptr [rdi+40h], 0
0x18000cdcc  jnz     loc_18000CE70
0x18000cdd2  cmp     qword ptr [rdi+38h], 0
0x18000cdd7  jnz     short loc_18000CE46
0x18000cdd9  call    cs:__imp_GetLastError
0x18000cddf  mov     r14d, eax
0x18000cde2  xor     r8d, r8d; pcbe
0x18000cde5  mov     rdx, rdi; pv
0x18000cde8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cdef  call    cs:__imp_CreateThreadpoolTimer
0x18000cdf5  mov     r15, rax
0x18000cdf8  mov     rbp, [rdi+38h]
0x18000cdfc  test    rbp, rbp
0x18000cdff  jz      short loc_18000CE39
0x18000ce01  call    cs:__imp_GetLastError
0x18000ce07  mov     ebx, eax
0x18000ce09  xor     r9d, r9d; msWindowLength
0x18000ce0c  xor     r8d, r8d; msPeriod
0x18000ce0f  xor     edx, edx; pftDueTime
0x18000ce11  mov     rcx, rbp; pti
0x18000ce14  call    cs:__imp_SetThreadpoolTimer
0x18000ce1a  mov     edx, 1; fCancelPendingCallbacks
0x18000ce1f  mov     rcx, rbp; pti
0x18000ce22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ce28  mov     rcx, rbp; pti
0x18000ce2b  call    cs:__imp_CloseThreadpoolTimer
0x18000ce31  mov     ecx, ebx; dwErrCode
0x18000ce33  call    cs:__imp_SetLastError
0x18000ce39  mov     [rdi+38h], r15
0x18000ce3d  mov     ecx, r14d; dwErrCode
0x18000ce40  call    cs:__imp_SetLastError
0x18000ce46  mov     rcx, [rdi+38h]; pti
0x18000ce4a  test    rcx, rcx
0x18000ce4d  jz      short loc_18000CE70
0x18000ce4f  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ce58  mov     r9d, 4E2h; msWindowLength
0x18000ce5e  xor     r8d, r8d; msPeriod
0x18000ce61  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000ce66  call    cs:__imp_SetThreadpoolTimer
0x18000ce6c  mov     byte ptr [rdi+40h], 1
0x18000ce70  test    rsi, rsi
0x18000ce73  jz      short loc_18000CE7F
0x18000ce75  mov     rcx, rsi; SRWLock
0x18000ce78  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ce7e  nop
0x18000ce7f  mov     rcx, [rsp+78h+var_40]
0x18000ce84  xor     rcx, rsp; StackCookie
0x18000ce87  call    __security_check_cookie
0x18000ce8c  add     rsp, 48h
0x18000ce90  pop     r15
0x18000ce92  pop     r14
0x18000ce94  pop     rdi
0x18000ce95  pop     rsi
0x18000ce96  pop     rbp
0x18000ce97  pop     rbx
0x18000ce98  retn
```
