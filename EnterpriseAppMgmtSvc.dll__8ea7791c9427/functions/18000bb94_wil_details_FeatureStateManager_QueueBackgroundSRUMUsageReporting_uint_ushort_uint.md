# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000bb94`
- end: `0x18000bd1d`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000dd70`

## callees

- `0x18000bb94`
- `0x18000e2cc`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bc42`
- `msvcrt!memcpy_s` at `0x18000bc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bcfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bcfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbf2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bcaf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bcaf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bc73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bc73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bc98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bcea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bc98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bcea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bca6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bca6`

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
0x18000bb94  push    rbx
0x18000bb96  push    rbp
0x18000bb97  push    rsi
0x18000bb98  push    rdi
0x18000bb99  push    r14
0x18000bb9b  push    r15
0x18000bb9d  sub     rsp, 48h
0x18000bba1  mov     rax, cs:__security_cookie
0x18000bba8  xor     rax, rsp
0x18000bbab  mov     [rsp+78h+var_40], rax
0x18000bbb0  mov     r14d, r9d
0x18000bbb3  movzx   ebp, r8w
0x18000bbb7  mov     ebx, edx
0x18000bbb9  mov     rdi, rcx
0x18000bbbc  cmp     byte ptr [rcx], 0
0x18000bbbf  jz      loc_18000BD03
0x18000bbc5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bbcc  jnz     loc_18000BD03
0x18000bbd2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bbd9  test    rax, rax
0x18000bbdc  jz      short loc_18000BBEB
0x18000bbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbe3  test    al, al
0x18000bbe5  jnz     loc_18000BD03
0x18000bbeb  lea     rsi, [rdi+28h]
0x18000bbef  mov     rcx, rsi; SRWLock
0x18000bbf2  call    cs:__imp_AcquireSRWLockExclusive
0x18000bbf8  xor     eax, eax
0x18000bbfa  mov     [rsp+78h+var_4A], ax
0x18000bbff  mov     [rsp+78h+Source], ebx
0x18000bc03  mov     [rsp+78h+var_4C], bp
0x18000bc08  mov     [rsp+78h+var_48], r14d
0x18000bc0d  lea     rbx, [rdi+0E8h]
0x18000bc14  lea     ebp, [rax+0Ch]
0x18000bc17  mov     edx, ebp; unsigned __int64
0x18000bc19  mov     rcx, rbx; this
0x18000bc1c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000bc21  test    al, al
0x18000bc23  jz      short loc_18000BC4C
0x18000bc25  mov     rcx, [rbx+8]; Destination
0x18000bc29  mov     rax, [rbx+10h]
0x18000bc2d  sub     rax, rcx
0x18000bc30  cmp     rcx, [rbx+10h]
0x18000bc34  sbb     rdx, rdx
0x18000bc37  and     rdx, rax; DestinationSize
0x18000bc3a  mov     r9d, ebp; SourceSize
0x18000bc3d  lea     r8, [rsp+78h+Source]; Source
0x18000bc42  call    cs:__imp_memcpy_s
0x18000bc48  add     [rbx+8], rbp
0x18000bc4c  cmp     byte ptr [rdi+40h], 0
0x18000bc50  jnz     loc_18000BCF4
0x18000bc56  cmp     qword ptr [rdi+38h], 0
0x18000bc5b  jnz     short loc_18000BCCA
0x18000bc5d  call    cs:__imp_GetLastError
0x18000bc63  mov     r14d, eax
0x18000bc66  xor     r8d, r8d; pcbe
0x18000bc69  mov     rdx, rdi; pv
0x18000bc6c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bc73  call    cs:__imp_CreateThreadpoolTimer
0x18000bc79  mov     r15, rax
0x18000bc7c  mov     rbp, [rdi+38h]
0x18000bc80  test    rbp, rbp
0x18000bc83  jz      short loc_18000BCBD
0x18000bc85  call    cs:__imp_GetLastError
0x18000bc8b  mov     ebx, eax
0x18000bc8d  xor     r9d, r9d; msWindowLength
0x18000bc90  xor     r8d, r8d; msPeriod
0x18000bc93  xor     edx, edx; pftDueTime
0x18000bc95  mov     rcx, rbp; pti
0x18000bc98  call    cs:__imp_SetThreadpoolTimer
0x18000bc9e  mov     edx, 1; fCancelPendingCallbacks
0x18000bca3  mov     rcx, rbp; pti
0x18000bca6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bcac  mov     rcx, rbp; pti
0x18000bcaf  call    cs:__imp_CloseThreadpoolTimer
0x18000bcb5  mov     ecx, ebx; dwErrCode
0x18000bcb7  call    cs:__imp_SetLastError
0x18000bcbd  mov     [rdi+38h], r15
0x18000bcc1  mov     ecx, r14d; dwErrCode
0x18000bcc4  call    cs:__imp_SetLastError
0x18000bcca  mov     rcx, [rdi+38h]; pti
0x18000bcce  test    rcx, rcx
0x18000bcd1  jz      short loc_18000BCF4
0x18000bcd3  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000bcdc  mov     r9d, 4E2h; msWindowLength
0x18000bce2  xor     r8d, r8d; msPeriod
0x18000bce5  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000bcea  call    cs:__imp_SetThreadpoolTimer
0x18000bcf0  mov     byte ptr [rdi+40h], 1
0x18000bcf4  test    rsi, rsi
0x18000bcf7  jz      short loc_18000BD03
0x18000bcf9  mov     rcx, rsi; SRWLock
0x18000bcfc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bd02  nop
0x18000bd03  mov     rcx, [rsp+78h+var_40]
0x18000bd08  xor     rcx, rsp; StackCookie
0x18000bd0b  call    __security_check_cookie
0x18000bd10  add     rsp, 48h
0x18000bd14  pop     r15
0x18000bd16  pop     r14
0x18000bd18  pop     rdi
0x18000bd19  pop     rsi
0x18000bd1a  pop     rbp
0x18000bd1b  pop     rbx
0x18000bd1c  retn
```
