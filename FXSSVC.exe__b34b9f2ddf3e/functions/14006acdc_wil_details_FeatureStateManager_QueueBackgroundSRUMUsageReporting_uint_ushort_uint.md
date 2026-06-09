# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14006acdc`
- end: `0x14006ae65`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14006ce70`

## callees

- `0x14006acdc`
- `0x14006d480`
- `0x1400818b0`
- `0x140085010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14006adbb`
- `KERNEL32!CreateThreadpoolTimer` at `0x14006adbb`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ade0`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ae32`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ade0`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ae32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006ad3a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006ad3a`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006adf7`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006adf7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006ae44`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006ae44`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006adee`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006adee`
- `KERNEL32!GetLastError` at `0x14006ada5`
- `KERNEL32!GetLastError` at `0x14006adcd`
- `KERNEL32!GetLastError` at `0x14006ada5`
- `KERNEL32!GetLastError` at `0x14006adcd`
- `KERNEL32!SetLastError` at `0x14006adff`
- `KERNEL32!SetLastError` at `0x14006ae0c`
- `KERNEL32!SetLastError` at `0x14006adff`
- `KERNEL32!SetLastError` at `0x14006ae0c`
- `msvcrt!memcpy_s` at `0x14006ad8a`
- `msvcrt!memcpy_s` at `0x14006ad8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
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
0x14006acdc  push    rbx
0x14006acde  push    rbp
0x14006acdf  push    rsi
0x14006ace0  push    rdi
0x14006ace1  push    r14
0x14006ace3  push    r15
0x14006ace5  sub     rsp, 48h
0x14006ace9  mov     rax, cs:__security_cookie
0x14006acf0  xor     rax, rsp
0x14006acf3  mov     [rsp+78h+var_40], rax
0x14006acf8  mov     r14d, r9d
0x14006acfb  movzx   ebp, r8w
0x14006acff  mov     ebx, edx
0x14006ad01  mov     rdi, rcx
0x14006ad04  cmp     byte ptr [rcx], 0
0x14006ad07  jz      loc_14006AE4B
0x14006ad0d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14006ad14  jnz     loc_14006AE4B
0x14006ad1a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14006ad21  test    rax, rax
0x14006ad24  jz      short loc_14006AD33
0x14006ad26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ad2b  test    al, al
0x14006ad2d  jnz     loc_14006AE4B
0x14006ad33  lea     rsi, [rdi+28h]
0x14006ad37  mov     rcx, rsi; SRWLock
0x14006ad3a  call    cs:__imp_AcquireSRWLockExclusive
0x14006ad40  xor     eax, eax
0x14006ad42  mov     [rsp+78h+var_4A], ax
0x14006ad47  mov     [rsp+78h+Source], ebx
0x14006ad4b  mov     [rsp+78h+var_4C], bp
0x14006ad50  mov     [rsp+78h+var_48], r14d
0x14006ad55  lea     rbx, [rdi+0E8h]
0x14006ad5c  lea     ebp, [rax+0Ch]
0x14006ad5f  mov     edx, ebp; unsigned __int64
0x14006ad61  mov     rcx, rbx; this
0x14006ad64  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14006ad69  test    al, al
0x14006ad6b  jz      short loc_14006AD94
0x14006ad6d  mov     rcx, [rbx+8]; Destination
0x14006ad71  mov     rax, [rbx+10h]
0x14006ad75  sub     rax, rcx
0x14006ad78  cmp     rcx, [rbx+10h]
0x14006ad7c  sbb     rdx, rdx
0x14006ad7f  and     rdx, rax; DestinationSize
0x14006ad82  mov     r9d, ebp; SourceSize
0x14006ad85  lea     r8, [rsp+78h+Source]; Source
0x14006ad8a  call    cs:__imp_memcpy_s
0x14006ad90  add     [rbx+8], rbp
0x14006ad94  cmp     byte ptr [rdi+40h], 0
0x14006ad98  jnz     loc_14006AE3C
0x14006ad9e  cmp     qword ptr [rdi+38h], 0
0x14006ada3  jnz     short loc_14006AE12
0x14006ada5  call    cs:__imp_GetLastError
0x14006adab  mov     r14d, eax
0x14006adae  xor     r8d, r8d; pcbe
0x14006adb1  mov     rdx, rdi; pv
0x14006adb4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14006adbb  call    cs:__imp_CreateThreadpoolTimer
0x14006adc1  mov     r15, rax
0x14006adc4  mov     rbp, [rdi+38h]
0x14006adc8  test    rbp, rbp
0x14006adcb  jz      short loc_14006AE05
0x14006adcd  call    cs:__imp_GetLastError
0x14006add3  mov     ebx, eax
0x14006add5  xor     r9d, r9d; msWindowLength
0x14006add8  xor     r8d, r8d; msPeriod
0x14006addb  xor     edx, edx; pftDueTime
0x14006addd  mov     rcx, rbp; pti
0x14006ade0  call    cs:__imp_SetThreadpoolTimer
0x14006ade6  mov     edx, 1; fCancelPendingCallbacks
0x14006adeb  mov     rcx, rbp; pti
0x14006adee  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14006adf4  mov     rcx, rbp; pti
0x14006adf7  call    cs:__imp_CloseThreadpoolTimer
0x14006adfd  mov     ecx, ebx; dwErrCode
0x14006adff  call    cs:__imp_SetLastError
0x14006ae05  mov     [rdi+38h], r15
0x14006ae09  mov     ecx, r14d; dwErrCode
0x14006ae0c  call    cs:__imp_SetLastError
0x14006ae12  mov     rcx, [rdi+38h]; pti
0x14006ae16  test    rcx, rcx
0x14006ae19  jz      short loc_14006AE3C
0x14006ae1b  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14006ae24  mov     r9d, 4E2h; msWindowLength
0x14006ae2a  xor     r8d, r8d; msPeriod
0x14006ae2d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14006ae32  call    cs:__imp_SetThreadpoolTimer
0x14006ae38  mov     byte ptr [rdi+40h], 1
0x14006ae3c  test    rsi, rsi
0x14006ae3f  jz      short loc_14006AE4B
0x14006ae41  mov     rcx, rsi; SRWLock
0x14006ae44  call    cs:__imp_ReleaseSRWLockExclusive
0x14006ae4a  nop
0x14006ae4b  mov     rcx, [rsp+78h+var_40]
0x14006ae50  xor     rcx, rsp; StackCookie
0x14006ae53  call    __security_check_cookie
0x14006ae58  add     rsp, 48h
0x14006ae5c  pop     r15
0x14006ae5e  pop     r14
0x14006ae60  pop     rdi
0x14006ae61  pop     rsi
0x14006ae62  pop     rbp
0x14006ae63  pop     rbx
0x14006ae64  retn
```
