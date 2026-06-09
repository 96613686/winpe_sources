# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400077a0`
- end: `0x140007928`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000a210`

## callees

- `0x1400077a0`
- `0x14000a87c`
- `0x140015b00`
- `0x140017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400078c3`
- `KERNEL32!SetLastError` at `0x1400078d0`
- `KERNEL32!SetLastError` at `0x1400078c3`
- `KERNEL32!SetLastError` at `0x1400078d0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400078b2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400078b2`
- `KERNEL32!GetLastError` at `0x140007869`
- `KERNEL32!GetLastError` at `0x140007891`
- `KERNEL32!GetLastError` at `0x140007869`
- `KERNEL32!GetLastError` at `0x140007891`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007908`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007908`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400078bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400078bb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400077fe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400077fe`
- `KERNEL32!SetThreadpoolTimer` at `0x1400078a4`
- `KERNEL32!SetThreadpoolTimer` at `0x1400078f6`
- `KERNEL32!SetThreadpoolTimer` at `0x1400078a4`
- `KERNEL32!SetThreadpoolTimer` at `0x1400078f6`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000787f`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000787f`
- `msvcrt!memcpy_s` at `0x14000784e`
- `msvcrt!memcpy_s` at `0x14000784e`

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
0x1400077a0  push    rbx
0x1400077a2  push    rbp
0x1400077a3  push    rsi
0x1400077a4  push    rdi
0x1400077a5  push    r14
0x1400077a7  push    r15
0x1400077a9  sub     rsp, 48h
0x1400077ad  mov     rax, cs:__security_cookie
0x1400077b4  xor     rax, rsp
0x1400077b7  mov     [rsp+78h+var_40], rax
0x1400077bc  cmp     byte ptr [rcx], 0
0x1400077bf  mov     r14d, r9d
0x1400077c2  movzx   ebp, r8w
0x1400077c6  mov     ebx, edx
0x1400077c8  mov     rdi, rcx
0x1400077cb  jz      loc_14000790E
0x1400077d1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400077d8  jnz     loc_14000790E
0x1400077de  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400077e5  test    rax, rax
0x1400077e8  jz      short loc_1400077F7
0x1400077ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077ef  test    al, al
0x1400077f1  jnz     loc_14000790E
0x1400077f7  lea     rsi, [rdi+28h]
0x1400077fb  mov     rcx, rsi; SRWLock
0x1400077fe  call    cs:__imp_AcquireSRWLockExclusive
0x140007804  xor     eax, eax
0x140007806  mov     [rsp+78h+Source], ebx
0x14000780a  mov     [rsp+78h+var_4C], bp
0x14000780f  lea     rbx, [rdi+0E8h]
0x140007816  mov     rcx, rbx; this
0x140007819  mov     [rsp+78h+var_4A], ax
0x14000781e  mov     [rsp+78h+var_48], r14d
0x140007823  lea     ebp, [rax+0Ch]
0x140007826  mov     edx, ebp; unsigned __int64
0x140007828  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000782d  test    al, al
0x14000782f  jz      short loc_140007858
0x140007831  mov     rcx, [rbx+8]; Destination
0x140007835  lea     r8, [rsp+78h+Source]; Source
0x14000783a  mov     rax, [rbx+10h]
0x14000783e  mov     r9d, ebp; SourceSize
0x140007841  sub     rax, rcx
0x140007844  cmp     rcx, [rbx+10h]
0x140007848  sbb     rdx, rdx
0x14000784b  and     rdx, rax; DestinationSize
0x14000784e  call    cs:__imp_memcpy_s
0x140007854  add     [rbx+8], rbp
0x140007858  cmp     byte ptr [rdi+40h], 0
0x14000785c  jnz     loc_140007900
0x140007862  cmp     qword ptr [rdi+38h], 0
0x140007867  jnz     short loc_1400078D6
0x140007869  call    cs:__imp_GetLastError
0x14000786f  xor     r8d, r8d; pcbe
0x140007872  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007879  mov     rdx, rdi; pv
0x14000787c  mov     r14d, eax
0x14000787f  call    cs:__imp_CreateThreadpoolTimer
0x140007885  mov     rbp, [rdi+38h]
0x140007889  mov     r15, rax
0x14000788c  test    rbp, rbp
0x14000788f  jz      short loc_1400078C9
0x140007891  call    cs:__imp_GetLastError
0x140007897  xor     r9d, r9d; msWindowLength
0x14000789a  xor     r8d, r8d; msPeriod
0x14000789d  xor     edx, edx; pftDueTime
0x14000789f  mov     rcx, rbp; pti
0x1400078a2  mov     ebx, eax
0x1400078a4  call    cs:__imp_SetThreadpoolTimer
0x1400078aa  mov     edx, 1; fCancelPendingCallbacks
0x1400078af  mov     rcx, rbp; pti
0x1400078b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400078b8  mov     rcx, rbp; pti
0x1400078bb  call    cs:__imp_CloseThreadpoolTimer
0x1400078c1  mov     ecx, ebx; dwErrCode
0x1400078c3  call    cs:__imp_SetLastError
0x1400078c9  mov     ecx, r14d; dwErrCode
0x1400078cc  mov     [rdi+38h], r15
0x1400078d0  call    cs:__imp_SetLastError
0x1400078d6  mov     rcx, [rdi+38h]; pti
0x1400078da  test    rcx, rcx
0x1400078dd  jz      short loc_140007900
0x1400078df  mov     r9d, 4E2h; msWindowLength
0x1400078e5  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1400078ee  xor     r8d, r8d; msPeriod
0x1400078f1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1400078f6  call    cs:__imp_SetThreadpoolTimer
0x1400078fc  mov     byte ptr [rdi+40h], 1
0x140007900  test    rsi, rsi
0x140007903  jz      short loc_14000790E
0x140007905  mov     rcx, rsi; SRWLock
0x140007908  call    cs:__imp_ReleaseSRWLockExclusive
0x14000790e  mov     rcx, [rsp+78h+var_40]
0x140007913  xor     rcx, rsp; StackCookie
0x140007916  call    __security_check_cookie
0x14000791b  add     rsp, 48h
0x14000791f  pop     r15
0x140007921  pop     r14
0x140007923  pop     rdi
0x140007924  pop     rsi
0x140007925  pop     rbp
0x140007926  pop     rbx
0x140007927  retn
```
