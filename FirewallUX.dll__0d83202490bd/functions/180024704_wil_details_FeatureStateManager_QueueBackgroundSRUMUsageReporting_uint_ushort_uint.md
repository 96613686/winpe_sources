# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180024704`
- end: `0x18002489f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180025c10`

## callees

- `0x180002b9a`
- `0x180002c04`
- `0x180024704`
- `0x180025fd4`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002479b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800247c5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002479b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800247c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024754`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024754`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002488b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002488b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024814`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024835`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024835`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024802`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024802`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002483e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002483e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024879`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024879`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x180024704  push    rbx
0x180024706  push    rbp
0x180024707  push    rsi
0x180024708  push    rdi
0x180024709  push    r14
0x18002470b  push    r15
0x18002470d  sub     rsp, 38h
0x180024711  mov     ebp, r9d
0x180024714  movzx   ebx, r8w
0x180024718  mov     r14d, edx
0x18002471b  mov     rdi, rcx
0x18002471e  cmp     byte ptr [rcx], 0
0x180024721  jz      loc_180024892
0x180024727  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002472e  jnz     loc_180024892
0x180024734  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002473b  test    rax, rax
0x18002473e  jz      short loc_18002474D
0x180024740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024745  test    al, al
0x180024747  jnz     loc_180024892
0x18002474d  lea     rsi, [rdi+28h]
0x180024751  mov     rcx, rsi; SRWLock
0x180024754  call    cs:__imp_AcquireSRWLockExclusive
0x18002475a  xor     eax, eax
0x18002475c  mov     word ptr [rsp+68h+var_48+6], ax
0x180024761  mov     dword ptr [rsp+68h+var_48], r14d
0x180024766  mov     word ptr [rsp+68h+var_48+4], bx
0x18002476b  lea     rbx, [rdi+0E8h]
0x180024772  lea     edx, [rax+0Ch]; unsigned __int64
0x180024775  mov     rcx, rbx; this
0x180024778  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002477d  test    al, al
0x18002477f  jz      short loc_1800247DB
0x180024781  mov     rcx, [rbx+8]; void *
0x180024785  mov     rax, [rbx+10h]
0x180024789  sub     rax, rcx
0x18002478c  cmp     rcx, [rbx+10h]
0x180024790  sbb     r8, r8
0x180024793  and     r8, rax; Size
0x180024796  test    rcx, rcx
0x180024799  jnz     short loc_1800247A9
0x18002479b  call    cs:__imp__o__errno
0x1800247a1  mov     dword ptr [rax], 16h
0x1800247a7  jmp     short loc_1800247D1
0x1800247a9  cmp     r8, 0Ch
0x1800247ad  jb      short loc_1800247BE
0x1800247af  movsd   xmm0, [rsp+68h+var_48]
0x1800247b5  movsd   qword ptr [rcx], xmm0
0x1800247b9  mov     [rcx+8], ebp
0x1800247bc  jmp     short loc_1800247D6
0x1800247be  xor     edx, edx; Val
0x1800247c0  call    memset_0
0x1800247c5  call    cs:__imp__o__errno
0x1800247cb  mov     dword ptr [rax], 22h ; '"'
0x1800247d1  call    _invalid_parameter_noinfo
0x1800247d6  add     qword ptr [rbx+8], 0Ch
0x1800247db  cmp     byte ptr [rdi+40h], 0
0x1800247df  jnz     loc_180024883
0x1800247e5  cmp     qword ptr [rdi+38h], 0
0x1800247ea  jnz     short loc_180024859
0x1800247ec  call    cs:__imp_GetLastError
0x1800247f2  mov     r14d, eax
0x1800247f5  xor     r8d, r8d; pcbe
0x1800247f8  mov     rdx, rdi; pv
0x1800247fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180024802  call    cs:__imp_CreateThreadpoolTimer
0x180024808  mov     r15, rax
0x18002480b  mov     rbp, [rdi+38h]
0x18002480f  test    rbp, rbp
0x180024812  jz      short loc_18002484C
0x180024814  call    cs:__imp_GetLastError
0x18002481a  mov     ebx, eax
0x18002481c  xor     r9d, r9d; msWindowLength
0x18002481f  xor     r8d, r8d; msPeriod
0x180024822  xor     edx, edx; pftDueTime
0x180024824  mov     rcx, rbp; pti
0x180024827  call    cs:__imp_SetThreadpoolTimer
0x18002482d  mov     edx, 1; fCancelPendingCallbacks
0x180024832  mov     rcx, rbp; pti
0x180024835  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002483b  mov     rcx, rbp; pti
0x18002483e  call    cs:__imp_CloseThreadpoolTimer
0x180024844  mov     ecx, ebx; dwErrCode
0x180024846  call    cs:__imp_SetLastError
0x18002484c  mov     [rdi+38h], r15
0x180024850  mov     ecx, r14d; dwErrCode
0x180024853  call    cs:__imp_SetLastError
0x180024859  mov     rcx, [rdi+38h]; pti
0x18002485d  test    rcx, rcx
0x180024860  jz      short loc_180024883
0x180024862  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18002486b  mov     r9d, 4E2h; msWindowLength
0x180024871  xor     r8d, r8d; msPeriod
0x180024874  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180024879  call    cs:__imp_SetThreadpoolTimer
0x18002487f  mov     byte ptr [rdi+40h], 1
0x180024883  test    rsi, rsi
0x180024886  jz      short loc_180024892
0x180024888  mov     rcx, rsi; SRWLock
0x18002488b  call    cs:__imp_ReleaseSRWLockExclusive
0x180024891  nop
0x180024892  add     rsp, 38h
0x180024896  pop     r15
0x180024898  pop     r14
0x18002489a  pop     rdi
0x18002489b  pop     rsi
0x18002489c  pop     rbp
0x18002489d  pop     rbx
0x18002489e  retn
```
