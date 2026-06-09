# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ae30`
- end: `0x18000afb9`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c820`

## callees

- `0x18000ae30`
- `0x18000d2e4`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aede`
- `msvcrt!memcpy_s` at `0x18000aede`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000af0f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af42`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af34`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af34`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af86`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af4b`

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
0x18000ae30  push    rbx
0x18000ae32  push    rbp
0x18000ae33  push    rsi
0x18000ae34  push    rdi
0x18000ae35  push    r14
0x18000ae37  push    r15
0x18000ae39  sub     rsp, 48h
0x18000ae3d  mov     rax, cs:__security_cookie
0x18000ae44  xor     rax, rsp
0x18000ae47  mov     [rsp+78h+var_40], rax
0x18000ae4c  mov     r14d, r9d
0x18000ae4f  movzx   ebp, r8w
0x18000ae53  mov     ebx, edx
0x18000ae55  mov     rdi, rcx
0x18000ae58  cmp     byte ptr [rcx], 0
0x18000ae5b  jz      loc_18000AF9F
0x18000ae61  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ae68  jnz     loc_18000AF9F
0x18000ae6e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ae75  test    rax, rax
0x18000ae78  jz      short loc_18000AE87
0x18000ae7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7f  test    al, al
0x18000ae81  jnz     loc_18000AF9F
0x18000ae87  lea     rsi, [rdi+28h]
0x18000ae8b  mov     rcx, rsi; SRWLock
0x18000ae8e  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae94  xor     eax, eax
0x18000ae96  mov     [rsp+78h+var_4A], ax
0x18000ae9b  mov     [rsp+78h+Source], ebx
0x18000ae9f  mov     [rsp+78h+var_4C], bp
0x18000aea4  mov     [rsp+78h+var_48], r14d
0x18000aea9  lea     rbx, [rdi+0E8h]
0x18000aeb0  lea     ebp, [rax+0Ch]
0x18000aeb3  mov     edx, ebp; unsigned __int64
0x18000aeb5  mov     rcx, rbx; this
0x18000aeb8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aebd  test    al, al
0x18000aebf  jz      short loc_18000AEE8
0x18000aec1  mov     rcx, [rbx+8]; Destination
0x18000aec5  mov     rax, [rbx+10h]
0x18000aec9  sub     rax, rcx
0x18000aecc  cmp     rcx, [rbx+10h]
0x18000aed0  sbb     rdx, rdx
0x18000aed3  and     rdx, rax; DestinationSize
0x18000aed6  mov     r9d, ebp; SourceSize
0x18000aed9  lea     r8, [rsp+78h+Source]; Source
0x18000aede  call    cs:__imp_memcpy_s
0x18000aee4  add     [rbx+8], rbp
0x18000aee8  cmp     byte ptr [rdi+40h], 0
0x18000aeec  jnz     loc_18000AF90
0x18000aef2  cmp     qword ptr [rdi+38h], 0
0x18000aef7  jnz     short loc_18000AF66
0x18000aef9  call    cs:__imp_GetLastError
0x18000aeff  mov     r14d, eax
0x18000af02  xor     r8d, r8d; pcbe
0x18000af05  mov     rdx, rdi; pv
0x18000af08  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000af0f  call    cs:__imp_CreateThreadpoolTimer
0x18000af15  mov     r15, rax
0x18000af18  mov     rbp, [rdi+38h]
0x18000af1c  test    rbp, rbp
0x18000af1f  jz      short loc_18000AF59
0x18000af21  call    cs:__imp_GetLastError
0x18000af27  mov     ebx, eax
0x18000af29  xor     r9d, r9d; msWindowLength
0x18000af2c  xor     r8d, r8d; msPeriod
0x18000af2f  xor     edx, edx; pftDueTime
0x18000af31  mov     rcx, rbp; pti
0x18000af34  call    cs:__imp_SetThreadpoolTimer
0x18000af3a  mov     edx, 1; fCancelPendingCallbacks
0x18000af3f  mov     rcx, rbp; pti
0x18000af42  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000af48  mov     rcx, rbp; pti
0x18000af4b  call    cs:__imp_CloseThreadpoolTimer
0x18000af51  mov     ecx, ebx; dwErrCode
0x18000af53  call    cs:__imp_SetLastError
0x18000af59  mov     [rdi+38h], r15
0x18000af5d  mov     ecx, r14d; dwErrCode
0x18000af60  call    cs:__imp_SetLastError
0x18000af66  mov     rcx, [rdi+38h]; pti
0x18000af6a  test    rcx, rcx
0x18000af6d  jz      short loc_18000AF90
0x18000af6f  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000af78  mov     r9d, 4E2h; msWindowLength
0x18000af7e  xor     r8d, r8d; msPeriod
0x18000af81  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000af86  call    cs:__imp_SetThreadpoolTimer
0x18000af8c  mov     byte ptr [rdi+40h], 1
0x18000af90  test    rsi, rsi
0x18000af93  jz      short loc_18000AF9F
0x18000af95  mov     rcx, rsi; SRWLock
0x18000af98  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af9e  nop
0x18000af9f  mov     rcx, [rsp+78h+var_40]
0x18000afa4  xor     rcx, rsp; StackCookie
0x18000afa7  call    __security_check_cookie
0x18000afac  add     rsp, 48h
0x18000afb0  pop     r15
0x18000afb2  pop     r14
0x18000afb4  pop     rdi
0x18000afb5  pop     rsi
0x18000afb6  pop     rbp
0x18000afb7  pop     rbx
0x18000afb8  retn
```
