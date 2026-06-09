# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003a310`
- end: `0x18003a4ab`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003be40`

## callees

- `0x180004912`
- `0x180004998`
- `0x18003a310`
- `0x18003c264`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a3a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a3d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a3a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003a3d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a360`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a497`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a45f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a45f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a40e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a40e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a433`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a485`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a433`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a485`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a441`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a441`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a44a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a44a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18003a310  push    rbx
0x18003a312  push    rbp
0x18003a313  push    rsi
0x18003a314  push    rdi
0x18003a315  push    r14
0x18003a317  push    r15
0x18003a319  sub     rsp, 38h
0x18003a31d  mov     ebp, r9d
0x18003a320  movzx   ebx, r8w
0x18003a324  mov     r14d, edx
0x18003a327  mov     rdi, rcx
0x18003a32a  cmp     byte ptr [rcx], 0
0x18003a32d  jz      loc_18003A49E
0x18003a333  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003a33a  jnz     loc_18003A49E
0x18003a340  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003a347  test    rax, rax
0x18003a34a  jz      short loc_18003A359
0x18003a34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a351  test    al, al
0x18003a353  jnz     loc_18003A49E
0x18003a359  lea     rsi, [rdi+28h]
0x18003a35d  mov     rcx, rsi; SRWLock
0x18003a360  call    cs:__imp_AcquireSRWLockExclusive
0x18003a366  xor     eax, eax
0x18003a368  mov     word ptr [rsp+68h+var_48+6], ax
0x18003a36d  mov     dword ptr [rsp+68h+var_48], r14d
0x18003a372  mov     word ptr [rsp+68h+var_48+4], bx
0x18003a377  lea     rbx, [rdi+0E8h]
0x18003a37e  lea     edx, [rax+0Ch]; unsigned __int64
0x18003a381  mov     rcx, rbx; this
0x18003a384  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18003a389  test    al, al
0x18003a38b  jz      short loc_18003A3E7
0x18003a38d  mov     rcx, [rbx+8]; void *
0x18003a391  mov     rax, [rbx+10h]
0x18003a395  sub     rax, rcx
0x18003a398  cmp     rcx, [rbx+10h]
0x18003a39c  sbb     r8, r8
0x18003a39f  and     r8, rax; Size
0x18003a3a2  test    rcx, rcx
0x18003a3a5  jnz     short loc_18003A3B5
0x18003a3a7  call    cs:__imp__o__errno
0x18003a3ad  mov     dword ptr [rax], 16h
0x18003a3b3  jmp     short loc_18003A3DD
0x18003a3b5  cmp     r8, 0Ch
0x18003a3b9  jb      short loc_18003A3CA
0x18003a3bb  movsd   xmm0, [rsp+68h+var_48]
0x18003a3c1  movsd   qword ptr [rcx], xmm0
0x18003a3c5  mov     [rcx+8], ebp
0x18003a3c8  jmp     short loc_18003A3E2
0x18003a3ca  xor     edx, edx; Val
0x18003a3cc  call    memset_0
0x18003a3d1  call    cs:__imp__o__errno
0x18003a3d7  mov     dword ptr [rax], 22h ; '"'
0x18003a3dd  call    _invalid_parameter_noinfo
0x18003a3e2  add     qword ptr [rbx+8], 0Ch
0x18003a3e7  cmp     byte ptr [rdi+40h], 0
0x18003a3eb  jnz     loc_18003A48F
0x18003a3f1  cmp     qword ptr [rdi+38h], 0
0x18003a3f6  jnz     short loc_18003A465
0x18003a3f8  call    cs:__imp_GetLastError
0x18003a3fe  mov     r14d, eax
0x18003a401  xor     r8d, r8d; pcbe
0x18003a404  mov     rdx, rdi; pv
0x18003a407  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003a40e  call    cs:__imp_CreateThreadpoolTimer
0x18003a414  mov     r15, rax
0x18003a417  mov     rbp, [rdi+38h]
0x18003a41b  test    rbp, rbp
0x18003a41e  jz      short loc_18003A458
0x18003a420  call    cs:__imp_GetLastError
0x18003a426  mov     ebx, eax
0x18003a428  xor     r9d, r9d; msWindowLength
0x18003a42b  xor     r8d, r8d; msPeriod
0x18003a42e  xor     edx, edx; pftDueTime
0x18003a430  mov     rcx, rbp; pti
0x18003a433  call    cs:__imp_SetThreadpoolTimer
0x18003a439  mov     edx, 1; fCancelPendingCallbacks
0x18003a43e  mov     rcx, rbp; pti
0x18003a441  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003a447  mov     rcx, rbp; pti
0x18003a44a  call    cs:__imp_CloseThreadpoolTimer
0x18003a450  mov     ecx, ebx; dwErrCode
0x18003a452  call    cs:__imp_SetLastError
0x18003a458  mov     [rdi+38h], r15
0x18003a45c  mov     ecx, r14d; dwErrCode
0x18003a45f  call    cs:__imp_SetLastError
0x18003a465  mov     rcx, [rdi+38h]; pti
0x18003a469  test    rcx, rcx
0x18003a46c  jz      short loc_18003A48F
0x18003a46e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18003a477  mov     r9d, 4E2h; msWindowLength
0x18003a47d  xor     r8d, r8d; msPeriod
0x18003a480  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18003a485  call    cs:__imp_SetThreadpoolTimer
0x18003a48b  mov     byte ptr [rdi+40h], 1
0x18003a48f  test    rsi, rsi
0x18003a492  jz      short loc_18003A49E
0x18003a494  mov     rcx, rsi; SRWLock
0x18003a497  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a49d  nop
0x18003a49e  add     rsp, 38h
0x18003a4a2  pop     r15
0x18003a4a4  pop     r14
0x18003a4a6  pop     rdi
0x18003a4a7  pop     rsi
0x18003a4a8  pop     rbp
0x18003a4a9  pop     rbx
0x18003a4aa  retn
```
