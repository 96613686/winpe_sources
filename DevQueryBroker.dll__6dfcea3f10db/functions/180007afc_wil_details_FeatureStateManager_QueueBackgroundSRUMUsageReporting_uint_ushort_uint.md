# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007afc`
- end: `0x180007c84`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800097c0`

## callees

- `0x180007afc`
- `0x180009d2c`
- `0x18000a1d0`
- `0x18000b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007baa`
- `msvcrt!memcpy_s` at `0x180007baa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007c64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007c64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007bdb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007bdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007c0e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007c17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007c52`

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
0x180007afc  push    rbx
0x180007afe  push    rbp
0x180007aff  push    rsi
0x180007b00  push    rdi
0x180007b01  push    r14
0x180007b03  push    r15
0x180007b05  sub     rsp, 48h
0x180007b09  mov     rax, cs:__security_cookie
0x180007b10  xor     rax, rsp
0x180007b13  mov     [rsp+78h+var_40], rax
0x180007b18  cmp     byte ptr [rcx], 0
0x180007b1b  mov     r14d, r9d
0x180007b1e  movzx   ebp, r8w
0x180007b22  mov     ebx, edx
0x180007b24  mov     rdi, rcx
0x180007b27  jz      loc_180007C6A
0x180007b2d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007b34  jnz     loc_180007C6A
0x180007b3a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007b41  test    rax, rax
0x180007b44  jz      short loc_180007B53
0x180007b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b4b  test    al, al
0x180007b4d  jnz     loc_180007C6A
0x180007b53  lea     rsi, [rdi+28h]
0x180007b57  mov     rcx, rsi; SRWLock
0x180007b5a  call    cs:__imp_AcquireSRWLockExclusive
0x180007b60  xor     eax, eax
0x180007b62  mov     [rsp+78h+Source], ebx
0x180007b66  mov     [rsp+78h+var_4C], bp
0x180007b6b  lea     rbx, [rdi+0E8h]
0x180007b72  mov     rcx, rbx; this
0x180007b75  mov     [rsp+78h+var_4A], ax
0x180007b7a  mov     [rsp+78h+var_48], r14d
0x180007b7f  lea     ebp, [rax+0Ch]
0x180007b82  mov     edx, ebp; unsigned __int64
0x180007b84  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007b89  test    al, al
0x180007b8b  jz      short loc_180007BB4
0x180007b8d  mov     rcx, [rbx+8]; Destination
0x180007b91  lea     r8, [rsp+78h+Source]; Source
0x180007b96  mov     rax, [rbx+10h]
0x180007b9a  mov     r9d, ebp; SourceSize
0x180007b9d  sub     rax, rcx
0x180007ba0  cmp     rcx, [rbx+10h]
0x180007ba4  sbb     rdx, rdx
0x180007ba7  and     rdx, rax; DestinationSize
0x180007baa  call    cs:__imp_memcpy_s
0x180007bb0  add     [rbx+8], rbp
0x180007bb4  cmp     byte ptr [rdi+40h], 0
0x180007bb8  jnz     loc_180007C5C
0x180007bbe  cmp     qword ptr [rdi+38h], 0
0x180007bc3  jnz     short loc_180007C32
0x180007bc5  call    cs:__imp_GetLastError
0x180007bcb  xor     r8d, r8d; pcbe
0x180007bce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007bd5  mov     rdx, rdi; pv
0x180007bd8  mov     r14d, eax
0x180007bdb  call    cs:__imp_CreateThreadpoolTimer
0x180007be1  mov     rbp, [rdi+38h]
0x180007be5  mov     r15, rax
0x180007be8  test    rbp, rbp
0x180007beb  jz      short loc_180007C25
0x180007bed  call    cs:__imp_GetLastError
0x180007bf3  xor     r9d, r9d; msWindowLength
0x180007bf6  xor     r8d, r8d; msPeriod
0x180007bf9  xor     edx, edx; pftDueTime
0x180007bfb  mov     rcx, rbp; pti
0x180007bfe  mov     ebx, eax
0x180007c00  call    cs:__imp_SetThreadpoolTimer
0x180007c06  mov     edx, 1; fCancelPendingCallbacks
0x180007c0b  mov     rcx, rbp; pti
0x180007c0e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007c14  mov     rcx, rbp; pti
0x180007c17  call    cs:__imp_CloseThreadpoolTimer
0x180007c1d  mov     ecx, ebx; dwErrCode
0x180007c1f  call    cs:__imp_SetLastError
0x180007c25  mov     ecx, r14d; dwErrCode
0x180007c28  mov     [rdi+38h], r15
0x180007c2c  call    cs:__imp_SetLastError
0x180007c32  mov     rcx, [rdi+38h]; pti
0x180007c36  test    rcx, rcx
0x180007c39  jz      short loc_180007C5C
0x180007c3b  mov     r9d, 4E2h; msWindowLength
0x180007c41  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180007c4a  xor     r8d, r8d; msPeriod
0x180007c4d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180007c52  call    cs:__imp_SetThreadpoolTimer
0x180007c58  mov     byte ptr [rdi+40h], 1
0x180007c5c  test    rsi, rsi
0x180007c5f  jz      short loc_180007C6A
0x180007c61  mov     rcx, rsi; SRWLock
0x180007c64  call    cs:__imp_ReleaseSRWLockExclusive
0x180007c6a  mov     rcx, [rsp+78h+var_40]
0x180007c6f  xor     rcx, rsp; StackCookie
0x180007c72  call    __security_check_cookie
0x180007c77  add     rsp, 48h
0x180007c7b  pop     r15
0x180007c7d  pop     r14
0x180007c7f  pop     rdi
0x180007c80  pop     rsi
0x180007c81  pop     rbp
0x180007c82  pop     rbx
0x180007c83  retn
```
