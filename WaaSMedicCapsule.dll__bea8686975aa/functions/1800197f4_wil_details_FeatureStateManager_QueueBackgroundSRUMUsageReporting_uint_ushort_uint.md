# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800197f4`
- end: `0x180019938`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `324`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001ad40`

## callees

- `0x180017ae4`
- `0x1800197f4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019924`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019924`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019844`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001989b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001989b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800198d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800198d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800198c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019912`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800198c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019912`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800198ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800198ce`

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
  int Src; // [rsp+20h] [rbp-48h] BYREF
  __int16 v14; // [rsp+24h] [rbp-44h]
  __int16 v15; // [rsp+26h] [rbp-42h]
  int v16; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Src = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Src, 0xCu);
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
0x1800197f4  push    rbx
0x1800197f6  push    rbp
0x1800197f7  push    rsi
0x1800197f8  push    rdi
0x1800197f9  push    r14
0x1800197fb  push    r15
0x1800197fd  sub     rsp, 38h
0x180019801  mov     ebx, r9d
0x180019804  movzx   ebp, r8w
0x180019808  mov     r14d, edx
0x18001980b  mov     rdi, rcx
0x18001980e  cmp     byte ptr [rcx], 0
0x180019811  jz      loc_18001992B
0x180019817  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001981e  jnz     loc_18001992B
0x180019824  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001982b  test    rax, rax
0x18001982e  jz      short loc_18001983D
0x180019830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019835  test    al, al
0x180019837  jnz     loc_18001992B
0x18001983d  lea     rsi, [rdi+28h]
0x180019841  mov     rcx, rsi; SRWLock
0x180019844  call    cs:__imp_AcquireSRWLockExclusive
0x18001984a  xor     eax, eax
0x18001984c  mov     [rsp+68h+var_42], ax
0x180019851  mov     [rsp+68h+Src], r14d
0x180019856  mov     [rsp+68h+var_44], bp
0x18001985b  mov     [rsp+68h+var_40], ebx
0x18001985f  lea     rcx, [rdi+0E8h]; this
0x180019866  lea     r8d, [rax+0Ch]; Size
0x18001986a  lea     rdx, [rsp+68h+Src]; Src
0x18001986f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019874  cmp     byte ptr [rdi+40h], 0
0x180019878  jnz     loc_18001991C
0x18001987e  cmp     qword ptr [rdi+38h], 0
0x180019883  jnz     short loc_1800198F2
0x180019885  call    cs:__imp_GetLastError
0x18001988b  mov     r14d, eax
0x18001988e  xor     r8d, r8d; pcbe
0x180019891  mov     rdx, rdi; pv
0x180019894  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001989b  call    cs:__imp_CreateThreadpoolTimer
0x1800198a1  mov     r15, rax
0x1800198a4  mov     rbp, [rdi+38h]
0x1800198a8  test    rbp, rbp
0x1800198ab  jz      short loc_1800198E5
0x1800198ad  call    cs:__imp_GetLastError
0x1800198b3  mov     ebx, eax
0x1800198b5  xor     r9d, r9d; msWindowLength
0x1800198b8  xor     r8d, r8d; msPeriod
0x1800198bb  xor     edx, edx; pftDueTime
0x1800198bd  mov     rcx, rbp; pti
0x1800198c0  call    cs:__imp_SetThreadpoolTimer
0x1800198c6  mov     edx, 1; fCancelPendingCallbacks
0x1800198cb  mov     rcx, rbp; pti
0x1800198ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800198d4  mov     rcx, rbp; pti
0x1800198d7  call    cs:__imp_CloseThreadpoolTimer
0x1800198dd  mov     ecx, ebx; dwErrCode
0x1800198df  call    cs:__imp_SetLastError
0x1800198e5  mov     [rdi+38h], r15
0x1800198e9  mov     ecx, r14d; dwErrCode
0x1800198ec  call    cs:__imp_SetLastError
0x1800198f2  mov     rcx, [rdi+38h]; pti
0x1800198f6  test    rcx, rcx
0x1800198f9  jz      short loc_18001991C
0x1800198fb  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180019904  mov     r9d, 4E2h; msWindowLength
0x18001990a  xor     r8d, r8d; msPeriod
0x18001990d  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180019912  call    cs:__imp_SetThreadpoolTimer
0x180019918  mov     byte ptr [rdi+40h], 1
0x18001991c  test    rsi, rsi
0x18001991f  jz      short loc_18001992B
0x180019921  mov     rcx, rsi; SRWLock
0x180019924  call    cs:__imp_ReleaseSRWLockExclusive
0x18001992a  nop
0x18001992b  add     rsp, 38h
0x18001992f  pop     r15
0x180019931  pop     r14
0x180019933  pop     rdi
0x180019934  pop     rsi
0x180019935  pop     rbp
0x180019936  pop     rbx
0x180019937  retn
```
