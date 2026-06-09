# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800065b8`
- end: `0x180006753`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008f00`

## callees

- `0x180002432`
- `0x1800024ac`
- `0x1800065b8`
- `0x18000959c`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000664f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006679`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000664f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006679`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000673f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000673f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006608`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006707`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800066fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006707`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800066db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000672d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800066db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000672d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800066b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800066b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800066f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800066f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800066e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800066e9`

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
0x1800065b8  push    rbx
0x1800065ba  push    rbp
0x1800065bb  push    rsi
0x1800065bc  push    rdi
0x1800065bd  push    r14
0x1800065bf  push    r15
0x1800065c1  sub     rsp, 38h
0x1800065c5  mov     ebp, r9d
0x1800065c8  movzx   ebx, r8w
0x1800065cc  mov     r14d, edx
0x1800065cf  mov     rdi, rcx
0x1800065d2  cmp     byte ptr [rcx], 0
0x1800065d5  jz      loc_180006746
0x1800065db  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800065e2  jnz     loc_180006746
0x1800065e8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800065ef  test    rax, rax
0x1800065f2  jz      short loc_180006601
0x1800065f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f9  test    al, al
0x1800065fb  jnz     loc_180006746
0x180006601  lea     rsi, [rdi+28h]
0x180006605  mov     rcx, rsi; SRWLock
0x180006608  call    cs:__imp_AcquireSRWLockExclusive
0x18000660e  xor     eax, eax
0x180006610  mov     word ptr [rsp+68h+var_48+6], ax
0x180006615  mov     dword ptr [rsp+68h+var_48], r14d
0x18000661a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000661f  lea     rbx, [rdi+0E8h]
0x180006626  lea     edx, [rax+0Ch]; unsigned __int64
0x180006629  mov     rcx, rbx; this
0x18000662c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006631  test    al, al
0x180006633  jz      short loc_18000668F
0x180006635  mov     rcx, [rbx+8]; void *
0x180006639  mov     rax, [rbx+10h]
0x18000663d  sub     rax, rcx
0x180006640  cmp     rcx, [rbx+10h]
0x180006644  sbb     r8, r8
0x180006647  and     r8, rax; Size
0x18000664a  test    rcx, rcx
0x18000664d  jnz     short loc_18000665D
0x18000664f  call    cs:__imp__o__errno
0x180006655  mov     dword ptr [rax], 16h
0x18000665b  jmp     short loc_180006685
0x18000665d  cmp     r8, 0Ch
0x180006661  jb      short loc_180006672
0x180006663  movsd   xmm0, [rsp+68h+var_48]
0x180006669  movsd   qword ptr [rcx], xmm0
0x18000666d  mov     [rcx+8], ebp
0x180006670  jmp     short loc_18000668A
0x180006672  xor     edx, edx; Val
0x180006674  call    memset_0
0x180006679  call    cs:__imp__o__errno
0x18000667f  mov     dword ptr [rax], 22h ; '"'
0x180006685  call    _invalid_parameter_noinfo
0x18000668a  add     qword ptr [rbx+8], 0Ch
0x18000668f  cmp     byte ptr [rdi+40h], 0
0x180006693  jnz     loc_180006737
0x180006699  cmp     qword ptr [rdi+38h], 0
0x18000669e  jnz     short loc_18000670D
0x1800066a0  call    cs:__imp_GetLastError
0x1800066a6  mov     r14d, eax
0x1800066a9  xor     r8d, r8d; pcbe
0x1800066ac  mov     rdx, rdi; pv
0x1800066af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800066b6  call    cs:__imp_CreateThreadpoolTimer
0x1800066bc  mov     r15, rax
0x1800066bf  mov     rbp, [rdi+38h]
0x1800066c3  test    rbp, rbp
0x1800066c6  jz      short loc_180006700
0x1800066c8  call    cs:__imp_GetLastError
0x1800066ce  mov     ebx, eax
0x1800066d0  xor     r9d, r9d; msWindowLength
0x1800066d3  xor     r8d, r8d; msPeriod
0x1800066d6  xor     edx, edx; pftDueTime
0x1800066d8  mov     rcx, rbp; pti
0x1800066db  call    cs:__imp_SetThreadpoolTimer
0x1800066e1  mov     edx, 1; fCancelPendingCallbacks
0x1800066e6  mov     rcx, rbp; pti
0x1800066e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800066ef  mov     rcx, rbp; pti
0x1800066f2  call    cs:__imp_CloseThreadpoolTimer
0x1800066f8  mov     ecx, ebx; dwErrCode
0x1800066fa  call    cs:__imp_SetLastError
0x180006700  mov     [rdi+38h], r15
0x180006704  mov     ecx, r14d; dwErrCode
0x180006707  call    cs:__imp_SetLastError
0x18000670d  mov     rcx, [rdi+38h]; pti
0x180006711  test    rcx, rcx
0x180006714  jz      short loc_180006737
0x180006716  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000671f  mov     r9d, 4E2h; msWindowLength
0x180006725  xor     r8d, r8d; msPeriod
0x180006728  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000672d  call    cs:__imp_SetThreadpoolTimer
0x180006733  mov     byte ptr [rdi+40h], 1
0x180006737  test    rsi, rsi
0x18000673a  jz      short loc_180006746
0x18000673c  mov     rcx, rsi; SRWLock
0x18000673f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006745  nop
0x180006746  add     rsp, 38h
0x18000674a  pop     r15
0x18000674c  pop     r14
0x18000674e  pop     rdi
0x18000674f  pop     rsi
0x180006750  pop     rbp
0x180006751  pop     rbx
0x180006752  retn
```
