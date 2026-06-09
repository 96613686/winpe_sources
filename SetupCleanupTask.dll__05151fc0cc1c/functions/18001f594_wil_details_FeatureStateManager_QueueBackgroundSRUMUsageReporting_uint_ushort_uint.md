# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001f594`
- end: `0x18001f71c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024040`

## callees

- `0x18001f594`
- `0x18002487c`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001f642`
- `msvcrt!memcpy_s` at `0x18001f642`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f6fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f5f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f5f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f6b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f6b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f685`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f698`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f6ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f698`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f6ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f6a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f6a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f673`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f673`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f6af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f6af`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18001f594  push    rbx
0x18001f596  push    rbp
0x18001f597  push    rsi
0x18001f598  push    rdi
0x18001f599  push    r14
0x18001f59b  push    r15
0x18001f59d  sub     rsp, 48h
0x18001f5a1  mov     rax, cs:__security_cookie
0x18001f5a8  xor     rax, rsp
0x18001f5ab  mov     [rsp+78h+var_40], rax
0x18001f5b0  cmp     byte ptr [rcx], 0
0x18001f5b3  mov     r14d, r9d
0x18001f5b6  movzx   ebp, r8w
0x18001f5ba  mov     ebx, edx
0x18001f5bc  mov     rdi, rcx
0x18001f5bf  jz      loc_18001F702
0x18001f5c5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001f5cc  jnz     loc_18001F702
0x18001f5d2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001f5d9  test    rax, rax
0x18001f5dc  jz      short loc_18001F5EB
0x18001f5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5e3  test    al, al
0x18001f5e5  jnz     loc_18001F702
0x18001f5eb  lea     rsi, [rdi+28h]
0x18001f5ef  mov     rcx, rsi; SRWLock
0x18001f5f2  call    cs:__imp_AcquireSRWLockExclusive
0x18001f5f8  xor     eax, eax
0x18001f5fa  mov     [rsp+78h+Source], ebx
0x18001f5fe  mov     [rsp+78h+var_4C], bp
0x18001f603  lea     rbx, [rdi+0E8h]
0x18001f60a  mov     rcx, rbx; this
0x18001f60d  mov     [rsp+78h+var_4A], ax
0x18001f612  mov     [rsp+78h+var_48], r14d
0x18001f617  lea     ebp, [rax+0Ch]
0x18001f61a  mov     edx, ebp; unsigned __int64
0x18001f61c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001f621  test    al, al
0x18001f623  jz      short loc_18001F64C
0x18001f625  mov     rcx, [rbx+8]; Destination
0x18001f629  lea     r8, [rsp+78h+Source]; Source
0x18001f62e  mov     rax, [rbx+10h]
0x18001f632  mov     r9d, ebp; SourceSize
0x18001f635  sub     rax, rcx
0x18001f638  cmp     rcx, [rbx+10h]
0x18001f63c  sbb     rdx, rdx
0x18001f63f  and     rdx, rax; DestinationSize
0x18001f642  call    cs:__imp_memcpy_s
0x18001f648  add     [rbx+8], rbp
0x18001f64c  cmp     byte ptr [rdi+40h], 0
0x18001f650  jnz     loc_18001F6F4
0x18001f656  cmp     qword ptr [rdi+38h], 0
0x18001f65b  jnz     short loc_18001F6CA
0x18001f65d  call    cs:__imp_GetLastError
0x18001f663  xor     r8d, r8d; pcbe
0x18001f666  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f66d  mov     rdx, rdi; pv
0x18001f670  mov     r14d, eax
0x18001f673  call    cs:__imp_CreateThreadpoolTimer
0x18001f679  mov     rbp, [rdi+38h]
0x18001f67d  mov     r15, rax
0x18001f680  test    rbp, rbp
0x18001f683  jz      short loc_18001F6BD
0x18001f685  call    cs:__imp_GetLastError
0x18001f68b  xor     r9d, r9d; msWindowLength
0x18001f68e  xor     r8d, r8d; msPeriod
0x18001f691  xor     edx, edx; pftDueTime
0x18001f693  mov     rcx, rbp; pti
0x18001f696  mov     ebx, eax
0x18001f698  call    cs:__imp_SetThreadpoolTimer
0x18001f69e  mov     edx, 1; fCancelPendingCallbacks
0x18001f6a3  mov     rcx, rbp; pti
0x18001f6a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f6ac  mov     rcx, rbp; pti
0x18001f6af  call    cs:__imp_CloseThreadpoolTimer
0x18001f6b5  mov     ecx, ebx; dwErrCode
0x18001f6b7  call    cs:__imp_SetLastError
0x18001f6bd  mov     ecx, r14d; dwErrCode
0x18001f6c0  mov     [rdi+38h], r15
0x18001f6c4  call    cs:__imp_SetLastError
0x18001f6ca  mov     rcx, [rdi+38h]; pti
0x18001f6ce  test    rcx, rcx
0x18001f6d1  jz      short loc_18001F6F4
0x18001f6d3  mov     r9d, 4E2h; msWindowLength
0x18001f6d9  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001f6e2  xor     r8d, r8d; msPeriod
0x18001f6e5  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18001f6ea  call    cs:__imp_SetThreadpoolTimer
0x18001f6f0  mov     byte ptr [rdi+40h], 1
0x18001f6f4  test    rsi, rsi
0x18001f6f7  jz      short loc_18001F702
0x18001f6f9  mov     rcx, rsi; SRWLock
0x18001f6fc  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f702  mov     rcx, [rsp+78h+var_40]
0x18001f707  xor     rcx, rsp; StackCookie
0x18001f70a  call    __security_check_cookie
0x18001f70f  add     rsp, 48h
0x18001f713  pop     r15
0x18001f715  pop     r14
0x18001f717  pop     rdi
0x18001f718  pop     rsi
0x18001f719  pop     rbp
0x18001f71a  pop     rbx
0x18001f71b  retn
```
