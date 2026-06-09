# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000bde8`
- end: `0x14000bf71`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e420`

## callees

- `0x14000bde8`
- `0x14000f454`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000be96`
- `msvcrt!memcpy_s` at `0x14000be96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000beb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000beb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bed9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000be46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000be46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bf50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bf50`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000beec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000beec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000befa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000befa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf03`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000bec7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000bec7`

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
0x14000bde8  push    rbx
0x14000bdea  push    rbp
0x14000bdeb  push    rsi
0x14000bdec  push    rdi
0x14000bded  push    r14
0x14000bdef  push    r15
0x14000bdf1  sub     rsp, 48h
0x14000bdf5  mov     rax, cs:__security_cookie
0x14000bdfc  xor     rax, rsp
0x14000bdff  mov     [rsp+78h+var_40], rax
0x14000be04  mov     r14d, r9d
0x14000be07  movzx   ebp, r8w
0x14000be0b  mov     ebx, edx
0x14000be0d  mov     rdi, rcx
0x14000be10  cmp     byte ptr [rcx], 0
0x14000be13  jz      loc_14000BF57
0x14000be19  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000be20  jnz     loc_14000BF57
0x14000be26  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000be2d  test    rax, rax
0x14000be30  jz      short loc_14000BE3F
0x14000be32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be37  test    al, al
0x14000be39  jnz     loc_14000BF57
0x14000be3f  lea     rsi, [rdi+28h]
0x14000be43  mov     rcx, rsi; SRWLock
0x14000be46  call    cs:__imp_AcquireSRWLockExclusive
0x14000be4c  xor     eax, eax
0x14000be4e  mov     [rsp+78h+var_4A], ax
0x14000be53  mov     [rsp+78h+Source], ebx
0x14000be57  mov     [rsp+78h+var_4C], bp
0x14000be5c  mov     [rsp+78h+var_48], r14d
0x14000be61  lea     rbx, [rdi+0E8h]
0x14000be68  lea     ebp, [rax+0Ch]
0x14000be6b  mov     edx, ebp; unsigned __int64
0x14000be6d  mov     rcx, rbx; this
0x14000be70  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000be75  test    al, al
0x14000be77  jz      short loc_14000BEA0
0x14000be79  mov     rcx, [rbx+8]; Destination
0x14000be7d  mov     rax, [rbx+10h]
0x14000be81  sub     rax, rcx
0x14000be84  cmp     rcx, [rbx+10h]
0x14000be88  sbb     rdx, rdx
0x14000be8b  and     rdx, rax; DestinationSize
0x14000be8e  mov     r9d, ebp; SourceSize
0x14000be91  lea     r8, [rsp+78h+Source]; Source
0x14000be96  call    cs:__imp_memcpy_s
0x14000be9c  add     [rbx+8], rbp
0x14000bea0  cmp     byte ptr [rdi+40h], 0
0x14000bea4  jnz     loc_14000BF48
0x14000beaa  cmp     qword ptr [rdi+38h], 0
0x14000beaf  jnz     short loc_14000BF1E
0x14000beb1  call    cs:__imp_GetLastError
0x14000beb7  mov     r14d, eax
0x14000beba  xor     r8d, r8d; pcbe
0x14000bebd  mov     rdx, rdi; pv
0x14000bec0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000bec7  call    cs:__imp_CreateThreadpoolTimer
0x14000becd  mov     r15, rax
0x14000bed0  mov     rbp, [rdi+38h]
0x14000bed4  test    rbp, rbp
0x14000bed7  jz      short loc_14000BF11
0x14000bed9  call    cs:__imp_GetLastError
0x14000bedf  mov     ebx, eax
0x14000bee1  xor     r9d, r9d; msWindowLength
0x14000bee4  xor     r8d, r8d; msPeriod
0x14000bee7  xor     edx, edx; pftDueTime
0x14000bee9  mov     rcx, rbp; pti
0x14000beec  call    cs:__imp_SetThreadpoolTimer
0x14000bef2  mov     edx, 1; fCancelPendingCallbacks
0x14000bef7  mov     rcx, rbp; pti
0x14000befa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000bf00  mov     rcx, rbp; pti
0x14000bf03  call    cs:__imp_CloseThreadpoolTimer
0x14000bf09  mov     ecx, ebx; dwErrCode
0x14000bf0b  call    cs:__imp_SetLastError
0x14000bf11  mov     [rdi+38h], r15
0x14000bf15  mov     ecx, r14d; dwErrCode
0x14000bf18  call    cs:__imp_SetLastError
0x14000bf1e  mov     rcx, [rdi+38h]; pti
0x14000bf22  test    rcx, rcx
0x14000bf25  jz      short loc_14000BF48
0x14000bf27  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000bf30  mov     r9d, 4E2h; msWindowLength
0x14000bf36  xor     r8d, r8d; msPeriod
0x14000bf39  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14000bf3e  call    cs:__imp_SetThreadpoolTimer
0x14000bf44  mov     byte ptr [rdi+40h], 1
0x14000bf48  test    rsi, rsi
0x14000bf4b  jz      short loc_14000BF57
0x14000bf4d  mov     rcx, rsi; SRWLock
0x14000bf50  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bf56  nop
0x14000bf57  mov     rcx, [rsp+78h+var_40]
0x14000bf5c  xor     rcx, rsp; StackCookie
0x14000bf5f  call    __security_check_cookie
0x14000bf64  add     rsp, 48h
0x14000bf68  pop     r15
0x14000bf6a  pop     r14
0x14000bf6c  pop     rdi
0x14000bf6d  pop     rsi
0x14000bf6e  pop     rbp
0x14000bf6f  pop     rbx
0x14000bf70  retn
```
