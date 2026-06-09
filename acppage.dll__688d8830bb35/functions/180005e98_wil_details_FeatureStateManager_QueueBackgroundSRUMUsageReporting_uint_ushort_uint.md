# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005e98`
- end: `0x180006020`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007d70`

## callees

- `0x180005e98`
- `0x18000835c`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005f46`
- `msvcrt!memcpy_s` at `0x180005f46`
- `KERNEL32!SetLastError` at `0x180005fbb`
- `KERNEL32!SetLastError` at `0x180005fc8`
- `KERNEL32!SetLastError` at `0x180005fbb`
- `KERNEL32!SetLastError` at `0x180005fc8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005faa`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005faa`
- `KERNEL32!GetLastError` at `0x180005f61`
- `KERNEL32!GetLastError` at `0x180005f89`
- `KERNEL32!GetLastError` at `0x180005f61`
- `KERNEL32!GetLastError` at `0x180005f89`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006000`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006000`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005fb3`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005fb3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005ef6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005ef6`
- `KERNEL32!SetThreadpoolTimer` at `0x180005f9c`
- `KERNEL32!SetThreadpoolTimer` at `0x180005fee`
- `KERNEL32!SetThreadpoolTimer` at `0x180005f9c`
- `KERNEL32!SetThreadpoolTimer` at `0x180005fee`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005f77`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005f77`

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
0x180005e98  push    rbx
0x180005e9a  push    rbp
0x180005e9b  push    rsi
0x180005e9c  push    rdi
0x180005e9d  push    r14
0x180005e9f  push    r15
0x180005ea1  sub     rsp, 48h
0x180005ea5  mov     rax, cs:__security_cookie
0x180005eac  xor     rax, rsp
0x180005eaf  mov     [rsp+78h+var_40], rax
0x180005eb4  cmp     byte ptr [rcx], 0
0x180005eb7  mov     r14d, r9d
0x180005eba  movzx   ebp, r8w
0x180005ebe  mov     ebx, edx
0x180005ec0  mov     rdi, rcx
0x180005ec3  jz      loc_180006006
0x180005ec9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005ed0  jnz     loc_180006006
0x180005ed6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005edd  test    rax, rax
0x180005ee0  jz      short loc_180005EEF
0x180005ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee7  test    al, al
0x180005ee9  jnz     loc_180006006
0x180005eef  lea     rsi, [rdi+28h]
0x180005ef3  mov     rcx, rsi; SRWLock
0x180005ef6  call    cs:__imp_AcquireSRWLockExclusive
0x180005efc  xor     eax, eax
0x180005efe  mov     [rsp+78h+Source], ebx
0x180005f02  mov     [rsp+78h+var_4C], bp
0x180005f07  lea     rbx, [rdi+0E8h]
0x180005f0e  mov     rcx, rbx; this
0x180005f11  mov     [rsp+78h+var_4A], ax
0x180005f16  mov     [rsp+78h+var_48], r14d
0x180005f1b  lea     ebp, [rax+0Ch]
0x180005f1e  mov     edx, ebp; unsigned __int64
0x180005f20  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005f25  test    al, al
0x180005f27  jz      short loc_180005F50
0x180005f29  mov     rcx, [rbx+8]; Destination
0x180005f2d  lea     r8, [rsp+78h+Source]; Source
0x180005f32  mov     rax, [rbx+10h]
0x180005f36  mov     r9d, ebp; SourceSize
0x180005f39  sub     rax, rcx
0x180005f3c  cmp     rcx, [rbx+10h]
0x180005f40  sbb     rdx, rdx
0x180005f43  and     rdx, rax; DestinationSize
0x180005f46  call    cs:__imp_memcpy_s
0x180005f4c  add     [rbx+8], rbp
0x180005f50  cmp     byte ptr [rdi+40h], 0
0x180005f54  jnz     loc_180005FF8
0x180005f5a  cmp     qword ptr [rdi+38h], 0
0x180005f5f  jnz     short loc_180005FCE
0x180005f61  call    cs:__imp_GetLastError
0x180005f67  xor     r8d, r8d; pcbe
0x180005f6a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005f71  mov     rdx, rdi; pv
0x180005f74  mov     r14d, eax
0x180005f77  call    cs:__imp_CreateThreadpoolTimer
0x180005f7d  mov     rbp, [rdi+38h]
0x180005f81  mov     r15, rax
0x180005f84  test    rbp, rbp
0x180005f87  jz      short loc_180005FC1
0x180005f89  call    cs:__imp_GetLastError
0x180005f8f  xor     r9d, r9d; msWindowLength
0x180005f92  xor     r8d, r8d; msPeriod
0x180005f95  xor     edx, edx; pftDueTime
0x180005f97  mov     rcx, rbp; pti
0x180005f9a  mov     ebx, eax
0x180005f9c  call    cs:__imp_SetThreadpoolTimer
0x180005fa2  mov     edx, 1; fCancelPendingCallbacks
0x180005fa7  mov     rcx, rbp; pti
0x180005faa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005fb0  mov     rcx, rbp; pti
0x180005fb3  call    cs:__imp_CloseThreadpoolTimer
0x180005fb9  mov     ecx, ebx; dwErrCode
0x180005fbb  call    cs:__imp_SetLastError
0x180005fc1  mov     ecx, r14d; dwErrCode
0x180005fc4  mov     [rdi+38h], r15
0x180005fc8  call    cs:__imp_SetLastError
0x180005fce  mov     rcx, [rdi+38h]; pti
0x180005fd2  test    rcx, rcx
0x180005fd5  jz      short loc_180005FF8
0x180005fd7  mov     r9d, 4E2h; msWindowLength
0x180005fdd  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005fe6  xor     r8d, r8d; msPeriod
0x180005fe9  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180005fee  call    cs:__imp_SetThreadpoolTimer
0x180005ff4  mov     byte ptr [rdi+40h], 1
0x180005ff8  test    rsi, rsi
0x180005ffb  jz      short loc_180006006
0x180005ffd  mov     rcx, rsi; SRWLock
0x180006000  call    cs:__imp_ReleaseSRWLockExclusive
0x180006006  mov     rcx, [rsp+78h+var_40]
0x18000600b  xor     rcx, rsp; StackCookie
0x18000600e  call    __security_check_cookie
0x180006013  add     rsp, 48h
0x180006017  pop     r15
0x180006019  pop     r14
0x18000601b  pop     rdi
0x18000601c  pop     rsi
0x18000601d  pop     rbp
0x18000601e  pop     rbx
0x18000601f  retn
```
