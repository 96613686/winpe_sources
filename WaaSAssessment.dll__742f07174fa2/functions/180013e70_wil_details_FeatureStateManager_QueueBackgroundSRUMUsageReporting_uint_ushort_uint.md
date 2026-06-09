# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013e70`
- end: `0x180013ff9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180015df0`

## callees

- `0x180013e70`
- `0x1800162c4`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013f1e`
- `msvcrt!memcpy_s` at `0x180013f1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013fd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013fd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ece`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ece`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013f82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013f82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013f8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013f8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013f4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013f4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013fc6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013fc6`

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
0x180013e70  push    rbx
0x180013e72  push    rbp
0x180013e73  push    rsi
0x180013e74  push    rdi
0x180013e75  push    r14
0x180013e77  push    r15
0x180013e79  sub     rsp, 48h
0x180013e7d  mov     rax, cs:__security_cookie
0x180013e84  xor     rax, rsp
0x180013e87  mov     [rsp+78h+var_40], rax
0x180013e8c  mov     r14d, r9d
0x180013e8f  movzx   ebp, r8w
0x180013e93  mov     ebx, edx
0x180013e95  mov     rdi, rcx
0x180013e98  cmp     byte ptr [rcx], 0
0x180013e9b  jz      loc_180013FDF
0x180013ea1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180013ea8  jnz     loc_180013FDF
0x180013eae  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180013eb5  test    rax, rax
0x180013eb8  jz      short loc_180013EC7
0x180013eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ebf  test    al, al
0x180013ec1  jnz     loc_180013FDF
0x180013ec7  lea     rsi, [rdi+28h]
0x180013ecb  mov     rcx, rsi; SRWLock
0x180013ece  call    cs:__imp_AcquireSRWLockExclusive
0x180013ed4  xor     eax, eax
0x180013ed6  mov     [rsp+78h+var_4A], ax
0x180013edb  mov     [rsp+78h+Source], ebx
0x180013edf  mov     [rsp+78h+var_4C], bp
0x180013ee4  mov     [rsp+78h+var_48], r14d
0x180013ee9  lea     rbx, [rdi+0E8h]
0x180013ef0  lea     ebp, [rax+0Ch]
0x180013ef3  mov     edx, ebp; unsigned __int64
0x180013ef5  mov     rcx, rbx; this
0x180013ef8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180013efd  test    al, al
0x180013eff  jz      short loc_180013F28
0x180013f01  mov     rcx, [rbx+8]; Destination
0x180013f05  mov     rax, [rbx+10h]
0x180013f09  sub     rax, rcx
0x180013f0c  cmp     rcx, [rbx+10h]
0x180013f10  sbb     rdx, rdx
0x180013f13  and     rdx, rax; DestinationSize
0x180013f16  mov     r9d, ebp; SourceSize
0x180013f19  lea     r8, [rsp+78h+Source]; Source
0x180013f1e  call    cs:__imp_memcpy_s
0x180013f24  add     [rbx+8], rbp
0x180013f28  cmp     byte ptr [rdi+40h], 0
0x180013f2c  jnz     loc_180013FD0
0x180013f32  cmp     qword ptr [rdi+38h], 0
0x180013f37  jnz     short loc_180013FA6
0x180013f39  call    cs:__imp_GetLastError
0x180013f3f  mov     r14d, eax
0x180013f42  xor     r8d, r8d; pcbe
0x180013f45  mov     rdx, rdi; pv
0x180013f48  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013f4f  call    cs:__imp_CreateThreadpoolTimer
0x180013f55  mov     r15, rax
0x180013f58  mov     rbp, [rdi+38h]
0x180013f5c  test    rbp, rbp
0x180013f5f  jz      short loc_180013F99
0x180013f61  call    cs:__imp_GetLastError
0x180013f67  mov     ebx, eax
0x180013f69  xor     r9d, r9d; msWindowLength
0x180013f6c  xor     r8d, r8d; msPeriod
0x180013f6f  xor     edx, edx; pftDueTime
0x180013f71  mov     rcx, rbp; pti
0x180013f74  call    cs:__imp_SetThreadpoolTimer
0x180013f7a  mov     edx, 1; fCancelPendingCallbacks
0x180013f7f  mov     rcx, rbp; pti
0x180013f82  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013f88  mov     rcx, rbp; pti
0x180013f8b  call    cs:__imp_CloseThreadpoolTimer
0x180013f91  mov     ecx, ebx; dwErrCode
0x180013f93  call    cs:__imp_SetLastError
0x180013f99  mov     [rdi+38h], r15
0x180013f9d  mov     ecx, r14d; dwErrCode
0x180013fa0  call    cs:__imp_SetLastError
0x180013fa6  mov     rcx, [rdi+38h]; pti
0x180013faa  test    rcx, rcx
0x180013fad  jz      short loc_180013FD0
0x180013faf  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180013fb8  mov     r9d, 4E2h; msWindowLength
0x180013fbe  xor     r8d, r8d; msPeriod
0x180013fc1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180013fc6  call    cs:__imp_SetThreadpoolTimer
0x180013fcc  mov     byte ptr [rdi+40h], 1
0x180013fd0  test    rsi, rsi
0x180013fd3  jz      short loc_180013FDF
0x180013fd5  mov     rcx, rsi; SRWLock
0x180013fd8  call    cs:__imp_ReleaseSRWLockExclusive
0x180013fde  nop
0x180013fdf  mov     rcx, [rsp+78h+var_40]
0x180013fe4  xor     rcx, rsp; StackCookie
0x180013fe7  call    __security_check_cookie
0x180013fec  add     rsp, 48h
0x180013ff0  pop     r15
0x180013ff2  pop     r14
0x180013ff4  pop     rdi
0x180013ff5  pop     rsi
0x180013ff6  pop     rbp
0x180013ff7  pop     rbx
0x180013ff8  retn
```
