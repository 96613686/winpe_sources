# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006f8c`
- end: `0x180007136`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `426`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009790`

## callees

- `0x18000273e`
- `0x180002874`
- `0x180006f8c`
- `0x180009e2c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000702c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007056`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000702c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007056`
- `KERNEL32!CreateThreadpoolTimer` at `0x180007093`
- `KERNEL32!CreateThreadpoolTimer` at `0x180007093`
- `KERNEL32!SetThreadpoolTimer` at `0x1800070b8`
- `KERNEL32!SetThreadpoolTimer` at `0x180007110`
- `KERNEL32!SetThreadpoolTimer` at `0x1800070b8`
- `KERNEL32!SetThreadpoolTimer` at `0x180007110`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006fe5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006fe5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800070cf`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800070cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007122`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007122`
- `KERNEL32!GetLastError` at `0x18000707d`
- `KERNEL32!GetLastError` at `0x1800070a5`
- `KERNEL32!GetLastError` at `0x18000707d`
- `KERNEL32!GetLastError` at `0x1800070a5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800070c6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800070c6`
- `KERNEL32!SetLastError` at `0x1800070d7`
- `KERNEL32!SetLastError` at `0x1800070e4`
- `KERNEL32!SetLastError` at `0x1800070d7`
- `KERNEL32!SetLastError` at `0x1800070e4`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+28h] [rbp-50h]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv) )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)_o__errno(v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180006f8c  push    rbx
0x180006f8e  push    rbp
0x180006f8f  push    rsi
0x180006f90  push    rdi
0x180006f91  push    r14
0x180006f93  push    r15
0x180006f95  sub     rsp, 48h
0x180006f99  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x180006fa2  mov     ebp, r9d
0x180006fa5  movzx   ebx, r8w
0x180006fa9  mov     r14d, edx
0x180006fac  mov     rdi, rcx
0x180006faf  cmp     byte ptr [rcx], 0
0x180006fb2  jz      loc_180007129
0x180006fb8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006fbf  jnz     loc_180007129
0x180006fc5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006fcc  test    rax, rax
0x180006fcf  jz      short loc_180006FDE
0x180006fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd6  test    al, al
0x180006fd8  jnz     loc_180007129
0x180006fde  lea     rsi, [rdi+28h]
0x180006fe2  mov     rcx, rsi; SRWLock
0x180006fe5  call    cs:__imp_AcquireSRWLockExclusive
0x180006feb  xor     eax, eax
0x180006fed  mov     word ptr [rsp+78h+var_50+6], ax
0x180006ff2  mov     dword ptr [rsp+78h+var_50], r14d
0x180006ff7  mov     word ptr [rsp+78h+var_50+4], bx
0x180006ffc  lea     rbx, [rdi+0E8h]
0x180007003  lea     edx, [rax+0Ch]; unsigned __int64
0x180007006  mov     rcx, rbx; this
0x180007009  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000700e  test    al, al
0x180007010  jz      short loc_18000706C
0x180007012  mov     rcx, [rbx+8]; void *
0x180007016  mov     rax, [rbx+10h]
0x18000701a  sub     rax, rcx
0x18000701d  cmp     rcx, [rbx+10h]
0x180007021  sbb     r8, r8
0x180007024  and     r8, rax; Size
0x180007027  test    rcx, rcx
0x18000702a  jnz     short loc_18000703A
0x18000702c  call    cs:__imp__o__errno
0x180007032  mov     dword ptr [rax], 16h
0x180007038  jmp     short loc_180007062
0x18000703a  cmp     r8, 0Ch
0x18000703e  jb      short loc_18000704F
0x180007040  movsd   xmm0, [rsp+78h+var_50]
0x180007046  movsd   qword ptr [rcx], xmm0
0x18000704a  mov     [rcx+8], ebp
0x18000704d  jmp     short loc_180007067
0x18000704f  xor     edx, edx; Val
0x180007051  call    memset_0
0x180007056  call    cs:__imp__o__errno
0x18000705c  mov     dword ptr [rax], 22h ; '"'
0x180007062  call    _invalid_parameter_noinfo
0x180007067  add     qword ptr [rbx+8], 0Ch
0x18000706c  cmp     byte ptr [rdi+40h], 0
0x180007070  jnz     loc_18000711A
0x180007076  cmp     qword ptr [rdi+38h], 0
0x18000707b  jnz     short loc_1800070EA
0x18000707d  call    cs:__imp_GetLastError
0x180007083  mov     r14d, eax
0x180007086  xor     r8d, r8d; pcbe
0x180007089  mov     rdx, rdi; pv
0x18000708c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007093  call    cs:__imp_CreateThreadpoolTimer
0x180007099  mov     r15, rax
0x18000709c  mov     rbp, [rdi+38h]
0x1800070a0  test    rbp, rbp
0x1800070a3  jz      short loc_1800070DD
0x1800070a5  call    cs:__imp_GetLastError
0x1800070ab  mov     ebx, eax
0x1800070ad  xor     r9d, r9d; msWindowLength
0x1800070b0  xor     r8d, r8d; msPeriod
0x1800070b3  xor     edx, edx; pftDueTime
0x1800070b5  mov     rcx, rbp; pti
0x1800070b8  call    cs:__imp_SetThreadpoolTimer
0x1800070be  mov     edx, 1; fCancelPendingCallbacks
0x1800070c3  mov     rcx, rbp; pti
0x1800070c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800070cc  mov     rcx, rbp; pti
0x1800070cf  call    cs:__imp_CloseThreadpoolTimer
0x1800070d5  mov     ecx, ebx; dwErrCode
0x1800070d7  call    cs:__imp_SetLastError
0x1800070dd  mov     [rdi+38h], r15
0x1800070e1  mov     ecx, r14d; dwErrCode
0x1800070e4  call    cs:__imp_SetLastError
0x1800070ea  mov     rcx, [rdi+38h]; pti
0x1800070ee  test    rcx, rcx
0x1800070f1  jz      short loc_18000711A
0x1800070f3  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800070ff  mov     r9d, 4E2h; msWindowLength
0x180007105  xor     r8d, r8d; msPeriod
0x180007108  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180007110  call    cs:__imp_SetThreadpoolTimer
0x180007116  mov     byte ptr [rdi+40h], 1
0x18000711a  test    rsi, rsi
0x18000711d  jz      short loc_180007129
0x18000711f  mov     rcx, rsi; SRWLock
0x180007122  call    cs:__imp_ReleaseSRWLockExclusive
0x180007128  nop
0x180007129  add     rsp, 48h
0x18000712d  pop     r15
0x18000712f  pop     r14
0x180007131  pop     rdi
0x180007132  pop     rsi
0x180007133  pop     rbp
0x180007134  pop     rbx
0x180007135  retn
```
