# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002c09c`
- end: `0x18002c225`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f590`

## callees

- `0x18002c09c`
- `0x1800302f4`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002c14a`
- `msvcrt!memcpy_s` at `0x18002c14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c204`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c204`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c0fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c0fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c1ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c1ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c1b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c1b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c17b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c17b`

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
0x18002c09c  push    rbx
0x18002c09e  push    rbp
0x18002c09f  push    rsi
0x18002c0a0  push    rdi
0x18002c0a1  push    r14
0x18002c0a3  push    r15
0x18002c0a5  sub     rsp, 48h
0x18002c0a9  mov     rax, cs:__security_cookie
0x18002c0b0  xor     rax, rsp
0x18002c0b3  mov     [rsp+78h+var_40], rax
0x18002c0b8  mov     r14d, r9d
0x18002c0bb  movzx   ebp, r8w
0x18002c0bf  mov     ebx, edx
0x18002c0c1  mov     rdi, rcx
0x18002c0c4  cmp     byte ptr [rcx], 0
0x18002c0c7  jz      loc_18002C20B
0x18002c0cd  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002c0d4  jnz     loc_18002C20B
0x18002c0da  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002c0e1  test    rax, rax
0x18002c0e4  jz      short loc_18002C0F3
0x18002c0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0eb  test    al, al
0x18002c0ed  jnz     loc_18002C20B
0x18002c0f3  lea     rsi, [rdi+28h]
0x18002c0f7  mov     rcx, rsi; SRWLock
0x18002c0fa  call    cs:__imp_AcquireSRWLockExclusive
0x18002c100  xor     eax, eax
0x18002c102  mov     [rsp+78h+var_4A], ax
0x18002c107  mov     [rsp+78h+Source], ebx
0x18002c10b  mov     [rsp+78h+var_4C], bp
0x18002c110  mov     [rsp+78h+var_48], r14d
0x18002c115  lea     rbx, [rdi+0E8h]
0x18002c11c  lea     ebp, [rax+0Ch]
0x18002c11f  mov     edx, ebp; unsigned __int64
0x18002c121  mov     rcx, rbx; this
0x18002c124  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002c129  test    al, al
0x18002c12b  jz      short loc_18002C154
0x18002c12d  mov     rcx, [rbx+8]; Destination
0x18002c131  mov     rax, [rbx+10h]
0x18002c135  sub     rax, rcx
0x18002c138  cmp     rcx, [rbx+10h]
0x18002c13c  sbb     rdx, rdx
0x18002c13f  and     rdx, rax; DestinationSize
0x18002c142  mov     r9d, ebp; SourceSize
0x18002c145  lea     r8, [rsp+78h+Source]; Source
0x18002c14a  call    cs:__imp_memcpy_s
0x18002c150  add     [rbx+8], rbp
0x18002c154  cmp     byte ptr [rdi+40h], 0
0x18002c158  jnz     loc_18002C1FC
0x18002c15e  cmp     qword ptr [rdi+38h], 0
0x18002c163  jnz     short loc_18002C1D2
0x18002c165  call    cs:__imp_GetLastError
0x18002c16b  mov     r14d, eax
0x18002c16e  xor     r8d, r8d; pcbe
0x18002c171  mov     rdx, rdi; pv
0x18002c174  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002c17b  call    cs:__imp_CreateThreadpoolTimer
0x18002c181  mov     r15, rax
0x18002c184  mov     rbp, [rdi+38h]
0x18002c188  test    rbp, rbp
0x18002c18b  jz      short loc_18002C1C5
0x18002c18d  call    cs:__imp_GetLastError
0x18002c193  mov     ebx, eax
0x18002c195  xor     r9d, r9d; msWindowLength
0x18002c198  xor     r8d, r8d; msPeriod
0x18002c19b  xor     edx, edx; pftDueTime
0x18002c19d  mov     rcx, rbp; pti
0x18002c1a0  call    cs:__imp_SetThreadpoolTimer
0x18002c1a6  mov     edx, 1; fCancelPendingCallbacks
0x18002c1ab  mov     rcx, rbp; pti
0x18002c1ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c1b4  mov     rcx, rbp; pti
0x18002c1b7  call    cs:__imp_CloseThreadpoolTimer
0x18002c1bd  mov     ecx, ebx; dwErrCode
0x18002c1bf  call    cs:__imp_SetLastError
0x18002c1c5  mov     [rdi+38h], r15
0x18002c1c9  mov     ecx, r14d; dwErrCode
0x18002c1cc  call    cs:__imp_SetLastError
0x18002c1d2  mov     rcx, [rdi+38h]; pti
0x18002c1d6  test    rcx, rcx
0x18002c1d9  jz      short loc_18002C1FC
0x18002c1db  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18002c1e4  mov     r9d, 4E2h; msWindowLength
0x18002c1ea  xor     r8d, r8d; msPeriod
0x18002c1ed  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18002c1f2  call    cs:__imp_SetThreadpoolTimer
0x18002c1f8  mov     byte ptr [rdi+40h], 1
0x18002c1fc  test    rsi, rsi
0x18002c1ff  jz      short loc_18002C20B
0x18002c201  mov     rcx, rsi; SRWLock
0x18002c204  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c20a  nop
0x18002c20b  mov     rcx, [rsp+78h+var_40]
0x18002c210  xor     rcx, rsp; StackCookie
0x18002c213  call    __security_check_cookie
0x18002c218  add     rsp, 48h
0x18002c21c  pop     r15
0x18002c21e  pop     r14
0x18002c220  pop     rdi
0x18002c221  pop     rsi
0x18002c222  pop     rbp
0x18002c223  pop     rbx
0x18002c224  retn
```
