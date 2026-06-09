# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000903c`
- end: `0x1800091d7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b6a0`

## callees

- `0x18000221a`
- `0x180002290`
- `0x18000903c`
- `0x18000bd0c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000914c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000914c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000917e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000918b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000917e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000918b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000908c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000908c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000916d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000916d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000915f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800091b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000915f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800091b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000913a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000913a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009176`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009176`

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
0x18000903c  push    rbx
0x18000903e  push    rbp
0x18000903f  push    rsi
0x180009040  push    rdi
0x180009041  push    r14
0x180009043  push    r15
0x180009045  sub     rsp, 38h
0x180009049  mov     ebp, r9d
0x18000904c  movzx   ebx, r8w
0x180009050  mov     r14d, edx
0x180009053  mov     rdi, rcx
0x180009056  cmp     byte ptr [rcx], 0
0x180009059  jz      loc_1800091CA
0x18000905f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009066  jnz     loc_1800091CA
0x18000906c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009073  test    rax, rax
0x180009076  jz      short loc_180009085
0x180009078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907d  test    al, al
0x18000907f  jnz     loc_1800091CA
0x180009085  lea     rsi, [rdi+28h]
0x180009089  mov     rcx, rsi; SRWLock
0x18000908c  call    cs:__imp_AcquireSRWLockExclusive
0x180009092  xor     eax, eax
0x180009094  mov     word ptr [rsp+68h+var_48+6], ax
0x180009099  mov     dword ptr [rsp+68h+var_48], r14d
0x18000909e  mov     word ptr [rsp+68h+var_48+4], bx
0x1800090a3  lea     rbx, [rdi+0E8h]
0x1800090aa  lea     edx, [rax+0Ch]; unsigned __int64
0x1800090ad  mov     rcx, rbx; this
0x1800090b0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800090b5  test    al, al
0x1800090b7  jz      short loc_180009113
0x1800090b9  mov     rcx, [rbx+8]; void *
0x1800090bd  mov     rax, [rbx+10h]
0x1800090c1  sub     rax, rcx
0x1800090c4  cmp     rcx, [rbx+10h]
0x1800090c8  sbb     r8, r8
0x1800090cb  and     r8, rax; Size
0x1800090ce  test    rcx, rcx
0x1800090d1  jnz     short loc_1800090E1
0x1800090d3  call    cs:__imp__o__errno
0x1800090d9  mov     dword ptr [rax], 16h
0x1800090df  jmp     short loc_180009109
0x1800090e1  cmp     r8, 0Ch
0x1800090e5  jb      short loc_1800090F6
0x1800090e7  movsd   xmm0, [rsp+68h+var_48]
0x1800090ed  movsd   qword ptr [rcx], xmm0
0x1800090f1  mov     [rcx+8], ebp
0x1800090f4  jmp     short loc_18000910E
0x1800090f6  xor     edx, edx; Val
0x1800090f8  call    memset_0
0x1800090fd  call    cs:__imp__o__errno
0x180009103  mov     dword ptr [rax], 22h ; '"'
0x180009109  call    _invalid_parameter_noinfo
0x18000910e  add     qword ptr [rbx+8], 0Ch
0x180009113  cmp     byte ptr [rdi+40h], 0
0x180009117  jnz     loc_1800091BB
0x18000911d  cmp     qword ptr [rdi+38h], 0
0x180009122  jnz     short loc_180009191
0x180009124  call    cs:__imp_GetLastError
0x18000912a  mov     r14d, eax
0x18000912d  xor     r8d, r8d; pcbe
0x180009130  mov     rdx, rdi; pv
0x180009133  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000913a  call    cs:__imp_CreateThreadpoolTimer
0x180009140  mov     r15, rax
0x180009143  mov     rbp, [rdi+38h]
0x180009147  test    rbp, rbp
0x18000914a  jz      short loc_180009184
0x18000914c  call    cs:__imp_GetLastError
0x180009152  mov     ebx, eax
0x180009154  xor     r9d, r9d; msWindowLength
0x180009157  xor     r8d, r8d; msPeriod
0x18000915a  xor     edx, edx; pftDueTime
0x18000915c  mov     rcx, rbp; pti
0x18000915f  call    cs:__imp_SetThreadpoolTimer
0x180009165  mov     edx, 1; fCancelPendingCallbacks
0x18000916a  mov     rcx, rbp; pti
0x18000916d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009173  mov     rcx, rbp; pti
0x180009176  call    cs:__imp_CloseThreadpoolTimer
0x18000917c  mov     ecx, ebx; dwErrCode
0x18000917e  call    cs:__imp_SetLastError
0x180009184  mov     [rdi+38h], r15
0x180009188  mov     ecx, r14d; dwErrCode
0x18000918b  call    cs:__imp_SetLastError
0x180009191  mov     rcx, [rdi+38h]; pti
0x180009195  test    rcx, rcx
0x180009198  jz      short loc_1800091BB
0x18000919a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800091a3  mov     r9d, 4E2h; msWindowLength
0x1800091a9  xor     r8d, r8d; msPeriod
0x1800091ac  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800091b1  call    cs:__imp_SetThreadpoolTimer
0x1800091b7  mov     byte ptr [rdi+40h], 1
0x1800091bb  test    rsi, rsi
0x1800091be  jz      short loc_1800091CA
0x1800091c0  mov     rcx, rsi; SRWLock
0x1800091c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091c9  nop
0x1800091ca  add     rsp, 38h
0x1800091ce  pop     r15
0x1800091d0  pop     r14
0x1800091d2  pop     rdi
0x1800091d3  pop     rsi
0x1800091d4  pop     rbp
0x1800091d5  pop     rbx
0x1800091d6  retn
```
