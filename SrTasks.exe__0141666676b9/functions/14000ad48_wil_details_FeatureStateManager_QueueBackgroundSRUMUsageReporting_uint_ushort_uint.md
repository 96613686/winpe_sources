# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000ad48`
- end: `0x14000aed0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000c8d0`

## callees

- `0x140006524`
- `0x14000ad48`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000ae11`
- `KERNEL32!GetLastError` at `0x14000ae39`
- `KERNEL32!GetLastError` at `0x14000ae11`
- `KERNEL32!GetLastError` at `0x14000ae39`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000ae5a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000ae5a`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000ae63`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000ae63`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ae27`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ae27`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae4c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae9e`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae4c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae9e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ada6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ada6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000aeb0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000aeb0`
- `KERNEL32!SetLastError` at `0x14000ae6b`
- `KERNEL32!SetLastError` at `0x14000ae78`
- `KERNEL32!SetLastError` at `0x14000ae6b`
- `KERNEL32!SetLastError` at `0x14000ae78`
- `msvcrt!memcpy_s` at `0x14000adf6`
- `msvcrt!memcpy_s` at `0x14000adf6`

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
0x14000ad48  push    rbx
0x14000ad4a  push    rbp
0x14000ad4b  push    rsi
0x14000ad4c  push    rdi
0x14000ad4d  push    r14
0x14000ad4f  push    r15
0x14000ad51  sub     rsp, 48h
0x14000ad55  mov     rax, cs:__security_cookie
0x14000ad5c  xor     rax, rsp
0x14000ad5f  mov     [rsp+78h+var_40], rax
0x14000ad64  cmp     byte ptr [rcx], 0
0x14000ad67  mov     r14d, r9d
0x14000ad6a  movzx   ebp, r8w
0x14000ad6e  mov     ebx, edx
0x14000ad70  mov     rdi, rcx
0x14000ad73  jz      loc_14000AEB6
0x14000ad79  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000ad80  jnz     loc_14000AEB6
0x14000ad86  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000ad8d  test    rax, rax
0x14000ad90  jz      short loc_14000AD9F
0x14000ad92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad97  test    al, al
0x14000ad99  jnz     loc_14000AEB6
0x14000ad9f  lea     rsi, [rdi+28h]
0x14000ada3  mov     rcx, rsi; SRWLock
0x14000ada6  call    cs:__imp_AcquireSRWLockExclusive
0x14000adac  xor     eax, eax
0x14000adae  mov     [rsp+78h+Source], ebx
0x14000adb2  mov     [rsp+78h+var_4C], bp
0x14000adb7  lea     rbx, [rdi+0E8h]
0x14000adbe  mov     rcx, rbx; this
0x14000adc1  mov     [rsp+78h+var_4A], ax
0x14000adc6  mov     [rsp+78h+var_48], r14d
0x14000adcb  lea     ebp, [rax+0Ch]
0x14000adce  mov     edx, ebp; unsigned __int64
0x14000add0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000add5  test    al, al
0x14000add7  jz      short loc_14000AE00
0x14000add9  mov     rcx, [rbx+8]; Destination
0x14000addd  lea     r8, [rsp+78h+Source]; Source
0x14000ade2  mov     rax, [rbx+10h]
0x14000ade6  mov     r9d, ebp; SourceSize
0x14000ade9  sub     rax, rcx
0x14000adec  cmp     rcx, [rbx+10h]
0x14000adf0  sbb     rdx, rdx
0x14000adf3  and     rdx, rax; DestinationSize
0x14000adf6  call    cs:__imp_memcpy_s
0x14000adfc  add     [rbx+8], rbp
0x14000ae00  cmp     byte ptr [rdi+40h], 0
0x14000ae04  jnz     loc_14000AEA8
0x14000ae0a  cmp     qword ptr [rdi+38h], 0
0x14000ae0f  jnz     short loc_14000AE7E
0x14000ae11  call    cs:__imp_GetLastError
0x14000ae17  xor     r8d, r8d; pcbe
0x14000ae1a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ae21  mov     rdx, rdi; pv
0x14000ae24  mov     r14d, eax
0x14000ae27  call    cs:__imp_CreateThreadpoolTimer
0x14000ae2d  mov     rbp, [rdi+38h]
0x14000ae31  mov     r15, rax
0x14000ae34  test    rbp, rbp
0x14000ae37  jz      short loc_14000AE71
0x14000ae39  call    cs:__imp_GetLastError
0x14000ae3f  xor     r9d, r9d; msWindowLength
0x14000ae42  xor     r8d, r8d; msPeriod
0x14000ae45  xor     edx, edx; pftDueTime
0x14000ae47  mov     rcx, rbp; pti
0x14000ae4a  mov     ebx, eax
0x14000ae4c  call    cs:__imp_SetThreadpoolTimer
0x14000ae52  mov     edx, 1; fCancelPendingCallbacks
0x14000ae57  mov     rcx, rbp; pti
0x14000ae5a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000ae60  mov     rcx, rbp; pti
0x14000ae63  call    cs:__imp_CloseThreadpoolTimer
0x14000ae69  mov     ecx, ebx; dwErrCode
0x14000ae6b  call    cs:__imp_SetLastError
0x14000ae71  mov     ecx, r14d; dwErrCode
0x14000ae74  mov     [rdi+38h], r15
0x14000ae78  call    cs:__imp_SetLastError
0x14000ae7e  mov     rcx, [rdi+38h]; pti
0x14000ae82  test    rcx, rcx
0x14000ae85  jz      short loc_14000AEA8
0x14000ae87  mov     r9d, 4E2h; msWindowLength
0x14000ae8d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000ae96  xor     r8d, r8d; msPeriod
0x14000ae99  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14000ae9e  call    cs:__imp_SetThreadpoolTimer
0x14000aea4  mov     byte ptr [rdi+40h], 1
0x14000aea8  test    rsi, rsi
0x14000aeab  jz      short loc_14000AEB6
0x14000aead  mov     rcx, rsi; SRWLock
0x14000aeb0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000aeb6  mov     rcx, [rsp+78h+var_40]
0x14000aebb  xor     rcx, rsp; StackCookie
0x14000aebe  call    __security_check_cookie
0x14000aec3  add     rsp, 48h
0x14000aec7  pop     r15
0x14000aec9  pop     r14
0x14000aecb  pop     rdi
0x14000aecc  pop     rsi
0x14000aecd  pop     rbp
0x14000aece  pop     rbx
0x14000aecf  retn
```
