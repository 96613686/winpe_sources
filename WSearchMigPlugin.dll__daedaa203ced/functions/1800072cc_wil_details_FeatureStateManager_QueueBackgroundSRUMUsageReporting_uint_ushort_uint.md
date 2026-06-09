# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800072cc`
- end: `0x180007476`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `426`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800099c0`

## callees

- `0x18000321a`
- `0x18000329c`
- `0x1800072cc`
- `0x18000a05c`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000736c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007396`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000736c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007396`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007325`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007462`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007462`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007424`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800073f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800073f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007450`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000740f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000740f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007406`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007406`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800073d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800073d3`

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
0x1800072cc  push    rbx
0x1800072ce  push    rbp
0x1800072cf  push    rsi
0x1800072d0  push    rdi
0x1800072d1  push    r14
0x1800072d3  push    r15
0x1800072d5  sub     rsp, 48h
0x1800072d9  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800072e2  mov     ebp, r9d
0x1800072e5  movzx   ebx, r8w
0x1800072e9  mov     r14d, edx
0x1800072ec  mov     rdi, rcx
0x1800072ef  cmp     byte ptr [rcx], 0
0x1800072f2  jz      loc_180007469
0x1800072f8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800072ff  jnz     loc_180007469
0x180007305  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000730c  test    rax, rax
0x18000730f  jz      short loc_18000731E
0x180007311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007316  test    al, al
0x180007318  jnz     loc_180007469
0x18000731e  lea     rsi, [rdi+28h]
0x180007322  mov     rcx, rsi; SRWLock
0x180007325  call    cs:__imp_AcquireSRWLockExclusive
0x18000732b  xor     eax, eax
0x18000732d  mov     word ptr [rsp+78h+var_50+6], ax
0x180007332  mov     dword ptr [rsp+78h+var_50], r14d
0x180007337  mov     word ptr [rsp+78h+var_50+4], bx
0x18000733c  lea     rbx, [rdi+0E8h]
0x180007343  lea     edx, [rax+0Ch]; unsigned __int64
0x180007346  mov     rcx, rbx; this
0x180007349  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000734e  test    al, al
0x180007350  jz      short loc_1800073AC
0x180007352  mov     rcx, [rbx+8]; void *
0x180007356  mov     rax, [rbx+10h]
0x18000735a  sub     rax, rcx
0x18000735d  cmp     rcx, [rbx+10h]
0x180007361  sbb     r8, r8
0x180007364  and     r8, rax; Size
0x180007367  test    rcx, rcx
0x18000736a  jnz     short loc_18000737A
0x18000736c  call    cs:__imp__o__errno
0x180007372  mov     dword ptr [rax], 16h
0x180007378  jmp     short loc_1800073A2
0x18000737a  cmp     r8, 0Ch
0x18000737e  jb      short loc_18000738F
0x180007380  movsd   xmm0, [rsp+78h+var_50]
0x180007386  movsd   qword ptr [rcx], xmm0
0x18000738a  mov     [rcx+8], ebp
0x18000738d  jmp     short loc_1800073A7
0x18000738f  xor     edx, edx; Val
0x180007391  call    memset_0
0x180007396  call    cs:__imp__o__errno
0x18000739c  mov     dword ptr [rax], 22h ; '"'
0x1800073a2  call    _invalid_parameter_noinfo
0x1800073a7  add     qword ptr [rbx+8], 0Ch
0x1800073ac  cmp     byte ptr [rdi+40h], 0
0x1800073b0  jnz     loc_18000745A
0x1800073b6  cmp     qword ptr [rdi+38h], 0
0x1800073bb  jnz     short loc_18000742A
0x1800073bd  call    cs:__imp_GetLastError
0x1800073c3  mov     r14d, eax
0x1800073c6  xor     r8d, r8d; pcbe
0x1800073c9  mov     rdx, rdi; pv
0x1800073cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800073d3  call    cs:__imp_CreateThreadpoolTimer
0x1800073d9  mov     r15, rax
0x1800073dc  mov     rbp, [rdi+38h]
0x1800073e0  test    rbp, rbp
0x1800073e3  jz      short loc_18000741D
0x1800073e5  call    cs:__imp_GetLastError
0x1800073eb  mov     ebx, eax
0x1800073ed  xor     r9d, r9d; msWindowLength
0x1800073f0  xor     r8d, r8d; msPeriod
0x1800073f3  xor     edx, edx; pftDueTime
0x1800073f5  mov     rcx, rbp; pti
0x1800073f8  call    cs:__imp_SetThreadpoolTimer
0x1800073fe  mov     edx, 1; fCancelPendingCallbacks
0x180007403  mov     rcx, rbp; pti
0x180007406  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000740c  mov     rcx, rbp; pti
0x18000740f  call    cs:__imp_CloseThreadpoolTimer
0x180007415  mov     ecx, ebx; dwErrCode
0x180007417  call    cs:__imp_SetLastError
0x18000741d  mov     [rdi+38h], r15
0x180007421  mov     ecx, r14d; dwErrCode
0x180007424  call    cs:__imp_SetLastError
0x18000742a  mov     rcx, [rdi+38h]; pti
0x18000742e  test    rcx, rcx
0x180007431  jz      short loc_18000745A
0x180007433  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000743f  mov     r9d, 4E2h; msWindowLength
0x180007445  xor     r8d, r8d; msPeriod
0x180007448  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180007450  call    cs:__imp_SetThreadpoolTimer
0x180007456  mov     byte ptr [rdi+40h], 1
0x18000745a  test    rsi, rsi
0x18000745d  jz      short loc_180007469
0x18000745f  mov     rcx, rsi; SRWLock
0x180007462  call    cs:__imp_ReleaseSRWLockExclusive
0x180007468  nop
0x180007469  add     rsp, 48h
0x18000746d  pop     r15
0x18000746f  pop     r14
0x180007471  pop     rdi
0x180007472  pop     rsi
0x180007473  pop     rbp
0x180007474  pop     rbx
0x180007475  retn
```
