# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180016f2c`
- end: `0x1800170c7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800191d0`

## callees

- `0x180001fe6`
- `0x180002024`
- `0x180016f2c`
- `0x18001980c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016fc3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016fed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016fc3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001703c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001706e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001707b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001706e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001707b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800170b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800170b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016f7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016f7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001702a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001702a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017066`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017066`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001705d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001705d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001704f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800170a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001704f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800170a1`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
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
0x180016f2c  push    rbx
0x180016f2e  push    rbp
0x180016f2f  push    rsi
0x180016f30  push    rdi
0x180016f31  push    r14
0x180016f33  push    r15
0x180016f35  sub     rsp, 38h
0x180016f39  mov     ebp, r9d
0x180016f3c  movzx   ebx, r8w
0x180016f40  mov     r14d, edx
0x180016f43  mov     rdi, rcx
0x180016f46  cmp     byte ptr [rcx], 0
0x180016f49  jz      loc_1800170BA
0x180016f4f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016f56  jnz     loc_1800170BA
0x180016f5c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016f63  test    rax, rax
0x180016f66  jz      short loc_180016F75
0x180016f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f6d  test    al, al
0x180016f6f  jnz     loc_1800170BA
0x180016f75  lea     rsi, [rdi+28h]
0x180016f79  mov     rcx, rsi; SRWLock
0x180016f7c  call    cs:__imp_AcquireSRWLockExclusive
0x180016f82  xor     eax, eax
0x180016f84  mov     word ptr [rsp+68h+var_48+6], ax
0x180016f89  mov     dword ptr [rsp+68h+var_48], r14d
0x180016f8e  mov     word ptr [rsp+68h+var_48+4], bx
0x180016f93  lea     rbx, [rdi+0E8h]
0x180016f9a  lea     edx, [rax+0Ch]; unsigned __int64
0x180016f9d  mov     rcx, rbx; this
0x180016fa0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180016fa5  test    al, al
0x180016fa7  jz      short loc_180017003
0x180016fa9  mov     rcx, [rbx+8]; void *
0x180016fad  mov     rax, [rbx+10h]
0x180016fb1  sub     rax, rcx
0x180016fb4  cmp     rcx, [rbx+10h]
0x180016fb8  sbb     r8, r8
0x180016fbb  and     r8, rax; Size
0x180016fbe  test    rcx, rcx
0x180016fc1  jnz     short loc_180016FD1
0x180016fc3  call    cs:__imp__o__errno
0x180016fc9  mov     dword ptr [rax], 16h
0x180016fcf  jmp     short loc_180016FF9
0x180016fd1  cmp     r8, 0Ch
0x180016fd5  jb      short loc_180016FE6
0x180016fd7  movsd   xmm0, [rsp+68h+var_48]
0x180016fdd  movsd   qword ptr [rcx], xmm0
0x180016fe1  mov     [rcx+8], ebp
0x180016fe4  jmp     short loc_180016FFE
0x180016fe6  xor     edx, edx; Val
0x180016fe8  call    memset_0
0x180016fed  call    cs:__imp__o__errno
0x180016ff3  mov     dword ptr [rax], 22h ; '"'
0x180016ff9  call    _invalid_parameter_noinfo
0x180016ffe  add     qword ptr [rbx+8], 0Ch
0x180017003  cmp     byte ptr [rdi+40h], 0
0x180017007  jnz     loc_1800170AB
0x18001700d  cmp     qword ptr [rdi+38h], 0
0x180017012  jnz     short loc_180017081
0x180017014  call    cs:__imp_GetLastError
0x18001701a  mov     r14d, eax
0x18001701d  xor     r8d, r8d; pcbe
0x180017020  mov     rdx, rdi; pv
0x180017023  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001702a  call    cs:__imp_CreateThreadpoolTimer
0x180017030  mov     r15, rax
0x180017033  mov     rbp, [rdi+38h]
0x180017037  test    rbp, rbp
0x18001703a  jz      short loc_180017074
0x18001703c  call    cs:__imp_GetLastError
0x180017042  mov     ebx, eax
0x180017044  xor     r9d, r9d; msWindowLength
0x180017047  xor     r8d, r8d; msPeriod
0x18001704a  xor     edx, edx; pftDueTime
0x18001704c  mov     rcx, rbp; pti
0x18001704f  call    cs:__imp_SetThreadpoolTimer
0x180017055  mov     edx, 1; fCancelPendingCallbacks
0x18001705a  mov     rcx, rbp; pti
0x18001705d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017063  mov     rcx, rbp; pti
0x180017066  call    cs:__imp_CloseThreadpoolTimer
0x18001706c  mov     ecx, ebx; dwErrCode
0x18001706e  call    cs:__imp_SetLastError
0x180017074  mov     [rdi+38h], r15
0x180017078  mov     ecx, r14d; dwErrCode
0x18001707b  call    cs:__imp_SetLastError
0x180017081  mov     rcx, [rdi+38h]; pti
0x180017085  test    rcx, rcx
0x180017088  jz      short loc_1800170AB
0x18001708a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180017093  mov     r9d, 4E2h; msWindowLength
0x180017099  xor     r8d, r8d; msPeriod
0x18001709c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800170a1  call    cs:__imp_SetThreadpoolTimer
0x1800170a7  mov     byte ptr [rdi+40h], 1
0x1800170ab  test    rsi, rsi
0x1800170ae  jz      short loc_1800170BA
0x1800170b0  mov     rcx, rsi; SRWLock
0x1800170b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800170b9  nop
0x1800170ba  add     rsp, 38h
0x1800170be  pop     r15
0x1800170c0  pop     r14
0x1800170c2  pop     rdi
0x1800170c3  pop     rsi
0x1800170c4  pop     rbp
0x1800170c5  pop     rbx
0x1800170c6  retn
```
